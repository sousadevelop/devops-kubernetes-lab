# Contributing

## Principles

- Treat this repository as an educational Kubernetes lab.
- Keep documentation aligned with existing manifests.
- Do not add production credentials, kubeconfig files, or private infrastructure data.
- Do not silently change manifest behavior in documentation PRs.
- Use separate PRs for compatibility fixes or manifest refactors.

## Development Flow

1. Create a branch from `main`.
2. Choose the lab exercise being updated.
3. Keep the change focused.
4. Review the diff for credentials and internal endpoints.
5. Validate YAML and Kubernetes compatibility when changing manifests.
6. Open a Pull Request with the exercise scope and validation performed.

## Pull Request Checklist

- [ ] Change is appropriate for an isolated lab.
- [ ] No real secrets or infrastructure identifiers were added.
- [ ] Manifest behavior changes are explicitly documented.
- [ ] Security notes are updated when needed.
- [ ] Validation commands and target Kubernetes version are recorded.
