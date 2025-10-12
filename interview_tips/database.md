## 🧩 Database

### 🧱 Fundamentals
- **RDBMS vs NoSQL**
  - RDBMS: structured schema, SQL-based, relational integrity
  - NoSQL: flexible schema, horizontal scalability, eventual consistency
  - Examples:
    - RDBMS: PostgreSQL, MySQL, MariaDB
    - NoSQL: MongoDB, Cassandra, Redis, DynamoDB
- **ACID Principles**
  - Atomicity, Consistency, Isolation, Durability
  - Ensures transactional reliability in RDBMS
- **CAP Theorem**
  - Consistency, Availability, Partition tolerance (choose 2)
  - CP: MongoDB, HBase  
  - AP: Cassandra, DynamoDB  
  - CA: traditional RDBMS (when no partition)
- **Choosing NoSQL Type**
  - Key-Value: Redis, DynamoDB (cache/session)
  - Document: MongoDB (flexible JSON data)
  - Column Family: Cassandra (analytics, wide tables)
  - Graph: Neo4j (relationship-heavy)

---

### ⚙️ Indexing
- **Principles**
  - Accelerates data retrieval by reducing disk I/O
  - Typically implemented with **B+ Trees**, sometimes **Hash Indexes**
- **Time Complexity**
  - Search: O(log n) for B+ Tree
  - Hash index: O(1) average but unordered
- **Use Cases**
  - B-Tree: range queries, sorted data
  - Hash: equality lookups
  - GIN / GiST: full-text search, arrays, JSONB in PostgreSQL
- **Advantages**
  - Drastically reduces query latency
- **Disadvantages**
  - Slower writes (INSERT/UPDATE)
  - Extra disk usage
- **Covering Index / Composite Index / Partial Index**
  - Optimize specific query patterns
  - Avoid over-indexing

---

### 🧩 Database Normalization
- 1NF: atomic values  
- 2NF: remove partial dependencies  
- 3NF: remove transitive dependencies  
- Denormalization for performance (joins trade-off)

---

### 🚀 RDBMS Optimization
- **Slow Query Optimization**
  - Use `EXPLAIN` / `EXPLAIN ANALYZE` to inspect query plans
  - Add indexes where needed
  - Avoid `SELECT *`
  - Optimize JOIN order and conditions
- **Sharding**
  - Splitting data across multiple nodes (horizontal scaling)
  - Requires application-level routing or proxy (e.g., Vitess)
- **Partitioning**
  - Divide a large table into smaller parts (range, list, hash)
  - Improves query performance and manageability
- **Using Redis as Cache**
  - Store frequently accessed data to reduce DB load
  - Cache invalidation strategies (write-through / write-behind / TTL)
- **Hardware Upgrade**
  - SSDs, more RAM for buffer pool, faster CPU cores
- **Read-Write Separation**
  - Primary for writes, replicas for reads (load balancing)
  - Use connection pooling and read routing
- **Connection Pooling**
  - Tools: `pgbouncer`, `HikariCP`
  - Reduces overhead of frequent connection creation
- **N+1 Problem**
  - Caused by excessive per-row queries
  - Use JOIN or ORM prefetching (e.g., Django `select_related` / SQLAlchemy `joinedload`)

---

### 🔥 Redis (In-Memory Store)
- **Core Characteristics**
  - In-memory, single-threaded (but event-driven & very fast)
- **Data Structures**
  - String, Hash, List, Set, Sorted Set, Bitmap, HyperLogLog, Geo
- **Distributed Lock**
  - Implemented via `SETNX` or Redlock algorithm
- **Atomic Operations**
  - All commands are atomic (single-threaded execution)
- **Transactions**
  - MULTI / EXEC / WATCH (not ACID but pseudo-atomic)
- **Persistence Options**
  - RDB snapshotting, AOF (Append Only File)
- **Advantages**
  - Extremely low latency, high throughput
- **Disadvantages**
  - Memory-limited, risk of data loss if not persisted
  - Needs eviction strategy for full memory
- **Common Use Cases**
  - Caching, session storage, message queues, distributed locks, rate limiting

---

### 🧰 SQL Basics
- **JOINs**
  - INNER, LEFT, RIGHT, FULL OUTER, CROSS
- **Aggregation**
  - COUNT, SUM, AVG, MAX, MIN
- **GROUP BY / HAVING**
  - Used for aggregation and filtering aggregated results
- **Subqueries / CTE (Common Table Expressions)**
- **Window Functions**
  - `ROW_NUMBER()`, `RANK()`, `LAG()`, `LEAD()`
- **Transactions**
  - BEGIN / COMMIT / ROLLBACK
  - Isolation levels: READ COMMITTED, REPEATABLE READ, SERIALIZABLE

---

### 🐘 PostgreSQL
- **Architecture**
  - Process-based model, shared buffer, WAL (Write-Ahead Log)
  - MVCC (Multi-Version Concurrency Control) for isolation
  - Background processes: autovacuum, walwriter, checkpointer
- **Key Features**
  - ACID-compliant
  - JSONB support (document-style queries)
  - Rich indexing (B-Tree, Hash, GIN, GiST, BRIN)
  - Window functions, CTEs, recursive queries
  - Advanced data types (Array, Range, HStore, Enum)
  - Full-text search with `tsvector` / `tsquery`
  - Foreign Data Wrapper (FDW) for external data sources
- **Optimization Tools**
  - `EXPLAIN (ANALYZE, BUFFERS)`
  - `pg_stat_statements` for slow query tracking
  - VACUUM / ANALYZE / REINDEX for maintenance
  - Index-only scans
- **Performance Tuning**
  - Adjust `work_mem`, `shared_buffers`, `effective_cache_size`
  - Partitioning large tables
  - Use connection poolers (`pgbouncer`, `pgpool-II`)
- **Replication**
  - Streaming replication (async/sync)
  - Logical replication for selective table sync
- **Backup & Recovery**
  - WAL archiving, PITR (Point-In-Time Recovery)
  - Tools: `pg_dump`, `pg_basebackup`
- **Security**
  - Role-based access control
  - SSL/TLS, row-level security, extensions like `pgcrypto`
- **Extensions**
  - PostGIS (GIS), TimescaleDB (time-series), pgvector (vector embeddings)
- **Common Interview Points**
  - How MVCC works  
  - How PostgreSQL handles dead tuples  
  - Difference between VACUUM and ANALYZE  
  - How JSONB is indexed  
  - How to tune connection pool size  

---

### ⚡ Quick Summary
> **RDBMS ensures ACID properties; NoSQL offers scalability and flexibility.**  
> Use **indexes** wisely for query speed but avoid over-indexing.  
> Optimize databases via **query analysis**, **partitioning**, and **caching (Redis)**.  
> **PostgreSQL** stands out for its MVCC, JSONB, and advanced indexing.  
> Real-world performance = schema design + indexing strategy + caching discipline.
