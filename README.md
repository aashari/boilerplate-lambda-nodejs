# AWS Lambda CI/CD Example Project

This repository serves as a companion example project for the Medium article:  
[Integrate GitHub Repository to Lambda Function using CodePipeline](https://medium.com/@aashari/integrate-github-repository-to-lambda-function-using-codepipeline-b3072ad822fd)

## Project Overview

This project demonstrates how to implement a complete CI/CD pipeline for AWS Lambda functions using:

- GitHub as the source repository
- AWS CodePipeline for orchestrating the deployment workflow
- AWS CodeBuild for building and packaging the Lambda function
- AWS CloudFormation for infrastructure-as-code deployment

## Repository Structure

- `index.js` - A simple Node.js Lambda function template
- `template.yaml` - AWS CloudFormation template that defines the Lambda function
- `buildspec.yml` - AWS CodeBuild specification file for building the Lambda package
- `package.json` - Node.js project configuration

## How to Use This Project

1. Fork this repository to your GitHub account
2. Follow the step-by-step instructions in the [associated Medium article](https://medium.com/@aashari/integrate-github-repository-to-lambda-function-using-codepipeline-b3072ad822fd)
3. Set up the AWS resources as described in the article:
   - IAM roles for CodePipeline, CodeBuild, CloudFormation, and Lambda
   - S3 bucket for artifacts
   - CodeBuild project
   - CloudFormation stack
   - CodePipeline with source, build, and deploy stages

## Pipeline Flow

1. Changes to your GitHub repository trigger the CodePipeline
2. CodePipeline pulls the latest code from GitHub
3. CodeBuild installs dependencies and packages the application
4. CloudFormation creates a changeset based on the template
5. CloudFormation executes the changeset to deploy/update the Lambda function

## Configuration

The CloudFormation template (`template.yaml`) accepts several parameters:

- `LambdaName` - The name for your Lambda function
- `LambdaDescription` - A description for your Lambda function
- `LambdaRole` - The IAM role ARN that the Lambda function will assume

## Future Improvements

- Add CloudFormation/Terraform templates to automate the creation of the CI/CD pipeline itself
- Add unit testing examples in the CI/CD pipeline
- Update to use newer Node.js runtime versions
- Add examples of Lambda triggers (API Gateway, S3, etc.)

## License

ISC

---

Created by [Andi Ashari](https://github.com/aashari) as a demonstration for AWS Lambda CI/CD best practices.
