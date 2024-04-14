## Netg Test
1. Set up and deploy ingress-controller of choice
2. Setup Flux
3. Commit kustomizations on flux to install

    a. ingress controller (any of your choice, i like traefik)

    b. deploy grafana on it, (https://artifacthub.io/packages/helm/grafana/grafana)
    
    c. make sure grafana has valid certificate using HTTP acme challenge

## Directory Structure
```
clusters
    └── joseph-lab-cluster
        ├── cert-manager
        │   ├── cluster-issuer-production.yaml
        │   ├── cluster-issuer-staging.yaml
        │   └── kustomization.yaml
        ├── flux-system
        │   ├── gotk-components.yaml
        │   ├── gotk-sync.yaml
        │   └── kustomization.yaml
        └── helm
            ├── releases
            │   ├── cert-manager_v1.14.4.yaml
            │   ├── grafana_v7.3.8.yaml
            │   └── traefik_v27.0.2.yaml
            └── repostories
                ├── grafana.yaml
                ├── jetstack.yaml
                └── traefik.yaml
```

## Prerequisites
- Flux. See [documentation](https://fluxcd.io/flux/installation/) for more information
