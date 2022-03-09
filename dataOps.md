# Introduction to data ops

DataOps is a methodology that spans people, processes, tools, and services to enable enterprises to deliver production data rapidly, repeatedly, and reliably from a vast array of enterprise data sources to a vast array of enterprise data consumers.

The necessity of Data Ops has emerged as individual in large traditional enterprise released that they should be using all the data generated in their company as a strategy asset to make better decision every day. However, most of the current organisation are unprepared, often because of the lag of their technical capabilities and current culture finding difficult to understand the importance of change.

## Data Ops benefits/values

- Rapid delivery of data products
- Quick resolution of issues and defects
- Fast response to the business needs and shorter release cycles
- More communication and visibility between the data team, infrastructure and stakeholders.
- Shift in scope and accountability
- Promotes Innovation and continuos learning
- Cost benefits, ephemeral testing instead of permanent testing

## Data Ops goals

Data Ops is the framework that will allow organisation to begin the journey towards treating their data as and asset

- Help the organisation to change existing process to more agile process
- Provide people behavior changes with data and operations
- Help to organise their data in small products or logical business entities. For example Customer, Products.
- Cost effective deliver timely, high-quality data that meets the ever-changing need of the organisation.

## Difference between Data Ops and DevOps

### What is Infrastructure as code

To be able to do DataOps, organisation require to have the right person with the right knowledge or skill available. With Infrastructure as code (IaC), deploying additional servers is a matter of running the appropriate code, reducing the time the deployment.

With IaC teams will be able to introduce in a new version of a deployment, they can roll back the deployment to a previous version while the issue is identified and address. To minimize issues found in production, organisation can deploy in staging and UAT or other environment, with full confidence that redeploying in production will not bring any surprises.

The infrastructure team will need to work closed to the data team to understand the components require for their implementation of the data products. THe IaC covers spinning data services and configuration of them. For example, azure sql databases and its firewalls in dev, qat and production.

### What is CI/CD

CI/CD is a set of practices that automate the building, testing and deployment stages of a data products.

The CI is always refers to continuos integration, which is an automation process for developers. A successfully CI means new code changes to the data product are regularly build, tested and merged to a repository. The CD refers to continuously delivery and deployment. Automatically releasing a developer's changes from the repository to production environment.

## Process

### Data Ops Principles

The agile process is one of the fundamental principles for Data Ops. The agile process generally follows these steps

#### Planning

The scope defined by the business also known as backlog.

Review of the backlog between the development team and the business to define priorities
Keep team independent, this means each team's responsibilities span all domains.
Resources to help to understand backlog best practices <https://docs.microsoft.com/en-us/azure/devops/boards/best-practices-agile-project-management?view=azure-devops&tabs=agile-process#choose-the-work-item-types-youll-use> and <https://docs.microsoft.com/en-us/azure/devops/boards/backlogs/backlogs-overview?view=azure-devops>

#### Developing

- The data product is designed, developed and iterated.
- Retrospective between the business and the development team.
- Work with your infrastructure, data teams and customers

#### Deliver

The data product is prepared for release for production after testing and fixing defects.

#### Operate

- The release is continuously improved and support is provided.

## How do we build a DataOps Team?

### Databases

- Integration
- Data to process orchestration
- Data policy deployment
- Data and model integration
- Data security and privacy controls
- Data Ops Challenges
- Compare with Software Development DataOps teams can have some challenges

### Resource Intensive

Even moderate-scale data places significant demands on infrastructure, so provisioning is another DataOps challenge. DataOps needs to consider data storage, movement, query processing, provenance, and logging. Storage must be provisioned for multiple releases of data as well as for different environments. Compute must be provisioned intelligently, to keep data transfers within acceptable limits.

### Schema change

Analysts require data changes for every new analytics or visualization, this modification, each change might require adjustment to the entire depth of the associated data pipeline however many tools still assume that schemas changes slowly or not at all and the DataOps team must implement responsiveness to schema change outside these tools.

### Governance

Regulations from both government and industry cover data access, retention, traceability, accountability, and more. DataOps must support these regulations and provide alerting, logging, provenance, and so on throughout the data-processing infrastructure

Another challenge faced in enterprise data is repeatability and scale, being able to find, shape and deploy data reliably with confidence.

## Data Ops Roles
