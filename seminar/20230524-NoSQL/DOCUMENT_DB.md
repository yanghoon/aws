# DocumentDB

## Key Concepts

### Features
* Schemaless (No Alter)
  * more large block size than RDB (_id + fields * rough unit size)
* Multi Leader Write (with Sharding)
* Support JSON Native (BSON)

### Write/Read

**Write**
* Buffer Pool
* Journal (Removed after checkpoint)
* Checkpoint (write dirty-page to disk on background)
  * I/O Throttle: MongoDB(x), RDB(o)
  * Schedule Period: default 1m

**Read**
* Keep buffer pool as default 50%
* Eviction : keep usage of buffer pool as 80%

### Replica Set

* Primary + Secondary + Arbitor
* Replica: 1 to 50
* $0.02/GB between AZ
* Oplog : Primary + One of Replica

### Sharding

* config server : have to configure as Replica Set
* mongos(Router)
  * in-memory cache of config server
* only key-range sharding (hsah-key as key-range)
* BroadCast Query (vs Target Query)
  * unknow data where is placed
  * query to all shard and aggregate them
  * scatter and gather

### Tak Executor Pool

* have to monitoring
* connection pool between routers and shards

### Cursor/Tcmalloc (on Single Query)

**Cursor**
* Called Getmore, Aggregtion, count()
* Used OS Heap 16MB by Tcmalloc

**Tcmalloc**
* by Google
* Each Thread Cache
* use Centreal Heap more large size
* Spin Lock Wait
* monitoring `spinlock_total_delay_ns`

### Read/Write Ticket (on All Query)

* Query Queue (Each Server, default 128)
* Each read/write take 1 ticket
* max(vCore x2, 128)
* Queued query is not monitored as Slow Query
