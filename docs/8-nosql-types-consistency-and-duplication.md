# 8 - NoSQL: Types, Consistency (R/W/RF), and Duplication Challenges

## NoSQL Types

- Key-Value: 
    - Fast lookup by key (O(1))
    - the value often is opaque to the database (database does not understand the structure).
    - Examples: Redis, DynamoDB.
- Document: 
    - Stores self-contained documents (JSON/BSON).
    - Each document is a self-contained unit of data. It can have nested objects, arrays, and varying fields.
    - Can query by indexed fields, including nested keys, and supports secondary indexes and complex queries.
    - Example: MongoDB.
- Wide Column: Column-family stores (e.g., Cassandra).
- Graph: Optimized for relationships (nodes/edges).

## Replication & Consistency (R, W, RF)

- RF (Replication Factor): number of nodes holding a copy of data.
- W (Write quorum): minimum nodes that must acknowledge a write.
- R (Read quorum): minimum nodes that must respond to a read.
- Strong consistency can be achieved if R + W > RF, for example if you have 5 DB all for read and write, then if you made write to 3 DB and read from 3 DB then you guarantee to take latest data in read query (with read, check overhead)..
- Not strong consistency if R + W <= RF (some time you may accept stale data, another you are lucky and get most recent data)

## Why NoSQL is more horizontally scalable

- Designed for horizontal scaling and avoiding joins; related data can be stored together so a single request often hits one node.

## Duplication problems

- Duplicated data must be kept consistent; updates often propagate asynchronously leading to eventual consistency and possible stale reads.
- Solutions include background propagation, event-driven updates, immutable data, read repair, and other application-level strategies.

## Relational DB vs JSON column

- Relational DB: structured tables, ACID by default, joins can be expensive at scale; JSON columns are supported but not as flexible as NoSQL.
- NoSQL: native schema flexibility and horizontal scaling.
