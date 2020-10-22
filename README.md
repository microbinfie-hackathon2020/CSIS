# CSIS
:detective: Code Safety Inspection Service

## In short

Many bioinformatics projects do not use unit testing.
Without unit testing, it is difficult to ensure which bioinformatics software is in working order,
 or which bioinformatics software adheres to basic standards.
We are adding basic unit tests for bioinformatics software here using the GitHub Actions platform.

## Long story

### Why is this useful?

If you have a project hosted on GitHub, you want to make sure it keeps working even if your code evolves through time. You push your own changes to the project and other people might fork your code and open pull requests. Checking whether the updated code works as expected is a repetitve task, and can be automated. However, this automated testing is missing from a lot of current projects.

### How does automated testing work?

GitHub Actions offers automated testing of code, which get triggered by certain events (e.g. pull requests). A new virtual machines is started on GitHub-hosted servers, on which the code gets installed and subsequently runs through a number of tests. Several virtual machine configurations are available, allowing users to test their code in a wide range of environments (e.g. different operating systems or using different versions of Python). You can also choose to host your own custom virtual machine for testing, if this is necessary. The exact automated testing workflow is defined in a `.yml` file, which describes the configuration of the system(s) you want to test on, the code and version you want to test, and the commands that make up the tests themselves. 

For more information on GitHub Actions, see [the documentation](https://docs.github.com/en/free-pro-team@latest/actions).

For test ideas and an example using Prokka, see [CONTRIBUTING.md](CONTRIBUTING.md).

### Why is this a cool idea for a hackathon?

Multiple widely-used tools could benefit from automated testing, and this is a process that can be crowdsourced well. Additionally, participants learn valuable skills that can be brought back to their own projects. 

# Current software

* ![CSIS](https://github.com/lskatz/CSIS/workflows/CSIS/badge.svg)
* ![prokka](https://github.com/lskatz/CSIS/workflows/prokka/badge.svg)

# Contributing

Please see [CONTRIBUTING.md](CONTRIBUTING.md)

# Etymology

CSIS is a play on the acronym for the [United States Food Safety Inspection Service](https://www.fsis.usda.gov).
Additionally, it has CSI in the acronym (Crime Scene Investigation) which has a sort of detective feel to it.
