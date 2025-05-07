# Circumplex‑AI Security Hardening Pack

This bundle implements the mitigations from the security assessment:

* **Kubernetes** least‑privilege RBAC, NetworkPolicy, PodSecurity
* **Redis** TLS/ACL configuration
* **CI/CD** Trivy & Cosign gate, Pytest 100 % coverage gate
* **Kustomize** overlay for blue/green rollout
* **Terraform** module for namespace + secrets + admission control

## Quick start

```bash
# 1. Apply RBAC + NetworkPolicy
kubectl apply -k k8s/overlays/prod

# 2. Bootstrap Redis with TLS
kubectl apply -f redis/redis-config.yaml
kubectl apply -f redis/redis-sts.yaml

# 3. Enable CI gates (GitHub)
#   commit .github/workflows/...
```
