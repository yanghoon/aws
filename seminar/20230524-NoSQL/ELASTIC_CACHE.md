# ElasticCache

## Key Concepts

* Write jounal log for persist in AZ
* can test by `redis-benchmark`
* cheeper 65% than MemoryDB for Redis

### Advantage (over Redis)
* Ops, HA, Scale, Cost

### Thread Model
* Elasticcache Redis 6.x : multiple worker thread
* Elasticcache Redis 7.x : enhanced IO multiplexing thread
  * better throught over 2000+ client

### Scacle
* Scale-Out than Scale-Up
* 500 Shard. Shard = 1 Primary + 0-5 Replica
* No Router Component

### Data Model
* String (bitmap, bitfield)
  * Simple Dynamic String (long len; long free; char bug[])
* Hash
  * Ziplist -> listpack (redis 7.x)
  * entry 512 bytes == hashtable, 64 kbytes ziplist
* List, Set, Sorted Set (eg. Rank)
* Geospatial
* HyperLogLog
* Stream
* PubSub

## Usecase

### Query Caching
* key == hash(MD5, Query String), value == result

* Header
* Recommendations
* Trending
* Main

### Patterns
**Lazy Loading**
* Cache Hit or Cache Miss -> Read Database -> Cache Update
  * Hot Data in Cache, Consistency
  * Eviction Algorithm

**Write Through**
* Write Database -> Change Data Capture -> Cache Update -> Cache Hit
  * All Data in Cache

### Props Elasticcache

**Cluster Connections**
* Single Cluster Endpoint (by DNS?)

**Support IAM**

**Global Datastore**
* for Global Latency (RTT)
* Primary Region, Replication Region

**Auto Scaling**
* Scale-Out > Scale-Up
