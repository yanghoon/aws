# 

## Trend
* Mainframe, Client Server, 3 Tier, Microservice
* 용도에 맞게
  * 트래픽 특성에 맞게
  * 데이터 구조에 맞게
* Morden Application Environments
  * User 1M+, Data Size Tera--peta
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
  * GSI: ??\
    20 GSIs

### DocumentDB
  * Document

### ElasticCache
  * In-Memory
  * Redis + Memcache
  * Session Status

### Neptune
  * Graph

### Timestream
  * Time-series

### QLDB
  * Ledger
  * 원장?

### Keyspaces
  * wide-column
  * Cassandra