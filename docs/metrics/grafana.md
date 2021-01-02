# Grafana

```editorconfig
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
sudo apt-get update
sudo apt-get install -y grafana
sudo /bin/systemctl enable grafana-server
sudo /bin/systemctl start grafana-server
```

## Aufruf
- http://192.168.0.xxx:3000

## automatisierter
Wenn sich jemand berufen fühlt, kann er gern ein Script bereitstellen, welches die Dokumentation überflüssig macht.\
Gern auch mit Test. :grin:
