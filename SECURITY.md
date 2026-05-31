# Security Policy

## Lab Scope

This repository is for educational Kubernetes exercises in isolated, authorized environments. Do not apply these manifests directly to production clusters.

## Sensitive Configuration

Do not commit:

- Real database passwords or application credentials.
- Tokens, kubeconfig files, certificates, private keys, or cloud credentials.
- Real internal endpoints, production IP addresses, or private DNS names.
- Cluster exports, logs, or screenshots containing sensitive infrastructure data.

Use placeholders and Kubernetes Secrets for sensitive values.

## Current Repository Notice

Some existing learning manifests contain hardcoded lab credentials and an environment-specific endpoint. They were preserved to avoid changing lab behavior in a documentation-only PR. Review [SECURITY_NOTES.md](SECURITY_NOTES.md) before running or reusing the manifests.

## Reporting

Report suspected exposure privately to repository maintainers. Do not open public issues containing credentials or infrastructure identifiers.

## Review Checklist

- [ ] The target cluster is isolated and authorized.
- [ ] No real secrets or kubeconfig files are committed.
- [ ] Hardcoded lab values are replaced before reuse.
- [ ] RBAC and TLS settings are reviewed.
- [ ] Images and Kubernetes API versions are validated.
