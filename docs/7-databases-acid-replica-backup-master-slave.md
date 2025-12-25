# 7 - Databases: ACID, Replication, Replica vs Backup, Master-Slave

## ACID (for transactions)

- Atomicity: all-or-nothing — either the full transaction happens or none of it does.
- Consistency: data moves from one valid state to another (constraints, FK, uniqueness, business rules).
- Isolation: transactions should not see unfinished work of other transactions (prevents dirty reads).
- Durability: once committed, data will not be lost even on crash.

## Master-Slave Replication

- Master (primary) accepts writes; slaves (replicas) accept reads and copy data from master.
- Can improve read throughput and, with failover, availability.
- reduce load on the master by sending read operations to slaves, very useful in heavy/intensive read systems like Facebook.
- if eventually consistency, the master response to the user then The master sends the new data to the slaves so they become copies of it, now slaves ready to read operations

## Replica vs Backup

- Replica: live copy continuously updated (synchronous or asynchronous). Often used for failover and scaling reads; may be affected by programmer errors that also affect primary (for example if programmer delete by default rows of table or dropped a table, then replicas also affected).
- Backup: point-in-time copy stored separately for recovery; not live or automatically in sync — safe against accidental deletions if taken earlier.

## Multi-master clustering

- Multiple nodes can accept writes and replicate to others. Pros: higher availability and write locality. Cons: conflict resolution is required when concurrent writes touch same data.
