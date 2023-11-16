# Wild Rydes Serverless Web Application

Welcome to the Wild Rydes Serverless Web Application tutorial! This comprehensive guide will walk you through the process of creating a free, robust, and user-friendly serverless web application that enables users to request unicorn rides from the Wild Rydes fleet. By utilizing AWS services such as AWS Lambda, Amazon API Gateway, Amazon DynamoDB, Amazon Cognito, and AWS Amplify Console, you'll build a scalable, secure, and efficient application.

<img width="1427" alt="AUFHAIUFHAHDADALJDL" src="https://github.com/ocramos2/Wild-Rydes-Serverless-Web-Application/assets/90172092/2de1abf9-d3e3-4ebd-b91f-b1f8bff9f7d6">

Before you begin, ensure you have the following:

- An [AWS account](https://aws.amazon.com/): If you don't have one, you can sign up at https://aws.amazon.com/.
- An [ArcGIS account](https://www.arcgis.com/): To incorporate mapping functionality into your app, sign up at https://www.arcgis.com/.
- A text editor: For code editing and development.
- A web browser: For testing and interacting with your application.

## Step 1: Set up Code Repository

1. Open AWS Console, then search for CodeCommit.
2. Click on "Create repository."
3. For Repository name, use "wildrydes-site," then click "Create."

## Step 2: Configure CodeCommit and IAM Permissions

### Configure CodeCommit Repository:

1. Open AWS Console, then search for CodeCommit.
2. Click on Repositories in the left menu.
3. Click on the "wildrydes-site" repository.
4. Click on "Clone URL," then choose "Clone HTTPS."
5. Open CloudShell terminal.
6. Type "git clone" and paste the clone URL, then hit Enter.
7. Enter User name (your admin username) and Password (paste once) from before.
8. If successful, you should see an empty repository.
9. Keep CloudShell open for the next step.

### Copy Website Files to Repository:

1. Paste "aws s3 cp s3://wildrydes-us-west-2/WebApplication/1_StaticWebHosting/website ./ --recursive", ensuring the correct AWS Region, then hit Enter.
2. Paste "git add .", then hit Enter.
3. Paste "git commit -m "Initial commit" ", then hit Enter.
4. Enter the following credentials:
   - "git config --global user.email "youremail@gmail.com""
   - "git config --global user.name "youradminusername""
   - "git config --global user.password "yourpassword""
5. Paste "git push", then hit Enter.
6. Double-check by going back to the "wildrydes-site" repository, click on "Code," and verify CSS and js files.

## Step 3: Host Website with AWS Amplify

1. Open AWS Console, then search for Amplify.
2. Click on "New app," then select "Host web app," "AWS CodeCommit," and "Continue."
3. Choose "wildrydes-site" under Recently updated repositories, then click "Next."
4. Check the box to allow Amplify to automatically deploy all files hosted in your project root directory.
5. Click "Next," then "Deploy."
6. Wait for the Provision, Build, and Deploy checkmarks to turn green.
7. Under master, click on the new link to access the deployed website.

## Step 4: Implement User Registration and Login

1. Open AWS Console, then search for Amazon Cognito.
2. Click on "Create user pool."
3. Configure user pool settings and client ID, then click "Create user pool."
4. Save User pool ID and Client ID in a text editor.
5. Update CodeCommit's js file with User pool ID, Client ID, and current region, then commit changes.
6. After deployment, test the sign-in option and copy the authentication token to a text editor.

## Steps 5 and 6: Implement Ride Sharing Functionality and Data Storage

1. Open AWS Console, then search for DynamoDB.
2. Create a new table named "Rides" with a partition key "Rideid."
3. Copy the Amazon Resource Name from Table settings.

### Set Up IAM Role for Lambda:

1. Open AWS Console, then search for IAM Dashboard.
2. Create a role named "WildRydesLambda" with "AWSLambdaBasicExecutionRole" permissions.
3. Create an inline policy for DynamoDB write access.

### Create Lambda Function (RequestUnicorn):

1. Open AWS Console, then search for AWS Lambda Dashboard.
2. Create a new function named "RequestUnicorn" with the existing role "WildRydesLambda".
3. Update the function code with provided code and deploy.
4. Test the function with a configured test event.

### Verify DynamoDB:

1. Open DynamoDB, verify the presence of a new RideId under Items returned.

## Step 7: Configure API Gateway for Ride Sharing Functionality

1. Open AWS Console, then search for API Gateway.
2. Create a new API named "WildRydes" with a resource "/ride" and a POST method.
3. Configure the integration type as Lambda function and link to the "RequestUnicorn" function.
4. Deploy the API to a new stage named "dev" and note the Invoke URL.

### Update CodeCommit Configuration:

1. Open AWS Console, then search for CodeCommit.
2. Edit config.js and ride.html in the "wildrydes-site" repository.
3. Paste the Invoke URL from API Gateway.
4. Commit the changes.

### Final Steps:

1. Verify your ArcGIS account is logged in.
2. Refresh the WildRydes HTML page.

## Cleanup:

Empty and delete AWS Amplify, Amazon Cognito, Lambda, IAM, DynamoDB, API Gateway, CodeCommit, and CloudWatch.

## Acknowledgment

This tutorial is adapted from the [Build a Serverless Web Application with AWS Lambda, Amazon API Gateway, AWS Amplify, Amazon DynamoDB, and Amazon Cognito](https://aws.amazon.com/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/) tutorial provided by Amazon Web Services. We extend our gratitude to AWS for providing this valuable resource, which served as the foundation for the Wild Rydes Serverless Web Application tutorial.
