---
title: AWS Icons in Mermaid
sync_to_confluence: true
---

# AWS Architecture Diagrams

This page demonstrates AWS architecture diagrams with actual AWS icons.

## Architecture Overview

| Component | Icon | Description |
|-----------|------|-------------|
| Route 53 | ![Route 53](images/aws-route53.svg) | DNS service |
| CloudFront | ![CloudFront](images/aws-cloudfront.svg) | CDN distribution |
| VPC | ![VPC](images/aws-vpc.svg) | Virtual private cloud |
| EC2 | ![EC2](images/aws-ec2.svg) | Compute instances |
| Lambda | ![Lambda](images/aws-lambda.svg) | Serverless functions |
| RDS | ![RDS](images/aws-rds.svg) | Relational database |
| DynamoDB | ![DynamoDB](images/aws-dynamodb.svg) | NoSQL database |
| S3 | ![S3](images/aws-s3.svg) | Object storage |

## Data Flow

```
Route 53 → CloudFront → ALB → EC2 Instances → RDS/DynamoDB
                              ↓
                           Lambda → S3
```

## Serverless Architecture

| Component | Icon | Role |
|-----------|------|------|
| API Gateway | ![API Gateway](images/aws-api-gateway.svg) | API endpoint |
| Lambda | ![Lambda](images/aws-lambda.svg) | Business logic |
| Cognito | ![Cognito](images/aws-cognito.svg) | Authentication |
| DynamoDB | ![DynamoDB](images/aws-dynamodb.svg) | Data persistence |
| SQS | ![SQS](images/aws-sqs.svg) | Message queuing |
| SNS | ![SNS](images/aws-sns.svg) | Notifications |

## AWS Icons Reference

All icons are stored in `images/` directory:

| Icon | Service | Filename |
|------|---------|----------|
| ![Lambda](images/aws-lambda.svg) | AWS Lambda | `aws-lambda.svg` |
| ![EC2](images/aws-ec2.svg) | Amazon EC2 | `aws-ec2.svg` |
| ![RDS](images/aws-rds.svg) | Amazon RDS | `aws-rds.svg` |
| ![DynamoDB](images/aws-dynamodb.svg) | Amazon DynamoDB | `aws-dynamodb.svg` |
| ![S3](images/aws-s3.svg) | Amazon S3 | `aws-s3.svg` |
| ![CloudFront](images/aws-cloudfront.svg) | Amazon CloudFront | `aws-cloudfront.svg` |
| ![Route 53](images/aws-route53.svg) | Amazon Route 53 | `aws-route53.svg` |
| ![VPC](images/aws-vpc.svg) | Amazon VPC | `aws-vpc.svg` |
| ![API Gateway](images/aws-api-gateway.svg) | Amazon API Gateway | `aws-api-gateway.svg` |
| ![Cognito](images/aws-cognito.svg) | Amazon Cognito | `aws-cognito.svg` |
| ![SQS](images/aws-sqs.svg) | Amazon SQS | `aws-sqs.svg` |
| ![SNS](images/aws-sns.svg) | Amazon SNS | `aws-sns.svg` |

## Tips

For comprehensive AWS architecture diagrams with full icon support, consider:
- [Draw.io with AWS4 library](https://app.diagrams.net/?splash=0&libs=aws4) - Export as SVG/PNG
- [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) - Official icon set
