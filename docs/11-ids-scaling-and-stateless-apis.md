# 11 - ID Generation, Scaling Decisions, and Stateless APIs

## ID Generation in Distributed Systems

- Auto-increment IDs break across multiple machines.
- Common solutions:
  - Central ID generator service (single source) — simple but becomes bottleneck and SPOF.
  - GUIDs/UUIDs — globally unique, large, not ordered, index performance impact.
  - Time-based + node id + counter — sortable, good index performance, no central service.
  - Server ranges — pre-allocate ID ranges per server.
  - Let DBMS generate IDs (e.g., MongoDB ObjectId).

## Vertical vs Horizontal Scaling Decision

- Vertical (scale up): increase CPU, RAM, disk on one server; simpler but has diminishing returns and SPOF risk.
- Horizontal (scale out): add more servers behind a load balancer — preferred to avoid SPOF.

## Stateless vs Stateful APIs

- Prefer stateless designs for backend APIs for horizontal scaling: any server can handle any request.
- Stateful servers keep sessions in memory and make horizontal scaling harder (sticky sessions, replication).
