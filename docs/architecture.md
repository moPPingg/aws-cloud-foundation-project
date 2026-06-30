# Architecture Overview

This document explains the simple service flow used in the AWS Cloud Foundation Project. The architecture is intentionally small and beginner-friendly so the main AWS concepts are easier to understand.

## Text-Based Architecture Diagram

```text
Developer Laptop -> AWS CLI -> Amazon S3 -> User Browser
Developer Laptop -> SSH -> EC2 Ubuntu Instance -> CloudWatch CPU Alarm
AWS Account -> AWS Budgets -> Email Alert
```

## S3 Website Flow

The website files are created locally using HTML and CSS. These files are uploaded to an Amazon S3 bucket configured for static website hosting. After the files are available in the bucket, the website can be opened in a browser through the S3 website endpoint.

Flow summary:

- Create or update files locally
- Upload files to Amazon S3
- Use S3 static website hosting settings
- Open the site from a browser

## AWS CLI Deployment Flow

The AWS CLI is used as the deployment method between the local project folder and Amazon S3. This keeps the deployment process simple and repeatable for a beginner lab.

Flow summary:

- Install and check AWS CLI locally
- Configure AWS credentials
- Verify the active AWS identity
- Sync the `website/` folder to the S3 bucket

## EC2 SSH Flow

An EC2 Ubuntu instance is used for basic Linux practice. The learner connects from a local machine to the EC2 instance using SSH to practice remote access and simple server commands.

Flow summary:

- Launch an Ubuntu EC2 instance
- Use the key pair and public connection details
- Connect from the local machine with SSH
- Practice Linux commands and instance management

## CloudWatch Alarm Flow

Amazon CloudWatch is used to observe basic EC2 metrics such as CPU utilization. A simple alarm can be created to introduce the idea of monitoring and alert conditions.

Flow summary:

- Open EC2 metrics in CloudWatch
- Select a basic metric such as CPU utilization
- Create a threshold-based alarm
- Use the alarm to understand simple monitoring behavior

## AWS Budgets Alert Flow

AWS Budgets is used to monitor estimated spending in the AWS account. This helps build early habits around cost visibility while working through hands-on labs.

Flow summary:

- Create a monthly budget
- Set an email notification threshold
- Monitor estimated spending
- Respond early if usage becomes higher than expected
