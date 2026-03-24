# Security Responsibility Matrix

## Service Model Classification

| Service | Model | Justification |
|--------|------|--------------|
| EC2 | IaaS | Full control over OS, applications, and configuration |
| S3 | PaaS | AWS manages infrastructure, customer manages data and access |
| VPC | IaaS | Customer configures networking (subnets, routing, security) |
| IAM | SaaS | AWS manages service, customer manages permissions |
| ALB | PaaS | AWS manages infrastructure, customer configures routing |
| RDS | PaaS | Not currently deployed |

---

## Responsibility Matrix


| Control | Service | AWS Responsibility | Customer Responsibility | Status | Risk Level |
|--------|--------|-------------------|------------------------|--------|-----------|
| Guest OS patching | EC2 | ❌ None | ✅ Patch OS regularly | ⚠️ TODO | 🔴 High |
| Application security | EC2 | ❌ None | ✅ Secure code | ⚠️ TODO | 🔴 High |
| Security group rules | VPC | ✅ Infra | ✅ Configure rules | ⚠️ Review | 🔴 High |
| S3 encryption | S3 | ✅ Infra | ✅ Enable encryption | ⚠️ TODO | 🔴 High |
| S3 public access block | S3 | ❌ None | ✅ Enable block | ⚠️ TODO | 🔴 High |
| IAM least privilege | IAM | ✅ Infra | ✅ Restrict access | ⚠️ Review | 🔴 High |
| Patch automation | EC2 | ❌ None | ✅ Use SSM | ❌ Not enabled | 🔴 High |
| CloudTrail logging | All | ✅ Infra | ✅ Enable logs | ⚠️ TODO | 🟠 Medium |
| Backup strategy | EC2/S3 | ❌ None | ✅ Define backup | ⚠️ TODO | 🟠 Medium |
| S3 versioning | S3 | ❌ None | ✅ Enable | ❌ Not enabled | 🟠 Medium |
| KMS key management | All | ✅ Infra | ✅ Manage keys | ⚠️ TODO | 🟠 Medium |
