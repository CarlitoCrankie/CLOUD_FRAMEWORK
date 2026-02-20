# AWS WAF & CAF Assessment – Two-Tier Web Application Migration

## Overview

This repository contains a complete assessment of a two-tier web application migration from on-premises infrastructure to AWS, evaluated through the lenses of both the **AWS Well-Architected Framework (WAF)** and the **AWS Cloud Adoption Framework (CAF)**.

## Repository Structure

```
.
├── README.md                        ← You are here
├── aws_waf_caf_assessment.md        ← Full assessment report (Tasks 1–4 + Reflection)
└── architecture/
    └── architecture_description.md  ← Detailed architecture diagram and component breakdown
```

## Approach

### Step 1 – Workload Analysis (Task 1)
The existing on-premises architecture was decomposed into its constituent components (web server, database, networking, storage, security). Each component was evaluated for risks including single points of failure, absent backup strategies, flat networking, and missing encryption.

### Step 2 – WAF Pillar Evaluation (Task 2)
Each of the five WAF pillars (Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization) was applied systematically to the workload. For each pillar, one strength and one area for improvement were identified, and a specific AWS service recommendation was made. Findings are summarized in the assessment table within the main report.

### Step 3 – CAF Perspective Analysis (Task 3)
All six CAF perspectives (Business, People, Governance, Platform, Security, Operations) were used to evaluate organizational readiness for the migration. Each perspective received a ~200-word analysis identifying key actions and enablers required for a successful transition.

### Step 4 – Improved Architecture Design (Task 4)
A revised target architecture was designed from scratch to address all five WAF pillars. The architecture includes:
- Amazon CloudFront + AWS WAF at the edge
- Multi-AZ VPC with public, private application, and private database subnets
- Application Load Balancer with Auto Scaling Group across two AZs
- Amazon ElastiCache for Redis (read caching)
- Amazon RDS Multi-AZ with automated backups and Secrets Manager integration
- Comprehensive observability via CloudWatch, CloudTrail, GuardDuty, and AWS Config

## Key AWS Services Used

| Category | Services |
|---|---|
| Networking | Amazon VPC, ALB, Route 53, NAT Gateway, AWS WAF |
| Compute | Amazon EC2, Auto Scaling, AWS Systems Manager |
| Database | Amazon RDS (Multi-AZ), ElastiCache for Redis |
| Storage | Amazon S3, AWS Backup |
| Security | AWS KMS, Secrets Manager, GuardDuty, CloudTrail, ACM |
| Observability | Amazon CloudWatch, AWS Config, AWS Trusted Advisor |
| Delivery | Amazon CloudFront, AWS CodePipeline |
| Cost Management | AWS Cost Explorer, AWS Budgets, Savings Plans |

## Frameworks Applied

- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Cloud Adoption Framework](https://aws.amazon.com/cloud-adoption-framework/)

## Submission

Submitted via Microsoft Forms as a GitHub repository link per the lab instructions.
