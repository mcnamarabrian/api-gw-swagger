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

Run the following command the first time the function is deployed.

```bash
sam deploy --guided
```

Save the outputs to the file `samconfig.toml`.  Subsequent runs will take advantage of the values stored in the configuration file.

```bash
sam deploy
```

# Cleanup

## Destroy cloudformation stack

```bash
aws cloudformation delete-stack --stack-name your_stack_name
```
