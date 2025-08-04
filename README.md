# Uptime-Kuma Helm Chart

This is an **enterprise-grade, Kubernetes-ready Helm chart** for deploying [Uptime-Kuma](https://github.com/louislam/uptime-kuma), a self-hosted monitoring and status page system.

> This Helm chart is designed with production-readiness, configurability, and extensibility in mind.

---

## Features

- Deploys Uptime-Kuma as a Stateful workload using Kubernetes best practices.
- Secure secret management via Kubernetes-native mechanisms.
- Supports persistent storage for data durability.
- Configurable ingress with TLS and annotations for Ingress controllers.
- Easy override of values using `values.yaml` or CLI.
- Works seamlessly with GitOps tools like ArgoCD, FluxCD.
- Lint-tested and CI-ready.

---

## Project Structure

uptime-kuma/
├── Chart.yaml # Helm chart metadata
├── values.yaml # Default config values
├── templates/
│ ├── deployment.yaml # Core app deployment
│ ├── service.yaml # Kubernetes service
│ ├── pvc.yaml # PersistentVolumeClaim
│ └── ingress.yaml # Optional ingress
└── README.md


---

## Requirements

- Kubernetes v1.20+
- Helm v3.7+
- Persistent Volume support in your cluster
- Optional: Ingress Controller (NGINX, Traefik, etc.)

---

## Installation

### Add Repo (Optional if hosted):
```bash
helm repo add uptime-kuma https://yourusername.github.io/helm-uptime-kuma
helm install my-uptime uptime-kuma/uptime-kuma

helm install my-uptime ./uptime-kuma

Configuration
The chart is fully configurable via values.yaml or --set CLI flags.

Persistence
persistence:
  enabled: true
  storageClass: "standard"
  accessMode: ReadWriteOnce
  size: 1Gi

Ingress
ingress:
  enabled: true
  className: "nginx"
  annotations: {}
  hosts:
    - host: uptime.example.com
      paths:
        - path: /
          pathType: Prefix
  tls:
    - hosts:
        - uptime.example.com
      secretName: uptime-kuma-tls
Ports
| Port | Description        |
| ---- | ------------------ |
| 3001 | Uptime-Kuma Web UI |

Upgrading
To upgrade the chart while retaining custom values:
helm upgrade my-uptime ./uptime-kuma -f my-values.yaml

Best Practices Followed

Standard Helm directory structure
Immutability and separation of concerns
Values-driven customization
Compatible with CI/CD and GitOps workflows
Minimal and production-ready

Use Cases
This chart is ideal for:

Self-hosting uptime monitors in dev/staging/prod
GitOps deployment via ArgoCD or Flux
Platform teams standardizing app deployment
Open-source showcase for Helm/K8s expertise

Troubleshooting
Check persistent volume events if data isn’t saving.
Use helm template to debug rendered manifests.
Use kubectl describe for PVC, Pod, and Service issues.

 Author & Maintainer
Kazeem Mohammed
DevOps / SRE / Platform Engineer
LinkedIn: 
GitHub: @

Contributing
PRs and suggestions are welcome!
Fork the repo
Clone and test changes locally
Run helm lint before committing
Submit a pull request

References
Uptime-Kuma GitHub: https://github.com/louislam/uptime-kuma
Helm Docs: https://helm.sh/docs/
Kubernetes Docs: https://kubernetes.io/docs/
