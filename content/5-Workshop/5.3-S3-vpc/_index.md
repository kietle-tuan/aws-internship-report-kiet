---
title: "Why Choose This Structure"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b>5.3 </b> "
---

# 5.3 WHY CHOOSE THIS STRUCTURE

## Why These AWS Services Were Chosen

---

## 1. Overview

The architecture of the **AWS Stock Analyzer** project was selected based on four main criteria:

- Low cost
- Simple deployment
- Managed Service / Serverless architecture
- Good scalability

This structure is suitable for an academic project because it reduces infrastructure management work and allows the team to focus on the main project logic: collecting stock data, calculating technical indicators, using Amazon Bedrock for AI-supported analysis, and displaying results on the dashboard.

---

## 2. Cost Efficiency

Cost was one of the main reasons for choosing this architecture.

Services such as AWS Lambda, Amazon S3, Amazon SQS, DynamoDB, API Gateway, CloudFront, and Amazon SES are suitable for a pay-as-you-go model.

The system does not need to run a server continuously, so the initial cost is lower than using an EC2 server running 24/7.

Examples:

- Lambda only generates cost when requests are triggered.
- SQS cost depends on the number of messages.
- DynamoDB cost depends on storage and read/write usage.
- S3 cost depends on the amount of data stored.
- CloudFront helps distribute frontend content without maintaining a separate web server.

This makes the system more suitable for a student project with limited budget.

---

## 3. Serverless Simplicity

The project uses a serverless architecture to reduce system operation work.

Instead of manually configuring servers, installing runtime environments, managing scaling, updating operating systems, and monitoring server resources, the system uses AWS serverless services.

Main serverless components include:

| Service | Role in the Project |
|---|---|
| AWS Lambda | Runs backend logic |
| API Gateway | Provides API endpoints |
| Amazon S3 | Stores raw data and frontend static files |
| Amazon SQS | Handles message queue processing |
| DynamoDB | Stores analysis results |

Thanks to this structure, the team can focus more on project features instead of infrastructure management.

---

## 4. Managed Services

Most services in the architecture are AWS Managed Services.

This means AWS handles much of the infrastructure operation, maintenance, and availability.

Examples:

- Amazon Bedrock supports AI analysis without deploying a machine learning model manually.
- DynamoDB provides NoSQL storage without managing a database server.
- Amazon SQS provides message queue processing without building a queue system from scratch.
- Amazon SES supports email sending without configuring a mail server.
- AWS KMS helps manage encryption keys for data protection.

Using managed services helps reduce operational risk and makes the project easier to maintain.

---

## 5. Scalability

The architecture has good scalability because the system is divided into separate components.

Each component has a clear responsibility:

- Frontend hosting
- API request handling
- Data ingestion
- Message queue processing
- Data processing
- AI-supported analysis
- Result storage
- Dashboard display

When the number of stock symbols or users increases, the system can scale each part separately.

Examples:

- If many users send analysis requests at the same time, API Gateway and Lambda can handle multiple requests.
- If there is a large amount of stock data, SQS can queue messages for Processing Lambda.
- If more reports need to be stored, DynamoDB and S3 can scale with data volume.
- If many users access the dashboard, CloudFront can distribute frontend content faster.
- If more security is required, AWS WAF rules can be improved.

This structure helps the system expand more easily in the future.

---

## 6. Why Not Use Traditional Server Deployment

A traditional deployment using EC2 could also run the system, but it would require more manual management.

For example, the team would need to:

- Configure servers manually.
- Install and maintain runtime environments.
- Manage operating system updates.
- Set up scaling manually.
- Monitor server performance.
- Handle more infrastructure-related issues.

Because this project focuses on AWS Cloud Computing and stock analysis workflow, using serverless and managed services was more suitable.

---

## 7. Future Improvements

The architecture can be improved in the future in several directions.

### 7.1 Expand Data Sources

Currently, the system uses Yahoo Finance as the main data source.

In the future, more data sources can be added to compare prices, improve reliability, and support more near-real-time data.

---

### 7.2 Improve AI Analysis

Amazon Bedrock currently analyzes based on calculated technical indicators.

In the future, the system can add more indicators such as:

- Bollinger Bands
- Stochastic
- ADX
- ATR

More input data can help the AI generate more useful analysis.

---

### 7.3 Add Real-Time Alerts

The system can add alerts when:

- Stock price reaches a specific threshold.
- RSI enters overbought or oversold zones.
- MACD changes direction.
- A strong buy or strong sell signal appears.

These alerts can be sent to traders or customers after review.

---

### 7.4 Improve User Management

The system can improve user roles for:

- Admin
- Trader
- Customer

For example:

- Admin manages users.
- Trader reviews and approves recommendations.
- Customer receives reports or views approved recommendations.

---

### 7.5 Improve Security

The system can be improved with more security features, such as:

- CloudWatch Alarm
- AWS WAF advanced rules
- IP request limitation
- CloudTrail audit logs
- KMS encryption for sensitive data

These improvements can help protect the system better.

---

### 7.6 Optimize Cost and Performance

Cost and performance can be optimized by:

- Reducing unnecessary Bedrock calls.
- Reducing input tokens.
- Caching stock data.
- Adjusting Lambda timeout and memory.
- Monitoring cost with AWS Cost Explorer.

This helps the system run more efficiently.

---

### 7.7 Improve Dashboard

The dashboard can be improved by adding:

- More visual charts
- Stock symbol filters
- Approval status filters
- Confidence score display
- Timeframe filter
- Analysis history

This would make the dashboard easier to use and review.

---

### 7.8 Add CI/CD

In the future, CI/CD can be added using GitHub Actions or AWS CodePipeline.

This would help automate build, test, and deployment for frontend and backend updates.

---

### 7.9 Improve Scaling and Reliability

When the number of users and stock symbols increases, the system can be improved by:

- Optimizing batch processing.
- Increasing Lambda concurrency.
- Configuring Dead Letter Queue for SQS.
- Setting retry policies clearly.
- Improving monitoring and alerting.

---

### 7.10 Add Accuracy Evaluation

After the system gives a recommendation, the actual stock result can be stored and compared later.

This can help evaluate whether the recommendation was correct or not.

The result can be used to improve the scoring logic and analysis quality.

---

## 8. Conclusion

The AWS Stock Analyzer architecture was chosen because it is cost-effective, simple to deploy, mostly serverless, and scalable.

Using AWS managed services helps reduce infrastructure management work and allows the team to focus more on the business logic of the project.

This structure is suitable for a student internship project and can be improved further if the system needs to support more users, more stock symbols, or more advanced analysis features.
