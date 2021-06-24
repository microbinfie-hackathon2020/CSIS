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

### Establish software needs and testing goals

Manually testing the functionality of a tool is feasible in early development, but can become laborious as software matures.
We recommend:

- Developers establish software needs and testing goals during planning and designing stages to ensure an efficient testing structure;
- A minimal test set should address the validation of core components or  the program as a whole (Blackbox testing) and gradually progress toward verification of key functions which can accommodate code changes over time (Whitebox testing).

The following table provides an overview of testing methodologies and can serve as a guide to developers that aim to implement testing practices.

ADD TABLE!

### Input test files: the good, the bad, and the ugly

When testing, it is important to include test files with known expected outcomes for a successful run.
However, it is equally important to include files on which the tool is expected to fail.
For example, some tools should recognize and report an empty input file or a wrong input format.
Examples of valid and invalid file formats are available through the [BioJulia project](https://github.com/BioJulia/BioFmtSpecimens).

### Use an easy-to-follow language format to implement testing

Understanding the test workflow is necessary not only to ensure continued software development but also the integrity of the project for developers and users.
This can be done through the adoption of a standardized and easy-to-follow format, such as [YAML](https://yaml.org/).

Additionally, testing packages or frameworks offer an efficient approach to test creation and design.
Frameworks such as [unittest](https://docs.python.org/3/library/unittest.html) or [pytest](https://docs.pytest.org/en/stable/) for Python improve test efficiency, help bug detection and reduce manual intervention.  
When possible frameworks should be integrated into test workflows.


## Goals

1. Introduce automated tests for bioinformatic tools.
2. Educate ourselves in unit testing, continuous integration (CI), and YAML markup language.
3. Network with other bioinformaticians.
4. Create a community resource for identifying software that can pass unit tests.
5. Publish.

## Program

### At a glance

* Register at https://forms.gle/rSSkQZv3pZXEAh3a7

**NB: This is a tentative planning and might be subject to change.**

Tentative dates: December 2nd to 4th (Wed-Fri), 2020. ASM NGS will take place from 7 to 11 December (Mon-Fri).
We adhere to the same timezone as the ASM NGS conference itself, meaning the default timezone will be Eastern Standard Time (GMT -5:00).
However, we will try to organize the schedule in such a way that takes into account timezones of all participants.

The main program will be in Eastern Standard Time, but individual groups can work in local timezones.

### December 2nd

**Orientation, team building, and project formation.**

_Times are in Eastern Time to coincide with ASM NGS_

| time   | what | presentor |
|--------|------|-----------|
| 9am    | Orientation - the hackathon concept, Zoom, Discord | Lee Katz |
| 9:30am | Go through an example | Boas van der Putten |
| 10am   | Team formation, network with team members, choose team captain, choose software for unit testing | via Discord |
| 10:30am| Record team names and team members on `TEAMS.md` | Individual groups |
| 11am   | Individual team discussions and logistics | Discord |
| 12pm   | close | - |

After hours: contact Lee Katz and Boas van der Putten
* New team formation
* Questions
* etc

### December 3rd

**Check in**

_Times are in Eastern Time to coincide with ASM NGS_

| time   | what | presentor |
|--------|------|-----------|
| 9am    | Day 2 introduction | Boas van der Putten |
| 9:15am | Keynote: _The why and the how of testing scientific software_  | Luis Pedro Coelho |
| 10am | Team updates | team captains |
| 11:30am| Closeout | Lee Katz |

### December 4th

**Wrap up**

_Times are in Eastern Time to coincide with ASM NGS_

| time   | what | presentor |
|--------|------|-----------|
| 9am    | Overview of contributions | Boas van der Putten |
| 9:30am | Presentations (5 min for presentation + 5 min for challenges faced) | Team captains |
| 11am   | Discussion of future plans | Lee Katz |
| 12pm   | Happy hour | In Discord |

## Teams

To stimulate interaction, we will subdivide participants into teams of 3-4 people.
Ideally, these teams will cover different levels of experience with Git, GitHub Actions, and software testing.
This way, every team can contribute to testing software.

To register your team, please edit and submit a pull request to [TEAMS.md](/TEAMS.md) according to the [contribution etiquette](/CONTRIBUTING.md#pull-request-etiquette).

## Communication

All links to Discord and Zoom will be emailed separately to help avoid "Zoom bombing."

To register, please go to https://forms.gle/rSSkQZv3pZXEAh3a7

* We will use a Discord server, to be determined.
Each team will have a channel, named after their team.
Although Discord is encouraged, each team can decide if there is a different platform that they would like to set up for themselves.
* To communicate new pull requests, please start with a new issue in GitHub.
* The hackathon itself will be held over Zoom.

