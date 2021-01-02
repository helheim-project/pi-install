# InfluxDB

````editorconfig
wget -qO- https://repos.influxdata.com/influxdb.key | sudo apt-key add -
source /etc/os-release
echo "deb https://repos.influxdata.com/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
sudo apt update && sudo apt install -y influxdb
sudo systemctl unmask influxdb.service
sudo systemctl start influxdb
sudo systemctl enable influxdb.service
````

## Aufruf
- http://192.168.0.xxx:8086/debug/vars

## automatisierter
Wenn sich jemand berufen fühlt, kann er gern ein Script bereitstellen, welches die Dokumentation überflüssig macht.\
Gern auch mit Test. :grin: