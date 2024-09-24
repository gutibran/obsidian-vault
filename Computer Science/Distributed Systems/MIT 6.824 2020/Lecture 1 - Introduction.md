# What are distributed systems
- a set of cooperating computers communicating over the network to solve some problem
- storage for big websites, big data computation (map reduce), p2p file sharing
- critical infrastructure is built out of distributed systems
- the guy teaching is Robert Morris, the first guy arrested for computer crime

# When to use distributed systems
Last resort. If you can use one computer

High performance, achieve parrallelism. Lots of CPU, GPU, Disk arms
- tolerate faults (switch to another computer when one fails) -> this is primary focus on this course
- physical reasons (geography)
- achieve security goal (dealing with code or entity that you do not trust), isolate your computer

# What make distributed systems hard
- Parts execute concurrently, deal with the common concurrency problems.
- Unexpected failure patterns. Partial failures
- Hard to achieve the performance boost with so many computers involved, requires careful design
- Used in the real world, large websites. Used to be an academic curiosity back then.
- There are common solved problems but their are also alot of unsolved problems (good for research)
- Robert Morris

Whitepapers are for every lecture.

map reduce
Raft -> replicating systems, manage automatic, switch automatic to working server
key-value server -> based on raft
clone key-value server, split up the data, parrallism, move chunks between different servers, sharded key-value services
	- partition data among different servers

infrastructure for applications, applications use the infrastructure
- storage -> well defined and useful abstraction, fault tolerance, distributed, high performacne
- communication -> as a tool used to build the system -> mit.6829
- computation -> map reduce

build abstractions that hide the distributed nature of the system
build interface that looks and acts as if it is not distributed

the abstractions are hard and they are getting better as time moves forward

# main idead
- implementation
	- RPC (remote procedure call)
	- threads (programming technique to harness multicore computers, structure concurrent operations which simplifies view from programmers perspective, locks, concurrency control)
- performance scalability (speed up)
	- get more computers (resources) to scale how fast or how many problems are solved
	- get more throughput -> this is good because you can buy hardware, programmers are more expensive

small amount of users, the web server and db can be on the single server (computer)
- labor intensive optimization
- buy more web servers
	- split users -> half to one server half to another one, all servers talk to single db
	- limit load on the db
	- at some point the db will be a bottleneck, some point need to add another database
	- design work needed to push this idea infinitely far

fault tolerance
- good hardware is reliable
- stable power
- os is reliable

at scale there are likely some computers messing up
rare events become common problems
always have to consider failure in the design
- availability (replicated servers)
- recover-ability (service will stop but after repair occurs, service will continue as if nothing happened)
	- non-volatile storage (hard drives, ssd, flash to store checkpoint or log to recover state and build back up from that)
		- expensive to update (to write to)
	- replication
		- replication management
			- replicas drift out of sync and stop being replicas -> main problem for this

consistency
put(k, v) > store the value for the key, big table
get(k) > return the value for the key, from the big table

KEY VALUE SERVICES

what does put and get mean
- what if the client crashses, how will the tables be in sync
- strongly consistent
- weakly consistent