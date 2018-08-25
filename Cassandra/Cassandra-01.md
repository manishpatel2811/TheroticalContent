# Cassandra

``` 
Apache Cassandra was developed at facebook by avinash lakshman and prashant malik. In 2009, It became a project in apache incubator.

```

```

The CAP theorem, also known as Brewer's theorem, states that it is impossible for a distributed computer system to simultaneously provide all three of the following guarantees:

* Consistency = (all nodes see the same data at the same time)
* Availability =  (a guarantee that every request receives a response about whether it was successful or failed)
* Partition tolerance = (the system continues to operate despite arbitrary message loss or failure of part of the system)

According to the theorm, a distributed system can't satisfy all three gurantees at the same time.

```

## Cassandra and CAP

```

Cassandra is typically classified as an AP system, meaning that availability and partition tolerance are generally considered to be more important than consistency in Cassandra. But Cassandra can be tuned with replication factor and consistency level to also meet C.

consistency as defined in the CAP theorem is quite different from the consistency guaranteed in ACID database transactions.

Database systems designed with traditional ACID guarantees in mind such as RDBMS choose consistency over availability, whereas systems designed around the BASE philosophy, common in the NoSQL movement for example, choose availability over consistency

```
