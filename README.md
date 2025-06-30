# Grafana Dashboard for Vault

This repository contains a Grafana Dashboard for Hashicorp Vault Enterprise with Disaster Recovery. It gives a overview about the status of your Hashicorp Vault Cluster, the utilization and health.

## Features

- Cluster-Health Monitoring (DR, Node-Status, WAL, Failure Tolerance)
- Identity (Entities by Method and Namespaces)
- Vault and Raft Leadership
- Token Statistics (Namespace,TTL, Auth Methods)
- Raft Performance

## Prerequisites

Before using the Grafana Dashboard, ensure you have the following prerequisites installed:

- [Grafana](https://grafana.com/get)
- [Prometheus](https://prometheus.io/download/)
- [Hashicorp Vault with telemetry 1.14+](https://developer.hashicorp.com/vault/install)

## Installation

1. Clone the repository:

```bash
    git clone https://github.com/adfinis/grafana-dashboard-vault
```
or 
```bash
    curl -LJO https://github.com/adfinis/grafana-dashboard-vault/blob/main/vault_dashboard.json
```

2. Import the Grafana Dashboard JSON file:
Open your Grafana instance in a web browser.
Navigate to the "+" menu on the left sidebar and select "Import."
Upload the JSON file located in the dashboards/ directory or import it with the Dashboard ID "tbd".


3. Configure the correct Prometheus Datasources:

Primary Vault(DS_VAULT-01)

Secondary Vault(DS_VAULT-02)

## Telemetry configuration

To enable the telemetry for Hashicorp Vault you can follow this [Tutorial](https://developer.hashicorp.com/vault/tutorials/archive/monitor-telemetry-grafana-prometheus).

Hashicorp Vault Telemetry Example:
```hcl
telemetry {
  disable_hostname = true
  prometheus_retention_time = "12h"
}
```

Prometheus Scrape Config Example:
```yml
scrape_configs:
  - job_name: vault-1
    metrics_path: /v1/sys/metrics
    params:
      format: ['prometheus']
    scheme: http
    static_configs:
    - targets: ['0.0.0.1:8200']
  - job_name: vault-2
    metrics_path: /v1/sys/metrics
    params:
      format: ['prometheus']
    scheme: http
    static_configs:
    - targets: ['0.0.0.2:8200']
```

Grafana Datasources:

Create the Datasources "DS_VAULT-01" and "DS_VAULT-02" in [Grafana](https://grafana.com/docs/grafana/latest/datasources/).


## About this repository

Adfinis fights for a software world that is more open, where the quality is
better and where software must be accessible to everyone. This repository
contains part of the action behind this commitment. Feel free to
[contact](https://adfinis.com/kontakt/?pk_campaign=github&pk_kwd=mopsos)
us if you have any questions.

## License

This application is free software: you can redistribute it and/or modify it under the terms
of the GNU Affero General Public License as published by the Free Software Foundation,
version 3 of the License.
