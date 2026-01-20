# Day 3 – VPC Core: Building Your Cloud Neighborhood 🌐

## Overview
Today’s goal was to understand how AWS networks (VPCs) work, and how **public vs private subnets**, **routes**, and **firewalls** control access.  

Even non-technical readers can think of it like this:  
- The **VPC** is your neighborhood.  
- **Subnets** are the streets — some lead to the outside world (public), some don’t (private).  
- **Internet Gateways** are the gates to the world.  
- **Route tables** are maps that tell traffic where to go.  
- **Security Groups** and **NACLs** are the guards checking who can enter or leave.  

---

## Steps Taken

### 1️⃣ Created VPC
- Name: `day3-vpc-core`  
- CIDR block: `10.0.0.0/16`  
> This gives us a private space for our resources, like owning a block of addresses in your neighborhood.

### 2️⃣ Added Subnets
- Public subnet: `10.0.1.0/24`  
- Private subnet: `10.0.2.0/24`  
> Public subnet can reach the internet; private subnet is internal only.

### 3️⃣ Internet Gateway
- Initially **detached**, so no traffic could go outside.  
- Fixed by attaching IGW to `day3-vpc-core`  
> Think of this as opening the gate to the outside world.  

---

### 4️⃣ Route Tables
- Created `public-rt` for the public subnet.  
- Added route: `0.0.0.0/0 → igw-xxxx`  
> Now all outbound traffic from the public subnet goes through the IGW.

---

### 5️⃣ Security Group vs NACL

#### Security Group (`day3-sg-test`)
- Stateful firewall for EC2 instances  
- Inbound: Allow HTTP (port 80) from my IP  
- Outbound: Allow all (default)

---
#### Network ACL (`day3-nacl-test`)
- Stateless firewall for subnet traffic  
- Can explicitly allow or deny traffic in both directions

---


> Key takeaway: Security Groups track connections (stateful), NACLs check each packet independently (stateless).

---

## Lessons Learned
- A subnet’s “public” label doesn’t automatically make it accessible to the internet — **routes + IGW + firewall rules** control access.  
- IGWs must be **attached** to the VPC to be used.  
- Security Groups are easier for instance-level rules; NACLs are good for subnet-wide traffic control.  
- Mistakes, like a detached IGW or wrong route table, are great learning moments.

---

## Deliverable
- `vpc-core.md` (this file)  
- Screenshots folder: `screenshots/` containing:
  - `igw-attached.png`  
  - `public-rt-routes.png`  
  - `sg-inbound.png`  
  - `sg-outbound.png`  
  - `nacl-rules.png`


---

## Non-Technical Summary
Think of your cloud network like a neighborhood:
- VPC = neighborhood  
- Subnets = streets (public or private)  
- IGW = main gate  
- Route tables = maps  
- Security Groups/NACLs = guards  

Set them up correctly, and your neighborhood is secure but functional. Miss a step, and the “street” is either completely closed or dangerously open.

**Author:** Miracle Ukwa  
**LinkedIn:** (https://www.linkedin.com/in/miracle-ukwa-7a29b7155)
