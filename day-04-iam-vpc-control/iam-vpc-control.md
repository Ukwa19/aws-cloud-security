# Day 4 – IAM + VPC Control

**Author:** Miracle Ukwa  
**LinkedIn:** [https://www.linkedin.com/in/miracle-ukwa-7a29b7155](https://www.linkedin.com/in/miracle-ukwa-7a29b7155)

---

## 1. Purpose of the Lab

Today we focused on **applying IAM guardrails** to EC2 security. The goal was to ensure that:

- Developers can **view resources** (read-only)  
- Developers **cannot modify or create Security Groups**  
- All denied attempts are logged in **CloudTrail** for auditing  

This demonstrates **least privilege** in practice.

---

## 2. Actions Taken

1. Logged in as **Admin**  
2. Created a **Deny policy** for Security Group modifications:
3. Attached the policy to the Developers group
4. Logged in as Miracle-dev to test:

- Attempted creating a Security Group → received AccessDenied
- Verified CloudTrail event logged the denied attempt



---
## 3. Explanation

IAM evaluates permissions like this:

Check Allow policies: Miracle-dev has AmazonEC2ReadOnlyAccess, so they can view resources

Check Deny policies: Explicit deny overrides any allow

Outcome: Miracle-dev can see EC2 Security Groups but cannot create, delete, or modify them

**Why it matters:**

Developers can operate without risking network misconfigurations

Explicit deny ensures critical resources are safe

CloudTrail provides audit-proof evidence for compliance

---
## 4. Lessons Learned

IAM is a powerful tool for least privilege and context-aware security

Testing denied actions safely (like creating a Security Group) shows policies actually work

CloudTrail logs are essential for tracking attempts and confirming policies


```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "DenySecurityGroupEdits",
            "Effect": "Deny",
            "Action": [
                "ec2:DeleteSecurityGroup",
                "ec2:CreateSecurityGroup",
                "ec2:AuthorizeSecurityGroupIngress",
                "ec2:AuthorizeSecurityGroupEgress",
                "ec2:RevokeSecurityGroupIngress",
                "ec2:RevokeSecurityGroupEgress"
            ],
            "Resource": "*"
        }
    ]
}





