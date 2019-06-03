# Jenkins Config As Code

Samples adapted from https://github.com/Praqma/praqma-jenkins-casc

## Quick Start

- Build local docker instance of Jenkins with a sample pipeline
```
docker-compose up --build -d
```
When complete, browse to http://localhost:8081

## Secrets

Currently any secrets (i.e. credentials to store git repo passwords, etc) are not managed via the CasC and will need to be setup manually once the server is running.
Eventually this will be updated to manage passwords securely, for now it requires a manual step.
