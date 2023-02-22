# playground.seedwing.io

Manifests for running playground.seedwing.io

## Prerequisites

* [Kubernetes](k8s.io) ([OpenShift](openshift.com) if you want to expose using the Route resource)
* [Cert Manager](https://cert-manager.io/)

## Deploying

```bash
oc apply -f deploy/server
```

## Monitoring

Monitoring requires the [prometheus-operator](https://github.com/prometheus-operator/prometheus-operator) and [grafana-operator](https://github.com/grafana-operator/grafana-operator) to be installed. To configure monitoring:

```bash
oc apply -f deploy/prometheus
oc apply -f deploy/grafana
```


## License

Apache License, Version 2.0 ([LICENSE](LICENSE))
