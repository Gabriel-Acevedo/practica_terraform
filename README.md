# Practica 01: Tecnicas y Herramientas para Despliegue Continuo

## Overview

This repository will demonstrate an example of GitOps workflow with Terraform, Jenkins and AWS.

## Requirements

* Terraform installed in Jenkins (or on Local Machine in case of running Jenkins on Local)
* Several Plugins installed on Jenkins, which will be listened below
* Github access token
* AWS Credentials and normal account (AWS Credentials do not work)
* S3 Bucket

## Setup Bucket

To have the pipeline work, there has to be an existing S3 bucket in AWS and configured in `main.tf':

```
# Terraform state will be stored in S3
terraform {
  backend "s3" {
    bucket = "terraform-bucket-ggordoarmen93"
    key    = "terraform-bucket-ggordoarmen93"
    region = "us-east-1"
  }
}
```

## Plugins Required in Jenkins:

* [Workspace Cleanup Plugin](https://wiki.jenkins.io/display/JENKINS/Workspace+Cleanup+Plugin)
* [Credentials Binding Plugin](https://wiki.jenkins.io/display/JENKINS/Credentials+Binding+Plugin)
* [AnsiColor Plugin](https://wiki.jenkins.io/display/JENKINS/AnsiColor+Plugin)
* [GitHub Plugin](https://wiki.jenkins.io/display/JENKINS/GitHub+Plugin)
* [Pipeline Plugin](https://wiki.jenkins.io/display/JENKINS/Pipeline+Plugin)
* [CloudBees AWS Credentials Plugin](https://wiki.jenkins.io/display/JENKINS/CloudBees+AWS+Credentials+Plugin)

	