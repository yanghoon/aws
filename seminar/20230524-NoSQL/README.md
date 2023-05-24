# 

## Trend
* Mainframe, Client Server, 3 Tier, Microservice
* 용도에 맞게
  * 트래픽 특성에 맞게
  * 데이터 구조에 맞게
* Characteristics of Internet-scale Apps ~~Morden Application Environments~~
  * User 1M+, Data Size Tera--Peta--Eta
  * Global Locality, access mobile+IoT+Device
  * Performance Microsec latency, Millions/s req rate
  * scale virtually unlimited, economics pay-as-you-go
  * developer access instance api access, development app and storage decoupled

## AWS Services

### DynamoDB
  * Key-Value. from Dynomo Paper
  * Historycal Data
  * Table = Items[] \
    Item = Partition Key + [Sort Key] + Item Key[] + Projected[]
  * Partition Size <= 10 GB
  * GSI: ??\
    20 GSIs
  * hash(Partition Key) == determine AZ

### DocumentDB
  * Document. like MongoDB
  * 1  Write Primary? \
    15  Read Replica
  * Global Cluters. Low Replica Lag < 1 sec

### ElasticCache
  * In-Memory. like Redis and Memcache
  * Session Status
  * Persist for Restart
  * Cache between EC2 and RDS
  * Support Multi AZ, Shard + Replica (eg. 3 Shards, 2 Replicas)

### Neptune
  * Graph
  * 3 AZ, 6 Copy (like Aurora)

### Timestream
  * Time-series
  * Ingestion Layer + Storage Layer + Query Layer \
    In-Memory -> HDD

### Quantum Ledger Database
  * Ledger. Block Chain(원장)
  * Block Chain as S3 Bucket
  * used HR

### Keyspaces
  * wide-column, Cassandra

