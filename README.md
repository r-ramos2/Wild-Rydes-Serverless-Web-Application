# Wild-Rydes-Serverless-Web-Application

In this tutorial, you will create a simple serverless web application that enables users to request unicorn rides from the Wild Rydes fleet. The application will present users with an HTML-based user interface for indicating the location where they would like to be picked up and will interact with a RESTful web service on the backend to submit the request and dispatch a nearby unicorn. The application will also provide facilities for users to register with the service and log in before requesting rides.

## Prerequisites

To complete this tutorial, you will need an AWS account, an account with ArcGIS to add mapping to your app, a text editor, and a web browser. If you don't already have an AWS account, you can follow the Setting Up Your AWS Environment getting started guide for a quick overview.

## Application architecture

The application architecture uses AWS Lambda, Amazon API Gateway, Amazon DynamoDB, Amazon Cognito, and AWS Amplify Console. Amplify Console provides continuous deployment and hosting of the static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser. JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway. Amazon Cognito provides user management and authentication functions to secure the backend API. Finally, DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.

## Modules

This tutorial is divided into five modules. Each module describes a scenario of what we're going to build and step-by-step directions to help you implement the architecture and verify your work.

### Host a Static Website (15 minutes)

Configure AWS Amplify to host the static resources for your web application with continuous deployment built in.

1. Sign in to the AWS Management Console.
2. In the console search bar at the top of the page, search for **Amplify**.
3. Choose **Get started** under Deploy.
4. Choose **Host web app**.
5. Connect your code repository service (GitHub) and choose **Continue**.
6. Choose your repository from the list.
7. Choose your branch (usually `main` or `master`) from the list.
8. Choose **Next**.
9. Accept all default build settings by choosing **Next**.
10. Review your changes and choose **Save and deploy**.

### Manage Users (30 minutes)

Create an Amazon Cognito user pool to manage your users' accounts.

1. Sign in to the AWS Management Console.
2. In the console search bar at the top of the page, search for **Cognito**.
3. On the Cognito dashboard, choose **Manage User Pools**.
4. Choose **Create a user pool**.
5. Enter a name for your user pool (e.g., `WildRydes`).
6. Choose **Review defaults**.
7. On the navigation menu on the left side of the page, choose **App clients** under General settings.
8. Choose **Add an app client**.
9. Enter a name for your app client (e.g., `WildRydesWebApp`).
10. Uncheck all options under Auth Flows Configuration.
11. Choose **Create app client**.

### Build a Serverless Backend (30 minutes)

Build a backend process for handling requests for your web application.

1. Sign in to the AWS Management Console.
2. In the console search bar at the top of the page, search for **Lambda**.
3. On the Lambda dashboard, choose **Create function**.
4. Choose **Author from scratch**.
5. Enter a name for your function (e.g., `RequestUnicorn`).
6. For Runtime, choose `Node.js`.
7. Expand Change default execution role and choose Use an existing role.
8. From Existing role drop-down list choose `WildRydesLambda`.

### Deploy a RESTful API (15 minutes)

Use Amazon API Gateway to expose the Lambda function you built in the previous module as a RESTful API.

### Terminate Resources

Clean up resources created during this tutorial by following these steps:

1. Sign in to the AWS Management Console.
2. In the console search bar at the top of the page, search for each service used in this tutorial (Amplify Console, Cognito, DynamoDB, Lambda) one at a time.
3. For each service:
    1. Navigate to its dashboard.
    2. Find the resources you created during this tutorial.
    3. Follow the service-specific instructions to delete the resources.
