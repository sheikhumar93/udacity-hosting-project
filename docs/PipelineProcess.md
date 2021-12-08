The CI/CD pipeline runs on CircleCI

1. The repository is public which is why CircleCI can be used for free with a very generous monthly limit
2. Add the project to your own Github/Bitbucket profile
3. Link your account to CircleCI
4. Add all the required environment variables to this project visible in `./screenshots/circle-env-vars.png`
5. Select the `main` branch in the project and `Trigger Pipeline`
6. The pipeline first builds a standard Ubuntu Nodejs environment using a docker image
7. AWS-CLI and EB-CLI orbs are installed next
8. Then the backend application is built with the provided scripts, tests are run and deployed via `eb cli`. The details of the BeanStalk application are already provided in the api folder under `.elasticbeanstalk/config.yml`
9. The frontend application is built next and deployed via AWS CLI to an S3 bucket

### Note: No sensitive environment variables are provided in the source code of the app. The backend api server address is provided in the source code under `./undergram/undergram-frontend/src/environments/environment.prod.ts` which is non-sensitive information in the first place.
