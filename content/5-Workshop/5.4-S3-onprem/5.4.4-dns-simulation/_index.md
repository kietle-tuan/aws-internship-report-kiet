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

During testing, the Bedrock service returned the following error:

```text
Too many tokens per day, please trying again.
