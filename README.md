# Software testing in microbial bioinformatics: a call to action

:detective: Code Safety Inspection Service

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

The following [table](#Table-1:-Overview-of-testing-approaches) provides an overview of testing methodologies and can serve as a guide to developers that aim to implement testing practices.

#### Table 1: Overview of testing approaches

<table cellpadding=0 cellspacing=0 width=1185 style='border-collapse:collapse table-layout:fixed;width:435pt'>
 <col width=179 style='mso-width-source:userset;mso=-width-alt:6260 width:135pt'>
 <col width=465 style='mso-width-source:userset;mso=-width-alt:16221;width:349pt'>
 <col width=541 style='mso-width-source:userset;mso=-width-alt:18897;width:406pt'>
 <tr height=19 style='height:14.5pt'>
  <td height=19 width=179 style='height:14.5pt;width:135pt'>
  <b>Name</b></td>
  <td width=465 style='border-left:none;width:349pt'><b>Description</b></td>
  <td width=541 style='border-left:none;width:406pt'><b>Example</b></td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td colspan=3 height=19 width=1185 style='border=-right:.5pt solid black;height:14.5pt;width:890pt'>
  <b>Installation testing: can the software be invoked on different setups?</b></td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19 width=179 style='height:14.5pt;borde=
r-top:none;
  width:135pt'><b>Installation testing</b></td>
  <td width=465 style='border-top:none;border-left:none;width:349pt'>
  Can the software be installed on different platforms?</td>
  <td width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X can be installed using apt-get, pip, conda and from source.</i></td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19  width=179 style='height:14.5pt;border-top:none;width:135pt'>
  <b>Configuration testing</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  With which dependencies can the software be used?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X can be used with different versions of BLAST+.</i></td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39  width=179 style='height:29.0pt;border-top:none;width:135pt'>
  <b>Implementation testing<b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  Do different implementations work similarly enough?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X works the same between the standalone and webserver versions.</i></td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19  width=179 style='height:14.5pt;border-top:none;width:135pt'>
  <b>Compatibility testing</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  Are newer versions compatible with previous input/output?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X can be used with older versions of the UniProtKB database.</i></td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39  width=179 style='height:29.0pt;border-top:none;width:135pt'>
  <b>Static testing</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  Is the source code syntactically correct?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Check whether all opening braces have corresponding closing braces or whether code is indented correctly in Software X.</i></td>
 </tr>
 <tr height=20 style='mso-height-source:userset;height:15.0pt'>
  <td colspan=3 height=20 width=1185 style='border=
-right:.5pt solid black;
  height:15.0pt;width:890pt'><b>Standard functionality testing: does the software do what it should in daily use?</b></td>
 </tr>
 <tr height=19 style='height:14.5pt'>
  <td height=19  width=179 style='height:14.5pt;border-top:none;width:135pt'>
  <b>Use case testing</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  Can the software do what it is supposed to do regularly?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X can annotate a small plasmid.</i></td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39  width=179 style='height:29.0pt;border-top:none;width:135pt'>
  <b>Workflow testing</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  Can the software succesfully traverse each path in the analysis?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X works in different modes (using fast mode, using rnammer over barrnap or using rfam mode).</i></td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39  width=179 style='height:29.0pt;border-top:none;width:135pt'>
  <b>Sanity testing</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  Can the software be invoked without errors?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X works correctly without flags, or when checking dependencies or displaying help info.</i></td>
 </tr>
 <tr height=20 style='mso-height-source:userset;height:15.0pt'>
  <td colspan=3 height=20 width=1185 style='border-right:.5pt solid black;
  height:15.0pt;width:890pt'>
  <b>Destructive testing: what makes the software fail?</b></td>
 </tr>
 <tr height=58 style='height:43.5pt'>
  <td height=58  width=179 style='height:43.5pt;border-top:none;width:135pt'>
  <b>Mutation/fuzz testing</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  How does the software handle different inputs and at which point does the software fail?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X can annotate different FASTA files: with spaces in the header, without a header, an empty file, with spaces in the sequence, with unknown characters in the sequences, et cetera.</i></td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39  width=179 style='height:29.0pt;border-top:none;width:135pt'>
  <b>Load testing</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  At what input size does the software fail?</td>
  <td  width=541 style='border-top:none;border-left:none;width:406pt'>
  <i>Test whether Software X can annotate a small plasmid (10 Kbp), a medium-size genome (2 Mbp) or an unrealistically large genome for a prokaryote (1 Gbp).</i></td>
 </tr>
 <tr height=39 style='height:29.0pt'>
  <td height=39  width=179 style='height:29.0pt;border-top:none;width:135pt'>
  <b>Fault injection</b></td>
  <td  width=465 style='border-top:none;border-left:none;width:349pt'>
  Does the software fail if faults are introduced and how is this handled?</td>
  <td  width=541 style='border-top:none border-left:none;width:406pt'>
  <i>Test whether Software X fails if nonsense functions are introduced in the gene calling code.</i></td>
 </tr>
</table>
<br>

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

We recommend contacting the authors, directly or through issues in the code repository, whose software you have tested to share successful outcomes or if you encountered abnormal behavior or component failures.
An external perspective can be useful to find bugs that the authors are unaware of.  

### 7. Encourage others to test your software

Software testing can be crowd-sourced, as showcased by the ASM NGS 2020 Hackathon.
Software suites such as [Pangolin](https://github.com/cov-lineages/pangolin) and [chewBBACA](https://github.com/B-UMMI/chewBBACA) have implemented automated testing developed during the Hackathon.

For developers, crowd-sourcing offers the benefits of fresh eyes on your software.
Feedback and contributions from users can expedite the implementation of software testing practices.
It also contributes to software sustainability by creating community buy-in, which ultimately helps the software maintainers keep pace with dependency changes, and identify current user needs.

## Current software

| Software | badge with link to CI | version badge | yaml |
|----------|-----------------------|---------------|------|
| [This repo](https://github.com/microbinfie-hackathon2020/CSIS/workflows/CSIS) | [![CSIS](https://github.com/microbinfie-hackathon2020/CSIS/workflows/CSIS/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3ACSIS) | [![Tested Version](https://img.shields.io/badge/version-v1-brightgreen)](https://github.com/microbinfie-hackathon2020/CSIS) |  [CSIS.yml](/.github/workflows/CSIS.yml) |
| [Genotyphi](https://github.com/katholt/genotyphi)   | [![genotyphi](https://github.com/microbinfie-hackathon2020/CSIS/workflows/genotyphi/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Agenotyphi) | [![Tested Version](https://img.shields.io/badge/version-4296976-brightgreen)](https://github.com/katholt/genotyphi/tree/42969769753a53bb74f15bfb60846b5828ff91) | [genotyphi.yml](/.github/workflows/genotyphi.yml) |
| [Kraken](https://github.com/DerrickWood/kraken)   | [![kraken](https://github.com/microbinfie-hackathon2020/CSIS/workflows/kraken/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Akraken) | [![Tested Version](https://img.shields.io/badge/version-v1.1.1-brightgreen)](https://github.com/DerrickWood/kraken/releases/tag/v1.1.1) | [kraken.yml](/.github/workflows/kraken.yml) |
| [KrakenUniq](https://github.com/fbreitwieser/krakenuniq)   | [![krakenuniq](https://github.com/microbinfie-hackathon2020/CSIS/workflows/krakenuniq/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Akrakenuniq) | [![Tested Version](https://img.shields.io/badge/version-v0.5.8-brightgreen)](https://github.com/fbreitwieser/krakenuniq/releases/tag/v0.5.8) | [krakenuniq.yml](/.github/workflows/krakenuniq.yml) |
| [Kraken2](https://github.com/DerrickWood/kraken2)   | [![kraken2](https://github.com/microbinfie-hackathon2020/CSIS/workflows/kraken2/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Akraken2) | [![Tested Version](https://img.shields.io/badge/version-v2.1.1-brightgreen)](https://github.com/DerrickWood/kraken2/releases/tag/v2.1.1) | [kraken2.yml](/.github/workflows/kraken2.yml) |
| [Centrifuge](https://github.com/DaehwanKimLab/centrifuge)   | [![centrifuge](https://github.com/microbinfie-hackathon2020/CSIS/workflows/centrifuge/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Acentrifuge) | [![Tested Version](https://img.shields.io/badge/version-v1.0.4_beta-brightgreen)](https://github.com/DaehwanKimLab/centrifuge/releases/tag/v1.0.4-beta) | [centrifuge.yml](/.github/workflows/centrifuge.yml) |
| [Prokka](https://github.com/tseemann/prokka)   | [![prokka](https://github.com/microbinfie-hackathon2020/CSIS/workflows/prokka/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Aprokka) | [![Tested Version](https://img.shields.io/badge/version-v1.14.5-brightgreen)](https://github.com/tseemann/prokka/releases/tag/v1.14.5) | [prokka.yml](/.github/workflows/prokka.yml) |
| [Quast](https://github.com/ablab/quast)    | [![quast](https://github.com/microbinfie-hackathon2020/CSIS/workflows/quast/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Aquast) | [![Tested Version](https://img.shields.io/badge/version-v5.0.2-brightgreen)](https://github.com/ablab/quast/releases/tag/quast_5.0.2) | [quast.yml](/.github/workflows/quast.yml) |
| [chewBBACA](https://github.com/B-UMMI/chewBBACA) | [![chewBBACA](https://github.com/B-UMMI/chewBBACA/workflows/chewbbaca/badge.svg)](https://github.com/B-UMMI/chewBBACA/actions?query=workflow%3Achewbbaca) | [![Tested Version](https://img.shields.io/badge/version-v2.5.5-brightgreen)](https://github.com/B-UMMI/chewBBACA/tree/v2.5.5) | [chewbbaca.yml](https://github.com/B-UMMI/chewBBACA/blob/master/.github/workflows/chewbbaca.yml) 
| [Pangolin](https://github.com/cov-lineages/pangolin)    | [![pangolin](https://github.com/microbinfie-hackathon2020/CSIS/workflows/pangolin/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Apangolin) | [![Tested Version](https://img.shields.io/badge/version-v2.0.8-brightgreen)](https://github.com/cov-lineages/pangolin/releases/tag/v2.0.8) | [pangolin.yml](/.github/workflows/pangolin.yml) |
| [SKESA](https://github.com/ncbi/SKESA)    | [![SKESA](https://github.com/microbinfie-hackathon2020/CSIS/workflows/skesa/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Askesa) | [![Tested Version](https://img.shields.io/badge/version-2.4.0-brightgreen)](https://github.com/ncbi/SKESA/releases/tag/2.4.0) | [skesa.yml](/.github/workflows/skesa.yml) |
| [Shovill](https://github.com/tseemann/shovill)    | [![shovill](https://github.com/microbinfie-hackathon2020/CSIS/workflows/shovill/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Ashovill) | [![Tested Version](https://img.shields.io/badge/version-v1.1.0-brightgreen)](https://github.com/tseemann/shovill/releases/tag/v1.1.0) | [shovill.yml](/.github/workflows/shovill.yml) |
| [BUSCO](https://gitlab.com/ezlab/busco)    | [![BUSCO](https://github.com/microbinfie-hackathon2020/CSIS/workflows/busco/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Abusco) | [![Tested Version](https://img.shields.io/badge/version-v4.1.4-brightgreen)](https://gitlab.com/ezlab/busco/-/tags/4.1.4) | [busco.yml](/.github/workflows/busco.yml) |
| [Unicycler](https://github.com/rrwick/Unicycler)    | [![unicycler](https://github.com/microbinfie-hackathon2020/CSIS/workflows/unicycler/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Aunicycler) | [![Tested Version](https://img.shields.io/badge/version-v0.4.8-brightgreen)](https://github.com/rrwick/Unicycler/releases/tag/v0.4.8) | [unicycler.yml](/.github/workflows/unicycler.yml) |
| [Trycycler](https://github.com/rrwick/Trycycler)    | [![trycycler](https://github.com/microbinfie-hackathon2020/CSIS/workflows/trycycler/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Atrycycler) | [![Tested Version](https://img.shields.io/badge/version-v0.4.1-brightgreen)](https://github.com/rrwick/Trycycler/releases/tag/v0.4.1) | [trycycler.yml](/.github/workflows/trycycler.yml) |
| [CheckM](https://github.com/Ecogenomics/CheckM)    | [![checkm](https://github.com/microbinfie-hackathon2020/CSIS/workflows/checkm/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Acheckm) | [![Tested Version](https://img.shields.io/badge/version-v1.1.3-brightgreen)](https://github.com/Ecogenomics/CheckM/releases/tag/v1.1.3) | [checkm.yml](/.github/workflows/checkm.yml) |
| [iVar](https://github.com/andersen-lab/ivar)   | [![iVar](https://github.com/microbinfie-hackathon2020/CSIS/workflows/ivar/badge.svg)](https://github.com/microbinfie-hackathon2020/CSIS/actions?query=workflow%3Aivar) | [![Tested Version](https://img.shields.io/badge/version-v1.3-brightgreen)](https://github.com/andersen-lab/ivar) | [ivar.yml](/.github/workflows/ivar.yml) |

## Etymology

CSIS is a play on the acronym for the [United States Food Safety Inspection Service](https://www.fsis.usda.gov).
Additionally, it has CSI in the acronym (Crime Scene Investigation) which has a sort of detective feel to it.

## Contributors
The following participants were responsible for compiling the set of recommendations presented in this repository: [Boas van der Putten](https://github.com/boasvdp) [Inês Mendes](https://github.com/cimendes), [Brook Talbot](https://github.com/bmtalbot), [Jolinda de Korne-Elenbaas](https://github.com/jolindadekorne), [Rafael Mamede](https://github.com/rfm-targa), [Pedro Vila-Cerqueira](https://github.com/pedrorvc), [Luis Pedro Coelho](https://github.com/luispedro), [Christopher A. Gulvik](https://github.com/chrisgulvik), [Lee S. Kat](https://github.com/lskatz). 

The following participants were contributed in automating tests for bioinformatics and contributing a community resource for identifying software that can pass unit tests, available in this repository: [Áine O'Toole](https://github.com/aineniamh), [Justin Payne](https://github.com/crashfrog), [Mário Ramirez](https://github.com/orgs/B-UMMI/people/ramirma), [Peter van Heusden](https://github.com/pvanheus), [Robert A. Petit III](https://github.com/rpetit3), [Verity Hill](), [Yvette Unoarumhi](). 