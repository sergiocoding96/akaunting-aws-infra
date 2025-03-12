# Akaunting AWS Infrastructure

This repository contains AWS CloudFormation templates for deploying Akaunting in AWS Free Tier.

## Quick Start

1. Go to AWS CloudFormation console
2. Click "Create stack" > "With new resources (standard)"
3. Choose "Upload a template file"
4. Upload `akaunting-combined.yaml`
5. Enter stack details:
   - Stack name: `akaunting-stack`
   - DBPassword: Create a secure password (e.g., `Akaunting2024!`)
6. Click through the next screens, acknowledge IAM capabilities
7. Click "Create stack"

## What's Included

The template creates:
- VPC with public and private subnets
- EC2 t2.micro instance (Free Tier)
- RDS db.t2.micro instance (Free Tier)
- Security groups and networking
- Automatic Akaunting installation

## Free Tier Usage

All resources are configured to stay within AWS Free Tier limits:
- EC2: t2.micro (750 hours/month free)
- RDS: db.t2.micro (750 hours/month free)
- Storage: Under 30GB total
- Data Transfer: Within free tier limits