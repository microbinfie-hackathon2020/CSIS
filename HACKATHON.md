# Software testing in microbial bioinformatics: a call to action

## The CSIS

Prior to the American Society for Microbiology Conference on Rapid Applied Microbial Next-Generation Sequencing and Bioinformatic Pipelines held in December 2020, we organized a collaborative three-day “Hackathon” and brought together more than twenty researchers in the field of microbial bioinformatics from five continents.
The goal of our Hackathon was to explore how to employ software testing in microbial bioinformatics.

The ASM NGS 2020 Hackathon aimed to promote the uptake of testing practices and engage the community in its adoption for public health.
This repository is an open-source project that gathers guidance, guidelines and examples for software testing for microbial bioinformatics researchers.

## Why Software Testing

Computational algorithms have become an essential component of research, with great efforts of the scientific community to raise standards on development and distribution of code.
Despite these efforts, sustainability and reproducibility are major issues since continued validation through software testing is still not a widely-adopted practice.

Based on the experiences from our Hackathon, we developed a set of seven recommendations for researchers seeking to improve the quality and reproducibility of their analyses through software testing.
We propose collaborative software testing as an opportunity to continuously engage software users, developers, and students to unify scientific work across domains.

## Our Recommendations

As automated software testing remains underused in scientific software, our set of recommendations not only ensures appropriate effort can be invested into producing a high quality and robust software, but also increases engagement in its sustainability.

Here we propose seven recommendations that should be followed during software development.

### 1. Establish software needs and testing goals

Manually testing the functionality of a tool is feasible in early development, but can become laborious as software matures.
We recommend:

- Developers establish software needs and testing goals during planning and designing stages to ensure an efficient testing structure;
- A minimal test set should address the validation of core components or  the program as a whole (Blackbox testing) and gradually progress toward verification of key functions which can accommodate code changes over time (Whitebox testing).

The following table provides an overview of testing methodologies and can serve as a guide to developers that aim to implement testing practices.

ADD TABLE!

### 2. Input test files: the good, the bad, and the ugly

When testing, it is important to include test files with known expected outcomes for a successful run.
However, it is equally important to include files on which the tool is expected to fail.
For example, some tools should recognize and report an empty input file or a wrong input format.
Examples of valid and invalid file formats are available through the [BioJulia project](https://github.com/BioJulia/BioFmtSpecimens).

### 3. Use an easy-to-follow language format to implement testing

Understanding the test workflow is necessary not only to ensure continued software development but also the integrity of the project for developers and users.
This can be done through the adoption of a standardized and easy-to-follow format, such as [YAML](https://yaml.org/).

Additionally, testing packages or frameworks offer an efficient approach to test creation and design.
Frameworks such as [unittest](https://docs.python.org/3/library/unittest.html) or [pytest](https://docs.pytest.org/en/stable/) for Python improve test efficiency, help bug detection and reduce manual intervention.  
When possible frameworks should be integrated into test workflows.

### 4. Testing is good, automated testing is better

When designing tests for your software, plan to automate.
Whether your tests are small or comprehensive, automatic triggering of tests will help reduce your workload.

Many platforms trigger tests automatically based on a set of user-defined conditions. Platforms such as [GitHub Actions](https://github.com/features/actions), [GitLab CI](https://about.gitlab.com/stages-devops-lifecycle/continuous-integration), [CircleCI](https://circleci.com/), [Travis CI](https://www.travis-ci.com/) or [Jenkins](https://www.jenkins.io/) offer straightforward automated testing of code seamlessly upon deployment.

### 5. Try the test once, then try it again

The result of an automated test in the context of one computational workspace does not ensure the same result will be obtained in a different setup.
Although package managers and containers have reduced variability between workspaces, it is still important to ensure your software can be installed and used across supported platforms.
One way to ensure this is to test on different environments, with varying dependency versions (e.g., multiple Python versions, instead of only the most recent one).

### 6. Showcase the tests

For prospective users, it is good to know whether you have tested your software and, if so, which tests you have included.
This can be done by displaying a badge in your [Github README](), or linking to your defined testing strategy e.g. a Github Actions YAML, (see [recommendation #2]()).

Documenting the testing goal and process enables end-users to easily check tool functionality and the level of testing.

We recommend contacting the authors, directly or through issues in the code repository, whose software you have tested to share successful outcomes or if you encountered abnormal behaviour or component failures.
An external perspective can be useful to find bugs that the authors are unaware of.  

### 7. Encourage others to test your software

Software testing can be crowdsourced, as showcased by the ASM NGS 2020 Hackathon.
Software suites such as [Pangolin](https://github.com/cov-lineages/pangolin) and [chewBBACA](https://github.com/B-UMMI/chewBBACA) have implemented automated testing developed during the hackathon.

For developers, crowdsourcing offers the benefits of fresh eyes on your software.
Feedback and contributions from users can expedite the implementation of software testing practises.
It also contributes to software sustainability by creating community buy-in, which ultimately helps the software maintainers keep pace with dependency changes, and identify current user needs.

## Examples

TODO
## Hackathon participants

TODO
### Teams

To stimulate interaction, we will subdivide participants into teams of 3-4 people.
Ideally, these teams will cover different levels of experience with Git, GitHub Actions, and software testing.
This way, every team can contribute to testing software.

To register your team, please edit and submit a pull request to [TEAMS.md](/TEAMS.md) according to the [contribution etiquette](/CONTRIBUTING.md#pull-request-etiquette).

## Conclusions

TODO

## Citation

TODO
