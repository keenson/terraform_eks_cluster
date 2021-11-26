# Terraform AWS EKS Cluster Lab

This is a deployment of an AWS EKS environment which can be used to build quick lab environments and easily tear them down for a true self-cleaning on-demand Kubernetes configuration.

## Why does this exist?

Setting up EKS for occasional use is not simple, nor is making sure you have all the dependencies, policies, networks, and more. It's also easy to leave behind a lot of remnants in AWS which are either costly or confusing (e.g. empty policies, unused subnets)

## Requirements

You will need:

- AWSCLI
- AWS IAM credentials
- IAM User

## Note:

Note state will be stored locally for this demo purpose only

## About the Lab Code

Terraform configuration built for Terraform 0.13.4 or higher

## What Does the EKS Lab Build?

The lab does the following which is also completely removed when you do a terraform destroy so you have no unnecessary remnants left behind:

- Set up new VPC
- Create 2 public subnets
- Create 2 private subnets
- Create 2 NAT Gateway
- Create Elastic IP
- Create Security Groups for ingress and egress
- Create an Internet Gateway
- Create 3 Routing Table and Subnet Associations
- Create an EKS Cluster
- Create an EKS Node Group

## Variables Needed for Terraform

You will need to have the following defined in your Terraform configuration. This was built using Terraform Cloud and Terraform Enterprise so the description

| Variable       | Type      | Content                              |
| -------------- | --------- | ------------------------------------ |
| aws_access_key | sensitive | Your AWS programmatic API key        |
| aws_secret_key | sensitive | Your AWS API secret key              |
| aws_region     | standard  | Region to launch in (e.g. us-east-1) |
