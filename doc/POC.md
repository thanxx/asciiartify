## Install K3D
```bash
curl -s https://raw.githubusercontent.com/k3d-io/k3d/main/install.sh | bash
```

## Create cluster
```bash
k3d cluster create
```

## Install ArgoCD
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Port-forward ArgoCD service

Wait for all pods have status Running

```bash
k port-forward -n argocd svc/argocd-server 33880:http
```

## Open ArgoCD web interface
```bash
https://127.0.0.1:33880/
```
