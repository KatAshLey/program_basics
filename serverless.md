# install node.js first
# MUST USE GIT BASH

# to install serverless
npm install -g serverless

# to create a template. 
# Make sure you create a folder for the app first and cd into it
# mkdir app1, cd app1
serverless create --template aws-python3

# to invoke a function
serverless invoke local --function hello


# search in documentation how to use serverless
# usage, events
https://www.serverless.com/framework/docs

# use event types from Amazon website
https://docs.aws.amazon.com/AmazonS3/latest/userguide/notification-how-to-event-types-and-destinations.html


# the function to find a s3 bucket called photos in yaml file
# bucket names must be globally unique
functions:
  create_thumbnail_function:
    handler: handler.create_thumbnail 
    name: create-thumbnail-function
# event bridge part below
    events:
      - s3:
          bucket: photos
          event: s3:ObjectCreated:*
          rules:
            - prefix: uploads/
            - suffix: .jpg


# handler file for above yaml
import json


def create_thumbnail(event, context):
    body = {
        "message": "I'm creating a thumbnail",
        "input": event
    }

    response = {
        "statusCode": 200,
        "body": json.dumps(body)
    }

    return response

# Install AWS CLI
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html


# in aws create a new iam user and create access keys
![Alt text](image.png)
![Alt text](image-1.png)
![Alt text](image-2.png)
![Alt text](image-3.png)
![Alt text](image-4.png)

# in VScode use access code from AWS iam user section
aws configure

AWS Access Key ID [None]: AKIAXOAQNOCM2WYEXIV7
AWS Secret Access Key [None]: ******************
Default region name [None]: us-east-1
Default output format [None]: yaml

# to check if above configure worked
aws sts get-caller-identity

# activate access key for use and deactivate when not being used in AWS

# Nicks instructions
![Alt text](image-5.png)

# ensure cd folder, package yaml file, with Docker open
sls package

# to deploy
sls deploy

# aws to check progress of deploy
aws -> cloudformation -> choose region -> click stack -> choose stack -> event tab

# upload to s3
must create uploads  folder
upload a .jpg file to s3 on AWS

# check lambda for invocation
![Alt text](image-6.png)

# check cloud watch logs for events triggered
add print(response) to the handler before the return statement for details to be sent to Cloudwatch

# deactivate the key when finished using

# to terminate
To nuke everything you can do 'rm ~/.aws/credentials' and then 'rm ~/.aws/config' on mac/linux

# provider info, overwrite defaults and define environment variables
provider:
  name: aws
  runtime: python3.9
# you can overwrite defaults here
  stage: dev
  region: us-east-1
# you can define service wide environment variables here
  environment:
    variable1: value1
  environment:
    S3_BUCKET_NAME: 'kat-cat-photos'


# creating an IAM role
in AWS -> Lambda -> select lambda function -> configuration -> permission

# google for IAM actions eg actions to access s3 
https://docs.aws.amazon.com/AmazonS3/latest/userguide/list_amazons3.html

# in yml file under provider, package, deploy and check on lambda -> configure -> permissions
  iamRoleStatements:
    - Effect: Allow
      Action:
        - s3:GetObject
      Resource:
        - "arn:aws:s3:::${self:provider.environment.S3_BUCKET_NAME}/uploads/*"


# requirement for docker use???
sls plugin install -n serverless-python-requirements

# to install packages locally, check cloudwatch for any modules it may also need in requirements.txt
pip install -r requirements.txt

# ensure lambda runtime setting set
AWS -> Lambda -> choose function -> runtime -> choose the same python version used to write

# make sure that Docker desktop app is open and running before you package and deploy
npm install
sls package
sls deploy

# to force deployment
sls deploy --force