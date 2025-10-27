# magic-wormhole-docker-compose

Simple setup for running the transit relay and mailbox server for magic-wormhole with docker compose. Uses a nginx as a reverse proxy infront of it, but you dont really need it.

## Start the containers

```bash
docker compose up -d
```

## mailbox-server

wormhole --relay-url=ws://[server ip here]:4000/v1 send FILENAME

## transit-relay

wormhole send --transit-helper=tcp:[server ip here]:4001 file-to-send

## mailbox-server and transit-relay

wormhole --relay-url=ws://[server ip here]:4000/v1 --transit-helper=tcp://[server ip here]:4001 send FILENAME

## Example with localhost

wormhole --relay-url=ws://localhost:4000/v1 --transit-helper=tcp://localhost:4001 send FILENAME

## Running Dockerfiles seperately

```bash
docker build -t mailbox-server .
docker run -p 4000:4000 -d mailbox-server
```

```bash
docker build -t transit-relay .
docker run -p 4001:4001 -d transit-relay
```


## Planned changes

- Change nginx to traefik.
- Check if its neccessary to update the docker images via apt-get while building.
- Check if possible to just switch to Podman

## Warning

~~Currently the services are running as root, this is planned to be changed.~~

