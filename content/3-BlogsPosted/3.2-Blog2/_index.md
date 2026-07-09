---
title: "Basic AWS Services"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b>3.2 </b> "
---

# BASIC AWS SERVICES

## 1. Overview

This blog summarizes several basic AWS services that I learned during the internship.

During the learning process, I mainly studied AWS through guided tutorials, AWS Study Group materials, and YouTube videos. My goal was to understand the basic purpose of each service before applying the knowledge to the final project **AWS Stock Analyzer**.

At this stage, my understanding was still at a beginner level, so this blog focuses on simple explanations rather than advanced AWS implementation.

---

## 2. AWS IAM

**IAM**, or Identity and Access Management, is used to manage users, roles, groups, and permissions in AWS.

IAM helps control who can access AWS resources and what actions they are allowed to perform.

### What I Learned

I learned that IAM is important because cloud systems need proper access control. Without suitable permissions, users may access resources they should not use, or they may not be able to use services needed for the project.

---

## 3. Amazon EC2

**Amazon EC2** provides virtual servers in the cloud.

EC2 can be used to run applications, backend services, or development environments.

### What I Learned

I learned that EC2 is one of the basic compute services in AWS. It allows users to create virtual machines instead of using physical servers.

Some related concepts I reviewed include:

- Instance type
- AMI
- Key pair
- Security group
- Public IP address

---

## 4. Amazon S3

**Amazon S3** is an object storage service.

It can be used to store files, images, static website files, logs, or other data objects.

### What I Learned

I learned that S3 uses buckets to store objects. It is useful for storing files in a cloud-based application.

I also learned that permissions are important when using S3 because files should not be made public unless necessary.

---

## 5. Amazon VPC

**Amazon VPC** allows users to create a private network environment in AWS.

It helps organize cloud resources inside a controlled network.

### What I Learned

I learned that VPC is related to networking in AWS. Although this topic was still difficult for me, I understood that VPC is important when building cloud systems because it controls how resources communicate.

---

## 6. Security Groups

**Security Groups** work like virtual firewalls for AWS resources such as EC2 instances.

They control inbound and outbound traffic.

### What I Learned

I learned that security groups are important for controlling which traffic can access a cloud resource.

For example, if a backend server is running on EC2, security group rules can control which ports are open and who can connect to the server.

---

## 7. Amazon CloudWatch

**Amazon CloudWatch** is used for monitoring AWS resources.

It can help collect logs, metrics, and system information.

### What I Learned

I learned that monitoring is important because it helps developers and teams observe application behavior.

CloudWatch can help identify problems such as errors, unusual system behavior, or performance issues.

---

## 8. Summary Table

| AWS Service | Main Purpose | My Understanding Level |
|---|---|---|
| IAM | Manage users, roles, and permissions | Basic |
| EC2 | Provide virtual servers | Basic |
| S3 | Store files and objects | Basic |
| VPC | Manage cloud networking | Beginner |
| Security Groups | Control network traffic | Basic |
| CloudWatch | Monitor logs and metrics | Basic |

---

## 9. Connection With Final Project

The services above helped me understand the general structure of a cloud-based application.

In the **AWS Stock Analyzer** project, my role was **QA Tester**, so I did not independently deploy the whole AWS infrastructure.

However, learning these AWS services helped me understand how the application could be supported by cloud components such as hosting, backend processing, storage, networking, and monitoring.

This knowledge also helped me check the project more clearly during manual testing.

---

## 10. Reflection

Learning AWS services was not easy at first because there are many services and technical terms.

I needed to review tutorials multiple times to understand the basic role of each service.

Although I still need more practice, this topic helped me build a basic foundation for understanding AWS Cloud Computing and the final project.

---

## 11. References

- [AWS Study Group](https://000001.awsstudygroup.com/vi/)
- [AWS Cloud Computing YouTube Playlist](https://www.youtube.com/playlist?list=PLahN4TLWtox3TSYFbN1DNX7NZgTVXNj3x)
