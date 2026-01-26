# Day 7 – Encryption

## Objective
Protect data at rest using AWS-native encryption services.

---

## KMS Key Creation
- Key type: Symmetric
- Usage: Encrypt and decrypt
- Alias: `day7-encryption-key`
- Key administrators: Admin user
- Key users: Admin user

---

## S3 Encryption
- Bucket encryption enabled
- Encryption type: SSE-KMS
- KMS key: `day7-encryption-key`
- Public access: Blocked

---

## Secrets Manager
- Secret name: `day7-demo-secret`
- Encryption: KMS (customer managed key)
- Rotation: Disabled (lab environment)

---

## IAM Key Policies
- Key access restricted to admin user
- Prevents unauthorized decrypt actions

---

## Key Takeaway
Encryption protects data even if access controls fail.  
Keys control who can read the data — not just who can see it.
