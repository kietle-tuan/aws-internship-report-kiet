---
title: "Bedrock Quota Issue and Suggested Fix"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b>5.4.4 </b> "
---

# 5.4.4 Bedrock Quota Issue and Suggested Fix

## Overview

During the testing process, I found an issue related to the AI analysis step of the **AWS Stock Analyzer** project.

The project used **Amazon Bedrock** to support AI-based stock analysis. However, while testing the analysis request, the system returned a quota-related error from Bedrock.

This section records the issue, actual behavior, temporary fallback result, and suggested solution.

---

## Testing Objective

The objective of this test was to check whether the AI analysis function could return a valid result after the stock data was processed.

The main points checked were:

- Whether the system could call Amazon Bedrock.
- Whether the AI analysis response could be generated.
- Whether the dashboard could still display a result when Bedrock had an error.
- Whether the error could be identified through logs.

---

## Issue Found

During testing, the Bedrock service returned the following error: **Too many tokens per day, please trying again.**

This error showed that the Bedrock usage quota had been exceeded. Because of this, the system could not complete the AI analysis step normally.

---

## Actual Behavior

After the Bedrock quota error occurred, the system used a fallback result instead of a real AI-generated result.

The fallback result showed a **mock confidence score of 68%**.

This score was lower than the expected threshold of **75%**, so the result did not meet the confidence requirement.

---

## Testing Evidence

The following image shows the backend flow and the Bedrock quota issue found during testing.

![Backend Flow and Bedrock Issue](../5.PNG)

---

## Expected Result

The expected result was that Amazon Bedrock should return an AI-generated analysis result successfully.

The system should then display the final analysis result on the dashboard, including a confidence score that meets the required threshold if the analysis is reliable.

---

## Actual Result

The system could process the stock analysis request, but the AI analysis step could not be completed because of the Bedrock quota limitation.

As a result:

- Bedrock returned a quota error.
- The system used a fallback mock result.
- The confidence score was **68%**.
- The score was below the required threshold of **75%**.

---

## Suggested Fix

To fix this issue, the AWS account should request a quota increase for the Bedrock model used in the project.

The suggested action is to request quota for:

**Claude 3.5 v2**

After the quota is increased, the test should be performed again to confirm whether Bedrock can return a normal AI analysis result.

---

## QA Tester Notes

From the QA testing perspective, this issue was important because the main stock data flow could still work, but the AI analysis feature was limited by the Bedrock quota.

This was not a frontend issue. It was related to the service quota of Amazon Bedrock.

For the next test, the team should increase the Bedrock quota and then retest the analysis function to confirm that the AI result can be generated correctly.
