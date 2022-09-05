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
- [vaultwarden](https://hub.docker.com/r/vaultwarden/server)
- [portainer](https://hub.docker.com/r/portainer/portainer-ce)

## Usage

Edit your settings in the `.env` file.

Start the containers with
```shell
docker compose up -d
```

### Enable host to container networking

* Create new interface (Interface name is *dockerrouteif*, and *eth0* is the host interface): 
```shell
ip link add {DOCKER_NETWORK} link {PARENT_INTERFACE} type macvlan mode bridge
ip link add asgard link eth0 type macvlan mode bridge #example
```

* Assign IP address to that interface:
```shell
ip addr add {AUX}/32 dev {DOCKER_NETWORK}
ip addr add 192.168.1.200/32 dev asgard #example
```

* Bring up that interface:
```shell
ip link set {DOCKER_NETWORK} up
ip link set asgard up  #example

```
* And finally define a range which should be routed trough that iterface:
```shell
ip route add {DOCKER_IP_RANGE} dev {DOCKER_NETWORK}
ip route add 192.168.1.192/27 dev asgard #example
```

**Success!**

## Requirements
- [Docker & Docker compose](https://github.com/docker/docker-install)
- [DuckDNS domain and API Token](https://www.duckdns.org/)

## Tasks

* guacamole
* elasticstack