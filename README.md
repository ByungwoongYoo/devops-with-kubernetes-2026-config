# DevOps with Kubernetes 2026 — configuration repository

This repository contains only Kubernetes/GitOps desired state for Exercise 4.10 and later.

Application source and image builds live in:
`ByungwoongYoo/devops-with-kubernetes-2026`

ArgoCD watches the overlays in this repository:
- `overlays/staging`
- `overlays/production`

The application repository CI builds and publishes images, then updates only the image references here. CI does not run `kubectl apply`.

## Secret boundary

`project-postgres-secret` is intentionally not committed. It must be provisioned out-of-band in each target namespace before ArgoCD syncs the workloads.
