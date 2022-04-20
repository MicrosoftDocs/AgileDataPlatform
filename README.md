
# Agile Data Platform

Architecture and documentation for a truly agile data platform that is operationally scalable, not just architecturally.

## Introduction

This repository is intended to provide examples and explanations of how to architect a modern cloud data platform which is driven by DevOps processes and allows enterprise scale in terms of both capability and work throughput. It is designed to remove unnecessary blockers and issues which arise with more traditional approaches by following the example of application development. Concepts such as "Cattle vs Pets" and loose coupling will be central to this architecture, alongside a modular approach with strong, contract based interactions between components. The documents here describe the platform as a whole and should not be confused with data engineering or data modelling documentation both of which still have their place inside of data products alongside aspects such as data quality and compliance.

This information has been created because we see customers with very specific problems arising from traditional approaches to their platforms. As a general rule, data platform evolution follows the stages set out below. While it might be possible to jump straight to the "mature" end of the spectrum the skills required to do so are not usually present within an organisation. For this reason, we recommend progressing naturally through the stages as the organisation matures according to requirements. Always remember that the purpose is to process and present data, and delivering this goal by whatever means you can as early as you can will get buy in from the business while spending a year trying to build an advanced platform may not deliver the data for the business to use.

Cloud Data Platform Maturity Journey
<table>
  <tr>
    <th>Stage 1</th>
    <th>Stage 2</th>
    <th>Stage 3</th>
    <th>Stage 4</th>
  </tr>
  <tr>
    <td>Initial Cloud Data Platform</td>
    <td>Enterprise Scale</td>
    <td>Agile Platform</td>
    <td>Code First Platform</td>
  </tr>
  <tr>
    <td>
      <ul>
        <li>Initial move to the cloud for data.</li>
        <li>Standard architecture</li>
        <li>Ad hoc deployment</li>
        <li>Ad hoc reporting</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>Scaling up</li>
        <li>Automated deployment of templates</li>
        <li>Mass onboarding of data</li>
        <li>Centralised data team</li>
        <li>Standardisation</li>
        <li>Centralisation</li>
        <li>Policy driven architecture</li>
        <li>Segregated staging environments</li>
        <li>Single version of the truth</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>Distributed Teams</li>
        <li>Strong Engineering Approach</li>
        <li>Automated Testing</li>
        <li>Product driven development</li>
        <li>Decentralised for operational scale</li>
        <li>Advanced automation</li>
        <li>Ephemeral staging environments</li>
        <li>Competing products for evolution and progress</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>Fully code driven</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td>
      <ul>
        <li>Slow deployment</li>
        <li>Hard to change</li>
        <li>Slow to scale</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>Teams cannot scale</li>
        <li>Deployments are high risk</li>
        <li>Team throughput slows</li>
        <li>Architecture is inflexible</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>Products interfaces become bottlenecks</li>
        <li>Repeatability is hard</li>
        <li>Copying solutions is difficult</li>
      </ul>
    </td>
    <td>
      <ul>
        <li>Advanced skills required</li>
      </ul>
    </td>
  </tr>
</table>

The agile data platform can be broken down into several topics, each of which can be considered independently if retrofitting into an existing practice, or together if starting from scratch. 

[Agile Data Platform Introduction](<presentations/00 Agile Data Platform Intro.pptx>)

### Structured Testing

This is an often misunderstood subject within the data practice since it does not focus on testing the data but rather the implementation. Structured testing allows you to perform unit testing and integration testing against your data platform and pipeline components to ensure quality and consistency.

[Structured Testing](docs/testing.md)

[Presentation - Introduction to Testing](<presentations/01 Testing Intro.pptx>)

### DataOps

DataOps are a set of processes and methods for managing a project and product development. While this may include some automation it is not simply scripted deployment. DataOps is the bringing together of the skills and people needed to successfully build a data product. These include data modelling, data engineering, testing, infrastructure, security, networking, disaster recovery and backup, reporting, monitoring and of course support. Each of these skills and more must be represented within the team to allow frictionless progress to be made, removing the need for change controls between departments and placing the responsibility directly with the project team itself. The processes here allow for quality checks and tests to be made during each development cycle, giving confidence that the next product release will do everything expected, with any issues and feedback being dealt with by the team itself.

[DataOps](docs/dataOps.md)

[Presentation - Introduction to DataOps](<presentations/02 DataOps Intro.pptx>)

### Agile Platform Architecture

Processes such as automation can make delivery more agile, but beyond a certain point team size becomes an issue and complexity starts to overtake agility and slows progress. To prevent this, a different architecture is needed which can break the problem down into smaller tasks and projects and make them more manageable. Not only to make the teams more manageable but to reduce operational complexity. Traditionally data platforms have been architected as end to end processes from source to destination with long interlinked ETL or ELT pipelines each interdependent to the point that one failure will break the whole system. With an agile data approach our aim is to follow the loosely coupled, highly focused "micro-service" approach from application development. Centralisation is often used in data platforms, and while this works initially it also adds unnecessary work and slows progress. The agile data architecture centralises only where necessary and justified.

[Architecture](docs/architecture.md)

[Presentation - Agile Data Platform Introduction](<presentations/03 Agile Data Architecture Intro.pptx>)

## Supporting Information

[Architectural Principles](docs/architecturalPrinciples.md)

[Glossary of terms](docs/glossary.md)

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
