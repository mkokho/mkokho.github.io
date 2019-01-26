# Reliability Pillar 

Design principles:
 - test recovery procedures
 - automatically recover from failure
 - scale horizontally
 - stop guessing capacity
 - manage change in automation

Understand **availability needs**: components that have higher availability design goals will necessitate deeper investment in the engineering, testing, and operations automation.

Areas
- [Foundations](#foundations)
- [Application design for availability](#application-design-for-availability)
- [Operational Considerations for Availability](#operational-Considerations-for-Availability)
- [Example checklist for a typical web application](#example-checklist-for-a-typical-web-application)


### Foundations 
 - limit management
  - physical limits
  - service limits
  - automate limit increase
 - networking
  - allow IP addresses for more than one region
  - allow space for multiple subnets
  - always leave unused CIDR blocks
  - consider cross-account connections to shared services
  - ensure resiliency of connectivity

### Application design for availability

 Common sources of interruption:
 - hardware failure
 - deployment failure
 - load induced
 - data induced
 - credential expiration
 - dependency
 - infrastructure
 - identifier exhaustion

Common practices to improve availability:
 - fault isolation zones and shards
 - redundant components
 - micro-service architecture
 - recovery oriented computing
   - isolation and redundancy
   - ability to rollback changes
   - ability to monitor health
   - ability to provide diagnostics
   - automated recovery
   - ability to restart
 - distributed systems best practices
   - throttling
   - retry with exponential fallback
   - fail fast
   - use of idempotency tokens
   - constant work ?
   - circuit breaker
   - statically stable ?

### Operational considerations for availability
- automated deployments
  - canary deployments
  - blue-green deployments
  - feature toggles
  - failure isolation zones deployments
- testing
  - load testing
  - failure testing
  - canary testing
- monitoring and alarming: generation, aggregation, real-time processing, storage and analytics
 - percentile metrics shows impending problems
 - monitor external endpoints from remote locations

### Example checklist for a typical web application
  - adapt to change in demand
  - use monitoring
  - deploy changes
  - back up data
  - implement resiliency
  - test resiliency
  - recover from disaster



