# Master Monitoring Server

### WARNING!
**To prevent possible malfunctions, we strongly recommend that you install the Master Monitoring Server on a computer different from the one where your node is installed.**

## Install software

### Install git with the command

```
sudo apt update && sudo apt install -y git
```

### Clone the project and start installing
```
cd ~ && git clone https://github.com/SchlafenderFox/EvmosMasterMonitorServer && cd ./EvmosMasterMonitorServer && ./setup.sh
```

### Open the settings file
```
nano ./prometheus.yml
```

### Enter the IP addresses of your Evmos node, change only the line ```- targets: []```, use the example suggested in the file.
```
Example:
```
![Alt text](images/example_settings_file.png?raw=true "Example setting file")

**Make sure you specify the IP address of your Evmos node with port 10100**

### Save the changes by pressing
```
CTRL + S
```

### Close the file by pressing
```
CTRL + X
```

### Execute the command 
```
docker restart prometheus
```

### Open your browser and go to 
```
http://your_master_server_ip:3000
```

### Enter login and password ```admin```, then enter a new password for your admin user.

### Go to 
```
http://your_master_server_ip:3000/datasources
```

### Add a new data source by clicking the ```Add data source``` button
![Alt text](images/add_data_source.png?raw=true "Add data source")

### Select ```Prometheus```
![Alt text](images/prometheus.png?raw=true "Prometheus")

### In the "URL" line we write ```http://localhost:9090```
![Alt text](images/localhost.png?raw=true "Localhost")

### Press the ```Save & test``` button at the bottom
![Alt text](images/save_and_test.png?raw=true "Save & test")

### Go to 
```
http://your_master_server_ip:3000/dashboards
```

### Press the ```Import``` button

### Insert the content from the ```https://raw.githubusercontent.com/SchlafenderFox/EvmosMasterMonitorServer/master/monitoring_template.json``` link into the ```Import via panel json``` field
![Alt text](images/import.png?raw=true "Import")

### Press ```Load``` and then ```Import```

### Use the handy monitoring! ^_^