# HStreamDB Chart

This document describes the configuration options of the HStreamDB chart.

## Values

Below table lists the configurable parameters of the HStreamDB chart and their default values.

> The following table focuses on cluster-related configuration parameters.
> For example, some parameters related to basic chart information may not be listed below.

| Parameter                       | Description                                                                           | Default               |
| ------------------------------- | ------------------------------------------------------------------------------------- | --------------------- |
| `image.repository`              | Image repository. Can be customized to a private registry.                            | `hstreamdb/hstreamdb` |
| `image.tag`                     | Image tag.                                                                            | `rqlite`              |
| `image.pullPolicy`              | Image pull policy for all containers.                                                 | `IfNotPresent`        |
| `clusterConfig`                 | HStreamDB cluster configuration.                                                      |                       |
| `clusterConfig.logDeviceConfig` | LogDevice configuration for HStore component. <https://logdevice.io/docs/Config.html> |                       |
