# helm-charts
Helm charts for i4Trust project

Repository for providing [HELM Charts](https://helm.sh/) for [i4Trust](https://i4Trust.org) experimentation framework. The charts can be installed into
 [Kubernetes](https://kubernetes.io/) with [helm3](https://helm.sh/docs/) .

For further information, look into the individual chart-readme's.

## Add Repo

To make use of the charts, you may add the repository: 

```helm repo add i4trust https://i4trust.github.io/helm-charts```

## Install

After the repo is added all charts can be installed via:

```helm install <RELEASE_NAME> i4trust/<CHART_NAME>```
