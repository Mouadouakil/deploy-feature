# Sample Gitops Project

This is a sample gitops repository for a project. It contains the following:

- A kustomize project to deploy a [react-app](/workloads/fronts/react-app/README.md)
- A kustomize project to deploy a [springboot backend](/workloads/backend/sb-api/README.md)
- A flux project to deploy the gitops project [flux](/infrastructure/flux/README.md)
- A kustomize project to deploy a [postgres database](/infrastructure/database/README.md)

## Prerequisites

You should have a name space with your project name for example `my-namespace`.

You should change namespace name in `kustomization.yaml` file.

# Project structure


# sample gitops Tests

```

cd workloads/fronts/react-app/overlays/dev

kustomize build .

kustomize build . | kubectl apply -
```
