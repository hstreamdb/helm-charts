# Append a sink-es logger container

This guide explains how to append a logger container to sink-es connector.

## Steps

1. Clone the hstreamdb Helm charts repository:

   ```shell
   git clone https://github.com/hstreamdb/helm-charts.git
   ```

2. Navigate to the `sink-es-with-logger` example directory:

   ```shell
   cd helm-charts/examples/sink-es-with-logger
   ```

3. Edit and apply the `sink-es.yaml` file:

   ```shell
   kubectl apply -f sink-es.yaml
   ```
