## Introduction

This is a full stack app whose back end api has been developed in NodeJS backed by PostgreSQL database and the front end has been developed in Angular.

### Services

The app uses the AWS service to deploy its various components:

1. Database deployed on the RDS service.
2. Backend api is deployed on Elastic Beanstalk
3. Frontend api is deployed on S3

### CI/CD

The app uses CircleCI for Continuous Integration & Delivery. With each commit to the git repository, CircleCI `config` available in the root dir of `.circleci/config.yml`

1. builds both the front and back ends
2. runs tests for the back end
3. deploys both of them to the appropriate AWS service using AWS CLI and EBS CLI orbs
4. with the appropriate environment variables also passed through CircleCI to AWS
