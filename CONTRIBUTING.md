# CONTRIBUTING

## Teams

We plan to subdivide participants into small teams to stimulate interaction. These teams will be of mixed experience and work together to introduce automated tests to as many tools as possible.

## Workflows

Your team can create a workflow in the `.github/workflows` folder.
It needs to be a file with extension `.yml`.
It should be named after the software being tested.
The `name` parameter in the file needs to be named after the software too.
Structure of the workflow is described [here](https://docs.github.com/en/free-pro-team@latest/actions/learn-github-actions/introduction-to-github-actions). Some examples can be found in [EXAMPLES](EXAMPLES.md)

Please fork the repo, create a separate branch in your repo.
Make changes.
When changes are done, create a pull request from your new branch with the dev branch on this repo.

### Basic test ideas

1. See if running the command with `--version` gives a version number and exits with 0
2. See if running the command with `--help` gives a usage with stdout and exits with 0
3. Run the most basic command and compare it with a simple expected value.
4. More ideas can be found in this publication: https://academic.oup.com/gigascience/article/2/1/2047-217X-2-15/2656133

# Code of conduct

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](code_of_conduct.md)

To stimulate a positive environment for all contributors, we have adopted v2.0 of the Contributor Covenant: https://www.contributor-covenant.org/version/2/0/code_of_conduct/.
