---
title: "Testing Summary and Cleanup Notes"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b>5.6 </b> "
---

# 5.6 Testing Summary and Cleanup Notes

## Overview

This section summarizes the testing process and cleanup notes for the **AWS Stock Analyzer** workshop.

Because my role in the project was **QA Tester**, this section does not describe that I deployed or removed the full AWS infrastructure by myself. Instead, it focuses on what was tested, what was observed, and what should be checked after testing.

---

## Testing Summary

During the workshop testing process, I checked the main user flow and backend processing flow of the AWS Stock Analyzer project.

The main testing activities included:

- Logging in to the system using Amazon Cognito.
- Checking the dashboard after successful login.
- Observing the initial stock information displayed on the dashboard.
- Selecting another stock symbol for analysis.
- Submitting a stock analysis request.
- Checking whether the backend flow was triggered.
- Reviewing CloudWatch logs to identify system behavior and errors.
- Recording the Bedrock quota issue found during testing.

---

## Main Flow Tested

The main flow tested in this workshop was:

**Login → Dashboard → Stock Analysis Request → Backend Processing → Result Display**

The backend architecture included several AWS services:

- Amazon S3 for storing raw stock data.
- Amazon SQS for message queue processing.
- AWS Lambda for ingestion and processing.
- Amazon DynamoDB for storing processed results.
- Amazon CloudWatch for logs and monitoring.
- Amazon Bedrock for AI-based analysis.

---

## Issue Found During Testing

During testing, the main issue found was related to **Amazon Bedrock quota**.

The system returned the following error: **Too many tokens per day, please trying again.**

Because of this quota limitation, the AI analysis step could not be completed normally.

The system used a fallback mock result with a confidence score of **68%**, which was lower than the expected threshold of **75%**.

---

## Suggested Follow-up Action

To fix the Bedrock issue, the team should request a quota increase for the Bedrock model used in the project.

The suggested model quota to request is:

**Claude 3.5 v2**

After the quota is increased, the stock analysis function should be tested again to confirm that the AI-generated analysis result can be returned successfully.

---

## Cleanup Notes

If this project is tested in a real AWS account, unused resources should be reviewed after testing to avoid unnecessary cost.

The team should check:

- Unused S3 objects or test data.
- Unused SQS messages or queues.
- Test records in DynamoDB.
- Lambda test versions or unused functions.
- CloudWatch logs and log retention settings.
- API Gateway test stages if no longer used.
- CloudFront or WAF configurations if they were created only for testing.

---

## Report Cleanup Notes

For the GitHub workshop report, old template content should not be kept if it does not match the AWS Stock Analyzer project.

The old sample sections related to unrelated S3, VPC, Policy, or Cleanup labs should be replaced with content that matches this project.

In this report, the workshop sections were updated to focus on:

- AWS Stock Analyzer architecture.
- Testing process.
- Security and access control.
- Bedrock issue and suggested fix.
- QA testing summary.

---

## QA Tester Notes

From the QA Tester perspective, the testing process helped identify that the basic system flow was working, but the AI analysis feature was affected by a Bedrock quota limitation.

The issue was recorded clearly so that the development team could review and fix it later.

This is a realistic result for the internship report because it shows not only successful testing steps, but also an actual issue found during the testing process.
