# DevOps Kubernetes Lab

## Vue d'ensemble

Ce dépôt est un laboratoire pédagogique Kubernetes consacré aux workloads, services, configurations, volumes persistants, probes, autoscaling et métriques du cluster.

Les manifests sont des supports d'étude, pas un package prêt pour la production.

## Objectif

Pratiquer les fondamentaux Kubernetes avec un exemple de système d'actualités composé d'une base de données, d'un système interne et d'un portail.

## Sujets

- Pods, Deployments, ReplicaSet et StatefulSet.
- Services `ClusterIP` et `NodePort`.
- ConfigMaps.
- PersistentVolume, PersistentVolumeClaim et StorageClass.
- Probes liveness et readiness.
- HorizontalPodAutoscaler.
- Ressources metrics-server et RBAC.

## Architecture

Le portail accède au système d'actualités, qui communique avec le service de base de données. Les PVC démontrent les montages persistants et metrics-server soutient l'exercice d'autoscaling.

Voir [ARCHITECTURE.md](../../ARCHITECTURE.md) et le [diagramme Mermaid](../../assets/diagrams/kubernetes-lab-architecture.mmd).

## Setup local

Utilisez un cluster Kubernetes local isolé et `kubectl`. Avant d'appliquer les manifests :

1. Lisez `SECURITY_NOTES.md`.
2. Choisissez seulement les fichiers nécessaires.
3. Remplacez les valeurs fixes du lab.
4. Vérifiez la compatibilité avec votre version Kubernetes.

## Sécurité

Les manifests actuels contiennent des valeurs fixes de laboratoire et ne doivent pas être réutilisés en production. Déplacez les identifiants vers des Secrets ou un gestionnaire externe.

Voir [SECURITY.md](../../SECURITY.md), [SECURITY_NOTES.md](../../SECURITY_NOTES.md) et [ROADMAP.md](../../ROADMAP.md).
