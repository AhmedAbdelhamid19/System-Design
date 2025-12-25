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
- may used to cache database queries, API rate limit, user sessions ...etc.

## Elasticsearch

- Optimized for large-scale full-text search, relevance ranking, and complex text queries.
- Often stores its own copy of data and is used as a search/indexing engine rather than the source of truth.

## IndexedDB
- used to store large amounts of structured data on the client side, enabling offline support, faster access, and reduced network requests.
- it's browser built in data base, persistent, asynchronous, used for offline support, caching API responses …etc.
- limited to browsers only, and user can clear it, and not shared across devices.