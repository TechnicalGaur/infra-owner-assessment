# Ownership Answers

## 1. Production Readiness
Top risks:
- Single node failure
- No backups
- No monitoring
- No autoscaling
- Secrets management

First fixes:
- Backups
- Monitoring & alerts

## 2. Failure Scenario
- First failure: node resource exhaustion
- Recovery: recreate node, redeploy workloads
- Next day: add autoscaling and HA

## 3. Security & Secrets
- Use Kubernetes Secrets or Vault
- Never commit secrets to Git
- Rotate SSH keys, DB credentials, API tokens

## 4. Backups
- Backup persistent data and configs
- Daily backups
- Test restore on new VM

## 5. Cost Ownership
- Use small VMs
- Avoid managed services early
- Move away from k3s when HA or multi-region needed
