# HStreamDB Chart

This document describes the configuration options of the HStreamDB chart.

## Values

Below table lists the configurable parameters of the HStreamDB chart and their default values.

> The following table focuses on cluster-related configuration parameters.
> For example, some parameters related to basic chart information may not be listed below.

| Parameter                       | Description                                                                             | Default                           |
| ------------------------------- | --------------------------------------------------------------------------------------- | --------------------------------- |
| `image.repository`              | Image repository. Can be customized to a private registry.                              | `hstreamdb/hstreamdb`             |
| `image.tag`                     | Image tag.                                                                              | `rqlite`                          |
| `image.pullPolicy`              | Image pull policy for all containers.                                                   | `IfNotPresent`                    |
| `clusterConfig`                 | HStreamDB cluster configuration.                                                        |                                   |
| `clusterConfig.logDeviceConfig` | LogDevice configuration for HStore component. <https://logdevice.io/docs/Config.html>   |                                   |
| `hserver.name`                  | HServer component name.                                                                 | `hserver`                         |
| `hserver.replicaCount`          | HServer component replica count.                                                        | `3`                               |
| `hserver.container`             | HServer container configuration. <https://kubernetes.io/docs/concepts/containers/>      |                                   |
| `storageClassName`              | Global `StorageClass` for HStore and HMeta components.                                  | `standard`                        |
| `hstore.name`                   | HStore component name.                                                                  | `hstore`                          |
| `hstore.replicaCount`           | HStore component replica count.                                                         | `3`                               |
| `hstore.storage`                | Storage size allocated to each HStore instances.                                        | `1Gi`                             |
| `hstore.container`              | HStore container configuration. <https://kubernetes.io/docs/concepts/containers/>       |                                   |
| `adminServer.name`              | AdminServer component name.                                                             | `admin-server`                    |
| `adminServer.replicaCount`      | AdminServer component replica count.                                                    | `1`                               |
| `adminServer.container`         | AdminServer container configuration. <https://kubernetes.io/docs/concepts/containers/>  |                                   |
| `hmeta.name`                    | HMeta component name.                                                                   | `hmeta`                           |
| `hmeta.replicaCount`            | HMeta component replica count.                                                          | `3`                               |
| `hmeta.storage`                 | Storage size allocated to each HMeta instances.                                         | `1Gi`                             |
| `hmeta.rqlite.version`          | Specify rqlite version.                                                                 | `7.21.4`                          |
| `console.enabled`               | Whether to enable Console component.                                                    | `true`                            |
| `console.name`                  | Console component name.                                                                 | `console`                         |
| `console.image`                 | Console component image.                                                                | `hstreamdb/hstream-kafka-console` |
| `console.replicaCount`          | Console component replica count.                                                        | `1`                               |
| `console.container`             | Console container configuration. <https://kubernetes.io/docs/concepts/containers/>      |                                   |
| `console.servicePorts`          | Specify node ports for Console component. See [values.yaml](./values.yaml) for details. | `31777`                           |

## Common usage

### Provide storage

Most of time, you need to specify the `storageClassName` value to provide storage for HStreamDB cluster. For example,
below command will install HStreamDB cluster under microk8s with hostpath-storage enabled.

```sh
helm install hstreamdb hstreamdb/hstreamdb -n hstreamdb --create-namespace --set storageClassName=microk8s-hostpath
```

### Integrate with Prometheus

HStreamDB cluster provides metrics for Prometheus. View [Prometheus integration](./prometheus.md) for details.
