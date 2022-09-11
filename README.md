Bioturing HELM charts
# [helm-chart](https://github.com/bioturing/helmchart)

## Usage

This Helm chart repository enables you to install Bioturing's softwares
Helm chart directly from it into your Kubernetes cluster. Please refer to the
[Bioturing Helm chart documentation](https://github.com/bioturing/helmchart)
the additional details required.

```shell
# Login to Bioturing's Helm chart repository
export HELM_EXPERIMENTAL_OCI=1
helm registry login -u your_account registry.bioturing.com

# Logout Bioturing's Helm chart repository
helm registry logout registry.bioturing.com

# Show information of helm chart name
helm show all oci://registry.bioturing.com/helm-charts/<helm chart name> --version <helm chart version>

# Action into helm chart name
helm template myrelease oci://registry.bioturing.com/helm-charts/<helm chart name> --version <helm chart version>
helm install myrelease oci://registry.bioturing.com/helm-charts/<helm chart name> --version <helm chart version>
helm upgrade myrelease oci://registry.bioturing.com/helm-charts/<helm chart name> --version <helm chart version>

# Example
helm template myrelease oci://registry.bioturing.com/helm-charts/bbrowserx --version 1.0.0
helm install myrelease oci://registry.bioturing.com/helm-charts/bbrowserx --version 1.0.0
```
