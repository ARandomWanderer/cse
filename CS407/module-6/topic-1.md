---
layout: default
course: CS407
module: 6
topic: 1
---

# Distributed Systems

## Ricart–Agrawala Algorithm

>Ricart–Agrawala algorithm is an algorithm to for mutual exclusion in a distributed system proposed by Glenn Ricart and Ashok Agrawala. 

>This algorithm is an extension and optimization of Lamport’s Distributed Mutual Exclusion Algorithm. Like Lamport’s Algorithm, it also follows permission based approach to ensure mutual exclusion.

In this algorithm:

- Two type of messages ( **REQUEST** and **REPLY**) are used and communication channels are assumed to follow FIFO order.
- A site send a **REQUEST** message to all other site to get their permission to enter critical section.
- A site send a **REPLY** message to other site to give its permission to enter the critical section.
- A timestamp is given to each critical section request using **Lamport’s logical clock**.
- Timestamp is used to determine priority of critical section requests. Smaller timestamp gets high priority over larger timestamp. 
- The execution of critical section request is always in the order of their timestamp.

### Requesting the critical section:
1. When a site Si wants to enter the CS, it broadcasts a timestamped REQUEST message to all other sites.
2. When site Sj receives a REQUEST message from site Si, it sends a REPLY message to site Si if and only if 
    - site Sj is neither requesting nor executing the CS, or if the site Sj is requesting or
    -  Si ’s request’s timestamp is smaller than site Sj ’s own request’s timestamp.

Otherwise, the reply is deferred and Sj sets RDj [i]=1 
### Executing the critical section:
3. Site Si enters the CS after it has received a REPLY message from
every site it sent a REQUEST message to.

### Releasing the critical section:
4. When site Si exits the CS, it sends all the deferred REPLY
messages: ∀j if RDi
`[j]=1`, then send a REPLY message to Sj and
set RDi `[j]=0.`

>Notes:
When a site receives a message, it updates its clock using the timestamp in the message.
When a site takes up a request for the CS for processing, it updates its local clock and assigns a timestamp to the request.