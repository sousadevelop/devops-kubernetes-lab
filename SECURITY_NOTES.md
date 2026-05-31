# Security and Compatibility Notes

This document records findings from the documentation review without repeating sensitive-looking values.

## Security Findings

- Database credentials are stored as plain text in ConfigMaps.
- The portal configuration contains an environment-specific internal endpoint.
- The metrics server example disables TLS verification for an API service connection.
- NodePort services expose fixed ports for lab access.
- The load helper sends repeated local requests and should run only in an isolated lab.

## Compatibility Findings

- The HorizontalPodAutoscaler manifest uses an API group spelling that should be reviewed before application.
- The HPA target name should be checked against the Deployment name used by the portal workload.
- The StatefulSet references a ConfigMap name that should be checked against the available ConfigMap file.
- Some metrics server resources use older API versions or image locations.
- Some manifests represent alternative learning stages and should not be applied as one bundle without review.

## Recommended Future Remediation

- Introduce sanitized templates with placeholders.
- Move credentials to Kubernetes Secrets or an external secret manager.
- Replace environment-specific endpoints with service discovery where appropriate.
- Validate manifests with the Kubernetes version used by the lab.
- Separate exercises by topic or stage after confirming the intended learning sequence.

No existing manifest was modified during this documentation pass.
