# New workflow

Please fill in the table below:

| Question | Your answer |
| --- | --- |
| Which software is tested? | SOFTWARE NAME |
| Do you have a link to your Github Actions YAML file? | LINK TO YML |

## Examples

For an example of a basic testing workflow, see [this Prokka workflow](../workflows/prokka.yml).

For an example of an advanced testing workflow, see [this CheckM workflow](../workflows/checkm.yml), courtesy of [Chris Gulvik](https://github.com/chrisgulvik)).

## Checklist

Please fill in the checklists below:

- [ ] I've read the guidelines for contributions: [CONTRIBUTING.md](../../CONTRIBUTING.md)

Checking the `name` and `on` sections (all boxes should be checked):
- [ ] The name of the test matches the name of the .yml file
- [ ] The tests are triggered on both push or pull requests, on the `main` and `dev` branches

These tests run on (at least one of these boxes should be checked):
- [ ] ubuntu-16.04, ubuntu-18.04, ubuntu-20.04 or ubuntu-latest (currently 18.04)
- [ ] macos-10.15, macos-11.0, or macos-latest (currently 10.15)
- [ ] windows-2019 or windows-latest (currently 2019)

The tests include (all boxes should be checked, see [this workflow as an example for a basic example](../workflows/prokka.yaml)):
- [ ] Installation of the software you're testing
- [ ] Checking what happens when the software is invoked without commands (e.g. `prokka`)
- [ ] Checking whether the `-h` and/or `--help` switches do not raise an error (e.g. `prokka -h` and/or `prokka --help`)
- [ ] Checking whether the `-v` and/or `--version` switches do not raise an error (e.g. `prokka -v` and/or `prokka --version`)
- [ ] Checking whether an error is raised when a non-sensical command is specified (e.g. `prokka --doesnotexist`)
- [ ] Performing a small, functional/black box test (does the tool complete on a toy dataset without raising errors?)

Optional tests (see [this workflow as an example for an advanced workflow](../workflows/checkm.yaml), courtesy of @chrisgulvik:
- [ ] Checking whether an error is correctly raised when invalid input file is specified (e.g. a truncated FastQ file)
- [ ] Checking whether dependencies are installed correctly
- [ ] Installing dependencies from source
- [ ] Checking whether dependencies pass their own tests
