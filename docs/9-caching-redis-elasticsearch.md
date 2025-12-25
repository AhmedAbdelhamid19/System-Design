# 9 - Caching, Redis, and Elasticsearch

## Caching Challenges

- Expiry time management.
- Cache invalidation: when and how to update cached values.
- Interactions with horizontally scaled systems.
- Added development complexity and engineering effort.

## Redis

- In-memory key-value store. Extremely fast (microseconds).
- Common uses: query caching, user sessions, API rate limiting.
- Not typically used as the primary data store due to RAM cost and potential data loss unless persisted.

## Elasticsearch

- Optimized for large-scale full-text search, relevance ranking, and complex text queries.
- Often stores its own copy of data and is used as a search/indexing engine rather than the source of truth.
