**Previous:** [[01 - Installation]]
**Next**:

# Kafka installation

- Java 8+ must be installed on the server. We will install the latest version:
```sh
sudo apt update && sudo apt install default-jre default-jdk
```

- Download Kafka
```sh
cd
curl https://dlcdn.apache.org/kafka/3.5.0/kafka_2.13-3.5.0.tgz --output kafka_2.13-3.5.0.tgz
tar -xzf kafka_2.13-3.5.0.tgz
cd kafka_2.13-3.5.0
```
## Start server

```sh
KAFKA_CLUSTER_ID="$(bin/kafka-storage.sh random-uuid)"

bin/kafka-storage.sh format -t $KAFKA_CLUSTER_ID -c config/kraft/server.properties

bin/kafka-server-start.sh config/kraft/server.properties
```

## Create topic

```sh
bin/kafka-topics.sh --create --topic inf876 --bootstrap-server localhost:9092
```

## List topic

```sh
bin/kafka-topics.sh --bootstrap-server localhost:9092 --list
```

## Start producer

```sh
bin/kafka-console-producer.sh --topic inf876 --bootstrap-server localhost:9092
```

## Start consumer

```sh
bin/kafka-console-consumer.sh --topic inf876 --from-beginning --bootstrap-server localhost:9092
```
