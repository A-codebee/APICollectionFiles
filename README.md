# Postman API Automation Integration with Github Actions #

This repository is a demonstration of POC for integrating postman tests with Github actions. The tests are written in postman and are executed on VM with help of newman and newman-reporter-htmlextra.
Github Actions will trigger test execution on every push that happens to the main branch. You can also execute the project manually using workflow_dispatch. Cron jobs are used to schedule test runs for a specific time. 

The HTML reports are archived and kept in the artifact section for the team to download. Report can directly be viewed from the github page : https://a-codebee.github.io/APICollectionFiles/

After the execution the reports are directly mailed to team members using GMAIL SMTP.

## Testing Coverage ##

1. Happy Flow Testing
2. Negative Testing and Edge Cases Testing
3. Token Testing
4. Schema Validation
5. Secrets Management using Github Secrets


# Tech Stack #

1. Postman
2. newman
3. Nodejs (V 22)
4. newman-reporter-htmlextra
5. Github Actions
6. GMAIL SMTP
7. Github Pages
8. AWS - EC2 instance for self hosted github runner

## Github pages ##

You can directly view the latest reports for the postman tests at : https://a-codebee.github.io/APICollectionFiles/

## HTML Report ##

Report will be created in the newman folder

![Postman Report](https://raw.githubusercontent.com/A-codebee/APICollectionFiles/static_content/Newman%20Report.png)

## Project Structure ##

```
Flow
├─ E2E_flow_API_Tests.postman_collection.json # Collection File
├─ QA.postman_environment.json # Environment File
└─ testdata.csv # Testdata file for Data Driven Testing

```

## How to run the project ## 

In order to run the project on the local system we can 

1. Clone the project on the local system from https://github.com/A-codebee/APICollectionFiles.git
2. Install node js and npm from : https://nodejs.org/en
3. Install newman using ``` npm install -g newman ```
4. Install html reporter using ``` npm install -g newman-reporter-htmlextra ```
5. Run the tests using the command

          newman run E2E_flow_API_Tests.postman_collection.json -e QA.postman_environment.json -r cli,htmlextra



