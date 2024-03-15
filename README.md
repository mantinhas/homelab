# Mantinhas' Homelab

## Overview

This projects contains the docker compose files used to deploy my self-hosted home server for a single host machine, a 10-year old laptop I had hanging arround. Including:

1. [Jellyfin](https://jellyfin.org/) media server, attached to [transmission](https://transmissionbt.com/) torrent client and the [arr](https://wiki.servarr.com/) stack for media management
2. Management tools such as [Nginx](https://nginxproxymanager.com/) and [Portainer](https://www.portainer.io/)
3. Monitoring system utilizing [Grafana](https://grafana.com/) and [Prometheus](https://prometheus.io/docs/introduction/overview/)

My deployments use SSL certificates for secure https, however that must be manually configured in Nginx Proxy Manager, and a domain name must be acquired for the services. In my case, I'm using [duckdns](https://www.duckdns.org/) assigned to a private IP address of my host machine

## Screenshots

![Homepage of all services](screenshots/homepage.png)
![Grafana, Prometheus and Node Exporter monitoring solution](screenshots/grafana.png)
![Media Server](screenshots/jellyfin.png)

## Deployment

For deployment follow these steps:

1. Configure a `.env` file with variables corresponding to the variables declared in the [homepage configuration file](https://github.com/mantinhas/homelab/blob/main/docker-compose/homepage/config/services.yaml). This only requires looking at the published ports, and the IP of the host machine, and adding variables such as: `HOMEPAGE_VAR_JELLYFIN_URL=192.168.1.10:8096`

2. Go into each of the folders in `docker-compose` directory, for example, `homepage` by running `cd homepage`

3. Run the docker compose `docker compose up -d`

4. Open each of the web interfaces and configure admin accounts

5. Repeat for each service
