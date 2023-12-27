# HStreamDB Helm Charts

Helm charts for HStreamDB.

## Overview

The main purpose of this repository is to provide a simple way to deploy HStreamDB on Kubernetes.
After deploying [hstream-operator](https://github.com/hstreamdb/hstream-operator), you can use this chart to deploy HStreamDB cluster.

## Usage

[Helm](https://helm.sh) must be installed to use the charts. Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```sh
helm repo add hstreamdb https://hstreamdb.github.io/helm-charts
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages. You can then run `helm search repo hstreamdb`
to see the charts.

To install the hstreamdb chart:

```sh
helm install hstreamdb hstreamdb/hstreamdb
```

To uninstall the chart:

```sh
helm delete hstreamdb
```

## License

HStreamDB helm charts are licensed under the [Apache License 2.0](./LICENSE).
