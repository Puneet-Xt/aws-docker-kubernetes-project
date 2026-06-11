# AWS Docker Kubernetes SNS Project

## Overview

This project demonstrates end-to-end deployment of a Node.js application using:

- AWS CloudFormation
- Amazon EC2
- Docker
- Kubernetes (K3s)
- AWS SNS

## Architecture

User
  ↓
AWS EC2
  ↓
Docker Container
  ↓
Kubernetes (K3s)
  ↓
NodePort Service
  ↓
Node.js Application
  ↓
AWS SNS Email Notification

## Technologies Used

- AWS EC2
- CloudFormation
- Docker
- Kubernetes (K3s)
- Node.js
- AWS SNS

## Application Deployment

1. Provision infrastructure using CloudFormation.
2. Connect to EC2.
3. Build Docker image.
4. Deploy application on Kubernetes.
5. Expose application using NodePort service.
6. Configure SNS notifications.

## Access Application

http://<EC2-PUBLIC-IP>:30080

## SNS Notification

Deployment notifications are sent through Amazon SNS email subscriptions.
