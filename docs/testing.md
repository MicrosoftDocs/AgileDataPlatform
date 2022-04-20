# Structured Testing

## Why Test?

Increase Quality
Increase Confidence
Reduce time to deploy
Improved Security
Reduced cost through smaller, ephemeral environments

## Structured vs Unstructured

Structured testing – Testing for known desired outcomes (e.g. correct maths) and anticipated error conditions 

Unstructured testing – Errors happen in pre-production when live data is introduced. Often known as a “smoke test” to see what the developers missed. This is not structured testing and cannot be automated since the outcome is not known until a new failure occurs. 

## Frameworks

### Example Frameworks

MS Test Framework
Pester (Powershell)
PyTest

### Choosing a Framework

### Defining Tests

Assert statements
failures can be asserted
expected outcomes, not correct data

### Integrating a framework to Azure DevOps

EXTERNAL LINK REQUIRED

## Types of Test

### Development Testing

These tests fall within the scope of the development of the product. These are generally triggered within Azure DevOps and relate to build or commit events in the project to check for release suitability and quality.

Unit vs integration
Automatic vs manual
Performance/capacity vs functional

### Operational Testing

The below are beyond the scope of this page, but are included to show the types of testing which will be included in your product deployment but not triggered by the development process. These are triggered by your data processing schedule or some other run time mechanism within the product.

Data Quality tests
Pipeline Monitoring
Performance and scale tests

## Test Data

Test data – Usually small, specific data for instance a badly formatted date, or date on a non existent leap year. Designed to check that the proper error is given in the solution. 

There are no useful scenarios for having regularly refreshed test data in large data sets. This often just wasted developer time since they are not testing for known outcomes and so there is no good  use for the results, and no plan of action. Simply running the solution on live data in pre-production achieves the same outcomes. 

<table>
  <tr>
    <td rowspan="2">Performance/Scale </td>
    <td>Against Production </td>
    <td>Use live data in a parallel run for performance comparison to live data</td>
  </tr>
  <tr>
    <td>Between Versions</td>
    <td>Standardised data set to build up a baseline performance picture so we can see improvements or slowdowns as features change</td>
  </tr>
  <tr>
    <td rowspan="2">Functionality</td>
    <td>Unit Tests</td>
    <td>Small test data within unit tests, mostly bad data with some good, testing specific failure modes (e.g. leap year or clock changes) </td>
  </tr>
  <tr>
    <td>Integration tests</td>
    <td>Multiple small sets of data designed to test integrations. Pipeline parts are tested individually and together to test for known failure modes as well as expected data results (e.g. does aggregation produce expected numbers for the test data date range?</td>
  </tr>
  <tr>
    <td rowspan="2">Live Data</td>
    <td>Smoke Test</td>
    <td>Unknown data will produce unknown results, so live data must be processed at least once in a pre-production or QA environment in parallel to the production processing. If unexpected errors are found then deployment to production should be delayed while the delivery team investigates.</td>
  </tr>
  <tr>
    <td>Operational Issues</td>
    <td>Sometimes unexpected circumstances cause unexpected failures. These will be investigated by operations and support to find root cause then new structured tests added to backlog for future inclusion in regression testing.</td>
  </tr>
</table>

## Ephemeral Environments

Some test types such as performance testing require parallel ephemeral environments to be automatically created

## What to Test

EVERYTHING

But…

Data quality tests – should the pipeline fail or should bad data be allowed through for data quality checks to catch? Ideally test for things which break deployment

## Example Tests

Dates
Data Types
Deployment success
Pipeline speed/capacity
