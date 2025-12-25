# 6 - CAP Theorem and Consistency

## Core problem

- In a distributed system (more than one machine) failures and network delays are guaranteed.
- You cannot assume all machines see the same data or that the network is always reliable.
- CAP theorem explains the limits of distributed systems under these conditions.

## CAP Theorem (short)

- When a network partition occurs you must choose Consistency or Availability; you cannot have both with Partition tolerance.
- Partition tolerance is mandatory in real systems.

## Definitions

- Consistency (strong): every successful read returns the most recent successful write.
- Availability: every request receives a response (might be stale) — the system remains operational even if some nodes are down.
- Partition tolerance: the system continues to work when the network breaks between machines.

## Tradeoffs

- CP (Consistency + Partition tolerance): Sacrifice Availability during partitions to maintain data integrity. The system may reject requests when it cannot guarantee the latest data.
- AP (Availability + Partition tolerance): Sacrifice strict Consistency to remain operational during partitions (eventual consistency). Useful when stale data for short time is acceptable (social feeds, likes, comments).
- CA (Consistency + Availability): Only possible when there is no partition — unrealistic in distributed systems.

## Interview tip

- Don’t say "I choose AP because it is scalable". Instead say: "I choose AP because showing stale data for 5 seconds is acceptable for this product."
