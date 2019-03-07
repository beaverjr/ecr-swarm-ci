# ecr-swarm-ci
Deploy on Docker swarm from ECR via CircleCI (Example Project)

## Description

This is  an example of how to build and test a Dockerized web application on CircleCI, push to an AWS EC2 Container Registry, and then deploy on Docker swarm.


## Prerequisites

* Configure a few CircleCI environment variables before the deploy script will work
```
AWS_ACCOUNT_ID
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
SSH_USER
SSH_HOST
```
* Add an SSH Key to CircleCI

* Define following environment variables in a .env file and place it in the same directory as the docker-compose.yml
```
export AWS_ACCOUNT_ID=your aws account id
export AWS_DEFAULT_REGION=aws reagion
export ECR_REPOSITORY_NAME_WP=wp
export ECR_REPOSITORY_NAME_MYSQL=mysql
```
* EC2 Container Registry must already be set up on AWS
* Docker swarm cluster must already be created on your server


## Usage
CircleCI automatically runs your build and test processes, and push image to ECR, deploy on Docker swarm from ECR when you update docker-compose.yml or Dockerfile.
