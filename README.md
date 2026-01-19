# AWS Cloud Security Labs

This repository contains **hands-on labs and documentation** for a 30-day AWS Cloud Security challenge.  
Each day focuses on a specific security concept and demonstrates how to implement it safely and professionally in AWS.

The goal is to create **production-style security artifacts**, showing best practices in identity, networking, logging, encryption, threat detection, and governance.

---

## Repository Structure

phase-1-identity-network-visibility/
├── day-01-iam-core/
│   ├── iam-core.md              # Day 1 deliverable
│   └── screenshots/             # Screenshots of IAM setup
├── day-02-iam-advanced/
│   ├── iam-advanced.md          # Day 2 deliverable
│   └── screenshots/             # Policy conditions, Policy Simulator, Access Analyzer
├── day-03-vpc-core/
│   ├── vpc-core.md              # Day 3 deliverable
│   └── screenshots/
├── day-04-iam-vpc-control/
│   ├── iam-vpc-control.md       # Day 4 deliverable
│   └── screenshots/
├── day-05-vpc-traffic/
│   ├── vpc-traffic.md           # Day 5 deliverable
│   └── screenshots/
├── day-06-logging/
│   ├── logging.md               # Day 6 deliverable
│   └── screenshots/
├── day-07-encryption/
│   ├── encryption.md            # Day 7 deliverable
│   └── screenshots/
├── day-08-secure-access-lab/
│   ├── ssm-lab.md               # Day 8 deliverable
│   └── screenshots/
├── day-09-review/
│   ├── review.md                # Day 9 deliverable
│   └── screenshots/
phase-2-managed-security-workloads/
├── day-10-inspector/
│   ├── inspector.md
│   └── screenshots/
├── day-11-edge-security/
│   ├── edge-security.md
│   └── screenshots/
├── day-12-threat-detection/
│   ├── threat-detection.md
│   └── screenshots/
├── day-13-centralized-security/
│   ├── centralized-security.md
│   └── screenshots/
├── day-14-serverless-security/
│   ├── serverless-security.md
│   └── screenshots/
├── day-15-containers/
│   ├── containers.md
│   └── screenshots/
├── day-16-auditing/
│   ├── auditing.md
│   └── screenshots/
├── day-17-detection-lab/
│   ├── detection-lab.md
│   └── screenshots/
├── day-18-19-catchup/
│   ├── catchup.md
│   └── screenshots/
phase-3-governance-identity/
├── day-20-organizations-scps/
│   ├── organizations-scps.md
│   └── screenshots/
├── day-21-advanced-iam/
│   ├── advanced-iam.md
│   └── screenshots/
├── day-22-identity-center/
│   ├── identity-center.md
│   └── screenshots/
├── day-23-customer-identity/
│   ├── customer-identity.md
│   └── screenshots/
├── day-24-resource-governance/
│   ├── resource-governance.md
│   └── screenshots/
├── day-25-advanced-vpc/
│   ├── advanced-vpc.md
│   └── screenshots/
├── day-26-scp-lab/
│   ├── scp-lab.md
│   └── screenshots/
phase-4-incident-response-capstone/
├── day-27-threat-hunting/
│   ├── threat-hunting.md
│   └── screenshots/
├── day-28-automation/
│   ├── automation.md
│   └── screenshots/
├── day-29-capstone-project/
│   ├── secure-baseline.md
│   └── screenshots/
├── day-30-review/
│   ├── final-review.md
│   └── screenshots/


- Each **day folder** contains:
  1. A `.md` file with step-by-step documentation of the security task.
  2. A `screenshots/` folder showing proof of configurations in AWS.
- This structure makes it easy for anyone to follow your learning journey day by day.

---

## How to Use This Repository

1. Open the folder for the day you want to review.  
2. Read the `.md` file to understand the task, configuration, and reasoning.  
3. View screenshots to see the AWS console setup for each step.  
4. Use this as a guide to replicate security best practices in your own AWS account safely.

---

## Learning Outcomes

By following this repository, you will learn how to:

- Harden AWS root accounts and enforce MFA  
- Implement least privilege using IAM users, groups, and policies  
- Secure VPC networks with proper subnetting and security controls  
- Monitor activity using CloudTrail, CloudWatch, and Flow Logs  
- Encrypt data and manage secrets securely  
- Detect threats with GuardDuty, Macie, and Security Hub  
- Apply governance through tagging, AWS Organizations, and Service Control Policies  

---

## Author

**Miracle Ukwa**  
30 Days of AWS Cloud Security Challenge  
[LinkedIn](https://www.linkedin.com/in/miracle-ukwa-7a29b7155)
