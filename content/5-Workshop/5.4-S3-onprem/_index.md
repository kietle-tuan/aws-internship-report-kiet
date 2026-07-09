---
title: "Testing Process"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b>5.4 </b> "
---

# 5.4 TESTING PROCESS

## AWS Stock Analyzer Testing

---

## 1. Overview

This section presents the testing process of the **AWS Stock Analyzer** project.

The application was accessed through the deployed CloudFront URL. The testing focused on checking login, dashboard display, stock analysis request, backend processing flow, data storage, CloudWatch logs, and the Bedrock quota issue.

In this part, my role was **QA Tester**. I checked the system from the user and tester perspective and recorded testing observations.

---

## 2. Deployed Application

The deployed application was accessed through CloudFront:

https://d3k9qj467czrvg.cloudfront.net/

The application title was:

**Stock Analyzer | Phân Tích Cổ Phiếu Thông Minh**

The system is an AWS Stock Analyzer dashboard used to analyze stock data and support trader review.

![Cognito Login](./3.PNG)

---

## 3. Main Testing Areas

| Testing Area | Description |
|---|---|
| Login Testing | Check Cognito login and user access |
| Dashboard Checking | Check whether stock data is displayed correctly |
| Stock Analysis Request | Submit a stock symbol and observe the response |
| Backend Flow Checking | Check S3, SQS, Lambda, and DynamoDB processing |
| CloudWatch Log Checking | Review Lambda logs to confirm processing behavior |
| Bedrock Issue Checking | Record quota/token issue during AI analysis |

---

## 4. Testing Flow

The main testing flow was:

1. Access the CloudFront application URL.
2. Login using Cognito.
3. Open the dashboard.
4. Select a stock symbol for analysis.
5. Submit an analysis request.
6. Check whether backend processing runs correctly.
7. Verify S3, SQS, DynamoDB, and CloudWatch logs.
8. Record any issue found during testing.

![Stock Analysis Request](./4.PNG)

---

## 5. Backend Processing Verification

After submitting the stock analysis request, the backend processing flow was checked.

The expected backend flow was:

1. Ingestion Lambda calls Yahoo Finance API.
2. Raw stock data is stored in Amazon S3.
3. A message is sent to Amazon SQS.
4. Processing Lambda is triggered.
5. Processing Lambda reads the data and calculates technical indicators.
6. Final result is stored in DynamoDB.
7. Dashboard displays the updated analysis result.

The SQS queue showed zero remaining messages after processing, which means the message had already been handled by Processing Lambda.

---

## 6. Issue Summary

During testing, an issue occurred in Amazon Bedrock.

The error message was related to token quota:

`Too many tokens per day, please trying again.`

Because of this issue, Bedrock could not complete the AI analysis normally. The system used fallback mock data with a confidence score of **68%**.

This issue was recorded and should be reviewed by the development team.

![Backend Flow and Bedrock Issue](./5.PNG)

---

## 7. Summary of Testing Result

| Task | Status |
|---|---|
| Accessed deployed CloudFront application | Completed |
| Logged in through Cognito | Completed |
| Checked dashboard display | Completed |
| Submitted stock analysis request | Completed |
| Checked backend processing flow | Completed |
| Checked DynamoDB result | Completed |
| Checked CloudWatch logs | Completed |
| Recorded Bedrock quota issue | Completed |

---

## 8. Conclusion

The testing process showed that the main application flow worked from frontend request to backend processing and dashboard display.

However, the Bedrock quota issue affected the AI analysis result. From the QA Tester perspective, this was an important issue to record because it impacted the final recommendation flow.
