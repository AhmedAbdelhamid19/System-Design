# 5 - Partitioning and Sharding

## Partitioning

- Splitting data into logical parts (within the same server or DB instance).
- Types:
  - Horizontal partitioning: split rows (e.g., by year: orders_2023, orders_2024).
  - Vertical partitioning: split columns into different tables connected by foreign keys.

## Sharding

- Splitting data across multiple machines or database instances (focuses on different servers).
- Example: users A–M on Server1, users N–Z on Server2.

## Challenges with Sharding

- Cross-shard joins are complex and costly (network calls).
  - for example if you made join with based specific column and some of user in server A and other on Server B, then it cost you network overhead
- Increased complexity in queries, transactions, and data management.
