# Node-Exporter
- aktuelle Version ermitteln: https://github.com/prometheus/node_exporter/releases
- im Homeverzeichnis
   - ``wget https://github.com/prometheus/node_exporter/releases/download/v1.0.1/node_exporter-1.0.1.linux-armv7.tar.gz``
   - ``tar xfz node_exporter-1.0.1.linux-armv7.tar.gz``
   - Ablage unter``/usr/local/bin`` => `sudo cp node_exporter /usr/local/bin`
- ``sudo chmod +x /usr/local/bin/node_exporter``
- ``sudo useradd -m -s /bin/bash node_exporter``
- ``sudo mkdir /var/lib/node_exporter``
- ``sudo chown -R node_exporter:node_exporter /var/lib/node_exporter``
  
## als Service einrichten
- ``sudo touch /etc/systemd/system/node_exporter.service``
- ``sudo vi /etc/systemd/system/node_exporter.service``

````editorconfig
[Unit]
Description=Prometheus Node Exporter
Documentation=https://prometheus.io/docs/guides/node-exporter/
After=network-online.target

[Service]
User=pi
Restart=on-failure
# Provide a text file location for https://github.com/fahlke/raspberrypi_exporter data with the
# --collector.textfile.directory parameter.
ExecStart=/usr/local/bin/node_exporter --collector.textfile.directory /var/lib/node_exporter/textfile_collector

[Install]
WantedBy=multi-user.target
````

- ``sudo systemctl daemon-reload``
- ``sudo systemctl enable node_exporter.service``
- ``sudo systemctl start node_exporter.service``
- ``sudo systemctl status node_exporter.service``

## Aufruf
- http://192.168.0.xxx:9100/metrics

## automatisierter
Wenn sich jemand berufen fühlt, kann er gern ein Script bereitstellen, welches die Dokumentation überflüssig macht.\
Gern auch mit Test. :grin: