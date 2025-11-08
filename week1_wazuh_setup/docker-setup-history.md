# Week 1 - Docker and Wazuh setup history

## Install Docker Engine and Compose

- sudo apt update
- sudo apt install -y ca-certificates curl gnupg lsb-release
- sudo mkdir -p /etc/apt/keyrings
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
- echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee - /etc/apt/sources.list.d/docker.list > /dev/null
- sudo apt update
- sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin docker-buildx-plugin
- sudo systemctl enable --now docker
- sudo usermod -aG docker $USER
- newgrp docker
- docker --version
- docker compose version
- docker run --rm hello-world

## Deploy Wazuh stack

- cd ~
- git clone https://github.com/wazuh/wazuh-docker.git
- cd wazuh-docker
- git fetch --all --tags
- git checkout v4.14.0
- cd single-node

# Generate certificates for Wazuh indexer (required once)
- docker compose -f generate-indexer-certs.yml run --rm generator

# Tune kernel parameter required by Elasticsearch
- sudo sysctl -w vm.max_map_count=262144
- echo 'vm.max_map_count=262144' | sudo tee -a /etc/sysctl.conf

# Pull images and start containers
- docker compose pull
- docker compose up -d

# Verify that Wazuh services are running
- docker compose ps
- docker compose logs -f wazuh.manager
- docker compose logs -f wazuh.indexer
- docker compose logs -f wazuh.dashboard
