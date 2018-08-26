
# Single node configurations

Start the zookeeper in one terminal

```

bin/zookeeper-server-start.sh config/zookeeper.properties

```

start a kafka broker in another terminal

```

bin/kafka-server-start.sh config/server.properties

```

create a kafka topic 

```

bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic Hello-Kafka

```

Show all topics 

```

bin/kafka-topics.sh --list --zookeeper localhost:2181

```

start producer to send messages

```

bin/kafka-console-producer.sh --broker-list localhost:9092 --topic Hello-Kafka

```


Start consumer to recieve messages 

```
bin/kafka-console-consumer.sh --zookeeper localhost:2181 —topic Hello-Kafka --from-beginning --whitelist Hello-Kafka 

```
