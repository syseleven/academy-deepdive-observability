# Linkerd and Prometheus

**This is required only once in the cluster.**

## Have Prometheus scrape Linkerd metrics

* Configure Linkerd to export metrics to prometheus

  ```shell
  linkerd viz install -f linkerd-use-prometheus.yaml | kubectl apply -f -
  ```

* Start Linkerd dashboard if you haven't already done

  ```shell
  linkerd viz dashboard
  ```

* Apply a podMonitor so Prometheus can pick up the metrics

  ```shell
  kubectl apply -f podmonitor.yaml
  ```

## Visualize Linkerd metrics with Grafana

* Import official linkerd Grafana dashboards

  https://github.com/linkerd/linkerd2/tree/main/grafana/dashboards

  https://grafana.com/orgs/linkerd/dashboards
