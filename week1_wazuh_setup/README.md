# Week 1: Wazuh Setup

## Objective
Deploy a single-node Wazuh SIEM environment using Docker Compose and integrate one Windows endpoint.

## Components
- Ubuntu 20.04 VM (`soc-mgmt`)
- Docker Engine 26.1.3 + Compose v2.29.2
- Wazuh 4.14.0 (manager, indexer, dashboard)

## Network
- Manager IP: 192.168.19.129
- Exposed ports: 443 (dashboard), 1514‑1515 (agents), 55000 (API)

## Result
- Wazuh dashboard accessible at `https://192.168.19.129:443`
- Default credentials: `admin` / `SecretPassword`
- Successful startup and communication between Wazuh manager, indexer, and dashboard.

![Wazuh Dashboard](dashboard.png)
*Figure 1: Wazuh SIEM stack running in Docker.*

## Lessons Learned
- Learned how to deploy Wazuh using Docker Compose.
- Resolved SSL certificate mount error by regenerating indexer certificates.
- Adjusted kernel parameter `vm.max_map_count` for Elasticsearch compatibility.
