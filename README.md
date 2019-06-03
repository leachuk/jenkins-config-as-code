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

## Jenkinsfile

The Jenkinsfiles usually reside in the root of the project repo which the Jenkins pipeline is building. Following convention, they are usually named as `Jenkinsfile`, but it can be arbitary and is defined in the pipelines config. 
Documentation for Jenkinsfiles is available at https://jenkins.io/doc/book/pipeline/jenkinsfile/

There are some samples available under /Jenkinsfile-samples which illustrate some useful tasks.

### Jenkinsfile-withMaven
The withMaven block is necessary for running maven as configured by Jenkins and the Maven Pipeline Plugin. 
This allows Jenkins to manage the maven dependency and allows different maven versions and settings to be used across multiple pipelines. Documentation can be found at https://wiki.jenkins.io/display/JENKINS/Pipeline+Maven+Plugin

Without using `withMaven(...)` you will likely recieve a `mvn not installed` error when the pipeline runs, and would need to install maven to the server manually. This is not recommended from a CasC perspective. 
