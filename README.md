# Repository Description

This repository is a mono repo that contains Helm charts for applications deployed using the GitOps method and the ArgoCD tool.

## Directory Structure

- `base`: Contains charts that are common between project environments, such as the `base-webapp` chart.
- Environment directories (e.g., `prd`, `staging`, `dev`): Each environment directory contains an `apps` directory, which contains ArgoCD application CRDs for deploying the required apps in that environment. The other directories in each environment directory are Helm charts for the necessary applications.

## Deployment Process

To deploy a new app in any environment:

1. Create an application CRD in the corresponding environment's `apps` directory.
2. The directories are watched using the ArgoCD [app of apps](https://argo-cd.readthedocs.io/en/stable/operator-manual/cluster-bootstrapping/#app-of-apps-pattern) pattern, and the applications inside them are automatically deployed.

Please refer to the individual Helm charts and ArgoCD documentation for more details on deploying and managing applications in this repository.
