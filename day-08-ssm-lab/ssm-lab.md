# Day 8 – Secure Access Lab (SSM Session Manager)

## Objective
Access a private EC2 instance securely without SSH or public IPs.

---

## IAM Role
- Role name: `EC2-SSM-Role`
- Policy attached: `AmazonSSMManagedInstanceCore`

---

## EC2 Instance
- Name: `day8-private-ec2`
- AMI: Amazon Linux 2023
- Subnet: Private subnet
- Public IP: Disabled
- Security group: No inbound rules
- IAM role: `EC2-SSM-Role`

---

## Access Method
- AWS Systems Manager → Session Manager
- No SSH keys used
- No port 22 opened

---

## Key Takeaway
Secure access does not require public exposure.  
Session Manager enables auditable, keyless access to private servers.
