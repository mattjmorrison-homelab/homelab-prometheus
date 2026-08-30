# k8s-prometheus

Prometheus deployment for the homelab k3s cluster, managed via ArgoCD.

Scrapes and stores metrics from Node Exporter and Kube State Metrics. Fires alerts to Alertmanager based on configured rules.

## Tests

```
make check
```

Runs the bats suite in `manifests/tests` against `helm template` output — validates scrape config content and alert rule definitions with no cluster required.

## CI

Pull requests run `mattjmorrison-homelab/actions-helm` (helm lint, `helm template`, and a server-side dry-run) via `.github/workflows/check.yml`. This is separate from `make check` — CI does not run the bats suite; that only runs locally.

---

[Homelab Docs](https://github.com/mattjmorrison/homelab/blob/main/docs/INDEX.md)
