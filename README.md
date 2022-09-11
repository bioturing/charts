Bioturing HELM charts
# [helm-chart](https://github.com/bioturing/helmchart)

## Usage

This Helm chart repository enables you to install Bioturing's softwares
Helm chart directly from it into your Kubernetes cluster. Please refer to the
[Bioturing Helm chart documentation](https://github.com/bioturing/helmchart)
the additional details required.

```shell
# Let helm the command line tool know about a Helm chart repository
# that we decide to name bioturing.
helm repo add bioturing oci://registry.bioturing.com/helm-charts/
helm repo update

# Simplified example on how to install a Helm chart from a Helm chart repository
# named bioturing. See the Helm chart's documentation for additional details
# required.
helm install bioturing/<helm chart name> --version <helm chart version>
```

## Refers

[Kubernetes]: https://kubernetes.io
[Helm]: https://helm.sh