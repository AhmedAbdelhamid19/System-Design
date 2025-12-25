# 3 - Scalability, Elasticity, and Replication, and Consistency

## Scalability

- Vertical scaling (scale up): upgrade a single server (more CPU, RAM, disk).
- Horizontal scaling (scale out): add more machines when load increases.

## Elasticity

- Resources automatically grow and shrink based on traffic (both directions).
- Commonly provided by cloud platforms (AWS, Azure, GCP).

## Replication

- Copying data across machines to improve availability and fault tolerance.
- Models:
  - Synchronous replication: writes applied to all replicas before acknowledging — strong consistency, higher latency, slower writes.
  - Asynchronous replication: primary acknowledges writes immediately while replicas are updated in background — faster writes, eventual consistency, possible data loss on failure.

## Consistency: 
    - All machines see the same data.
    - Strong consistency: all servers see the new value immediately, like bank balance or booking ticket.
    - Eventual consistency: servers may show old data briefly (for short time), like post/comment update/delete in facebook, sometimes it's acceptable depending on the business.
