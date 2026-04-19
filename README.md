# AWS Integrated GRC Platform - Capstone Project

## Project Overview
This project is a comprehensive **Governance, Risk, and Compliance (GRC)** platform deployed on AWS. It demonstrates an automated, secure, and scalable architecture designed to manage risk assessments, compliance monitoring, and immutable evidence collection using Industry Best Practices.

## 🚀 Technical Achievements
- **Infrastructure as Code (IaC)**: Fully deployed via AWS CloudFormation.
- **Automated Validation**: Successfully passed all **22 automated integration tests** validating risk scoring and compliance logic.
- **Data Security**: Implemented **AES-256 encryption-at-rest** across RDS and S3 using **AWS KMS**.
- **Audit Readiness**: Configured S3 Versioning and CloudWatch Logs Export for tamper-proof evidence collection.

## 🏗️ Architecture Components
- **Relational Database**: Amazon RDS (MySQL 8.0) for structured GRC records and policy management.
- **NoSQL Storage**: Amazon DynamoDB for high-velocity Risk Registers and Compliance Status tracking.
- **Evidence Locker**: Amazon S3 buckets with Versioning and Public Access Block enabled.
- **Identity & Security**: IAM LabRole integration with KMS-managed encryption keys.

## 🛠️ Deployment Summary
The infrastructure was deployed in the `us-east-1` region using the following environment configuration:

- **Environment Name**: `grc-imaab-capstone`
- **Database Endpoint**: `://amazonaws.com`
- **Primary Technical Control**: NIST 800-53 & ISO 27001 aligned encryption and logging.

## 📋 Compliance & Audit Evidence
As part of the Audit & Evidence module, the following controls were implemented and verified:
1. **Encryption**: All data in the RDS instance `grc-imaab-capstone-db` is encrypted via KMS.
2. **Immutability**: S3 buckets `grc-config-bucket-358604343131` and `grc-cloudtrail-logs-358604343131` were provisioned to serve as secure evidence repositories.
3. **Monitoring**: Continuous configuration monitoring via AWS Config and audit logging via CloudWatch.

## 🧪 Validation Results
Successfully executed `test_cases.py` with the following results:
- **Total Tests**: 22
- **Status**: PASSED (OK)
- **Coverage**: Risk Scoring, Compliance Percentages, and Data Validation Logic.

## Author
**Abimbola Olowoporoku**  
GRC208 Capstone Project  
AWS Academy Learner Lab  
April 2026
