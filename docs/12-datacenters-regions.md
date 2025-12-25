# 12 - Data Centers, Availability Zones, and Regions

## Levels

- Server → Datacenter → Availability Zone → Region → Global

## Deployment choices

- Same datacenter:
  - simple, low latency between servers, but single point of failure for the datacenter.
- Same region (multiple datacenters in region):
  - better resilience against single datacenter failure.
- Multiple regions:
  - lower latency for users worldwide and highest availability, but adds replication complexity and legal/regulatory concerns (GDPR, HIPAA).

## Considerations

- Data locality, compliance (GDPR), replication strategy, and avoiding a single global primary DB for all regions.
