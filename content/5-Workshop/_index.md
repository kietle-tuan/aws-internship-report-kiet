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

The system returned the following error:

```text
Too many tokens per day, please trying again.
