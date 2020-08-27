# api-gw-swagger

This project demonstrates how to use define API Gateway APIs using swagger that incorporates dynamic values from the SAM template.

# Pre-requisites

* [AWS CLI version 2](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

* [AWS SAM CLI (0.41.0 or higher)](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)

* [Docker](https://docs.docker.com/install/)

# Deployment

## Build

```bash
sam build --use-container
```

## Deploy

## Upload swagger file to accessible S3 bucket

The swagger file that contains the API definition will need to be uploaded to a S3 bucket.

```bash
aws s3 cp src/apigateway/swagger.yml s3://some_bucket_you_own
```

Make note that you'll need to provide the S3 bucket when deploying the application stack.

## Deploy the serverless application

Run the following command the first time the application is deployed.

```bash
sam deploy --guided
```

You will be prompted to enter the S3 bucket from the previous step.  

Save the outputs to the file `samconfig.toml`.  Subsequent runs will take advantage of the values stored in the configuration file.

```bash
sam deploy
```

# Cleanup

## Destroy cloudformation stack

```bash
aws cloudformation delete-stack --stack-name your_stack_name
```
