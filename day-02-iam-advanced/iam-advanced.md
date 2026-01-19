# Day 2 – Advanced IAM Controls

## Objective
Strengthen IAM security using advanced controls, conditions, role trust relationships, and auditing tools.

---

## Policy Conditions
A custom IAM policy (`EC2-ReadOnly-Restricted`) was created to enforce **context-based access control**.  
Access to `DescribeInstances` in EC2 is allowed **only if**:
- Request comes from a specific IP (`YOUR.PUBLIC.IP/32`)  
- Multi-Factor Authentication (MFA) is present

This ensures access is denied even if credentials are compromised.

**Screenshot:** `policy-conditions-sourceip-mfa.png`

---

## Trust vs Permission Policies
- **Trust Policies** define **who can assume a role**  
- **Permission Policies** define **what the role/user can do**  

Both are necessary for secure role usage. Understanding this distinction is critical in designing secure AWS IAM architectures.

---

## IAM Policy Simulator
The IAM Policy Simulator was used to **validate policy behavior** safely, without deploying resources.  

**Test Cases:**
1. Access from allowed IP with MFA → **Allowed**  
2. Access from wrong IP → **Denied**  
3. Access without MFA → **Denied**

**Screenshots:**   
- `policy-simulator-denied.png`

This confirms that the IAM conditions are enforcing access **exactly as intended**.

---

## IAM Access Analyzer
Access Analyzer was enabled to scan the account for unintended public or cross-account access.

**Findings:**
- No public access detected  
- No cross-account access detected  

This confirms that the IAM policies are configured securely and follow the **principle of least privilege**.

**Screenshot:** `access-analyzer-dashboard.png`

---

## Security Takeaways
- IAM security is about **controlling context, verifying behavior, and continuously auditing risk**.  
- Even read-only access should be **restricted based on IP and MFA**.  
- Understanding **trust vs permissions** is key for safe role management.  
- Policy Simulator and Access Analyzer are essential **proof tools for audits and documentation**.

---


## Author
**Miracle Ukwa**  
30 Days of AWS Cloud Security Challenge  
[LinkedIn](https://www.linkedin.com/in/miracle-ukwa-7a29b7155)

