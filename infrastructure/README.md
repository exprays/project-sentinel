# Infrastructure Overview

This directory stores infrastructure-as-code, deployment manifests, and automation scripts for Project SENTINEL.

## Structure

- `terraform/` – Terraform modules for AWS resources (provisioned in later phases)
- `helm/` – Helm charts for Kubernetes deployments
- `scripts/` – Operational scripts for provisioning and maintenance tasks

Create the subdirectories when you begin implementing the corresponding tooling.

## AWS Account Configuration Checklist

- Create a dedicated AWS account or project-level sandbox
- Enforce multi-factor authentication and least-privilege IAM roles
- Store credentials in AWS Secrets Manager or AWS SSO where possible
- Enable CloudTrail and Config for account-level auditing
- Set billing alerts to monitor hackathon spending limits
