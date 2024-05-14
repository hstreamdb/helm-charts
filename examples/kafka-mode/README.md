# Kafka Mode

## External Access

To access the Kafka cluster from outside the Kubernetes cluster, currently HStreamDB only supports the NodePort service type. You can configure the chart values like this:

```yaml
clusterConfig:
  kafkaMode: true
  # For external access, set the following fields and uncomment them.
  externalAccess:
    accessType: nodeport
    advertisedAddresses:
      - instance: 0
        host: "hstream://localhost"
        port: 31092
        nodePort: 31092
      - instance: 1
        host: "hstream://localhost"
        port: 31093
        nodePort: 31093
      - instance: 2
        host: "hstream://localhost"
        port: 31094
        nodePort: 31094
```

Explanation:

1. `accessType`: The type of external access, currently only supports `nodeport`.
2. `advertisedAddresses`: The address information of each hserver. The `instance` field is the hserver ID, `host` is the advertised address, `port` is the advertised port, and `nodePort` is the NodePort port.

   The key point is that the `port` should be the same as the `nodePort`.

After deploying, you'll find several services base on your instance number, like:

```shell
hstreamdb-hserver-1                  NodePort    10.152.183.61    <none>        31093:31093/TCP              20d
hstreamdb-hserver-0                  NodePort    10.152.183.137   <none>        31092:31092/TCP              20d
hstreamdb-hserver-2                  NodePort    10.152.183.45    <none>        31094:31094/TCP              20d
```
