# BioTuring Library for Kubernetes

Popular applications, provided by [BioTuring](https://bioturing.com), ready to launch on Kubernetes using Kubernetes Helm.

## TL;DR

```shell
# Add repo charts
helm repo add bioturing https://bioturing.github.io/charts/apps/
helm repo update
helm search repo bioturing

# Login BioTuring registry
helm registry login -u admin registry.bioturing.com

# Show information of helm chart name
helm show all bioturing/<helm chart name> --version <helm chart version>

# Action into helm chart name
helm template bioturing bioturing/<helm chart name> --version <helm chart version>
helm install bioturing bioturing/<helm chart name> --version <helm chart version>
helm upgrade bioturing bioturing/<helm chart name> --version <helm chart version>
```

## Installation guide

For simple installation

[Use this script](https://github.com/bioturing/installation)

For manual installation

[Helm chart Values](https://github.com/bioturing/installation)

```
# Example
BBTOKEN="USE TOKEN OBTAINED FROM BIOTURING"
SSLCRT="base64 -w 0 ./bioturing.com.crt" # <- (REPLACE THIS WITH A PATH TO YOUR CRT CERTFICATE)
SSLKEY="base64 -w 0 ./bioturing.com.key" # <- (REPLACE THIS WITH A PATH TO YOUR KEY)
ADMIN_USERNAME="admin"
ADMIN_PASSWORD="admin" # <- (CHANGE YOUR PASSWORD IF NECESSARY)
USELETSENCRYPT="false"
SVHOST="k8stest.bioturing.com" # <- (CHANGE THIS TO YOUR K8S INGRESS DOMAIN)
APP_DATA_SIZE="50Gi" # <- (CHANGE THIS TO YOUR APP-PVC SIZE)
USER_DATA_SIZE="100Gi" # <- (CHANGE THIS TO YOUR USER-PVC SIZE)
SHM_SIZE="64Gi" # <- (CHANGE THIS TO YOUR SHM SIZE)
CHART_VERSION="1.0.24" # <- (CHANGE IT IF NECESSARY)
LC_ALL="C.UTF-8" # <- (CHANGE IT IF NECESSARY)
LC_LANG="C.UTF-8" # <- (CHANGE IT IF NECESSARY)

helm upgrade --install --set secret.data.bbtoken="${BBTOKEN}" \
  --set secret.data.domain="${SVHOST}" \
  --set secret.server.certificate="${SSLCRT}" \
  --set secret.server.key="${SSLKEY}" \
  --set secret.server.useletsencrypt="${USELETSENCRYPT}" \
  --set secret.server.lcall="${LC_ALL}" \
  --set secret.server.lclang="${LC_LANG}" \
  --set secret.admin.username="${ADMIN_USERNAME}" \
  --set secret.admin.password="${ADMIN_PASSWORD}" \
  --set persistence.dirs.app.size="${APP_DATA_SIZE}" \
  --set persistence.dirs.user.size="${USER_DATA_SIZE}" \
  --set persistence.dirs.shm.size="${SHM_SIZE}" \
  bioturing bioturing/ecosystem --version ${CHART_VERSION}
```

## Before you begin

### Prerequisites

1. Kubernetes 1.19+
2. Helm 3.2.0+

### Setup a Kubernetes Cluster

For setting up Kubernetes on your cloud platforms or bare-metal servers refer to the Kubernetes [getting started guide](https://kubernetes.io/docs/setup/).

### Install Helm

Helm is a tool for managing Kubernetes charts. Charts are packages of pre-configured Kubernetes resources.

To install Helm, refer to the [Helm install guide](https://github.com/helm/helm#install) and ensure that the helm binary is in the PATH of your shell.

### Add Repo

The following command allows you to download and install all the charts from this repository:

```
helm repo add bioturing https://bioturing.github.io/charts/apps
```

### Using Helm

Once you have installed the Helm client, you can deploy a Bioturing Helm Chart into a Kubernetes cluster.

Please refer to the [Quick Start guide](https://helm.sh/docs/intro/quickstart/) if you wish to get running in just a few commands, otherwise the [Using Helm Guide](https://helm.sh/docs/intro/using_helm/) provides detailed instructions on how to use the Helm client to manage packages on your Kubernetes cluster.

Useful Helm Client Commands:

1. View available charts: helm search repo
2. Install a chart: helm install my-release bioturing<package-name>
3. Upgrade your application: helm upgrade

### License

Copyright © 2022 Bioturing

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

```
http://www.apache.org/licenses/LICENSE-2.0
```

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.