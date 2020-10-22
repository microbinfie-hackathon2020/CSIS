# Examples

This file contains two examples of GitHub Actions workflows:

1. An install of Prokka on Ubuntu, with some basic command tests and a small annotation command
2. Four installs of Quast using different versions of Python, using the `--test` command of Quast

## Prokka

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

## Quast

### Name and events

From [this line](.github/workflows/quast.yml#L1):

```
name: quast

on:
  push:
    branches: [ main, dev ]
  pull_request:
    branches: [ main, dev ]
```

This is the same as for prokka: `name: quast` specifies the name of the workflow and `on: ` specifies which events should trigger Actions.

### Specifying a job using a matrix

From [this line](.github/workflows/quast.yml#L9):

```
jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        python-version: [3.5, 3.6, 3.7, 3.8]
```

This is mostly identical to the prokka example above, except for the `strategy: `. In this case, we define a matrix of Python versions to test the tool on. Also see https://docs.github.com/en/free-pro-team@latest/actions/guides/building-and-testing-python.

### Specifying steps within the build job

From [this line](.github/workflows/quast.yml#16):

```
    steps:
    - uses: actions/checkout@v2
    - name: Set up Python ${{ matrix.python-version }}
      uses: actions/setup-python@v2
      with:
        python-version: ${{ matrix.python-version }}
    - name: apt
      run: |
        sudo apt-get install tree
    - uses: actions/checkout@v2
      with:
        repository: ablab/quast
        path: quast
    - name: Install quast
      run: |
        cd $GITHUB_WORKSPACE/quast
        ./setup.py install
    - name: test 1
      run: |
        wget quast.sf.net/test_data.tar.gz && tar xzf test_data.tar.gz
        tree test_data
        which quast.py
        quast.py --threads 1 --test
```

Again, largely similar to the prokka example above. The largest difference is in the first step, where in this case we checkout the Python versions defined in the matrix before. To check out Python versions, use the predefined `setup-python` action from https://github.com/marketplace/actions/setup-python.

The steps thereafter are pretty similar: we install tree through apt (`name: apt`, to get an idea of the repository structure, mostly needed for debugging). Then we check out the Quast GitHub repo using the predefined checkout action (from https://github.com/marketplace/actions/checkout). We then install quast using their `setup.py` script (`name: Install quast`). Finally, we download the Quast test data and run their own tests (`name: test 1`).

As we have defined a matrix of Python versions, this job is repeated for Python 3.5, 3.6, 3.7 and 3.8. It's also possible to define multiple matrices (e.g. Python versions and operating systems), which then get combined.
