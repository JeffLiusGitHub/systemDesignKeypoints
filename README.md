# systemDesignKeypoints

## Scaling

1.Single server design(server+database)-if failure, all service down
2.Separating out database - a little bit good for resiliency point (server database don't shut down at the same time) and can scale separately depend on need more CPU or storage space or data intensive operation(join).
3. Vertical scaling (maybe a better hardware virtual machine)  still single point of failure, but fewer service to maintain
4. Horizontal scaling - have load balancer to distributing the load (round robin/ partitioner)
RR: cpu run evenly time on different process, Partitioner: seperate the large task and distributing to different server (server should be stateless, cause server don't know previous status, from other router)


