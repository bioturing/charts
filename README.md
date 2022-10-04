Bioturing HELM charts
# [helm-chart](https://github.com/bioturing/helmchart)

## Usage

This Helm chart repository enables you to install Bioturing's softwares
Helm chart directly from it into your Kubernetes cluster. Please refer to the
[Bioturing Helm chart documentation](https://github.com/bioturing/helmchart)
the additional details required.

```shell
# Prior to Helm v3.8.0, OCI support was considered experimental and needed to be enabled. As of v3.8.0 it is enabled by default.
# Login to Bioturing's Helm chart repository
export HELM_EXPERIMENTAL_OCI=1
helm registry login -u your_account registry.bioturing.com

# Add repo charts
helm repo add bioturing https://github.com/bioturing/helmchart/apps/
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
