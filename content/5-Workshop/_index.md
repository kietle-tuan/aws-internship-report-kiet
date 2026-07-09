---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b>5. </b> "
---

# 5. Workshop

## Workshop Overview

This section presents the workshop content related to my internship topic: **AWS Cloud Computing**.

The workshop was based on the final project **AWS Stock Analyzer**, a serverless application that supports stock data collection, processing, analysis, and dashboard display using AWS services.

My role in this project was **QA Tester**. Therefore, this section focuses on understanding the system architecture, checking the application flow, testing the dashboard, reviewing backend behavior, and recording issues found during testing.

I did not independently deploy the whole AWS infrastructure. My main contribution was testing and documenting the system behavior based on the deployed application and available evidence.

---

## Project Name

**AWS Stock Analyzer**

---

## Project Architecture

The project used an **AWS Serverless architecture**.

The main services and components included:

- **Yahoo Finance API** for stock market data source.
- **Amazon S3** for storing raw stock data.
- **Amazon SQS** for queue-based asynchronous processing.
- **AWS Lambda Ingestion** for collecting stock data.
- **AWS Lambda Processing** for processing and analyzing data.
- **Amazon DynamoDB** for storing processed stock analysis results.
- **AWS KMS** for encryption support.
- **Amazon Cognito** for user authentication.
- **Amazon API Gateway** for API access.
- **Amazon S3 Static Hosting** for frontend hosting.
- **Amazon CloudFront** for content delivery.
- **AWS WAF** for frontend protection.
- **Amazon Bedrock** for AI-based analysis support.
- **Amazon CloudWatch** for logs and monitoring.

---

## Main System Flow

The main system flow was:

**User Login → Dashboard → Stock Analysis Request → Backend Processing → Result Display**

After logging in, the user could access the dashboard and submit a stock analysis request.

For example, during testing, the dashboard initially displayed stock information for **FPT**. I then selected another stock symbol, **VNM**, to check whether the system could process a new stock analysis request.

The expected backend flow was:

**Frontend → API Gateway → Lambda Ingestion → Yahoo Finance API → S3 → SQS → Lambda Processing → DynamoDB → Dashboard**

---

## Testing Focus

As a QA Tester, I focused on checking the following parts:

- Login process using Amazon Cognito.
- Dashboard display after successful login.
- Stock analysis request from the frontend.
- Backend processing flow.
- CloudWatch logs for checking system behavior.
- Error found during AI analysis using Amazon Bedrock.
- Fallback result when Bedrock quota was exceeded.

---

## Testing Result Summary

The basic application flow was working during testing.

The system allowed login, dashboard access, stock selection, and stock analysis request submission.

However, one issue was found during the AI analysis step. Amazon Bedrock returned a quota-related error: **Too many tokens per day, please trying again.**

Because of this issue, the system used a fallback mock confidence score of **68%**, which was lower than the expected threshold of **75%**.

The suggested fix is to request a quota increase for the Bedrock model, especially **Claude 3.5 v2**, and then retest the AI analysis function.

---

## Workshop Sections

This workshop section includes the following parts:

1. **Workshop Overview**
2. **Prerequisite**
3. **Why Choose This Structure**
4. **Testing Process**
5. **Security and Access Control**
6. **Testing Summary and Cleanup Notes**

---

## QA Tester Notes

This workshop helped me understand how an AWS serverless application can be structured and tested.

The most important part for me was not only checking whether the frontend worked, but also understanding how the backend services connected together.

Through the testing process, I learned how to record realistic test results, check CloudWatch logs, identify service quota issues, and document findings clearly in a project report.
