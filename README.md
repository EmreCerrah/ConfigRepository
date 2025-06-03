# ConfigRepository

This repository contains configuration files for a Spring Cloud Gateway service.
It also includes an example monitoring stack using Prometheus and Grafana.

## Files

- `gateway-service.yml` - Gateway route configuration.
- `api-gateway-service.yml` - Alternative gateway config.
- `docker-compose.yml` - Compose file for Prometheus and Grafana.
- `prometheus.yml` - Prometheus scrape configuration.

## Running Prometheus and Grafana

Launch the monitoring stack using Docker Compose:

```bash
docker compose up -d
```

Prometheus will be available at `http://localhost:9090` and Grafana at
`http://localhost:3000` (login with `admin` / `admin`). The Prometheus
configuration scrapes the gateway's `/actuator/prometheus` endpoint. Ensure
that the gateway service exposes this endpoint by enabling Spring Boot Actuator
and including `management.endpoints.web.exposure.include=prometheus` in its
properties.
