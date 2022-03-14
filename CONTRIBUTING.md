# CONTRIBUTING

The hackathon has been completed and our collaborative manuscript has been published in Microbial Genomics (https://doi.org/10.1099/mgen.0.000790). However, we are still welcoming contributions to this repository.

We especially welcome contributions of two kinds:
1. Adding or improving guidelines for software testing.
2. Testing workflows which serve as good examples for the microbial bioinformatics community.

For all other contributions, we will first assess whether these fit the intended scope of this repository.



## THE INFORMATION BELOW DESCRIBES CONTRIBUTING GUIDELINES DURING THE HACKATHON (DECEMBER 2020). CURRENT CONTRIBUTING GUIDELINES ARE LISTED ABOVE
*During the hackathon, contributions focused on implementing software testing workflows using GitHub Actions*


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
