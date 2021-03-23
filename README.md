# TODOIST API / POSTMAN USE CASE:


## Requests implemented in the collection based on the TODOist API docs:
https://developer.todoist.com/rest/v1/


- Get Active tasks
- Create new tasks
- Get an Active task
- Update a task
- Change task status to 'complete'
- ReOpen a task
- Delete a task

## Run collection via CLI
### Install requirements:
## Install individual dependencies 
`npm install -g newman`
`npm install -g newman-reporter-htmlextra`
## Install dependencies from this package:
`npm install`


### Run the postman collection from this project via newman:
- Obtain your todoist api token in the following URL below API TOKEN:
https://todoist.com/prefs/integrations

- Once newman is installed run newman from the command line with the following command:
`newman run TODOIST.postman_collection.json -e TODOIST_ENVIRONMENT.postman_environment.json --env-var "API_TOKEN=SUBSTITUE_THIS_WITH_YOUR_API_TOKEN" -r htmlextra`
- Or Set an env var in your system and call the previous command by using the envvar value as an argument
for example: set the TODOIST API TOKEN to a var named TODOIST_APITOKEN and call the CLI with that env var:
(mac and linux)
`export TODOIST_APITOKEN=SUBSTITUE_THIS_WITH_YOUR_API_TOKEN`
`newman run TODOIST.postman_collection.json -e TODOIST_ENVIRONMENT.postman_environment.json --env-var "API_TOKEN=$TODOIST_APITOKEN" -r htmlextra`


## Integrating with a CI/CD
- Set TODOIST_API_TOKEN as a secret var or env var for a pipeline job. 
- Clone this repo from a CI/CD pipeline
- (Install dependencies if it is required)
- Call the following command from the pipeline as a shell script
- Using the reporter "htmlextra" is optional `-r htmlextra` but you can artifact these results in your CI/CD pipeline
so that they can be visualized. the relative exported path would be `newman/*.html`

`newman run TODOIST.postman_collection.json -e TODOIST_ENVIRONMENT.postman_environment.json --env-var "API_TOKEN=$TODOIST_APITOKEN" -r htmlextra`


## Troubleshooting:
