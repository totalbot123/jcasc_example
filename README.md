# JCasC Example project

Example project for setting up CICD using freestyle jobs. CICD and Jenkins are fully configured using JCasC, along side Docker.

# Details

There are 6 jobs: Build -> Test -> Integration Test -> Code Analysis -> Sonar Scanner -> Deploy
The name pretty much suggests what each one of them does.
To make these work, you would need to make few more integrations

## Nexus

Each job has hardcoded configuration for nexus (setup with settings.xml file that is passed to maven). This might be changed in future.
You will also need to provide url and authentication to Nexus.

## Sonarqube

You will need to provide url and access token.

## Slack

You will need to provide few things like api token and most of channel configuration as it is hardcoded in jobs. This might be changed in the future.

# How to run it

docker-compose up -d

## Authors

* **Milan Jecmenica** - *Initial work* - [totalbot123](https://github.com/totalbot123)
