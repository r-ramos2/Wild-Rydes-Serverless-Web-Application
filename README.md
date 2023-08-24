# Wild-Rydes-Serverless-Web-Application

Welcome to the Wild Rydes Serverless Web Application tutorial! This comprehensive guide will walk you through the process of creating a robust and user-friendly serverless web application that enables users to request unicorn rides from the Wild Rydes fleet. By utilizing AWS services such as AWS Lambda, Amazon API Gateway, Amazon DynamoDB, Amazon Cognito, and AWS Amplify Console, you'll build a scalable, secure, and efficient application.

## Prerequisites

Before you begin, ensure you have the following:

- An AWS account: If you don't have one, you can sign up at https://aws.amazon.com/.
- An ArcGIS account: To incorporate mapping functionality into your app, sign up at https://www.arcgis.com/.
- A text editor: For code editing and development.
- A web browser: For testing and interacting with your application.

If you're new to AWS, we recommend reviewing the "Setting Up Your AWS Environment" guide for a quick introduction.

## Application Architecture

Our application leverages a powerful combination of AWS services:

- **AWS Lambda**: Serverless computing for executing code without provisioning or managing servers.
- **Amazon API Gateway**: Create, deploy, and manage APIs for serverless backends.
- **Amazon DynamoDB**: A NoSQL database for storing data in a scalable and flexible manner.
- **Amazon Cognito**: User management and authentication service to secure your backend.
- **AWS Amplify Console**: Continuous deployment and hosting for your web resources.

This architecture ensures that your application is highly available, scalable, and secure.

## Tutorial Modules

This tutorial is organized into five comprehensive modules, each addressing a key aspect of building your Wild Rydes Serverless Web Application. By following these modules, you'll progressively build your application with detailed step-by-step instructions.

### Module 1: Host a Static Website

In this module, you'll configure AWS Amplify to host your static web resources.

1. Sign in to the AWS Management Console.
2. Search for **Amplify** using the console search bar.
3. Choose **Get started** under Deploy.
4. Select **Host web app** and connect your code repository (e.g., GitHub).
5. Choose your repository and branch.
6. Configure build settings and review your changes.
7. Save and deploy your changes.

### Module 2: Manage Users

This module focuses on setting up Amazon Cognito to manage user accounts.

1. Sign in to the AWS Management Console.
2. Search for **Cognito** using the console search bar.
3. Access the Cognito dashboard and choose **Manage User Pools**.
4. Create a new user pool (e.g., `WildRydes`).
5. Review default settings and navigate to **App clients**.
6. Add a new app client (e.g., `WildRydesWebApp`).
7. Configure app client settings and create the app client.

### Module 3: Build a Serverless Backend

Here, you'll develop the backend process to handle ride requests.

1. Sign in to the AWS Management Console.
2. Search for **Lambda** using the console search bar.
3. Access the Lambda dashboard and choose **Create function**.
4. Choose **Author from scratch** and define a function name (e.g., `RequestUnicorn`).
5. Select `Node.js` as the runtime.
6. Use an existing role named `WildRydesLambda`.

### Module 4: Deploy a RESTful API

Expose your Lambda function as a RESTful API using Amazon API Gateway.

1. Sign in to the AWS Management Console.
2. Search for **API Gateway** using the console search bar.
3. Access the API Gateway dashboard and choose **Create API**.
4. Choose **HTTP API** and click **Build**.
5. Configure your API, create a resource, and define a method.
6. Integrate the method with your Lambda function.
7. Deploy the API to make it accessible.

### Module 5: Terminate Resources

Finally, learn how to clean up resources to avoid unnecessary costs.

1. Sign in to the AWS Management Console.
2. Search for each service used in the tutorial (Amplify Console, Cognito, DynamoDB, Lambda, API Gateway).
3. For each service:
   1. Access its dashboard.
   2. Locate tutorial-related resources.
   3. Follow service-specific instructions to delete resources.
