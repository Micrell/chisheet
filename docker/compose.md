# Template

```yaml
version: "3.7"
services:
	<serviceName>:
		container_name: <name> # postfix
		image: <name>:<label> # ubuntu:latest
		build:
			context: <pathToDirOfDockerfile> # . or ./postfix/ assuming Dockerfile is in postfix dir
			dockerfile: <dockerFileName> # Dockerfile
		networks:
			<networkName>: # mail_net
				ipv4_address: <ip@> # 172.18.0.2
		dns:
		  - <ip@> # 172.18.0.9
		  - <anotherOne> # 192.168.1.1
		ports:
		  - <externalPort>:<internalPort> # 80:80 or 8880:80

networks:
	<networkName>: # mail_net
		external: true
		ipam:
			driver: <type> # bridge
			config:
			  - subnet: "<net@>/<mask>" # "172.20.0.0/24"
				gateway: "gateway@" # "192.168.1.1"
```

# Start stack

```sh
docker compose up
```

| OPTION   | ALIAS | EFFECT                                  |
| -------- | ----- | --------------------------------------- |
| --build  |       | rebuild the images |
| --detach | -d    | run stack in background                 |


# Stop stack

```sh
docker compose down
```

