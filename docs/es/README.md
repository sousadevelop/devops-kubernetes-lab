# DevOps Kubernetes Lab

## Visión general

Este repositorio es un laboratorio educativo de Kubernetes para estudiar workloads, servicios, configuración, persistencia, probes, autoscaling y métricas de cluster.

Los manifests son materiales de aprendizaje, no un paquete listo para producción.

## Objetivo

Practicar fundamentos de Kubernetes con un ejemplo de sistema de noticias compuesto por una base de datos, un sistema interno y un portal.

## Temas

- Pods, Deployments, ReplicaSet y StatefulSet.
- Servicios `ClusterIP` y `NodePort`.
- ConfigMaps.
- PersistentVolume, PersistentVolumeClaim y StorageClass.
- Probes liveness y readiness.
- HorizontalPodAutoscaler.
- Recursos metrics-server y RBAC.

## Arquitectura

El portal accede al sistema de noticias, el sistema se comunica con el servicio de base de datos, los PVC demuestran montajes persistentes y metrics-server apoya el ejercicio de autoscaling.

Consulta [ARCHITECTURE.md](../../ARCHITECTURE.md) y el [diagrama Mermaid](../../assets/diagrams/kubernetes-lab-architecture.mmd).

## Setup local

Usa un cluster Kubernetes local aislado y `kubectl`. Antes de aplicar manifests:

1. Lee `SECURITY_NOTES.md`.
2. Elige solo los archivos requeridos por el ejercicio.
3. Sustituye valores fijos del lab.
4. Valida compatibilidad con tu versión de Kubernetes.

## Seguridad

Los manifests actuales contienen valores fijos de laboratorio y no deben reutilizarse en producción. Mueve credenciales a Secrets o a un gestor externo.

Consulta [SECURITY.md](../../SECURITY.md), [SECURITY_NOTES.md](../../SECURITY_NOTES.md) y [ROADMAP.md](../../ROADMAP.md).
