## what's the difference between replica, redundancy, partitioning, sharding?
    - Replication (copy data) focuses on data and means copying data from one server to other servers.
    - Redundancy (copy component/resource …) means having extra resources available so the system keeps working if something fails (servers, databases (backup), networks, power supplies, disks).
    - Partitioning means splitting one database table into logical parts inside the same database server.
        - horizontal partitioning
            □ for example the able order is split into partition 2023, 2024 …
            □ organize and speed up large tables, inside same server like single big notebook divided into sections        
        - vertical partitioning
            □ split the columns itself in very big table that consist of multiple columns and connect them by FK
    - sharding (slices) means splitting the data across multiple servers or multiple database instances, focuses on different machines.
        - horizontal sharding (common)
            - user A to M lives on Server1, user N to Z lives on server2, like instead of one notebook, you make multiple notebook each for some sort of data
        - vertical sharding
            - split columns to different servers
        - sharding usually means same table, split by rows, across many servers.
        - interact with horizontally scaling and high availability (solution for huge traffic).

## what's the different between NoSQL and use JSON column in relation database?
    - relation DB: 
        - You still have tables and columns, but one column can store dynamic JSON data.
        - Horizontal scaling (sharding) is possible, but becomes complex due to joins, cross shard queries, and distributed transactions.
        - some DBMS allow you to query inside JSON but it's not as rich as NoSQL query system
    - NoSQL:
        - You can store data in formats like key-value, document (JSON-like), column-family, or graph.
        - Built to scale horizontally easily (sharding across multiple servers is native).
        - you can query based on keys and nested keys (document), this supported in NoSQL databases like MongoDB
## what's the problems that may appears with sharding?
    - joins, because you will need to make network calls so it slow the query and make it complex (cross sharding queries).

## what serverless means?
    - means you don’t manage servers (doesn't mean you don't use servers at all).
    - The cloud provider (AWS, Azure, GCP) handles scaling, infrastructure, failures …etc.

## what's the difference between fault tolerance and availability?
    - they are connected but are not the same.
    - system may have High availability but low fault tolerance
        - you have powerful server with no backups, so your system available unless it fails
        - availability touches with latency, load and responsiveness, for example we made our system available 99% percent of the time or 99.99% percent .
    - system may have High fault tolerance but low availability
        - A system might survive failures but take a long time to recover or respond slowly
        - fault tolerance means when part of system dies, then who should your system recover quickly and make your data in safe hand.

## do you prefer your system to be AP or CP?
    - It depends on business requirements and acceptable behavior during a partition.

## list some differences between relational DB and NoSQL DB?
    - relational DB focuses on correctness and structure first, NoSQL focuses on scaling and flexibility.
    - sometimes hybrid system used, so some features deal with NoSQL, other deal with relational DB.
    - relational
        - correctness, transactions (ACID), integrity.
        - data split into many tables connected by relationships, this avoid duplication but requires joins (joins become expensive at scale).
        - add new columns requires migration, change schema (modern relational databases support online schema changes without full table locks), lock table, and risk in production.
        - you get right data, no contradictions.
        - you can make column of type JSON and store nested data (but don't powerful like NoSQL database)
    - NoSQL (not only sql)
        - scalability, horizontal scale, flexibility (schemaless). 
        - you don't need to make joins (you can store nested data), support fast read, but cost duplication.
        - instead of storing data in seperated tables, we store it as nested data (store devices information inside user collection).
        - should have implicit schema to reduce work and overhead you make, means avoiding random keys and random nested data …etc. to ease it to you when you work with backend (deserialization).

## what's more high available NoSQL or relational DB?
    - NoSQL prioritizes availability, relation DB support strong consistency (remember CAP theorem)

## list some challenges should be handled with caching?
    - expiry time should be handled carefully.
    - when the cache be updated.
    - caching in horizontal scaling.
    - complexity and development time and effort

## backend should by stateless or statefull?
    - Backend APIs should be stateless, especially in modern web systems, unless there is a specific case that forces a stateful design.
    - because When many users hit your backend at the same time, you want any request to be handle by any server (if you scaled horizontally).
    - if it was stateful (The server keeps the user session or temporary data in its memory), you will consume server resources.

## what's the difference between caching and statefull backend?
    - statefull means The server remembers user specific data between requests.
    - caching means storing reusable data to avoid recomputation.

## what challenges may appears with duplication with NoSQL databases?
    - the core problem is keeping duplicated data consistent (up-to-date).
    - for example if 'price' stored in product document and order document …., and 'price' is updated, the challenge is how to update the price in all instances in all documents.
    - updates are often propagated asynchronously, which commonly results in eventual consistency where users may temporarily read stale data.

## there're a lot of ways to update the data in NoSQL database list some?
- background propagation (send event to workers to updated related parts), immutable data (old data never update), read repair (on read detect stale data) …etc.