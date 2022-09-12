

1. Seperate Engine: OLTP(ByteNDB, like Aurora）+ OLAP(Flink), Two OLTP Row-data + OLAP Delta Store（row，IN-MEM）+ Base Store（Col，Persistent）
2. OLTP log repica to OLAP, two operation（Insert、Delete), Delete-list and delete hashmap and bitmap（RocksDB）,soft-delete optimization：put delete-list and wait for groom process to compaction or GC

Adavantages:

+ High data freshness(less than one sec)

+ Strong data consistency

  using global timestamps(global snapshot) to provide consistency between OLTP and OLAP nodes.

​	   Doesn't support mixed DMLs and OLAP read-only queries due to ByteHTAP does not support distributed transactions across OLTP and OLAP engines