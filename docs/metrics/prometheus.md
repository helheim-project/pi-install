# Prometheus
- aktuelle Version ermitteln: https://github.com/prometheus/prometheus/releases
- im Homeverzeichnis
   - ``wget https://github.com/prometheus/prometheus/releases/download/v2.23.0/prometheus-2.23.0.linux-armv7.tar.gz``
   - ``tar xfz prometheus-2.23.0.linux-armv7.tar.gz``
   - ``ln -s prometheus-2.23.0.linux-armv7 prometheus``
- ``sudo useradd -m -s /bin/bash prometheus``
- ``sudo mkdir /var/lib/prometheus``
- ``sudo chown -R prometheus:prometheus /var/lib/prometheus``

## als Service einrichten
- ``sudo touch /etc/systemd/system/prometheus.service``
- ``sudo vi /etc/systemd/system/prometheus.service``

````editorconfig
[Unit]
Description=Prometheus Server
Documentation=https://prometheus.io/docs/introduction/overview/
After=network-online.target

[Service]
User=pi
Restart=on-failure

ExecStart=/home/pi/prometheus/prometheus \
--config.file=/home/pi/prometheus/prometheus.yml \
--storage.tsdb.path=/home/pi/prometheus/data

[Install]
WantedBy=multi-user.target
````
- ``sudo systemctl daemon-reload``
- ``sudo systemctl enable prometheus.service``
- ``sudo systemctl start prometheus.service``
- ``sudo systemctl status prometheus.service``

## Node-Exporter aufnehmen
````yaml
...
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: 'prometheus'
    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.
    static_configs:
    - targets: ['localhost:9090']
  - job_name: 'mypi1'
    static_configs:
    - targets: ['mypi1:9100']
  - job_name: 'mypi2'
    static_configs:
    - targets: ['mypi2:9100']
...
````

## Aufruf
- http://192.168.0.xxx:9090

## automatisierter
Wenn sich jemand berufen fühlt, kann er gern ein Script bereitstellen, welches die Dokumentation überflüssig macht.\
Gern auch mit Test. :grin: