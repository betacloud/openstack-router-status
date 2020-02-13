# openstack-router-status

Simple service to check all routers on our public network (`public`) for
reachability via ICMP.

The service used is Vigil (https://github.com/valeriansaliou/vigil). A status page for microservices.

## Usage

```
openstack --os-cloud service port list --device-owner network:router_gateway --network public -f json > data.json
```

```
{ "data": [
CONTENT OF data.json
] }
```

```
pip3 install j2cli
```

```
j2 --filter filters.py -f json -o config.cfg config.cfg.j2 data.json
```

```
docker-compose up -d
```
