Services and Rails, The Shit They Don't Tell You
@brianxq3

- How Yammer built services alongside Rails

- Fun Facts
  - Over 100 web, 40 memcache
  - 98% cache hit rate
  - 240,000 memcache gets/sec

- Not Fun Facts
  - Test suite takes ~10 hours

- Clean code is easier to extract into services

- Yammer, a huge rails app
  - 300+ models, 200 controllers
  - 20+ jvm services

- Service Oriented Architectures
- Components that scale *individually*

- Reusability
  - Rails app
  - Denormalized data store service
  - Indexing service
    - Search interface
    - Auto-complete

- Scalability
  - Easier to scale out service
  - Known and predictable usage

- Loose coupling
  - Smaller and more focused
  - Encapsulated concerns
  - Push updates independently
  - Change out everything without telling anyone

- Codebases that scale organizationally

- Distributed execution
  - Enabled by loose coupling
  - Assign a team to the service
  - Two teams coordinate/agree on APIs
  - Use dummy components

- This doesn't happen overnight

- Conway's Law
  - Organizations which design systems are constrained to produce designs which are copies of the communication structures of these organizations - Melvin Conway

- The messaging team
  - Rails -> Service
  - Decides on the interface and implements
  - Has siloed knowledge of system

- Rils and Core Services Teams
  - Rails -> Services

- Cross-functional Teams
  - 2-10 people for 2-10 weeks
  - Developer tools, core-product features, etc.
  - Pool of engineers to work on wide-range of problems
  - Spin up, learn domain
  - Take advantage of distruted execution

- Tradeoffs
  - Have some cost with not having siloed "experts"
  - Be careful not to couple the API implementation to the client
  - After project is completed, we still have to support the feature

- There's more than one way to do this

- Put them all behind rails
  - Browser talks to rails, rails talks to database and services

- ActiveRecord holds your data hostage

- Record-cache

- What are your options?
  - Don't use activerecord?
  - Use your services as indexes - just store the IDs
  - Move the data to the service that owns it

- Moving data means duplicating

- Moving data
  - Chances are you can't have downtime to move data

- Double dispatching
  - Backfill data to the service
  - Write data to database and POST to the service
  - Service can be monitored and profiled
  - Move to the service incrementally

- Now you have duplicate data

- The old way is comfortable
  - Have to be OK with breaking comfort zone

- Make shit easy for developers
  - Vagrant

- Development environment
  - Close to production
  - Running services locally
  - Keep up with rapidly changing services
  - Shouldn't need intimate knowledge

- Deploying services
  - Need a system that allows you to add new services quickly
  - Easy to deploy each service
  - Maintain stable and pre-released versions

- Monitoring and alerting
  - Performance monitoring
  - Capacity planning and queue depths
  - Reachability from dependent clients
  - Ganglia?

- Standarized Tools
  - Dropwizard (dropwizard.codehale.com)

- Service tradeoffs
  - Handle unavailability
  - Transactions aren't free
  - APIs are much harder to change
  - There are no atomic deploys

- Complex systems fail

- Know what happens when shit blows up

- Recap
  - Always reevaluate your costs and their viability
  - Something I missed
  - Tools that allow you to keep moving fast