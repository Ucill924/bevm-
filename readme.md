# BEVM Incentivized Node Testnet (BTC Layer2)

## System Requirements
- OS: Ubuntu 20.4+
- CPU: 2 Cores
- RAM: 2 GB
- SSD: 300 GB

## Installation

### 1. Running with Docker

#### Installation
1. Update dependencies:
    ```bash
    sudo apt update -y
    ```

2. Download the Docker installation script:
    ```bash
    curl -fsSL https://get.docker.com -o get-docker.sh
    ```

3. Run the Docker installation script:
    ```bash
    sudo sh get-docker.sh
    ```

#### Establish a Host Mapping Path
1. Navigate to a path to store data on your VPS:
    ```bash
    cd /var/lib
    mkdir node_bevm_test_storage
    ```

2. Fetch the Docker image:
    ```bash
    sudo docker pull btclayer2/bevm:v0.1.1
    ```

#### Run a Docker Container
Replace `/var/lib/node_bevm_test_storage` with your own host mapping path, and replace `your_node_name` with your desired node name:
    ```bash
    sudo docker run -d -v /var/lib/node_bevm_test_storage:/root/.local/share/bevm btclayer2/bevm:v0.1.1 bevm "--chain=testnet" "--name=your_node_name" "--pruning=archive" --telemetry-url "wss://telemetry.bevm.io/submit 0"
    ```

#### Check Container ID.
```bash
docker ps
