# Kafka

Apache Kafka is a publish-subscribe messaging system. 

what is a messaging system?

A messaging system lets you send messages between processes, applications, and servers

Apache Kafka is a software where topics can be defined [Think of a topic as a category]

Applications may connect to this system and transfer a message onto the topic. A message can include any kind of information. A message is something like having information about an event that has happened on your website, or it could just be a simple text message that is supposed to trigger an event. Another application may connect to the system and process messages from a topic.

## Kafka Broker

A Kafka cluster consists of one or more servers (Kafka brokers), which are running Kafka.
Producers are processes that publish data (push messages) into Kafka topics within the broker.
A consumer of topics pulls messages off a Kafka topic.

## Kafka Topic

A Topic is a category/feed name to which messages are stored and published
Messages are byte arrays that can store any object in any format.
As said before, all Kafka messages are organized into topics.
If you wish to send a message you send it to a specific topic and if you wish to read a message you read it from a specific topic.
Producer applications write data to topics and consumer applications read from topics. 
Messages published to the cluster will stay in the cluster until a configurable retention period has passed by. Kafka retains all messages for a set amount of time, and therefore, consumers are responsible to track their location.


## Kafka Topic Partition

Kafka topics are divided into a number of partitions, which contains messages in an unchangeable sequence.
Each message in a partition is assigned and identified by its unique offset.
A topic can also have multiple partition logs which allows for multiple consumers to read from a topic in parallel.

In Kafka, replication is implemented at the partition level. The redundant unit of a topic partition is called a replica.
Each partition usually has one or more replicas meaning that partitions contain messages that are replicated over a few Kafka brokers in the cluster.

It's possible for the producer to attach a key to the messages and tell which partition the message should go to. All messages with the same key will arrive at the same partition.

Partitions allow you to parallelize a topic by splitting the data in a particular topic across multiple brokers.

Every partition (replica) has one server acting as a leader and the rest of them as followers. The leader replica handles all read-write requests for the specific partition and the followers replicate the leader. If the leader server fails, one of the follower servers become the leader by default. 

The leader appends the message to its commit log and increments its message offset. Kafka only exposes a message to a consumer after it has been committed and each piece of data that comes in will be stacked on the cluster.


## Consumers and consumer groups

Consumers can read messages starting from a specific offset and are allowed to read from any offset point they choose.  This allows consumers to join the cluster at any point in time.

Consumers can join a group called a consumer group. A consumer group includes the set of consumer processes that are subscribing to a specific topic. Each consumer in the group is assigned a set of partitions to consume from. They will receive messages from a different subset of the partitions in the topic. Kafka guarantees that a message is only read by a single consumer in the group.

Consumers pull messages from topic partitions. Different consumers can be responsible for different partitions. Kafka can support a large number of consumers and retain large amounts of data with very little overhead. 

Consumers pull messages from topic partitions. Different consumers can be responsible for different partitions. Kafka can support a large number of consumers and retain large amounts of data with very little overhead. By using consumer groups, consumers can be parallelised so that multiple consumers can read from multiple partitions on a topic, allowing a very high message processing throughput. The number of partitions impacts the maximum parallelism of consumers as you cannot have more consumers than partitions.

Data/messages are never pushed out to consumers, the consumer will ask for messages when the consumer is ready to handle the message.
The consumers will never overload themselves with lots of data or loose any data since all messages are being queued up in Kafka. If the consumer is behind while processing messages, it has the option to eventually catch up and get back to handle data in real time.

# Apache Kafka and server concepts

```
1. Producer: Application that sends the messages.
2. Consumer: Application that receives the messages.
3. Message: Information that is sent from the producer to a consumer through Apache Kafka.
4. Connection: A connection is a TCP connection between your application and the Kafka broker.
5. Topic: A Topic is a category/feed name to which messages are stored and published.
6. Topic partition: Kafka topics are divided into a number of partitions, which allows you to split data across multiple brokers.
7. Replicas A replica of a partition is a "backup" of a partition. Replicas never read or write data. They are used to prevent data loss.
8. Consumer Group: A consumer group includes the set of consumer processes that are subscribing to a specific topic.
9. Offset: The offset is a unique identifier of a record within a partition. It denotes the position of the consumer in the partition.
10. Node: A node is a single computer in the Apache Kafka cluster.
11. Cluster: A cluster is a group of nodes i.e., a group of computers.

```

