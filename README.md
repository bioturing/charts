# The Bioturing Library for Kubernetes

Popular applications, provided by Bioturing, ready to launch on Kubernetes using Kubernetes Helm.

## TL;DR

```shell
# Login to Bioturing's Helm chart repository
export HELM_EXPERIMENTAL_OCI=1
helm registry login -u your_account registry.bioturing.com

# Add repo charts
helm repo add bioturing https://charts.bioturing.com/bioturing/apps/
helm repo list
helm repo update

# Logout Bioturing's Helm chart repository
helm registry logout registry.bioturing.com

# Show information of helm chart name
helm show all bioturing/<helm chart name> --version <helm chart version>

# Action into helm chart name
helm template bioturing bioturing/<helm chart name> --version <helm chart version>
helm install bioturing bioturing/<helm chart name> --version <helm chart version>
helm upgrade bioturing bioturing/<helm chart name> --version <helm chart version>

# Example
helm template bioturing bioturing/bbrowserx --version 1.0.18
helm install bioturing bioturing/bbrowserx --version 1.0.18
```
