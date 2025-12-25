# 8 - NoSQL: Types, Consistency (R/W/RF), and Duplication Challenges

## NoSQL Types

- Key-Value: Fast lookup by key (O(1)). Examples: Redis, DynamoDB.
- Document: Stores self-contained documents (JSON/BSON). Example: MongoDB.
- Wide Column: Column-family stores (e.g., Cassandra).
- Graph: Optimized for relationships (nodes/edges).

## Replication & Consistency (R, W, RF)

- RF (Replication Factor): number of nodes holding a copy of data.
- W (Write quorum): minimum nodes that must acknowledge a write.
- R (Read quorum): minimum nodes that must respond to a read.
- Strong consistency can be achieved if R + W > RF.

## Why NoSQL is more horizontally scalable

- Designed for horizontal scaling and avoiding joins; related data can be stored together so a single request often hits one node.

## Duplication problems

- Duplicated data must be kept consistent; updates often propagate asynchronously leading to eventual consistency and possible stale reads.
- Solutions include background propagation, event-driven updates, immutable data, read repair, and other application-level strategies.

## Relational DB vs JSON column

- Relational DB: structured tables, ACID by default, joins can be expensive at scale; JSON columns are supported but not as flexible as NoSQL.
- NoSQL: native schema flexibility and horizontal scaling.
