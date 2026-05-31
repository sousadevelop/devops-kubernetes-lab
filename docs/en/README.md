# DevOps Kubernetes Lab

## Overview

This repository is an educational Kubernetes laboratory for workloads, services, configuration, persistence, probes, autoscaling, and cluster metrics.

The manifests are learning materials, not a production-ready deployment package.

## Lab Goal

Practice Kubernetes fundamentals with a news system example composed of a database, an internal news system, and a portal.

## Topics

- Pods, Deployments, ReplicaSet, and StatefulSet.
- `ClusterIP` and `NodePort` services.
- ConfigMaps.
- PersistentVolume, PersistentVolumeClaim, and StorageClass.
- Liveness and readiness probes.
- HorizontalPodAutoscaler.
- Metrics server resources and RBAC.

## Architecture

The portal accesses the news system, the news system accesses the database service, PVCs demonstrate persistent mounts, and metrics server resources support autoscaling exercises.

See [ARCHITECTURE.md](../../ARCHITECTURE.md) and the [Mermaid diagram](../../assets/diagrams/kubernetes-lab-architecture.mmd).

## Local Setup

Use an isolated local Kubernetes cluster and `kubectl`. Before applying manifests:

1. Read `SECURITY_NOTES.md`.
2. Choose only the files required for the exercise.
3. Replace fixed lab values.
4. Validate compatibility with your Kubernetes version.

## Security

Existing manifests contain fixed lab values and must not be reused in production. Move credentials to Secrets or an external secret manager.

See [SECURITY.md](../../SECURITY.md), [SECURITY_NOTES.md](../../SECURITY_NOTES.md), and [ROADMAP.md](../../ROADMAP.md).
