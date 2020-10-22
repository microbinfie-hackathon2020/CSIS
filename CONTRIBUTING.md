# CONTRIBUTING

## Workflows

You can create a workflow in the `.github/workflows` folder.
It needs to be a file with extension `.yml`.
It should be named after the software being tested.
The `name` parameter in the file needs to be named after the software too.
Structure of the workflow is described [here](https://docs.github.com/en/free-pro-team@latest/actions/learn-github-actions/introduction-to-github-actions).

Please fork the repo, create a separate branch in your repo.
Make changes.
When changes are done, create a pull request with the dev branch.

### Basic test ideas

1. See if running the command with `--version` gives a version number and exits with 0
2. See if running the command with `--help` gives a usage with stdout and exits with 0
3. Run the most basic command and compare it with a simple expected value.
4. More ideas can be found in this publication: https://academic.oup.com/gigascience/article/2/1/2047-217X-2-15/2656133

## Example

In [.github/workflows/](.github/workflows), examples are provided. If we look at the example of Prokka (`prokka.yml`), the following sections are important to study:

### Name of the workflow

From [this line](.github/workflows/prokka.yml#L3):

```
name: prokka
```

This section defines the name of the software you want to test. This needs to match the name of the YAML file (without the `.yml` extension).

### Events triggering the tests

From [this line](.github/workflows/prokka.yml#L5):

```
# Controls when the action will run. Triggers the workflow on push or pull request
# events but only for the main branch
on:
  push:
    branches: [ main, dev ]
  pull_request:
    branches: [ main, dev ]
```

This section describes the events that trigger automatic testing, and on  which branches this should be done. In this case, every time an update gets pushed or a pull request is opened on the main or dev branches, the automatic tests will be performed.

### Specifying jobs within a workflow

From [this line](.github/workflows/prokka.yml#L13):

```
# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest
```

This section specifies which jobs should be run within this workflow. In this case, a single job (`build`) is specified. This job runs on the latest version of Ubuntu, hosted by GitHub itself.

### Specifying steps within a job

From [this line](.github/workflows/prokka.yml#L20):
 
```
    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      - name: apt
        run:  sudo apt-get install tree libdb-dev libbio-perl-perl libxml-simple-perl
      # Checks-out prokka under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v2
        with:
          repository: tseemann/prokka
          path: prokka
      - name: directory structure
        run: tree -d $GITHUB_WORKSPACE
      - name: ls bin dir
        run: ls -lh $GITHUB_WORKSPACE/prokka/bin $GITHUB_WORKSPACE/prokka/binaries/linux
      - name: test prokka
        run: |
         export PATH=$GITHUB_WORKSPACE/prokka/bin:$PATH
         export PATH=$GITHUB_WORKSPACE/prokka/binaries/linux:$PATH
         cd $GITHUB_WORKSPACE/prokka
         which prokka
         which makeblastdb
         prokka --version
         prokka --help
         ! prokka --doesnotexist
         prokka --depends
         prokka --setupdb
         prokka --listdb
         prokka --cpus 2 --outdir asm --prefix asm test/plasmid.fna
         grep '>' asm/asm.fna
         prokka --cleandb
```

This is where the actual testing happens. Within the `build` job, these five steps are defined. The first couple of steps are used to install dependencies through apt (`name: apt`), download the Prokka repository to the virtual machine (`uses: actions/checkout@v2`), print the directory structure (`name: directory structure`), check whether the correct executables are present (`name: ls bin dir`) and finally performs the test (`name: test prokka`).

In this example, the tests that are included are:

- Whether prokka and makeblastdb can be found in PATH (using `which`)
- Whether `prokka --version` and `prokka --help` work and exit without raising an error
- Whether a nonsense option does raise an error (`! prokka --doesnotexist`)
- Whether different Prokka commands work (`--depends`, `--setupdb`, `--listdb`, `--cleandb`)
- Whether a small test file can be annotated `prokka --cpus 2 --outdir asm --prefix asm test/plasmid.fna; grep '>' asm/asm.fna`

As can be seen in the Actions tab of the CSIS GitHub repo, the Prokka test works as expected and raises no errors. Example tests are taken from https://github.com/tseemann/prokka/blob/master/.travis.yml

## Documentation

Making the documentation on this page more clear would be very helpful!
