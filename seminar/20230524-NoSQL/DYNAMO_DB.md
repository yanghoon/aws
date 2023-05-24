# DynamoDB

## History And Trends

* Most Traffic quering 1 Single Table
* On-Premise(DC) + Commercial Database
* Tier 0 service (Backbond Data Storage for AWS Service)

* Global-Scale Events
  * Cruise Mode in Korea and US
  * Traffic Explosion by Mobile Device

* AWS Bookstore Example
  * https://github.com/aws-samples/aws-bookstore-demo-app
  * Unlimited Items. Low Latency
  * Counting
  * User Custom Data

* mission-critical OLTP
* full serverless experience

* Elastic of Database
  * 2x Write Traffic, Chatting Apps (12.31 - 01.01)
  * Variable Cost of Database

* Low Latency
  * Millions of req/sec per table
  * Millisecond 

* high-performance, globally distributed
* low-latency reads and writes to locally avaliable tables
* multi-region redundancy and resiliency and 99.999% availability
* multi-active writes from any regison
* legal, replicated data tiering

### DynamoDB Accelerator (DAX)
* Read Cache in front of Dynamo
* 1 Primary, Max 10 Replica

## Cost Optimization

per-req
per-gb-storage
scale-to-zero

no instance
no manintenance windows
no version upgrade
no query processor
automatic scaling

### Usage
* No Ops
  * devops (no dba)
  * global service
  * no versions
* write intensive
  * IoT / Monitoring
  * User Activity Logging
  * Tracking (History)
  * Step Count (Vote, Ticketing)
  * Chatting
* Consistent Latency
  * Ad
  * Session Store
  * User Profile
  * Purchase History of Product Details

### References
* https://www.youtube.com/watch?v=Lq4aNihcS8A

## Key Concepts

Optimized for storage (SQL)
* normalized/relational
* ad hoc queries
* scale vertically
* goot for oltp & olap

### Global secondary index (GSI)

### Local secondary index (LSI)

* Stored in Partition (<=10GB)
* Strong Consistency
* Not Modified after Creating Parition



