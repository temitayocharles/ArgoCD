# ArgoCD

Argo CD bootstrap and application management repo for GitOps reconciliation.

## Start Here
- Core app definitions + values references: [platform-gitops](https://github.com/temitayocharles/platform-gitops)
- Helm chart catalog: [helm-charts](https://github.com/temitayocharles/helm-charts)
- Non-secret runtime configuration: [configurations](https://github.com/temitayocharles/configurations)
- Vault policies, roles, and path governance: [vault-ops](https://github.com/temitayocharles/vault-ops)

## What Lives Here
- Argo CD bootstrap manifests
- Project and application registration manifests
- Cluster-level Argo CD wiring

## Operating Flow
1. Commit GitOps changes in the source repos.
2. Argo CD reconciles desired state to the cluster.
3. Verify app status is `Synced` and `Healthy`.
4. For cleanup, delete Applications first, then dependent namespace workloads.

## Standards
- Prefer multi-source Helm applications (chart source + values source).
- Keep secrets in Vault, consume via External Secrets.
- Do not manually patch running resources in cluster unless break-glass.

## Docs
- [DEPENDENCY_LADDER.md](./DEPENDENCY_LADDER.md)
- [ARCHITECTURE.md](./ARCHITECTURE.md)
