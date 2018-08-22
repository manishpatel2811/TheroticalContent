# Where Is Data Stored

For each column family, there are 3 layer of data stores: memtable, commit log and SSTable.

1For efficiency, Cassandra does not repeat the names of the columns in memory or in the SSTable. For example, data is inserted using these CQL statements:

```
INSERT INTO k1.t1 (c1) VALUES (v1);
INSERT INTO k2.t1 (c1, c2) VALUES (v1, v2);
INSERT INTO k1.t1 (c1, c3, c2) VALUES (v4, v3, v2);

```

In the memtable, Cassandra stores this data:

```
k1 c1:v4 c2:v2 c3:v3
k2 c1:v1 c2:v2

```

In the commit log on disk, Cassandra stores this data:

```
k1, c1:v1
k2, c1:v1 C2:v2
k1, c1:v4 c3:v3 c2:v2

```
In the SSTable on disk, Cassandra stores this data after flushing the memtable:

```
k1 c1:v4 c2:v2 c3:v3
k2 c1:v1 c2:v2
```




