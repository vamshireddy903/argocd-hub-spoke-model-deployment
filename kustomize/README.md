kustomize/
├── base/
│   ├── deployment.yaml
│   ├── service.yaml          # optional, if you expose your app
│   └── kustomization.yaml
│
└── overlay/
    ├── dev/
    │   └── kustomization.yaml
    │
    ├── staging/
    │   └── kustomization.yaml
    │
    └── production/
        └── kustomization.yaml
