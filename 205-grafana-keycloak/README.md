# Grafana Keycloak Auth

## Connect Grafana with Keycloak

* Obtain a client secret from your Keycloak client Grafana should connect to

* Edit the file `prom-values.yaml` and adjust the `client_secret` accordingly

* Update Grafana with the new settings

```shell
helm upgrade --install --namespace monitoring -f prom-values.yaml --version 45.6.0 prom prometheus-community/kube-prometheus-stack
```

* Log in to Grafana web interface
  * Visit: https://grafana.workshop.metakube.org
  * Use the Keycloak login button below the login form
  * A user-account is provided by the trainer of this workshop
