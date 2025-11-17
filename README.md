# ArgoCD GitOps - Portal Mamaloo

Repositório GitOps para gerenciar deployments da aplicação Portal Mamaloo usando ArgoCD.

## Estrutura

```
argocd-gitops/
├── apps/
│   ├── mamaloo-dev.yaml      # Application dev
│   └── mamaloo-prod.yaml     # Application prod
└── README.md
```

## Applications

- **mamaloo-dev**: Deploy da aplicação em ambiente de desenvolvimento
- **mamaloo-prod**: Deploy da aplicação em ambiente de produção

Ambas apontam para o Helm chart em: `https://github.com/Analarie/Portal-Mamaloo-desenvolvimento/helm/mamaloo-app`

## Deploy

```bash
# Aplicar applications
kubectl apply -f apps/mamaloo-dev.yaml
kubectl apply -f apps/mamaloo-prod.yaml

# Ver status
kubectl get applications -n argocd
```

## Acesso ArgoCD UI

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Acesse: https://localhost:8080
