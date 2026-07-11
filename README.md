# 🚀 Production-Grade GitOps Platform on AWS EKS

A production-style cloud-native GitOps platform built on AWS using **Terraform**, **Amazon EKS**, **GitHub Actions**, **Argo CD**, **Helm**, **Docker**, **Amazon ECR**, and **SonarQube**.

This project demonstrates how modern DevOps and Platform Engineering teams automate infrastructure provisioning, continuous integration, container image management, GitOps deployments, and Kubernetes operations using multiple repositories.

---

# Architecture

<p align="center">
<img src="architecture.png" width="100%">
</p>

---

# Overview

This platform is organized into **three independent repositories**, following a real-world GitOps workflow.

```
Developer
      │
      ▼
Application Repository
      │
      ▼
CI Pipeline
      │
      ▼
Amazon ECR
      │
      ▼
Helm Repository
      │
      ▼
ArgoCD
      │
      ▼
Amazon EKS
```

Infrastructure is managed independently using Terraform through a dedicated Infrastructure repository.

---

# Related Repositories

## Application Repository

Responsible for application development and Continuous Integration.

### Responsibilities

- Java Application
- Maven Build
- Unit Testing
- Checkstyle
- SonarQube Analysis
- Docker Build
- Push Images to Amazon ECR

---

## Helm Repository

Responsible for GitOps deployments.

### Responsibilities

- Helm Charts
- Kubernetes Manifests
- Values Files
- ArgoCD Application

ArgoCD continuously monitors this repository and synchronizes changes into Amazon EKS.

---

## Infrastructure Repository

Responsible for Infrastructure as Code.

### Responsibilities

- Terraform Modules
- Amazon EKS
- VPC
- IAM
- Route53
- ACM
- GitHub Actions
- Drift Detection
- Slack Notifications

---

# End-to-End Platform Workflow

## Infrastructure Pipeline

```
GitHub

↓

Terraform Validate

↓

Terraform Plan

↓

Manual Approval

↓

Terraform Apply

↓

Amazon AWS

↓

Scheduled Drift Detection

↓

Slack Notifications
```

---

## Application CI Pipeline

```
Developer

↓

GitHub

↓

GitHub Actions

↓

Maven Build

↓

Unit Testing

↓

Checkstyle

↓

SonarQube

↓

Docker Build

↓

Push Image

↓

Amazon ECR
```

---

## GitOps Deployment Pipeline

```
Amazon ECR

↓

Update Helm Chart

↓

Git Repository

↓

ArgoCD

↓

Continuous Sync

↓

Amazon EKS
```

---

# AWS Architecture

The infrastructure provisions a production-style Amazon EKS environment consisting of:

## Networking

- Amazon VPC
- Public Subnets
- Private Subnets
- Route53
- Application Load Balancer
- AWS Load Balancer Controller

---

## Kubernetes Platform

- Amazon EKS
- Managed Node Groups
- CoreDNS
- kube-proxy
- VPC CNI
- Metrics Server
- EBS CSI Driver

---

## Kubernetes Resources

- Deployments
- Services
- Ingress
- ConfigMaps
- Secrets
- Persistent Volumes
- Persistent Volume Claims

---

## Storage

- Amazon EBS
- Amazon ECR
- Amazon S3 (Terraform State)

---

## Security

- IAM Roles
- Security Groups
- ACM Certificates

---

## Monitoring

- CloudWatch
- CloudTrail
- SonarQube
- Slack Notifications

---

# Technology Stack

## Cloud

- Amazon Web Services

## Infrastructure as Code

- Terraform

## Containers

- Docker

## Kubernetes

- Amazon EKS
- Helm
- ArgoCD

## CI/CD

- GitHub Actions

## DevSecOps

- SonarQube

## Registry

- Amazon ECR

## Build

- Maven

---

# Key Features

- Production-grade GitOps Architecture
- Infrastructure as Code
- Continuous Integration
- Continuous Deployment
- Continuous Reconciliation
- Automated Infrastructure Provisioning
- Infrastructure Drift Detection
- Helm-based Kubernetes Deployments
- SonarQube Quality Gates
- Amazon ECR Image Registry
- Slack Infrastructure Notifications
- Multi-Repository GitOps Workflow

---

# Learning Outcomes

Through this project I gained practical experience with:

- Platform Engineering
- GitOps
- Amazon EKS
- Kubernetes
- Terraform
- GitHub Actions
- Helm
- ArgoCD
- Docker
- Amazon ECR
- Infrastructure Automation
- Kubernetes Networking
- Continuous Delivery
- Cloud Architecture
- AWS Security
- Infrastructure Drift Detection

---

# Future Improvements

- Multi-Environment Deployments
- Blue-Green Deployments
- Canary Releases
- Argo Rollouts
- Prometheus & Grafana Monitoring
- External Secrets Operator
- OPA Gatekeeper
- Kyverno Policies
- OpenTelemetry
- Multi-Cluster GitOps

---

# Repository Links

| Repository | Description |
|------------|-------------|
| **vprofile-app** | Application source code and CI pipeline |
| **vprofile-helm** | Helm charts and GitOps configuration |
| **vprofile-infra** | Terraform infrastructure and AWS provisioning |

---

# Author

**Eranga Kavishanka**

AWS Certified Cloud Practitioner (AWS CCP)

Kubernetes and Cloud Native Associate (KCNA)

Software Engineering Undergraduate

**DevOps • Cloud • Platform Engineering • Site Reliability Engineering (SRE)**

---

⭐ If you found this project useful, consider giving it a Star.
