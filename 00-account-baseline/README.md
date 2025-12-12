# AWS Account Baseline

This document outlines the initial security, billing, and governance configurations applied
to the AWS account used for hands-on cloud architecture projects.

Establishing a strong account baseline is a critical first step to ensure cost control,
security, and operational visibility.

---

## Account Setup Overview

- Account purpose: Learning and portfolio development
- Primary region: us-east-1 (N. Virginia)
- Account structure: Single account with multiple isolated projects
- Billing model: AWS Free Tier with cost monitoring

---

## Root Account Security

The root account is secured and used only for account-level administrative tasks.

- Multi-Factor Authentication (MFA) enabled on root user
- Root user access keys not created
- Root account login restricted to billing and account configuration only

---

## IAM Configuration

- Dedicated administrator IAM user created for daily operations
- AdministratorAccess policy attached during learning phase
- MFA enabled on IAM admin user
- Root user avoided for all routine tasks

Future improvements:
- Transition to least-privilege IAM policies
- Use IAM roles for service access

---

## Billing and Cost Controls

To prevent unexpected charges, the following cost controls are configured:

- AWS Budgets enabled
- Monthly cost budget set to $5
- Email alerts triggered at threshold breaches
- Free Tier usage monitored regularly

---

## Logging and Monitoring

Account-level visibility is enabled to support security and troubleshooting.

- AWS CloudTrail enabled
- Multi-region trail configured
- Management events (read and write) captured
- CloudTrail logs stored in an encrypted S3 bucket

---

## Resource Governance

To support organization and cleanup:

- Consistent resource naming conventions applied
- Mandatory tagging strategy:
  - Project
  - Environment
  - Owner
  - Purpose
  - CostCenter
  - DeleteBy

---

## Cost Awareness and Cleanup

- All resources are reviewed after each lab
- Non-essential resources are terminated immediately after use
- DeleteBy tags used to avoid orphaned resources

---

## Why This Matters

This baseline reflects real-world AWS best practices and demonstrates:

- Security-first mindset
- Cost-conscious cloud usage
- Operational discipline
- Readiness for production environments

