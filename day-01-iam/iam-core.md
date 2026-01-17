# AWS IAM Core Setup – Day 1  
**30 Days of AWS Cloud Security**

## Objective
Establish a secure identity foundation for an AWS account by implementing least privilege access, removing daily dependency on the root account, and enforcing cost visibility.

This setup mirrors real-world production IAM practices rather than lab-only configurations.

---

## Threat Model
Common risks addressed on Day 1:
- Root account compromise
- Accidental privilege misuse
- Unauthorized access
- Unexpected billing spikes

---

## Security Controls Implemented

### 1. Root Account Hardening
**Risk:** Root credentials provide unrestricted access to all AWS services and billing.

**Mitigations Applied:**
- Enabled Multi-Factor Authentication (MFA)
- Disabled use of root for daily operations
- Root account reserved for emergency use only

**Outcome:**  
Root access is protected and removed from day-to-day activity.

---

### 2. Cost Safety Guardrail
**Risk:** Accidental resource creation leading to unexpected charges.

**Mitigations Applied:**
- Configured AWS Budget with a $1 threshold
- Enabled automated email alerts when threshold is reached

**Outcome:**  
Immediate visibility into cost anomalies (smoke detector model).

---

### 3. IAM Group Architecture
IAM permissions are assigned only to groups, never directly to users.

#### Admins Group
- Policy: `AdministratorAccess`
- Purpose: Full account administration without using root

#### Auditors Group
- Policy: `ReadOnlyAccess`
- Purpose: Visibility for compliance and auditing without modification rights

#### Developers Group
- Policy: None (Day 1)
- Purpose: Enforce least privilege by granting access only when required

---

### 4. IAM Users Created

| User Name        | Group        | Access Level | Purpose |
|-----------------|-------------|-------------|--------|
| miracle-admin   | Admins      | Full        | Daily administrative tasks |
| miracle-auditor | Auditors    | Read-only   | Security and compliance review |
| miracle-dev     | Developers  | None        | Future workload access |

**Note:**  
Only `miracle-admin` has AWS Management Console access on Day 1.

---

## Validation & Testing
- Verified `miracle-admin` can perform administrative actions
- Confirmed `miracle-auditor` cannot modify or delete resources
- Confirmed `miracle-dev` has zero access by default

Access testing ensures policies behave as expected.

---

## Security Principles Applied
- Least Privilege
- Separation of Duties
- Defense in Depth
- Cost-Aware Security Design

---

## Key Takeaway
Security is not something added after infrastructure is built.  
It is the foundation everything else depends on.

This IAM baseline ensures the AWS account is secure, auditable, and scalable before any workloads are deployed.

---

## Next Steps (Day 2)
- Design secure VPC architecture
- Compare Security Groups vs NACLs
- Implement network-level access controls

---

### Author
**Miracle Ukwa**  
30 Days of AWS Cloud Security  
Day 1 – Identity & Access Management
