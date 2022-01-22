# Welcome to the MetroStar Tech Challenge 

This repository contains a small Java Spring/SpringBoot application which you will need to deploy to an AWS account via automation. The automation framework of preference is Terraform, but if you don't have experience with it, you are free to use Ansible, CloudFormation, Pulumi, or something comparable.  Additionally, a CI/CD Pipeline will need to be setup using a tool such as CodePipeline, Gitlab, Github Actions, etc... Tool selection is largely at your discretion so pick a stack you're familiar with and can implement with minimal effort.

# The Challenge

In the AWS environment, you will deploy the infrastructure necessary to host, build and deploy the Java SpringBoot app in this repo. The requirement is to have the web backend (the java app in this repo) built and deployed as a Docker image to ECR, hosted in an AWS resource capable of running Docker images (EC2, ECS, EKS, etc...), and testable from a local web browser.

To accomplish this you'll need to:
1) Create an ECR resource
2) Create hosting resources (EC2, ECS, whatever will be used to run the deployed app)
3) Create any needed infrastructure to expose a web application
4) Create any needed IAM roles/policies
5) Create a CI/CD pipeline that does the following at a minimum
  a.	Clone: clone from github repository that holds Java Springboot code for helloworld
  b.	Build: Use maven to build .jar file from Java Springboot code
  c.  Unit test: Run any unit tests included in the application source
  d.	Containerize: Build docker image that containerizes the springboot app
  e.	Deploy: Deploy image to AWS ECR and update the hosted environment with the new image tag


# InterviewSpringApp
A simple Java based "Hello, World" web service has been provided along with a sample Dockerfile. No changes to the application source code are required or expected as part of this challenge, though you may feel free to modify the provided Dockerfile as needed.


# AWS Account
Regarding the AWS account you'll be working with, you have full admin privileges.  Please be certain to follow best practices when configuring services from both a performance and cost perspective.

Within the account, you are free to remove any existing resource and can use any service you deem necessary for the completion of the project.

The two restrictions are:
1) Do not alter any of the existing resources.
2) All resources should be allocated in the N. Va region

# Deliverable
1) Create a branch from main and add all infrastructure automation and build pipeline code needed to achieve the stated requirements
2) Deploy your solution to the provided AWS account
3) Create a pull request to main and assign to "csg-devops"
4) During the final interview, you'll walk us through your solution
