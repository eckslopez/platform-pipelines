# platform-pipelines

Reusable GitHub Actions workflows for infrastructure and database automation.

## Workflows

### `.github/workflows/terraform-rds.yml`

Reusable Terraform workflow that:
- Assumes an AWS IAM role via GitHub OIDC
- Runs `terraform init`, `validate`, `plan`
- Optionally runs `terraform apply`

### `.github/workflows/db-bootstrap-psql.yml`

Reusable workflow that:
- Gets a PostgreSQL endpoint (passed in as input)
- Connects using `psql`
- Runs one or more SQL files to bootstrap the database (schemas, roles, tenants, etc.)

These workflows are intended to be called from other repos via `workflow_call`.
