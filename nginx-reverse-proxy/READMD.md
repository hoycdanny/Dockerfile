## Nginx Reverse Proxy Dockerfile


This repository contains **Dockerfile** of [Nginx](http://nginx.org/) for [Docker](https://www.docker.com/)'s [automated build](https://hub.docker.com/r/hoycdanny/nginx-reverse-proxy/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).


### Base Docker Image

* [ubuntu:14.04](https://github.com/tianon/docker-brew-ubuntu-core/blob/31ebd22e9e83185d69d50b3492911aedf519dd4a/trusty/Dockerfile)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://hub.docker.com/r/hoycdanny/nginx-reverse-proxy/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull hoycdanny/nginx-reverse-proxy`

   (alternatively, you can build an image from Dockerfile: `docker build -t="hoycdanny/nginx-reverse-proxy" github.com/hoycdanny/nginx-reverse-proxy`)


### Usage

    docker run -tdi -e PROXY_PASS=https://www.nginx.com -e PROXY_PATH=nginx -p 80:80 nginx-reverse-proxy

#### Attach persistent/shared directories

    docker run -tdi -e PROXY_PASS=**PASS_URL** -e PROXY_PATH=**PASS_PATH** -p 80:80 nginx-reverse-proxy

After few seconds, open `http://<host>` and `http://<host>/PASS_PATH` to see the welcome page and PASS_URL.

