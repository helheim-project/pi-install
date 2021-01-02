# Metriken 
Wie bekommt man den Gesundheitszustand von seinem ``Raspberry PI`` mit? 
Natürlich vorausgesetzt, dass man ein Interesse daran hat, kann man die folgenden 
Bechreibungen für einen einzelnen oder mehrere PI's nutzen, um Metriken bekommen 
und auswerten zu können.

## Node-Exporter
Beim Einsatz mehrerer PI's kann man ein Konstrukt von Prometheus nutzen, bei denen 
auf den einzelnen PI's Metrik Endpunkte zur Verfügung gestellt werden, die dann als Targets 
im Prometheus Server aufgenommen werden.

### genutzte Doku
-> [Prometheus node exporter on Raspberry Pi – How to install](https://linuxhit.com/prometheus-node-exporter-on-raspberry-pi-how-to-install/)

### eigene Doku
[Installation](node-exporter.md)

## Prometheus
Egal ob man einen einzelnen oder mehrere PI's nutzt, es genügt die Installation 
eines einzelnen Prometheus Servers, welcher Metriken an einem Punkt zur Verfügung stellt.

### genutzte Doku
-> [Installing Prometheus on the Raspberry Pi](https://pimylifeup.com/raspberry-pi-prometheus/)

### eigene Doku
[Installation](prometheus.md)

## Grafana
Egal ob man einen einzelnen oder mehrere PI's nutzt, es genügt die Installation
einer Grafana Instanz, welche Metriken an einem Punkt visualisieren kann.

### genutzte Doku
-> [Install Grafana on Raspberry Pi](https://grafana.com/tutorials/install-grafana-on-raspberry-pi)

### eigene Doku
[Installation](grafana.md)
