# Redis Cache Client-side

1. Client-side caching is a technique to enhance service performance by storing a subset of database information in application memory.
2. It reduces latency and database load by reusing replies of popular queries without contacting the database again.
3. A challenge is invalidating the information to avoid serving stale data, which can be addressed by setting a maximum "time to live" for the cached information or using Redis' Pub/Sub system.
4. Redis 6 introduces direct support for client-side caching, called "Tracking", with two modes: a simple mode and a broadcasting mode.
5. To limit server-side memory use and CPU cost, Redis uses two key ideas: two connections mode and using the new RESP3 protocol.
6. Client-side caching tracks every key mentioned in the context of a read-only command, but clients can also choose to cache only selected keys (opt-in) or cache everything (opt-out).
