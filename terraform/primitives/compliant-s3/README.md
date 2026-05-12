# Lab 2.3 — Compliant S3 Bucket

This module enforces SC-28 (AES-256 encryption at rest), AU-3/AU-6 (server access logging to a dedicated log bucket), CM-6 (versioning and mandatory compliance tags applied at the provider level), and AC-3 (all public access vectors explicitly blocked) on a single AWS S3 bucket.

NIST 800-53 controls satisfied: SC-28, AU-3, AU-6, CM-6, AC-3

## Usage

```bash
terraform init
terraform validate
terraform plan -var="project_name=cgep-lab" -var="environment=dev" -out=tfplan
terraform apply -auto-approve tfplan
```

## Capture evidence

```bash
mkdir -p evidence
terraform show -json tfplan > evidence/plan.json
terraform show -json        > evidence/state.json
```

## Cleanup

```bash
terraform destroy -var="project_name=cgep-lab" -var="environment=dev"
```
