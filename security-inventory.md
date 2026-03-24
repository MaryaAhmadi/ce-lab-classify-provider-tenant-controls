# AWS Resource Inventory

## Compute (EC2 Instances)
- i-009fd10ef98703c58 (logging-server)
- i-009a8cc45befc2202 (observability-node)
- i-0e3db1c98ae015cf0 (rightsizing-data-processor)
- i-0a91b51bf7c5f042e (dev-frontend - stopped)
- i-001646f31723c3c1d (web-server)
- i-0ad44fadae1193a74 (rightsizing-web-server)
- i-028d8db34216950e9 (rightsizing-api-server)
- i-0411d41c34c155eb5 (dev-backend)
- i-02d8cdaeff97542a9 (unused-instance - stopped)

## Database
- ❌ No RDS instances currently deployed

## Storage (S3 Buckets)
- ce-lab-archive-294152
- ce-lab-data-294152
- ce-lab-logs-294152
- config-bucket-070638634202

## Networking

### VPCs
- vpc-0b140bcdffa69bb4b (web-tier-vpc)
- vpc-0cc721be72d4902d7 (default VPC)
- vpc-02ecac44338f8cc46 (logging VPC)

### Security Groups
- sg-04153522db82ffd3a (default - logging VPC)
- sg-02707098ed9bb0568 (launch-wizard-1)
- sg-096c2c7d87525961f (SSH)
- sg-0f3e9ba3e4484fd41 (launch-wizard-3)
- sg-015385f2d54cd9a23 (web-sg)
- sg-0d15e35d33eefd04a (launch-wizard-2)
- sg-0e31764b5cc3981e3 (default - web-tier VPC)
- sg-03371688ba8ff5d91 (default - default VPC)

## Identity (IAM Roles)
- AWSServiceRoleForConfig
- AWSServiceRoleForElasticLoadBalancing
- AWSServiceRoleForResourceExplorer
- AWSServiceRoleForSupport
- AWSServiceRoleForTrustedAdvisor
- BudgetActionRole
- CloudWatchAgentRole
- EC2CloudWatchRole
- FinOpsLambdaRole
- observability
