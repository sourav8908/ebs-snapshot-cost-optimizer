
# EBS Snapshot Cleanup for Cost Optimization

## Overview
This project provides an AWS Lambda function written in Python that automates the identification and deletion of stale EBS snapshots not associated with any active EC2 instances. The automation helps optimize AWS storage costs by removing unused snapshots safely and efficiently.

## Features
- Detects EBS snapshots owned by the account that are no longer linked to running or stopped EC2 instances.  
- Automatically deletes stale snapshots to reduce unnecessary storage costs.  
- Uses AWS SDK (boto3) and AWS Lambda for serverless automation.  
- Secure execution with IAM roles following the least-privilege principle.  
- Logs and monitors Lambda execution via AWS CloudWatch for operational insights.

## Architecture
1. Lambda function fetches all snapshots owned by the AWS account.  
2. Retrieves the list of active EC2 instances (running and stopped).  
3. Cross-references snapshot volume IDs with volumes attached to EC2 instances.  
4. Deletes snapshots not linked to any active instance volume.

## Prerequisites
- AWS account with appropriate permissions to manage EC2 and EBS resources.  
- AWS CLI configured or AWS Management Console access.  
- IAM role with permissions for Lambda to list and delete snapshots and describe instances.  

## Deployment Instructions
1. Clone this repository:  
   ```bash
   git clone https://github.com/your-username/ebs-snapshot-cleanup.git
