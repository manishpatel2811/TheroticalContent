# What is Cassandra DB.

```
Apache Cassandra™ is a massively scalable open source NoSQL database. It can managing large amounts of structured, semi-structured, and unstructured data across multiple data centers and the cloud. It delivers continuous availability , linear scalability and operaional simplicity accross many commodity servers with no single point of failure along with a powerfil dynamic data model designed for maximum flexibility and fast response times.

Cassandra is 

-> partitioned row store database
-> Automatic data distibution
-> Customizable Replication
-> Linear scalability

```
## Features 

```
1. Partitioning [Data distribution ]

The architecture of Cassandra is “masterless”, meaning all nodes are the same
Cassandra provides automatic data distribution across all nodes that participate 
in a “ring” or database cluster. There is nothing programmatic that a developer or 
administrator needs to do or code to distribute data across a cluster because data 
is transparently partitioned across all nodes in a cluster.

2. Replication 

Cassandra also provides built-in and customizable replication, which stores redundant copies of data across nodes that participate in a Cassandra ring. This means that if any node in a cluster goes down, one or more copies of that node’s data is available on other machines in the cluster. Replication can be configured to work across one data center, many data centers, and multiple cloud availability zones.

3. Horizontal Scalability

Cassandra supplies linear scalability, meaning that capacity may be easily added simply by adding new nodes online.
 
4. Runs on any kind hardware, even in commodity hardware as well.

```

