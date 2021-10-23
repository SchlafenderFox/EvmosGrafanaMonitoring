# Node Viewer

## Variables in ```settings.env```
##### MASTER_SERVER_IP - IP address of the computer where Master Monitoring Server is installed
##### PROMETHEUS_METRICS_PORT - The port on which the tendermint prometheus works
##### RPC_API_PORT - Port for accessing the Cosmos REST API
##### MONIKER - Moniker of your validator

## Install software

### Update package repositories and install git

```
sudo apt update && sudo apt install -y git
```

### Clone the project and start installing
```
cd ~ && git clone https://github.com/SchlafenderFox/EvmosNodeViewer && cd ./EvmosNodeViewer && ./setup.sh
```

### Enter value for MASTER_SERVER_IP variable ```Example:```
![Alt text](images/enter_master_server_ip.png?raw=true "Master server IP")

### Reboot the server
```
reboot
```

## Helpful commands

### Update software

```
cd ~/EvmosNodeViewer && git pull && docker-compose up -d --build
```

### Change settings

```
cd ~/EvmosNodeViewer

nano ./settings.env

docker-compose up -d --build
```