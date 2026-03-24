# Lab M8.01 - Classify Controls into Provider vs Tenant Responsibility

**Repository:** https://github.com/MaryaAhmadi/ce-lab-classify-provider-tenant-controls.git

**Activity Type:** Individual  
**Estimated Time:** 45-60 minutes

## 🎯 Learning Objectives

- Understand and apply the AWS Shared Responsibility Model
- Classify security controls between AWS and Customer responsibilities
- Identify service responsibility boundaries (IaaS, PaaS, SaaS)
- Build a security responsibility matrix for a real-world architecture
- Perform gap analysis and prioritize security improvements

---

## 📌 Prerequisites

- Completed Module 8 Lesson 1
- AWS account with active resources (EC2, S3, VPC, IAM)
- Basic understanding of:
  - IAM roles and policies
  - Security groups and networking
  - Encryption concepts (KMS, S3 encryption)

---

## 🧠 Introduction

The AWS Shared Responsibility Model defines a clear division of security responsibilities:

- **AWS** is responsible for *security of the cloud* (infrastructure)
- **Customer** is responsible for *security in the cloud* (configuration, data, access)

Misunderstanding this model leads to:
- Security vulnerabilities
- Data breaches
- Compliance failures

This lab demonstrates how to properly classify and implement these responsibilities.

---

## 🏗️ Scenario

You are a **Cloud Security Engineer** working for a startup with a three-tier AWS architecture:

- **Web Tier:** EC2 instances (public access)
- **App Tier:** EC2 instances (private/internal)
- **Data Tier:** S3 buckets *(RDS not currently deployed)*

Your task is to evaluate and document security responsibilities across this architecture.

---

## 🛠️ Deliverables

You must create:

1. `security-inventory.md`
2. `responsibility-matrix.md`
3. `gap-analysis.md`
4. `assessment-report.md`

---

## ✅ Success Criteria

- At least **20 security controls documented**
- All services correctly classified (IaaS / PaaS / SaaS)
- Minimum **5 security gaps identified**
- Clear AWS vs Customer responsibility separation
- Professional documentation (Markdown)

---

### 🧩 Step 1: Resource Inventory

Document all AWS resources.

📄 **File:** `security-inventory.md`

### Example Structure:

```md
# AWS Resource Inventory

## Compute
- EC2 Instance: i-xxxx (web-server)

## Database
- ❌ No RDS deployed

## Storage
- S3 Bucket: example-bucket

## Networking
- VPC: vpc-xxxx
- Security Groups: sg-web, sg-app

## Identity
- IAM Roles: ec2-role

### 🧩 Step 2: Responsibility Matrix
📄 File: responsibility-matrix.md
Requirements:
Minimum 20 controls
Include:
AWS responsibility
Customer responsibility
Status
(Optional) Risk level ⭐

### 🧩 Step 3: Service Model Classification
Service	Model	Explanation
EC2	IaaS	Full control over OS and applications
S3	PaaS	AWS manages infra, customer manages data
IAM	SaaS	Managed service, customer configures access
VPC	IaaS	Customer defines network
RDS	PaaS	Not deployed

###🧩 Step 4: Security Controls Mapping
🔐 Network Security
Control	AWS	Customer	Status
VPC isolation	✅	✅	✅
Security groups	✅	✅	⚠️ Review
NACLs	✅	✅	⚠️ TODO
DDoS protection	✅	⚠️ Optional	❌
🖥️ Compute Security
Control	AWS	Customer	Status
Host OS	✅	❌	✅
Guest OS	❌	✅	⚠️ TODO
Application security	❌	✅	⚠️ TODO
IAM roles	✅	✅	⚠️ Review
📦 Data Security (S3)
Control	AWS	Customer	Status
Storage durability	✅	❌	✅
Encryption	✅	✅	⚠️ TODO
Bucket policies	❌	✅	⚠️ Review
Public access block	❌	✅	⚠️ TODO
Versioning	❌	✅	❌

### 🧩 Step 5: Gap Analysis
📄 File: gap-analysis.md
Identify:
Critical risks
High risks
Medium risks
Example:
❌ No encryption → Critical
⚠️ Open security groups → High
❌ No versioning → Medium

###🧩 Step 6: Assessment Report
📄 File: assessment-report.md
Include:
Executive summary
Architecture overview
Key findings
Recommendations
Conclusion

### 🧩 Step 7: Validation
Verify against AWS documentation:
👉 https://aws.amazon.com/compliance/shared-responsibility-model/

🎨 Step 8: Architecture Diagram (Bonus)
📄 Title:
AWS Shared Responsibility Architecture Diagram
📌 Include:
AWS vs Customer boundary
Three-tier structure
Security layers
🔍 Verification Checklist
 20+ controls documented
 Service models correct
 Responsibilities clearly split
 Gaps identified
 Recommendations provided
 Documentation clean and professional



Use draw.io or similar tool to create a visual representation:

```
┌─────────────────────────────────────────────┐
│         AWS RESPONSIBILITY                  │
│  Physical Security, Hardware, Hypervisor    │
└─────────────────────────────────────────────┘
                    ↑
                    │
┌─────────────────────────────────────────────┐
│       CUSTOMER RESPONSIBILITY               │
│  Guest OS, Applications, Data, IAM,         │
│  Encryption, Network Config, Firewall       │
└─────────────────────────────────────────────┘
```

## Key Insight
AWS secures the infrastructure.
You secure everything you build on top of it.

## 🧠 Reflection
Biggest risk? → Misconfiguration
Most misunderstood? → IAM & Security Groups
Key takeaway? → Shared responsibility ≠ Shared equally

## 📚 Resources
AWS Shared Responsibility Model
AWS Security Best Practices
CIS AWS Benchmark

## 🏁 Conclusion
A strong understanding of shared responsibility is essential for secure cloud environments.
Security failures are rarely due to AWS — they are almost always due to misconfiguration.


## Additional Resources

- [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)
- [AWS Security Best Practices](https://aws.amazon.com/architecture/security-identity-compliance/)
- [CIS AWS Foundations Benchmark](https://www.cisecurity.org/benchmark/amazon_web_services)
- [Capital One Breach Post-Mortem](https://krebsonsecurity.com/2019/07/capital-one-breach-spotlights-need-for-defense-in-depth/)

**Good luck! 🔒**
