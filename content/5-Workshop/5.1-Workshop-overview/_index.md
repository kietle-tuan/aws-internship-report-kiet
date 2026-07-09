---
title: "Overview Project"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b>5.1 </b> "
---

# 5.1 OVERVIEW PROJECT

## AWS Stock Analyzer Project Overview

---

## 1. System Overview

The **AWS Stock Analyzer** system was built to support stock analysis using an AWS Serverless architecture.

The system collects stock market data from Yahoo Finance, processes the data through AWS services, calculates technical indicators, and displays the final analysis result on a dashboard for trader review.

The system does not send AI recommendations directly to customers immediately. Instead, the analysis result is reviewed by a trader before any recommendation is sent to customers by email.

---

## 2. Main Purpose

The main purpose of the system is to help analyze stock data more efficiently.

The system supports the following tasks:

- Collect stock market data from Yahoo Finance.
- Store raw stock data for checking and reprocessing.
- Calculate technical indicators such as RSI, MACD, MA, and Volume.
- Use Amazon Bedrock to support AI-based analysis.
- Store final analysis results in DynamoDB.
- Display stock analysis results on the dashboard.
- Allow traders to review and approve recommendations before sending them to customers.

This helps reduce manual analysis time and allows traders to monitor multiple stock symbols more easily.

---

## 3. Target Users

The target users of the system include:

- Individual investors who want stock analysis support.
- Beginners who need help understanding technical signals.
- Traders or financial consultants who need a dashboard to review stock recommendations before sending them to customers.

In this system, customers do not directly receive AI recommendations immediately. The trader reviews the result first to reduce risk before sending investment-related information.

---

## 4. Problem to Solve

Manual stock analysis can take time and may miss important technical signals, especially when traders need to follow many stock symbols at the same time.

The AWS Stock Analyzer system helps automate several steps:

- Collecting stock data from Yahoo Finance.
- Storing raw data for checking and reprocessing.
- Calculating technical indicators in the backend.
- Using AI to support analysis.
- Saving analysis results to DynamoDB.
- Allowing traders to review recommendations before sending email notifications.

---

## 5. My Role

In this workshop, my role was **QA Tester**.

My work focused on:

- Understanding the system overview.
- Reviewing the main project flow.
- Checking the deployed application.
- Testing stock analysis requests.
- Observing backend processing behavior.
- Recording issues found during testing.

I did not independently deploy the whole AWS infrastructure. My contribution focused mainly on testing, checking system behavior, and recording observations.
