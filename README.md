# Homelab

## Docker

I'd like to run all my services within docker for an easy of use and backing things up.

### Networks

There are a few internal docker networks that need to be setup:

```bash
docker network create traefik
docker network create grafana
docker network create postgres
```

### Containers

#### Avahi

Avahi is a mDNS reflector between the host and docker internal networks.

#### Esphome

Esphome boards/devices

#### Files

A simple nginx server to serve static files over the LAN and WAN networks.

#### Grafana

Using grafana dashboarding for making looking into logs and statistics a bit easier.

#### Loki

Log aggreration system that collects logs from all the docker containers. This requires a docker plugin to be installed:

```bash
docker plugin install grafana/loki-docker-driver:2.9.2 --alias loki --grant-all-permissions
```

#### Mqtt

Just a simple mosquitto mqtt server.

#### Traefik

The ingress router that handles all the external HTTP traffic.

#### Zigbee2mwtt

Controls the sonoff zigbee stick.
