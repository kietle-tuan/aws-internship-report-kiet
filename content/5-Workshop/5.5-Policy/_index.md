---
title: "Security and Access Control"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b>5.5 </b> "
---

# 5.5 Security and Access Control

## Overview

In the **AWS Stock Analyzer** project, security and access control were important because the system included user login, API requests, stock data processing, database storage, and AI analysis.

This section explains the security-related services used in the architecture and the points that should be checked from a QA Tester perspective.

---

## Main Security Components

The project used several AWS services to support security and access control:

- **Amazon Cognito** for user authentication.
- **API Gateway** to manage API access from the frontend.
- **AWS WAF** to protect the frontend from common web attacks.
- **Amazon CloudFront** to deliver the frontend securely.
- **AWS KMS** to support data encryption.
- **IAM Roles and Policies** to control service permissions.
- **CloudWatch Logs** to support monitoring and troubleshooting.

---

## Cognito Authentication

Amazon Cognito was used to manage user login.

During testing, I checked whether the login page worked correctly and whether the user could access the dashboard after successful authentication.

The expected behavior was:

- Users must log in before accessing the dashboard.
- Invalid login information should not allow access.
- After login, the user should be redirected to the dashboard.

---

## API Gateway Access Control

API Gateway was used as the entry point between the frontend and backend services.

From the testing perspective, the API should only accept valid requests from the application. The request should then be sent to the backend Lambda functions for processing.

The main checking points were:

- Whether the frontend could send a request to the API.
- Whether the API could trigger the correct backend function.
- Whether failed requests could be identified through logs.

---

## IAM Roles and Permissions

IAM roles and policies were used to control what each AWS service could access.

For example:

- Lambda Ingestion needed permission to write raw data to S3.
- Lambda Processing needed permission to read messages from SQS.
- Lambda Processing needed permission to write processed data to DynamoDB.
- CloudWatch permission was needed for logging.

Using IAM roles helps avoid giving unnecessary permissions to services.

---

## Data Protection

The project architecture included data storage in Amazon S3 and DynamoDB.

AWS KMS was included to support encryption and protect stored data.

The expected security design was:

- Raw stock data should be stored securely in S3.
- Processed results should be stored securely in DynamoDB.
- Sensitive access should be controlled by IAM policies.
- Logs should be available in CloudWatch for checking and debugging.

---

## WAF and CloudFront Protection

The frontend was hosted using S3 Static Website Hosting and delivered through CloudFront.

AWS WAF was included to help protect the web application from common web attacks and unwanted traffic.

This improves the security of the public-facing frontend.

---

## QA Tester Notes

From the QA Tester perspective, I did not create all security policies myself. My focus was to understand and verify the security design of the system.

The main points I checked were:

- Users needed to log in before accessing the dashboard.
- The dashboard could send requests after login.
- Backend services used separated AWS components.
- Logs could be checked through CloudWatch.
- The architecture included security services such as Cognito, WAF, IAM, and KMS.

This helped confirm that the project considered basic security and access control requirements.
