# home-server

This repository helps to host your own home server.

## Services

- [ouroboros](https://hub.docker.com/r/pyouroboros/ouroboros)
- [pihole](https://hub.docker.com/r/pihole/pihole)
- [homer](https://hub.docker.com/r/b4bz/homer)
- [wireguard](https://hub.docker.com/r/linuxserver/wireguard)
- [homeassistant](https://hub.docker.com/r/homeassistant/home-assistant)
- [nextcloud](https://hub.docker.com/_/nextcloud)
- [postgres](https://hub.docker.com/_/postgres)
- [guacamole](https://hub.docker.com/r/guacamole/guacamole)
- [vaultwarden](https://hub.docker.com/r/vaultwarden/server)
- [portainer](https://hub.docker.com/r/portainer/portainer-ce)
- [elastic stack](https://hub.docker.com/_/elasticsearch)

## Usage

Edit your settings in the `.env` file.

Start the containers with

```shell
docker-compose up -d
```

:warning: You have to install docker and docker-compose first.

## Tasks

* guacamole
* elastic stack