# systemDesignKeypoints

## Scaling

1.Single server design(server+database)-if failure, all service down
2.Separating out database - a little bit good for resiliency point (server database don't shut down at the same time) and can scale separately depend on need more CPU or storage space or data intensive operation(join).
3. Vertical scaling (maybe a better hardware virtual machine)  still single point of failure, but fewer service to maintain
4. Horizontal scaling - have load balancer to distributing the load (round robin/ partitioner)
RR: cpu run evenly time on different process, Partitioner: seperate the large task and distributing to different server (server should be stateless, cause server don't know previous status, from other router)


## datalake
just throw data into text file(csv json) into big distributed storage system like Amazon S3
which called data lake (maybe unstructured file)
Amazon glue will create a schema for that data
Amazon Athena (serverless) to query
Amazon Redshift (distributed data warehouse)
need to partition data for performance(maybe based on date and how end user will query these data)

## ACID Compliance
Atomicity: either entire transacrtion succeeds or fails(rolled back) eg: transaction
Consistency: consistently applying the rules, or transaction is rolled back
Isolation: No transaction is affected by any other transaction that is still in progess
Durability: Once a transaction is committed, it stays, even if the system crashed immediately

## CAP Theorem
(Availability, consistency, partitionTolerance) choose 2 from 3


## Caching layers
Keep in memory copies of database
Horizontally scaled servers
client hash request give server in-memory
ask interviewer how long can I hold data in cache
hotspots-celebrity problem, can be cache
cold start- no data in the cache, all request goes to database may make DB failed (before user can make request, artifically make request based on the backlog to simulated request and build cache)

## Eviction policies

LRU: Least recently used, LFU: Least frequently used, FIFO: First in first out

## Cache technology
Redis, ElastiCache (AWS)

## CDN content delivery networks
desribute the serving of data globally from local resources
edge location physically close to the end user
(pricey)

AWS cloudFront

## Design for Resiliency

things can fail: single server, entire rack, entire data center(AZ availability zone), engire region

secondaries (backup) spread accross multiple racks, AZ, and regions
system has enough capacity to survive a filure 



