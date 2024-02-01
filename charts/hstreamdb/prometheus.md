# Integrate with Prometheus

HStreamDB cluster provides metrics for Prometheus. You can use the following command to install Prometheus:

> Below commands are copied from [kube-prometheus-stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack).
>
> For more install instructions, please refer to the official document.

```sh
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

# Install Prometheus
helm install [RELEASE_NAME] prometheus-community/kube-prometheus-stack
```

## Configure Prometheus

Here is an example of Prometheus configuration:

```yaml
prometheus:
  prometheusSpec:
    additionalScrapeConfigs:
      - job_name: "hstream_metrics"
        scrape_interval: "5s"
        static_configs:
          - targets:
              - "hstreamdb-internal-hserver.hstreamdb:9700"
            labels:
              monitor: "hstream-monitor"
```

The target address indicates the internal address of HStreamDB cluster.

You can customize the target address base on your cluster configuration, and keep
the other configurations unchanged.
