# Day 5 – VPC Traffic

**Objective:** Monitor and control VPC traffic while keeping costs minimal.

---

## ✅ Tasks Completed

1. **Create S3 Gateway Endpoint**
   - Allows private subnet to access **S3 without using the internet**.
   - Zero-cost solution (no interface endpoints used).
   - **Endpoint Name:** `day5-s3-gateway`
     
2. **Enable VPC Flow Logs**
   - Captures **all traffic** going in/out of the VPC.
   - Helps analyze traffic and detect issues or unexpected connections.
   - **Flow Log Name:** `/aws/vpc/day5-vpc-flow-log`
   - **Destination:** CloudWatch Logs

3. **Analyze Traffic**
   - Verified traffic from private subnet reaches S3 endpoint.
   - No internet traffic from private subnet.

---

## 💡 Notes / Key Takeaways

- Private subnet can access S3 **internally** without internet or NAT Gateway.  
- **Gateway Endpoint** is free — chosen for **zero cost architecture**.  
- Flow Logs provide visibility into VPC traffic for auditing and troubleshooting.  


