# Grafana Dashboard for Vault

This repository contains a Grafana Dashboard for Hashicorp Vault Enterprise with Disaster Recovery. It gives a overview about the status of your Hashicorp Vault Cluster, the utilization and health.

## Usage

### Prerequisites

Before using the Grafana Dashboard, ensure you have the following prerequisites installed:

- [Grafana](https://grafana.com/get)
- [Prometheus](https://prometheus.io/download/)

### Installation

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
Upload the JSON file located in the dashboards/ directory.

3. Configure data sources:

Configure prometheus as a data source for Grafana

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
