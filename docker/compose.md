# Template

```yaml
version: "3.9"
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
		volumes:
			- <name>:/path/in/container # Ex for Mongo: /data/db

networks:
	<networkName>: # mail_net
		external: true
		ipam:
			driver: <type> # default is bridge
			config:
			  - subnet: "<net@>/<mask>" # "172.20.0.0/24"
				gateway: "gateway@" # "192.168.1.1"
volumes:
	<name>:
```

```ad-info
'version' attribute is only necessary to retro compatibility, if you write a new compose file you might omit it. 
```

# Dotenv

To use env variable from your `.env`file in your project, just call the variable with ${VAR}

If your .env file is like:
```
TOKEN=mysupersecrettoken
```
then call the token in your compose.yaml like:
```yaml
services:
	web:
		envrionment:
		  - TOKEN=${TOKEN}
```



# Start stack

```sh
docker compose up
```

| OPTION   | ALIAS | EFFECT                  |
| -------- | ----- | ----------------------- |
| --build  |       | rebuild the images      |
| --detach | -d    | run stack in background |
## Example

Run the compose file (must be alone) in the current directory in background: 
```sh
docker compose up -d
```

# Stop stack

```sh
docker compose down
```

