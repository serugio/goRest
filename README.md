# goRest

REST API test case implementation using postman and newman


## local test execution

https://user-images.githubusercontent.com/43422922/235315764-83ba13e8-a0f4-4bcd-a287-7ff690e105ce.mp4


## pipeline newman demo



https://user-images.githubusercontent.com/43422922/235315948-35b7fd72-bee5-4628-8e50-2fca99256433.mp4

## To Enable CI/CD in Jenkins

1. Make sure you have installed Jenkins with following any guide like this one and make sure to install suggested plugins: https://www.jenkins.io/download/#downloading-jenkins
2. fork whis repo in your github account.
3. set credentialsId in your jenkins instance
 - go to the nex path and click on "add credentials" and fill with your github credentials. Disclaimer: this is an unrestricted credential and doesn't follow any good practice regarding security
 ![image](https://user-images.githubusercontent.com/43422922/235029270-5346bff5-d9de-4e55-8992-50453b2596bc.png)

 
4. inside "Jenkinsfile" file replace 'credentialsId' and 'url' parameters 
 - url: replace for your forked repository
 - credendialsId: <your_credentialId>

![image](https://user-images.githubusercontent.com/43422922/235028298-bfa8ec3f-f82d-4b2e-8c44-acf294e187db.png)

### Note
Jenkinsfile was created in a windows machine, for this reason "bat" command is used to execute bash commands. If this job is intende to be executed in a Unix based OS, 'bat' commands should be replaced for 'sh' 

![image](https://user-images.githubusercontent.com/43422922/235029743-1a243155-b8e5-4c1a-81c9-ce1b79e8b8a0.png)

5. Create jenkins job
 - click on "add" in jenkins dashboard.
 - fill "name" and choose "pipeline"
 ![image](https://user-images.githubusercontent.com/43422922/235032351-443be23e-3637-4bc0-8739-9245dbc5edb9.png)
 
 - go to 'general' section and mark 'build periodically' and fill as the image below. (this schedule the job to be executed on daily bases
 ![image](https://user-images.githubusercontent.com/43422922/235033425-7fe5cf00-c82a-4356-aaa8-39271ae5d032.png)

- go to 'pipeline' section and choose 'script from SCM'
![image](https://user-images.githubusercontent.com/43422922/235032519-7eb6b119-0bb8-4aab-9091-044a8f3c8609.png)
- fill the fields as the image below, take into account to replace your repository URL and your credentialsID. Leave other fields as default
- click on "apply"

![image](https://user-images.githubusercontent.com/43422922/235032658-59cf4343-e2a4-4884-bca9-8f33bbbdbb35.png)

### NOTE

- If you want to execute the project locally:
- make sure to download the repo 
- do checkout to 'master' branch
- execute 'npm install'
- execute 'npm run E2ETest' which is a custom command to execute the automated test case.

## ABOUT THE SOLUTION

Is the implementation of an E2E test case for the purchase flow of the https://www.saucedemo.com/ web application.
- Cypress is the chosen automation tool
- It was added support to Gherkins syntax in order to allow BDD approach. (using 'feature' 'stepDefinition' and 'pageClasess' approach.
- It was added support to typescript
- It is using mochawesome reports as reporting tool.

## ABOUT THE TESTING APPROACH
- due to the time I chosed to work with an E2E test case that covers the positive path of the purchase flow. However, the coverage can be improved adding different scenarios like (logout in the middle of the flow and then re-login, include error paths, validate that prices and taxes work as intended).
-test case design is delivered in attached file trough email.

