# DevOps

## What is DevOps?

* DevOps is a methodology that spans people, processes, tools, and services to enable enterprises to deliver into production rapidly, repeatedly, and reliably
* DataOps is simply DevOps applied to data solutions
* Designed to enable rapid development and a robust feedback cycle

### Goals

* Changing an existing process to more agile process
* Align team structures and skills for rapid progress
* Organise in small products or logical business entities
* Cost effective timely delivery

## Product Team

### Product Owner

* Owns the Road Map
* Interacts with the Business
* Owns Direction of product
* Feedback from business
* Owns Budget

### Project Manager

* Owns the Backlog
* Project Cadence
* Resource Planning
* Project Budget

### Delivery Team

* Develop Features
* Fixes
* Testing
* 3rd Line Operational Support

## Product Planning

* Who is/are the customer(s)
* What do they need?
* What can we realistically deliver?
* What is the budget?
* Roadmap
  * Features
  * User Stories
  * Prioritised
  * Regular feedback

### Marketing

* Product Usage
  * Monthly Active Users (MAU)
  * Justify the product
  * Compete against alternatives
* Success Stories
* Skilling initiatives	
  * Product Training
* Advertising
  * Product Awareness
  * Seminars
  * Posters, mailers, user groups

## Project Management

### Backlog

* Work Items
  * Epics
  * Features
  * User Stories
  * Bugs
  * Issues
* Don’t boil the ocean
  * Keep below about 3 months in the backlog
  * Large backlogs make prioritisation harder
  * Slows the feedback loop

### Sprint Planning

* Prioritise Backlog
  * Productivity gains first, including support issues
  * Business and user priorities
  * Product goals
  * Technical debt
* Sprint
  * Achievable progress, known goals
  * Fixed time
  * Available resources
  * Complimentary work items

### Resource Planning

* Build a team
  * Skills required
  * Capacity of each skill
  * Availability of resources
* Velocity
  * Throughput of work per sprint

## Product Development

### CI/CD

**Continuous Integration**

Each team member's changes and features are integrated often into the collaboration branch, allowing access for the whole project to test things together

**Continuous Deployment**

Changes are deployed to production quickly and (ideally) automatically following testing and approval processes

### Source Control

* Source Control
  * Azure Repos or GitHub
  * Each data product stored in one repository
  * Dependencies such as libraries stored elsewhere
* Branch Definition and policies
  * Feature branches 
  * Collaboration Branch
  * Main Branch
* Pull Requests
  * Ask the owner to pull your changes into their branch
  * Requests let your team give feedback on changes in feature branches before they merge code into the collaboration branch
  * You do not push code to higher branches

### Deployment

* Approval Gates
  * Test outcomes
  * Reviews
* Staged delivery
  * Pre-production used to give early access
  * Non-structured testing
  * Smoke tests
* Scripted Deployment

### Operations

#### Operations Team

* Monitoring and Alerting
* Hygiene
* Scheduling  (production pipelines)
* Availability and Disaster Recovery
* End user support

#### Product Team

* Solve problems and escalations, major issues logged in the backlog by 1st and 2nd line support 
* Logged any areas where the product doesn't meet operation requirements into the backlog

### Support Structure

* Product team takes responsibility for support
* More direct
* Easier to change/fix product


<table>
  <tr>
    <td><b>Traditional</b></td>
    <td>1st Line</td>
    <td>2nd Line</td>
    <td>3rd Line</td>
    <td align="center">Product Support</td>
  </tr>
  <tr>
    <td><b>DevOps</b></td>
    <td>1st Line</td>
    <td>2nd Line</td>
    <td colspan="2" align="center">Delivery Team</td>
  </tr>
</table>