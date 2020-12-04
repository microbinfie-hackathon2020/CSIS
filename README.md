# CSIS
:detective: Code Safety Inspection Service

## In short

Many bioinformatics projects do not use unit testing.
Without unit testing, it is difficult to ensure which bioinformatics software is in working order,
 or which bioinformatics software adheres to basic standards.
We are adding basic unit tests for bioinformatics software here using the GitHub Actions platform.

# Current software

| Software | badge with link to CI | version badge | yaml |
|----------|-----------------------|---------------|------|
| This repo| [![CSIS](https://github.com/microbinfie-hackathon2020/CSIS/workflows/CSIS/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3ACSIS) | [![Tested Version](https://img.shields.io/badge/version-v1-brightgreen)](https://github.com/microbinfie-hackathon2020/CSIS) |  [CSIS.yml](/.github/workflows/CSIS.yml) |
| Genotyphi   | [![genotyphi](https://github.com/microbinfie-hackathon2020/CSIS/workflows/genotyphi/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Agenotyphi) | [![Tested Version](https://img.shields.io/badge/version-4296976-brightgreen)](https://github.com/katholt/genotyphi/tree/42969769753a53bb74f15bfb3d60846b5828ff91) | [genotyphi.yml](/.github/workflows/genotyphi.yml) |
| Kraken   | [![kraken](https://github.com/microbinfie-hackathon2020/CSIS/workflows/kraken/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Akraken) | [![Tested Version](https://img.shields.io/badge/version-v1.1.1-brightgreen)](https://github.com/DerrickWood/kraken/releases/tag/v1.1.1) | [kraken.yml](/.github/workflows/kraken.yml) |
| KrakenUniq   | [![krakenuniq](https://github.com/microbinfie-hackathon2020/CSIS/workflows/krakenuniq/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Akrakenuniq) | [![Tested Version](https://img.shields.io/badge/version-v0.5.8-brightgreen)](https://github.com/fbreitwieser/krakenuniq/releases/tag/v0.5.8) | [krakenuniq.yml](/.github/workflows/krakenuniq.yml) |
| Kraken2   | [![kraken2](https://github.com/microbinfie-hackathon2020/CSIS/workflows/kraken2/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Akraken2) | [![Tested Version](https://img.shields.io/badge/version-v2.1.1-brightgreen)](https://github.com/DerrickWood/kraken2/releases/tag/v2.1.1) | [kraken2.yml](/.github/workflows/kraken2.yml) |
| Prokka   | [![prokka](https://github.com/microbinfie-hackathon2020/CSIS/workflows/prokka/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Aprokka) | [![Tested Version](https://img.shields.io/badge/version-v1.14.5-brightgreen)](https://github.com/tseemann/prokka/releases/tag/v1.14.5) | [prokka.yml](/.github/workflows/prokka.yml) |
| Quast    | [![quast](https://github.com/microbinfie-hackathon2020/CSIS/workflows/quast/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Aquast) | [![Tested Version](https://img.shields.io/badge/version-v5.0.2-brightgreen)](https://github.com/ablab/quast/releases/tag/quast_5.0.2) | [quast.yml](/.github/workflows/quast.yml) |

## Long story

### Why is this useful?

If you have a project hosted on GitHub, you want to make sure it keeps working even if your code evolves through time. 
You push your own changes to the project and other people might fork your code and open pull requests. 
Checking whether the updated code works as expected is a repetitve task, and can be automated. 
However, this automated testing is missing from a lot of current projects.

### How does automated testing work?

GitHub Actions offers automated testing of code, which get triggered by certain events (e.g. pull requests). 
A new virtual machines is started on GitHub-hosted servers, on which the code gets installed and subsequently runs through a number of tests. 
Several virtual machine configurations are available, allowing users to test their code in a wide range of environments
(e.g. different operating systems or using different versions of Python). 
You can also choose to host your own custom virtual machine for testing, if this is necessary. 
The exact automated testing workflow is defined in a `.yml` file, which describes the configuration of the system(s) you want to test on,
the code and version you want to test, and the commands that make up the tests themselves. 

For more information on GitHub Actions, see [the documentation](https://docs.github.com/en/free-pro-team@latest/actions).

For test ideas and examples using Prokka and Quast, see [EXAMPLES.md](EXAMPLES.md).

### Why is this a cool idea for a hackathon?

* Multiple widely-used tools could benefit from automated testing.
* This is a process that can be crowdsourced well. 
* Participants learn valuable skills that can be brought back to their own projects. 
* Early warning system for software that is breaking

### Why GitHub Actions?

There are many continuous integration (CI) platforms available.
Examples include CircleCI, Travis, Galaxy's Planemo or Jenkins.
While many of these platforms offer the same or highly similar functionalities, GitHub Actions offers a couple of advantages:

1. Actions fully integrates with GitHub
2. Actions is completely free for public repositories, including running builds and tests on GitHub servers
3. Actions provides many premade configurations on Marketplace

Based on these characteristics, we think that GitHub Actions is a great way to learn CI and unit testing.

# Contributing

Please see [CONTRIBUTING.md](CONTRIBUTING.md)

Register your team at [TEAMS.md](TEAMS.md)

# Practicalities

Please see [HACKATHON.md](HACKATHON.md) for information on the teams, schedule, communication and other practicalities.

# Etymology

CSIS is a play on the acronym for the [United States Food Safety Inspection Service](https://www.fsis.usda.gov).
Additionally, it has CSI in the acronym (Crime Scene Investigation) which has a sort of detective feel to it.
