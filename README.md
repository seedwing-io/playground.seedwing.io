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

## Continuous Deployment

The playground instance is automatically updated every night. Whenever a nightly or release build in
the seedwing-policy repository runs, it will trigger the 'deploy' workflow in this repository.

The deploy workflow will update the Kubernetes manifest in the deploy/server/deployment.yaml and
re-deploy that pointing to the updated image.

For this reason, some permissions are setup for the deployer serviceaccount to be able to apply the
new version.

## License

Apache License, Version 2.0 ([LICENSE](LICENSE))
