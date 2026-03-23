# k3s-gitops

GitOps repository for my homelab K3s cluster.
ArgoCD watches this repo as the single source of truth for everything deployed on the cluster.

## What This Is
All Kubernetes manifests live here. No manual kubectl applies in production.
ArgoCD pulls from this repo and reconciles cluster state automatically.

## Cluster
- 3-node K3s cluster (1 control plane, 2 workers)
- Traefik ingress with TLS via cert-manager and Let's Encrypt
- ArgoCD for GitOps continuous delivery
- Prometheus + Grafana for observability

## Structure
\`\`\`
k3s-gitops/
  apps/
    nadland/        → nadLand project manifests
  infrastructure/
    cert-manager/
    monitoring/
    argocd/
\`\`\`

## Projects Running on This Cluster
| Project | Repo | Description |
|---|---|---|
| nadLand | [nadland-frontend](https://github.com/ShalevNatan/nadland-frontend) | Hybrid cloud portfolio project |
