# Cloud Architecture Outline

## Project
A simple web application where users log in and use an API to save and view data.

## Compute (where the code runs)
- Website files: Amazon S3 + CloudFront
- Backend API: AWS Lambda with API Gateway

## Storage (where data is kept)
- Database: Amazon DynamoDB
- Images and files: Amazon S3
- Backups: automatic daily backups

## Networking (how things connect)
- CloudFront delivers the website quickly to users
- API Gateway receives requests from the website
- Everything is accessed only over HTTPS
- Firewall (AWS WAF) blocks bad traffic

## Identity (who can log in and access what)
- Users log in with Amazon Cognito
- IAM roles give each service only the permissions it needs

## Flow
User -> CloudFront -> API Gateway -> Lambda -> DynamoDB
