---
title: AWS Icons in Mermaid
sync_to_confluence: true
---

# AWS Architecture Diagram with Mermaid

This page demonstrates the AWS icons available in Mermaid architecture diagrams via [iconify](https://icon-sets.iconify.design/?query=aws).

## Example Architecture

```mermaid
architecture-beta
    group vpc(logos:aws-vpc)[VPC]
    group compute(logos:aws-ec2)[Compute Layer] in vpc
    group data(logos:aws-rds)[Data Layer] in vpc

    service alb(logos:aws-elastic-load-balancing)[ALB]
    service ec2a(logos:aws-ec2)[EC2 Instance] in compute
    service ec2b(logos:aws-ec2)[EC2 Instance] in compute
    service lambda(logos:aws-lambda)[Lambda] in compute
    service rds(logos:aws-rds)[RDS Postgres] in data
    service dynamodb(logos:aws-dynamodb)[DynamoDB] in data
    service s3(logos:aws-s3)[S3 Bucket]
    service cloudfront(logos:aws-cloudfront)[CloudFront]
    service route53(logos:aws-route-53)[Route 53]

    route53:R --> L:cloudfront
    cloudfront:R --> L:alb
    alb:R --> L:ec2a
    alb:R --> L:ec2b
    ec2a:B --> T:rds
    ec2b:B --> T:dynamodb
    lambda:B --> T:s3
```

## Available AWS Icons (logos: prefix)

Here are the AWS icons available via iconify's `logos:` prefix:

| Icon Code | Service |
|-----------|---------|
| `logos:aws` | AWS Logo |
| `logos:aws-api-gateway` | API Gateway |
| `logos:aws-aurora` | Aurora |
| `logos:aws-cloudformation` | CloudFormation |
| `logos:aws-cloudfront` | CloudFront |
| `logos:aws-cloudwatch` | CloudWatch |
| `logos:aws-codedeploy` | CodeDeploy |
| `logos:aws-cognito` | Cognito |
| `logos:aws-dynamodb` | DynamoDB |
| `logos:aws-ec2` | EC2 |
| `logos:aws-ecs` | ECS |
| `logos:aws-eks` | EKS |
| `logos:aws-elastic-cache` | ElastiCache |
| `logos:aws-elastic-load-balancing` | ELB |
| `logos:aws-elasticbeanstalk` | Elastic Beanstalk |
| `logos:aws-fargate` | Fargate |
| `logos:aws-glacier` | Glacier |
| `logos:aws-iam` | IAM |
| `logos:aws-kinesis` | Kinesis |
| `logos:aws-kms` | KMS |
| `logos:aws-lambda` | Lambda |
| `logos:aws-mq` | MQ |
| `logos:aws-opensearch` | OpenSearch |
| `logos:aws-rds` | RDS |
| `logos:aws-redshift` | Redshift |
| `logos:aws-route-53` | Route 53 |
| `logos:aws-s3` | S3 |
| `logos:aws-ses` | SES |
| `logos:aws-sns` | SNS |
| `logos:aws-sqs` | SQS |
| `logos:aws-step-functions` | Step Functions |
| `logos:aws-vpc` | VPC |

## Serverless Example

```mermaid
architecture-beta
    group serverless(logos:aws-lambda)[Serverless Stack]

    service apigw(logos:aws-api-gateway)[API Gateway]
    service fn1(logos:aws-lambda)[Auth Function] in serverless
    service fn2(logos:aws-lambda)[API Function] in serverless
    service cognito(logos:aws-cognito)[Cognito] in serverless
    service dynamo(logos:aws-dynamodb)[DynamoDB]
    service sqs(logos:aws-sqs)[SQS Queue]
    service sns(logos:aws-sns)[SNS Topic]

    apigw:R --> L:fn1
    fn1:R --> L:cognito
    fn1:B --> T:fn2
    fn2:R --> L:dynamo
    fn2:B --> T:sqs
    sqs:R --> L:sns
```

## Data Pipeline Example

```mermaid
architecture-beta
    group ingest(cloud)[Ingestion]
    group process(cloud)[Processing]
    group store(cloud)[Storage]

    service kinesis(logos:aws-kinesis)[Kinesis] in ingest
    service lambda(logos:aws-lambda)[Transform] in process
    service glue(logos:aws-cloudformation)[Glue ETL] in process
    service s3raw(logos:aws-s3)[Raw Data] in store
    service s3proc(logos:aws-s3)[Processed] in store
    service redshift(logos:aws-redshift)[Redshift] in store

    kinesis:R --> L:lambda
    lambda:R --> L:s3raw
    s3raw:B --> T:glue
    glue:R --> L:s3proc
    s3proc:B --> T:redshift
```

## Limitations

⚠️ **Not all AWS services have icons** in the iconify `logos:` collection. Missing services include:
- Transfer Family
- GuardDuty
- Security Hub
- EventBridge
- AppSync
- Amplify
- And many others...

For comprehensive AWS diagrams, consider using [draw.io with AWS4 library](https://app.diagrams.net/?splash=0&libs=aws4) and exporting as SVG.
