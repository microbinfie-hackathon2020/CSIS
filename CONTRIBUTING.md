# CONTRIBUTING

## Workflows

Your team can create a workflow in the `.github/workflows` folder.
It needs to be a file with extension `.yml`.
It should be named after the software being tested.
The `name` parameter in the file needs to be named after the software too.
Structure of the workflow is described [here](https://docs.github.com/en/free-pro-team@latest/actions/learn-github-actions/introduction-to-github-actions). Some examples can be found in [EXAMPLES](EXAMPLES.md).

## Pull request etiquette

Please fork the repo, create a separate branch in your repo.
Make changes.
When changes are done, create a pull request from your new branch with the dev branch on this repo.

From time to time, the owners of this repo will merge the dev branch with the main branch.

Please see [Read Git Flow](https://leanpub.com/git-flow/read#leanpub-auto-git-flow-example) for more information,
or also please see this depiction for our workflow: https://leanpub.com/site_images/git-flow/git-workflow-release-cycle-3release.png

**Important:** in the basic templates, triggering tests on push events is switched off by default (e.g. lines 8 and 9 in `prokka.yaml`).
The reason is that if you are working on a Quast test in your fork, you don't want to trigger a Prokka test every time you push to your fork.
However, keep in mind that when starting the development of a new test, you need to activate triggering tests on push by uncommenting these lines.
We will explain this in the examples we will present and if anything's unclear, don't hesitate to ask Lee or Boas.

### Basic test ideas

_These are ideas and are not mandatory_

1. See if running the command with `--version` gives a version number and exits with 0
2. See if running the command with `--help` gives a usage with stdout and exits with 0
3. Run the most basic command and compare it with a simple expected value.
4. More ideas can be found in this publication: https://academic.oup.com/gigascience/article/2/1/2047-217X-2-15/2656133

## Code of conduct

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](code_of_conduct.md)

To stimulate a positive environment for all contributors, we have adopted v2.0 of the Contributor Covenant: https://www.contributor-covenant.org/version/2/0/code_of_conduct/.

## Practicalities

Please see [HACKATHON.md](HACKATHON.md).

## Git flow depiction

![Git flow](https://leanpub.com/site_images/git-flow/git-workflow-release-cycle-3release.png)
