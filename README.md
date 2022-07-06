# aptos validator node

## Installing

1. Run the script

```sh
. <(wget -qO- sh.f5nodes.com) aptos
```

2. Enter your validator moniker in the input, then wait till the end of installation.

## Commands

Check validator node logs:

```sh
docker logs -f --tail 100 aptos-validator-1
```

Restart node:

```sh
cd ~/.aptos && docker-compose restart
```

Stop node:

```sh
cd ~/.aptos && docker-compose stop
```

Progress can be monitored by querying the metrics port:

```sh
curl 127.0.0.1:9101/metrics 2> /dev/null | grep aptos_state_sync_version
```

Information for filling out the form can be viewed by running the commands:

```sh
source ~/.bash_profile
cat ~/.aptos/$APTOS_NODENAME.yaml
```

Ports used:

```sh
TCP ports: 80, 6180, 6181, 6182, 9101
```

Delete node:

```sh
cd ~/.aptos && docker-compose down -v
rm -rf ~/.aptos /opt/aptos
```
