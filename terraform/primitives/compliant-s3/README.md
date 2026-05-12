# Lab 2.3 — Compliant S3 Bucket

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
