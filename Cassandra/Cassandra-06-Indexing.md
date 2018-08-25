# Indexing

```
An index (former name: secondary index) provides means to access data in Cassandra using non-primary key fields other than the partition key. The benefit is fast, efficient lookup of data matching a given condition. Actually, if there is no index on a normal column, it is even not allowed to conditionally query by the column.

An index indexes column values in a separate, hidden column family (table) from the one that contains the values being indexed. The data of an index is local only, which means it will not be replicated to other nodes. This also means, for data query by indexed column, the requests has to be forwarded to all the nodes, waiting for all the resonses, and then the results are merged and returned. So if you have many nodes, the query response slows down as more machines are added to the cluster.

Caution:

By the current version (2.0.7) of Apache Cassandra, you could only query by an indexed column with equality comparison condition. Range select or order-by by an indexed column is not supported. The reason is the keys stored in the hidden column family are unsorted.

```

# When to Use An Index?

Cassandra's built-in indexes are best on a table having many rows that contain the indexed value. The more unique values that exist in a particular column, the more overhead you will have for querying and maintaining the index. For example, suppose you had a playlists table with a billion songs and wanted to look up songs by the artist. Many songs will share the same column value for artist. The artist column is a good candidate for an index.

# When Not to Use An Index?

Do not use an index in these situations:

On high-cardinality columns because you then query a huge volume of records for a small number of results
In tables that use a counter column
On a frequently updated or deleted column
To look for a row in a large partition unless narrowly queried

# References

http://www.datastax.com/documentation/cql/3.1/cql/ddl/ddl_primary_index_c.html
http://www.datastax.com/documentation/cql/3.1/cql/ddl/ddl_when_use_index_c.html
