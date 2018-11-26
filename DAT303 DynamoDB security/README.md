# Protecting your greatest asset: (your data): Security Best Practices on DynamoDB

## KMS to encrypt DDB

KMS results cached for 5 min

Default encryption at rest: tables indices streams and backups using KMS AES256

### IAM roles

Create role with DDB access, deny everything else. Should work right?
But when using sse-specification, denied, becuase user needs access to the key in KMS through the same policy

## Connection Pooling
* SDK Java: default 50 connection limit
* Python: 10 connections
* Node: No connection pooling by default

[Connection-Pooling-Slide](./connection-pooling.jpg)

## CloudTrail audit logs
Control Plane operations
NOT data plane operations
[Cloud Trail Reporting](./cloud-trail-reporting.jpg)

Can get notifications in cloudwatch from dynamoDB events (such as delete table etc)

##Fine grained control:
DynamoDB access control
[Fine Grained Access](./fine-grained-access.jpg)

##Create VPC endpoint for DynamoDB
Source restriction policy (IP whitelist) changes, source ip is not populated when requesting VPC endpoint from within the VPC

Can ignore whitelist source IP with "StringEqualsIfExist": { "aws:sourcevpce": "vpc-id"}
[Source IP VPC access](./source-ip-vpc-access.jpg)

Can also set access to only accounts in your org
[VPC Org Access](./vpc-org-access.jpg)

