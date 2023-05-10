# sample gitops

This is a sample gitops repository for a project. It contains the following:

- A kustomize project to deploy a [postgres database](/infrastructure/database/README.md)
- A kustomize project to deploy a [react-app](/workloads/fronts/react-app/README.md)
- A kustomize project to deploy a [springboot backend](/workloads/backend/sb-api/README.md)

## Prerequisites

You should have a name space with your project name for example `my-namespace`.

You should change namespace name in `kustomization.yaml` file.

# Project structure

```
+-- infrastructure        // this folder contains all the infrastructure components
|   +-- flux
|   +-- database 
|   |   +-- base
|   |   +-- overlays
|   |   |   +-- dev
|   |   |   +-- ..
|   |   |   +-- prod
+-- workloads             // Contains all the workloads
|   +-- fronts            // Frontend workloads for example react-app, you can have as many directories as the number of front apps.
|   |   +-- react-app     // react-app deployment artifacts
|   |   |   +-- base      // Base artifacts for react-app
|   |   |   +-- overlays  // Overlays for react-app, overlay override the base artifacts according to the environment
|   |   |   |   +-- dev   // dev environment artifacts
|   |   |   |   +-- ..
|   +-- backend // this folder contains all the backend workloads
|   |   +-- sb-api
|   |   |   +-- base
|   |   |   +-- overlays
|   |   |   |   +-- dev
|   |   |   |   +-- ..

```

# sample gitops Tests

```

cd workloads/fronts/react-app/overlays/dev

kustomize build .

kustomize build . | kubectl apply -
```

# Sealing secrets

```
cat secrets.yaml | kubeseal --controller-namespace sealed-secrets --controller-name sealed-secrets --format yaml > ss-postgres.yaml
```