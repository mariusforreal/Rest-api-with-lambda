
# S3 JSON Retrieval REST API

This project demonstrates how to create a serverless REST API using AWS Lambda and API Gateway to retrieve the content of a JSON file stored in an S3 bucket.

## Overview

The project consists of an AWS Lambda function written in Python that retrieves the content of a JSON file from a specified S3 bucket and returns it as a JSON response when the REST API is invoked.

## Prerequisites

- AWS Account
- AWS CLI configured with necessary credentials
- Basic understanding of AWS Lambda, API Gateway, and S3

## Setup

1. Clone this repository to your local machine:
 git clone https://github.com/mariusforreal/Rest-api-with-lambda.git
cd Rest-api-with-lambda


2. Create an S3 bucket (e.g., `devops-00237`) and upload a JSON file named `foo.json` with content `"Hi, I am the foo"`.

3. Deploy the Lambda function:
   
   - Replace the `bucket_name` and `file_name` variables in the `lambda_handler` function within `lambda_function.py` with your S3 bucket name and JSON file name.
   - lambda code can be found here: https://github.com/mariusforreal/lambda-code-for-rest-api/blob/main/code

4. Deploy the Lambda function using the AWS CLI:


aws lambda create-function --function-name S3JsonRetrievalFunction --zip-file fileb://lambda_function.zip --runtime python3.8 --role arn:aws:iam::YOUR_ACCOUNT_ID:role/YourLambdaRole --handler lambda_function.lambda_handler


5. Create an API Gateway and link it to the Lambda function.

6. Deploy the API to make it publicly accessible.

7. Access the API endpoint to retrieve the JSON content from the S3 bucket:

GET https://your-api-url/resource?bucket=devops-00237&file=foo.json


## Usage

Make a GET request to the API endpoint with the required query parameters:

- `bucket`: The name of the S3 bucket.
- `file`: The name of the JSON file to retrieve.

The API will return the JSON content of the specified file.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.


#################

Deploying in infrastructure as code (Teraform)

git clone this repo for terraform script
git clone https://github.com/mariusforreal/terraform-for-api-deployment/tree/main

