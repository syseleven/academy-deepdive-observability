# Linkerd and Prometheus

**This is required only once in the cluster.**

## Have Prometheus scrape Linkerd metrics

* Configure Linkerd to export metrics to prometheus

  `linkerd viz install -f linkerd-use-prometheus.yaml | kubectl apply -f -`

* Start Linkerd dashboard if you haven't already done

  `linkerd viz dashboard`

* Apply a podMonitor so Prometheus can pick up the metrics

  `kubectl apply -f podmonitor.yaml`

## Visualize with Grafana

* import linkerd grafana dashboards

https://github.com/linkerd/linkerd2/tree/main/grafana/dashboards
