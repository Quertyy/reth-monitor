# Reth Monitoring

## Description
This repository provides a Docker Compose setup for monitoring reth. It leverages Prometheus for monitoring, Grafana for data visualization, and Alertmanager for alert management. With this setup, you can gain insights into the performance and health of your Reth Ethereum node.

## Prerequisites
- [Docker](https://docs.docker.com/engine/install/)
- [Docker Compose](https://docs.docker.com/compose/install/linux/#install-the-plugin-manually)

## Installation

1. Clone this repository:

```bash
git clone https://github.com/your-repo/reth-monitoring.git
cd reth-monitoring
```

2. If you want to use Alertmanager with a Discord Webhook, you can copy the `.env.example` file to set your Webhook URL and rename the file to `.env`.

3. Set the EL and CL metrics port targets in `prometheus/prometheus.yaml`

4. Start the Docker containers:
```bash
docker compose up -d
```

5. Access Grafana by opening `http://localhost:3000` in your web browser.

## Configuration

- Prometheus and Alertmanager configuration files are located in the `prometheus` and `alertmanager` directories, respectively.
- Grafana dashboards are automatically provisioned from the `grafana/provisioning/dashboards` directory.

# Monitoring Other EL Clients
It is possible to monitor any Ethereum Layer (EL) client by importing the corresponding dashboard into Grafana. To do this, follow these steps:

1. Obtain the JSON file of the dashboard you want to import.
2. Place this file in the `grafana/provisioning/dashboards` directory.
3. Restart the Grafana container to apply the changes.

The dashboard will then be automatically imported and available in Grafana.
