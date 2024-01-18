# Override HServer Config

This guide explains how to override the configuration of HServer.

## Prerequisites

Before you begin, make sure you have the following:

- A running Kubernetes cluster
- Helm installed on your local machine

## Steps

1. Clone the hstreamdb Helm charts repository:

   ```shell
   git clone https://github.com/hstreamdb/helm-charts.git
   ```

2. Navigate to the `override-hserver-config` example directory:

   ```shell
   cd helm-charts/examples/override-hserver-config
   ```

3. Edit and apply the custom configuration first:

   ```sh
   vi hserver-custom-config.yaml
   kubectl apply -f hserver-custom-config.yaml
   ```

4. Install HStreamDB with the custom configuration:

   ```shell
   helm install hstreamdb hstreamdb/hstreamdb -f values.yaml
   ```
