# playground.seedwing.io

Manifests for running playground.seedwing.io

## Prerequisites

* [Kubernetes](k8s.io) ([OpenShift](openshift.com) if you want to expose using the Route resource)
* [Cert Manager](https://cert-manager.io/)

## Deploying

```bash
oc apply -f deploy/
```

## License

Apache License, Version 2.0 ([LICENSE](LICENSE))
