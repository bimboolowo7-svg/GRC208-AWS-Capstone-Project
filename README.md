# AWS Integrated GRC Platform - Capstone Project

## Overview

The AWS Integrated GRC Platform is a comprehensive Governance, Risk, and Compliance solution designed for GRC208 students. This capstone project demonstrates how to build, deploy, and manage an enterprise-grade GRC platform using Amazon Web Services (AWS) and industry best practices.

---

## Before You Begin — Setting Up Your AWS Account

> **Important:** Every student must have an active AWS account before starting this project. Follow the steps below to get started for FREE.

### Step 1: Create a Free AWS Account

Go to [https://aws.amazon.com/free](https://aws.amazon.com/free) and click **Create a Free Account**. You will need:

- A valid email address
- A phone number for verification
- A credit or debit card (for identity verification only — you will NOT be charged if you stay within Free Tier limits)

Once registered, you automatically receive **12 months of AWS Free Tier** access, which covers everything needed for this project at **zero cost**.

### Step 2: Claim Your Free Student Credits

AWS offers multiple free credit programmes for students. Choose the one that applies to you:

| Programme | Credits | How to Apply | Best For |
|-----------|---------|--------------|----------|
| **AWS Educate** | Free sandbox + labs | [aws.amazon.com/education/awseducate](https://aws.amazon.com/education/awseducate) | All students (no credit card needed) |
| **AWS Academy** | $50–$100 credits | Ask your instructor if your institution is enrolled | Students at AWS Academy member schools |
| **AWS Free Tier** | 12 months free | Automatic on new account creation | All new AWS accounts |
| **AWS Activate** | Up to $1,000 credits | [aws.amazon.com/activate](https://aws.amazon.com/activate) | Students building startup/portfolio projects |

> **Recommended:** Sign up for both **AWS Educate** AND create a **Free Tier account**. Together, they give you more than enough resources to complete this entire capstone project.

### Step 3: What the Free Tier Covers for This Project

This entire capstone project runs comfortably within the AWS Free Tier limits. The table below shows the estimated usage versus what is free:

| AWS Service | Free Tier Allowance | Estimated Project Usage | Cost |
|-------------|--------------------|-----------------------|------|
| Amazon RDS MySQL | 750 hours/month | ~100 hours | **FREE** |
| AWS Lambda | 1,000,000 requests/month | ~10,000 requests | **FREE** |
| Amazon S3 | 5 GB storage | ~100 MB | **FREE** |
| Amazon DynamoDB | 25 GB + 25 WCU/RCU | Minimal | **FREE** |
| AWS CloudTrail | First trail free | 1 trail | **FREE** |
| Amazon CloudWatch | 10 custom metrics | Basic metrics | **FREE** |
| AWS Config | 1–2 rules | ~5 rules ($0.003/rule) | **~$0.01** |
| **Total Estimated Cost** | | | **$0 – $5/month** |

### Step 4: Set a Billing Alert (Mandatory)

Before deploying anything, set up a billing alert to avoid unexpected charges:

1. Log in to the [AWS Console](https://console.aws.amazon.com)
2. Go to **Billing Dashboard** > **Budgets** > **Create Budget**
3. Select **Cost Budget** and set the amount to **$10**
4. Add your email address to receive alerts
5. Click **Create Budget**

This ensures you will be notified immediately if costs ever approach $10, giving you time to review and clean up resources.

### Step 5: Enable MFA on Your Root Account

This is a security best practice and a GRC requirement:

1. Go to **IAM** > **Security credentials** in the AWS Console
2. Under **Multi-factor authentication (MFA)**, click **Assign MFA device**
3. Use an authenticator app (Google Authenticator or Authy)
4. Follow the on-screen steps to complete setup

> **Never use your root account for day-to-day work.** Create an IAM user with admin permissions for all project activities.

---

## Project Objectives

Students completing this capstone will learn to:

1. Design and implement a multi-tier application architecture on AWS
2. Integrate AWS native security and compliance services
3. Implement Infrastructure as Code (IaC) using CloudFormation
4. Develop serverless functions for compliance automation
5. Map technical controls to compliance frameworks
6. Create comprehensive compliance monitoring and reporting solutions
7. Implement audit logging and evidence collection
8. Manage risk assessment and mitigation strategies

## Key Features

### Governance Module
- Framework management (ISO 27001, NIST, PCI DSS, HIPAA, GDPR, SOC 2)
- Control library and mapping
- Policy management and tracking
- Role-based access control (RBAC)

### Risk Management Module
- Risk identification and assessment
- Risk scoring matrix (probability × impact)
- Mitigation strategy tracking
- Risk register and reporting

### Compliance Module
- Compliance status monitoring
- AWS Config integration
- Automated compliance checks
- Control implementation tracking
- Compliance reporting

### Audit & Evidence Module
- Centralized evidence repository (S3)
- Audit trail logging (CloudTrail)
- Assessment evidence collection
- Audit report generation

## Technology Stack

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Infrastructure** | AWS CloudFormation | Infrastructure as Code |
| **Compute** | AWS Lambda, ECS Fargate | Application and automation |
| **Database** | Amazon RDS MySQL | Relational data storage |
| **Data Storage** | Amazon S3 | Evidence and reports |
| **Cache/NoSQL** | Amazon DynamoDB | Compliance status and risks |
| **Encryption** | AWS KMS | Data encryption |
| **Monitoring** | AWS Config, Security Hub | Compliance monitoring |
| **Audit** | AWS CloudTrail | Audit logging |
| **Networking** | VPC, ALB, NAT Gateway | Network infrastructure |
| **Automation** | Python, AWS Lambda | Compliance automation |

## Project Structure

```
grc-capstone-project/
├── README.md                              # Project overview
├── DEPLOYMENT_GUIDE.md                    # Step-by-step deployment
├── architecture_design.md                 # Architecture documentation
├── cloudformation-network-stack.yaml      # Network infrastructure
├── cloudformation-database-stack.yaml     # Database infrastructure
├── lambda_compliance_monitor.py           # Compliance monitoring function
├── sample_data.sql                        # Sample data for testing
├── test_cases.py                          # Comprehensive test suite
├── deploy.sh                              # Automated deployment script
├── requirements.txt                       # Python dependencies
├── docs/
│   ├── AWS_SERVICES_GUIDE.md             # AWS services explanation
│   ├── COMPLIANCE_FRAMEWORKS.md          # Framework details
│   ├── BEST_PRACTICES.md                 # Implementation best practices
│   └── TROUBLESHOOTING.md                # Common issues and solutions
└── examples/
    ├── compliance_report_template.md     # Report template
    ├── risk_assessment_template.md       # Risk template
    └── audit_checklist.md                # Audit checklist
```

## Quick Start

### Prerequisites
- AWS Account with appropriate permissions
- AWS CLI v2 installed and configured
- Python 3.8+
- Git

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd grc-capstone-project

# Install Python dependencies
pip install -r requirements.txt

# Configure AWS credentials
aws configure

# Deploy infrastructure
./deploy.sh
```

### First Steps

1. **Review Architecture**: Read `architecture_design.md` to understand the system design
2. **Follow Deployment Guide**: Use `DEPLOYMENT_GUIDE.md` for step-by-step instructions
3. **Load Sample Data**: Execute `sample_data.sql` to populate the database
4. **Run Tests**: Execute `test_cases.py` to validate the deployment
5. **Explore AWS Console**: Navigate to AWS Console to see deployed resources

## AWS Services Used

### Core Services
- **AWS CloudFormation**: Infrastructure as Code for resource provisioning
- **Amazon VPC**: Isolated network environment with public/private subnets
- **Amazon RDS**: MySQL database for GRC data
- **Amazon S3**: Storage for evidence and compliance reports
- **AWS Lambda**: Serverless functions for compliance automation

### Security & Compliance Services
- **AWS Config**: Continuous monitoring of resource configurations
- **AWS Security Hub**: Centralized security findings and compliance
- **AWS CloudTrail**: API activity and audit logging
- **AWS IAM**: Identity and access management
- **AWS KMS**: Key management and encryption

### Monitoring & Alerting
- **Amazon CloudWatch**: Metrics, logs, and alarms
- **Amazon SNS**: Alert notifications
- **Amazon EventBridge**: Event-driven automation

## Compliance Frameworks Supported

The platform supports mapping to the following compliance frameworks:

- **ISO 27001:2022** - Information Security Management System
- **NIST Cybersecurity Framework** - Risk management and security controls
- **PCI DSS 3.2.1** - Payment Card Industry Data Security Standard
- **HIPAA** - Health Insurance Portability and Accountability Act
- **GDPR** - General Data Protection Regulation
- **SOC 2** - Service Organization Control Framework

## Architecture Diagram

```
┌─────────────────────────────────────────────────────────────┐
│                     AWS Account                              │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │                    VPC (10.0.0.0/16)                 │   │
│  │                                                       │   │
│  │  ┌─────────────────────────────────────────────┐    │   │
│  │  │        Public Subnets (ALB, NAT)            │    │   │
│  │  │  ┌──────────────────────────────────────┐   │    │   │
│  │  │  │   Application Load Balancer (ALB)    │   │    │   │
│  │  │  └──────────────────────────────────────┘   │    │   │
│  │  └─────────────────────────────────────────────┘    │   │
│  │                        ↓                             │   │
│  │  ┌─────────────────────────────────────────────┐    │   │
│  │  │      Private Subnets (ECS, RDS)             │    │   │
│  │  │  ┌──────────────────────────────────────┐   │    │   │
│  │  │  │  ECS Fargate (GRC Application)       │   │    │   │
│  │  │  └──────────────────────────────────────┘   │    │   │
│  │  │                                              │    │   │
│  │  │  ┌──────────────────────────────────────┐   │    │   │
│  │  │  │  RDS MySQL (GRC Database)           │   │    │   │
│  │  │  └──────────────────────────────────────┘   │    │   │
│  │  └─────────────────────────────────────────────┘    │   │
│  │                                                       │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
│  ┌──────────────────────────────────────────────────────┐   │
│  │              AWS Native Services                      │   │
│  │  ┌──────────────┐  ┌──────────────┐  ┌────────────┐ │   │
│  │  │ AWS Config   │  │ Security Hub │  │ CloudTrail │ │   │
│  │  └──────────────┘  └──────────────┘  └────────────┘ │   │
│  │  ┌──────────────┐  ┌──────────────┐  ┌────────────┐ │   │
│  │  │ Lambda       │  │ DynamoDB     │  │ S3         │ │   │
│  │  └──────────────┘  └──────────────┘  └────────────┘ │   │
│  └──────────────────────────────────────────────────────┘   │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

## Data Flow

```
AWS Resources
    ↓
AWS Config (Compliance Status)
    ↓
Lambda Function (Compliance Monitor)
    ↓
DynamoDB (Compliance Status Table)
    ↓
RDS Database (GRC Platform)
    ↓
S3 (Evidence & Reports)
    ↓
CloudWatch (Monitoring)
    ↓
SNS (Alerts)
```

## Testing

The project includes comprehensive test cases covering:

- Compliance monitoring functionality
- Risk assessment and scoring
- Data validation
- Database operations
- Framework mapping
- Audit logging
- Report generation
- Integration workflows

### Run Tests

```bash
# Run all tests
python3 test_cases.py

# Run with verbose output
python3 -m unittest test_cases -v

# Run specific test class
python3 -m unittest test_cases.TestComplianceMonitoring -v
```

## Deployment

### Automated Deployment

```bash
# Make script executable
chmod +x deploy.sh

# Run deployment script
./deploy.sh
```

### Manual Deployment

Follow the step-by-step instructions in `DEPLOYMENT_GUIDE.md`

## Configuration

### Environment Variables

Create a `.env` file with the following variables:

```bash
AWS_REGION=us-east-1
AWS_ACCOUNT_ID=123456789012
DB_HOST=grc-capstone-db.xxxxx.us-east-1.rds.amazonaws.com
DB_PORT=3306
DB_NAME=grcdb
DB_USER=grcadmin
DB_PASSWORD=SecurePassword123!
```

## Documentation

- **DEPLOYMENT_GUIDE.md**: Complete step-by-step deployment instructions
- **architecture_design.md**: System architecture and design decisions
- **docs/AWS_SERVICES_GUIDE.md**: Detailed explanation of AWS services
- **docs/COMPLIANCE_FRAMEWORKS.md**: Compliance framework details
- **docs/BEST_PRACTICES.md**: Implementation best practices
- **docs/TROUBLESHOOTING.md**: Common issues and solutions

## Learning Outcomes

Upon completing this capstone, students will be able to:

1. Design scalable cloud architectures for GRC applications
2. Implement AWS native security and compliance services
3. Write Infrastructure as Code using CloudFormation
4. Develop serverless applications with AWS Lambda
5. Implement comprehensive audit logging and monitoring
6. Map technical controls to compliance frameworks
7. Create automated compliance checking and reporting
8. Manage cloud security and governance

## Best Practices Implemented

- **Infrastructure as Code**: All infrastructure defined in CloudFormation
- **Security**: Encryption at rest and in transit, least privilege access
- **High Availability**: Multi-AZ deployment with load balancing
- **Monitoring**: Comprehensive CloudWatch metrics and alarms
- **Automation**: Serverless functions for compliance automation
- **Audit Trail**: Complete audit logging with CloudTrail
- **Disaster Recovery**: Automated backups and recovery procedures
- **Cost Optimization**: Use of serverless and managed services

## Troubleshooting

For common issues and solutions, see `docs/TROUBLESHOOTING.md`

## Support

For questions or issues:
1. Check the troubleshooting guide
2. Review AWS documentation
3. Check CloudWatch logs
4. Review CloudFormation events

## References

- AWS GRC Documentation: https://docs.aws.amazon.com/grc/
- AWS Security Best Practices: https://aws.amazon.com/security/best-practices/
- AWS Config User Guide: https://docs.aws.amazon.com/config/
- AWS Lambda Developer Guide: https://docs.aws.amazon.com/lambda/
- AWS CloudFormation User Guide: https://docs.aws.amazon.com/cloudformation/

## License

This project is provided as educational material for GRC208 students.

## Acknowledgments

This project incorporates best practices from:
- AWS Security Reference Architecture
- NIST Cybersecurity Framework
- ISO 27001:2022 Standard
- AWS Well-Architected Framework

## Version History

- **v1.0** (March 2026): Initial release
  - Core GRC platform
  - AWS Config integration
  - Compliance monitoring
  - Risk assessment
  - Audit logging

## Author

Designed, Developed and Maintained by:

**Aminu Idris**
AMCPN Founder | International Cybersecurity and Digital Forensics Academy (ICDFA)

| Credential | Detail |
|------------|--------|
| **Certifications** | CCNA, CompTIA Security+, CEH, OSCP, CISSP, AWS Security Specialist |
| **Role** | Cybersecurity Educator & Mentor |
| **Organisation** | International Cybersecurity and Digital Forensics Academy (ICDFA) |
| **Title** | AMCPN Founder |

> *"Empowering the next generation of cybersecurity and GRC professionals through practical, hands-on education."*

## Contact

For questions about this capstone project, reach out through the International Cybersecurity and Digital Forensics Academy (ICDFA).

---

**Last Updated**: March 2026
**Status**: Production Ready
**Maintenance**: Actively Maintained
**Maintained by**: Aminu Idris — ICDFA
