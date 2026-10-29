#### Strict isolation
- Strict isolation - guarantee we never experience lost updates, dirty reads, or unrepeatable reads
- Non-strict isolation - let transaction continue to execute despite potential problems (optimistic)
- Can be enforced with two-phase locking, timestamp ordering and optimistic concurrency control