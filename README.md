# Infrastructure Owner Assessment – Hetzner

This repository contains the complete solution for the Infrastructure DevOps Intern assessment.

## Environment
- Cloud: Hetzner
- OS: Ubuntu 24
- Kubernetes: k3s (single-node)
- Container Runtime: Docker
- Application: Open WebUI (Helm)

## Steps Performed

### 1. VM Setup
- Installed Docker
- Installed k3s
- Configured kubectl access

### 2. Application Deployment
- Added Open WebUI Helm repo
- Deployed application using Helm (ClusterIP)

### 3. OIDC Configuration
- Enabled OIDC via Helm values
- Application failed intentionally due to self-signed certificate

### 4. Debugging
- Identified TLS trust issue with OIDC provider
- Fixed using insecureSkipVerify (temporary)
- Explained production-grade fix using custom CA

## Validation Outputs
See screenshot png file

## Notes
This setup is suitable for early-stage startups due to low cost and operational simplicity but is not HA-ready.
