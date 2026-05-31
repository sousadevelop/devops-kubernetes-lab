# DevOps Kubernetes Lab

## Visão geral

Este repositório é um laboratório educacional para estudos de Kubernetes. Os manifests exploram recursos de workloads, serviços, configuração, persistência, probes, autoscaling e métricas de cluster.

O conteúdo não deve ser tratado como pacote pronto para produção. Alguns arquivos representam etapas alternativas de aprendizado.

## Objetivo do lab

Praticar conceitos fundamentais de Kubernetes usando um exemplo de sistema de notícias com três componentes:

- Banco de dados.
- Sistema interno de notícias.
- Portal de notícias.

## Recursos estudados

| Categoria | Recursos |
| --- | --- |
| Workloads | Pod, Deployment, ReplicaSet, StatefulSet |
| Rede | Service `ClusterIP`, Service `NodePort` |
| Configuração | ConfigMap |
| Persistência | PersistentVolume, PersistentVolumeClaim, StorageClass |
| Saúde | Liveness probe, readiness probe |
| Escala | HorizontalPodAutoscaler |
| Métricas | Metrics server, RBAC, APIService, ServiceAccount |

## Arquitetura

Fluxo conceitual:

1. O portal recebe acesso local por Service `NodePort`.
2. O portal referencia o sistema de notícias.
3. O sistema de notícias referencia o serviço do banco.
4. O StatefulSet demonstra montagem de PVCs para imagens e sessão.
5. O metrics-server apoia o exercício de HPA.
6. `stress.sh` gera requisições locais repetidas para observar comportamento em laboratório.

Consulte [ARCHITECTURE.md](../../ARCHITECTURE.md) e o [diagrama Mermaid](../../assets/diagrams/kubernetes-lab-architecture.mmd).

## Arquivos principais

| Arquivo | Papel no estudo |
| --- | --- |
| `db-noticias*.yaml` | Exemplos de Pod e Deployment para banco. |
| `sistema-noticias*.yaml` | Exemplos de Pod, Deployment e StatefulSet. |
| `portal-noticias*.yaml` | Exemplos de Pod, ReplicaSet, Deployment e HPA. |
| `svc-*.yaml` | Serviços para comunicação entre componentes. |
| `*-configmap.yaml` | Configurações dos componentes. |
| `pv.yaml`, `pvc*.yaml`, `sc.yaml` | Exercícios de persistência e storage class. |
| `components.yaml` | Recursos do metrics-server usados no lab. |
| `stress.sh` | Gerador local de requisições para estudo. |

## Setup local

Pré-requisitos recomendados:

- Cluster Kubernetes local e isolado.
- `kubectl`.
- Shell compatível com o script de stress, se necessário.

Antes de aplicar manifests:

1. Leia `SECURITY_NOTES.md`.
2. Escolha apenas os arquivos relevantes para o exercício.
3. Substitua valores fixos de laboratório.
4. Valide compatibilidade com sua versão do Kubernetes.
5. Use somente clusters descartáveis ou autorizados.

## Variáveis e configurações

Os manifests atuais usam ConfigMaps e valores fixos de lab. O arquivo `.env.example` serve apenas como referência para futuras automações.

Variáveis conceituais:

| Variável | Finalidade |
| --- | --- |
| `DB_ROOT_PASSWORD` | Placeholder para senha administrativa do banco no lab. |
| `DB_PASSWORD` | Placeholder para senha da aplicação no lab. |
| `PORTAL_SYSTEM_ENDPOINT` | Placeholder para endpoint do sistema usado pelo portal. |

Não use valores reais em commits.

## Segurança

Os manifests existentes incluem valores fixos que devem ser substituídos antes de reutilização. Credenciais devem migrar para Secrets ou gerenciador externo.

Consulte [SECURITY.md](../../SECURITY.md) e [SECURITY_NOTES.md](../../SECURITY_NOTES.md).

## Limitações conhecidas

- Alguns manifests precisam de revisão de compatibilidade.
- Há arquivos alternativos para o mesmo componente.
- Os manifests não formam necessariamente um bundle único.
- O lab não foi certificado para produção.

## Próximos passos

Consulte [ROADMAP.md](../../ROADMAP.md).
