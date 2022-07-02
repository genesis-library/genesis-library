Antipatterns
- Massive arrays
16mb doc size limit,

In particular any data that is not useful apart from its parent document should be part of the same document.

[[?sharding]]
[[?profiler_usage]]
[[?journaling]]
[[?master_slave]]

[[atomicity]]
[[planning_schema]]
[[oreilly-notes]]

Disk lazy, goes to journal immediately

How replication works?
Replication set?

ObjectId: timestamp + clientMachineId + clientProcessId + 3byteIncrementedCounter

Atomic on single document
No transaction
Embedding for Atomicity and Isolation

[[indexes]]
[[?map-reduce]]
[[?optimizations]]
[[performance-killers]]
[[bson-objects]]
[[transaction-example]]