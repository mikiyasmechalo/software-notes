---
title: Distributed Systems
teacher: Felix Edisa
---
# CH 01: Introduction

 The organization of a (a) centralized, (b) decentralized, and (c) distributed system, according to various popular sources.
![[Pasted image 20261026175725.png]]

> When does a decentralized system become distributed? how many new links?

If we think of a networked computer system as a collection of computers connected in a network, we can ask ourselves how these computers even became connected to each other in the first place.
There are roughly two views:-
- **Integrative view**: connecting existing networked computer systems into a larger a system.
	- when services running on a system need to be made available to users and applications that were not thought of before.
	- e.g. integrating financial services with project management services in a single organization
- **Expansive view**: an existing networked computer systems is extended with additional computers.
	- most often related to the field of distributed systems.
	-  It entails expanding a system with computers to hold resources close to where those resources are needed.
	- An expansion may also be driven by the need to improve dependability, in case of failure.
	- e.g. adding a web interface for a system for a remote uses & applications.
- The distinction between an integrative and an expansive view is not a clear-cut.
- In both cases, we see that the networked system runs services, where each service is implemented as a collection of processes and resources spread across multiple computers. 
- The two views lead to a natural distinction between two types of networked computer systems:

- A **decentralized system** is a networked computer system in which processes and resources are *necessarily* spread across multiple computers.
	- No single point of control.
	- They come to being because we want to connect systems, yet may be hindered by administrative boundaries. (Integrative view)
	- e.g. distributed ledger/blockchain. -  is a decentralized system in which processes and resources are, necessarily spread across multiple computers, in this case due to lack of trust (participating parties do not trust each other enough to set up simple schemes for collaboration).
	- e.g. systems that are naturally geographically dispersed, like powerplants, traffic lights, satellites. Here, the necessity for spreading processes and resources comes from a spatial argument.

- A **distributed system** is a networked computer system in which processes and resources are *sufficiently* spread across multiple computers.
	- Emphasizes system-wide integration.
	- e.g. an email service like Gmail, the user configures a specific mail client with incoming and outgoing server. while it seems there are only 2 computers handling those servers in the backend, in reality the Gmail service is implemented and spread across many computers to ensure scalability & fault tolerance. BUT this fact is highly transparent to the user.
	- e.g. A CDN, usually have a lot of servers worldwide., the user is transparently redirected to a nearby server that holds all or part of the content of that Website. The user knows nothing about what is going on behind the scenes. (transparency)
		- and also, that content is not copied to all servers, yet only to where it makes sense, that is, "*sufficiently*" and for reasons of performance, and also dependability.
	- e.g. NAS - any authorized device, and as such can offer services like shared storage, automated backups, streaming media, and so on. "Sharing" is the key point here, where and how the shared files are stored is hidden (i.e., the distribution is transparent).
		- Assuming that sharing files is the goal, then we see that indeed a NAS can provide sufficient spreading of processes and resources.

#### Some common misconceptions
**"Centralized solutions do not scale"** 
-  a difference should be made between logical and physical designs.
- A logically centralized solution can be implemented in a highly scalable distributed manner.

e.g. *Domain Name System (DNS)* 
- *Logically*, DNS is organized as a huge tree, where each path from the root to a leaf node represents a fully qualified name, such as www.distributed-systems.net.
- *Physically* massively distributed - the root node is implemented by 13 different root servers, each server, in turn, implemented as a large cluster computer.
- Decentralized across multiple organizations

**"Centralized solutions have a single point of failure"** 
Generally not true (e.g., the root of DNS). 
and even then, sometimes a single point of failure is often:
- easier to manage
- easier to make more robust

**Common misconceptions exist regarding:** 
- Scalability
- Fault tolerance
- Security

Notes:
- Distributed and decentralized systems suffer almost continuously from partial failures.
	- some resource or process may not operate as expected, and discovering that failure might take some time. while, they are preferably masked from the user.
	- participating nodes, processes, resources, and so on, come and go. This makes these systems highly dynamic, in turn requiring forms of automated management and maintenance, in turn increasing the complexity.
 - In principle, the less spreading, the better. Yet at the same time, we need to realize that spreading is sometimes truly necessary, as illustrated by the examples of decentralized systems.


## Design Goals
Just because it is possible to build distributed systems does not necessarily mean that it is a good idea.
Four important goals that should be met to make building a distributed system worth the effort:
#### 1. Resource sharing
 - Efficient use of distributed hardware and software resources.
- Resources can be virtually anything, but typical examples include peripherals, storage facilities, data, files, services, and networks.
- Many reasons to want this: - Economics, easier to collaborate and exchange information.
- Resource sharing in distributed systems is also illustrated by the success of file-sharing peer-to-peer networks like BitTorrent.
- Seamless integration of resource-sharing facilities in a networked environment is also now commonplace. e.g. shared folders over LAN

#### 2. Distribution transparency
- to hide the fact that its processes and resources are physically distributed across multiple computers, possibly separated by large distances. (Complex.)
- achieving distribution transparency is realized through what is known as middleware.
- what applications get to see is the same interface everywhere, whereas behind that interface, where and how processes and resources are and how they are accessed is kept transparent.
- *Types of Transparency*: (object can be a process or resource)
	- Access - Hide differences in data representation and how an object is accessed.
	- Location - Hide where an object is located
	- Relocation - Hide that an object may be moved to another location while in use.
	- Migration - Hide that an object may move to another location
	- Replication - Hide that an object is replicated
	- Concurrency - Hide that an object may be shared by several independent users
	- Failure - Hide the failure and recovery of an object
- Although distribution transparency is generally considered preferable for any distributed system, there are situations in which blindly attempting to hide all distribution aspects from users is not a good idea. So, it should be considered together with other issues such as performance and comprehensibility.
- Completely hiding failures of networks and nodes is (theoretically and practically) impossible, You cannot distinguish a slow computer from a failing one.

#### 3. Openness
- offers components that can easily be used by, or integrated into other systems.
- A general approach is to define services through interfaces using an Interface Definition Language (IDL).
- *Interoperability* - how well components made by different manufacturers can co-exist by merely relying on each other's services as specified in the common standard.
- *Portability* - the extent an application developed for a distributed system A can be executed without modification on another system B that implements the same interfaces.
- an open distributed system should also be *extensible*. (easy to add/replace components.)

#### 4. Dependability
- degree to that a computer can be relied upon to operate as expected.
- In DS this is more intricate due to partial failures. In fact, one should assume that at any time, there are always partial failures occurring.
- An important goal of distributed systems is to mask those failures, as well as mask the recovery from those failures. AKA ***Fault Tolerance***.
- Dependability covers several requirements for DSs including:
	- *Availability*: system is ready to be used immediately. probability that the system is operating correctly at any given moment.
	- *Reliability*: the system runs continuously and without failure. Defined in terms of a time interval instead of an instant in time. High availability != High reliability.
		- a system that goes down for one millisecond every hour has high availability (99.999) but is unreliable.
		- a system that never crashes but is shut down for 2 specific weeks in august has a 96% availability but is highly reliable.
	- *Safety*: when a system fails to operate correctly, no catastrophic events happen.
	- e.g. control systems for a nuclear power plant are required to provide a high degree of safety, since a small failure could be disastrous.
	- *Maintainability*: how easy a failed system can be repaired. 
	- a highly maintainable system may also show a high degree of availability, especially maintenance is automatic (easier said than done).

Traditionally Fault-tolerance has been related to the following 3 metrics:
1. ***Mean Time To Failure (MTTF)***: The average time until a component fails.
2. ***Mean Time To Repair (MTTR)***: The average time needed to repair a component.
3. ***Mean Time Between Failures (MTBF)***: MTBF+MTTR

Note that these metrics make sense only if we have an accurate notion of what a failure actually is. (identifying the occurrence of a failure may not be so obvious).

##### Faults, Errors, Failures
A system is said to *fail* when it cannot meet its promises.
In DS, the system has failed when one or more of the services it provides cannot be (completely) provided.

An *error* is a part of a system’s state that may lead to a failure.
e.g. for packets, it is expected that some may be damaged (the receiver may incorrectly sense a bit value (e.g., reading a 1 instead of a 0), or may even be unable to detect that something has arrived)

The cause of an error is called a *fault*.
e.g., a wrong or bad transmission medium may easily cause packets to be damaged (easy to fix). but transmission errors may also be caused by bad weather conditions, in wireless networks.
- for a program w/c crashed by a buggy code (a programming error), the cause is a programmer.

**Handling faults**

| **Term**          | **Description**                                                         | **Example**                                                                  |
| ----------------- | ----------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Fault prevention  | Prevent the occurrence of a fault                                       | Don’t hire sloppy programmers                                                |
| Fault tolerance   | Build a component and make it mask the occurrence of a fault            | Build each component by two independent programmers                          |
| Fault removal     | Reduce the presence, number, or seriousness of a fault                  | Get rid of sloppy programmers                                                |
| Fault forecasting | Estimate current presence, future incidence, and consequences of faults | Estimate how a recruiter is doing when it comes to hiring sloppy programmers |

Building dependable systems closely relates to controlling faults. Important for DS is **Fault tolerance**, meaning that a system can provide its services even in the presence of faults.
- e.g. applying error correcting codes for transmitting packets.

**Faults Types** 
*Transient Faults* - occur once then disappear. If the operation is repeated the fault goes away.
*Intermittent Fault* - occurs then vanishes on its own accord, then re-appears and so on.
- e.g. a loose connector. are difficult to diagnose.
*Permanent Fault* - continues to exist until the faulty component is replaced. 
- e.g. bugs, burnt-out chips, disk-head crashes.

#### 5. Security
A distributed system that is not secure, is not dependable. 
A special attention is needed to ensure *confidentiality* and *integrity*, both of which are directly coupled to authorized disclosure and access of information and resources.

- **Authorization** is done by checking whether an identified entity has proper *access rights*.
	- this means that the system should know it is indeed dealing with the proper entity. For this reason, authentication is essential.
- **Authentication**: verifying the *correctness* of a claimed identity. Equally important is the notion of *trust*. 
	- since if a not trust worthy person is authenticated, proper authorization may limit any damage that person can cause.
- **Trust**: one entity can be assured that another will perform particular actions according to a specific expectation

**Key elements needed to understand security** 
Security in distributed systems is all about encrypting and decrypting data using security keys. (Cryptography).
The easiest way of considering a security key K is to see it as a function operating on some data data. `K(data)` -> K operates on data.

There are two ways of encrypting and decrypting data. 
In a ***symmetric cryptosystem***, encryption and decryption takes place with a single key. $E_K (data)$ 
- If $\text{data} = D_K (E_K (\text{data}))~ then ~D_K = E_K$ 
The key will need to be kept secret by all parties that are authorized to encrypt or decrypt data.

In an ***asymmetric cryptosystem***, the keys used for encryption and decryption are different. 
In particular, there is a *public key* PK that can be used by anyone, and a *secret key* SK that is, as its name suggests, to be kept secret. Asymmetric cryptosystems are also called *public-key systems*.


**2 Ways to Use Asymmetric Cryptosystems** 
Encryption and decryption in public-key systems can be used in two, fundamentally different ways:
1. **Confidentiality (Encryption):** If Alice wants to encrypt data that only Bob can read, she uses Bob's public key `PKB`, producing `PKB(data)`. Only Bob, who holds the matching secret key `SKB`, can decrypt it via `SKB(PKB(data))` → `data`.  > PKB = public key bob

2. **Digital Signatures (Authentication):** To prove data came from Alice, she encrypts it with her secret key `SKA`, producing `SKA(data)`. Anyone with her public key `PKA` can decrypt it; successful decryption proves Alice (the sole holder of `SKA`) endorsed the data.
> Assumption: Alice is the only one holding `SKA`.

In Practice, Digital signature is generally more efficient to implement by a **Hash Function (H)**. 
When operating on some data `H(data)` always returns a fixed length string, regardless of length of the data. Any change to the data data* will result in a different hash value `H(data*)`.

And given a hash value H, it is computationally impossible in practice to discover the original data.

So,  Alice computes `sig = SKA(H(data))` as her signature, and tells Bob about data, H and sig. Bob, in turn, can then verify that signature by computing `PKA(sig)` and verifying that it matches the value `H(data)`.

$[data, H(data) ? = PK_{alice}(sgn)] = [data, H, sgn = SK_{alice}(H(data))]$ 
          Check by bob                                      Sent by Alice

Cryptography is also used to realize secure distributed data structures like the *Blockchain*. w/c is a chain of blocks (B), in w/c the basic idea is: hash the data in $B_i$ and place it in $B_{i+1}$ and so on, so that if an attacker tries to modify $B_i$ it would also have to change the hash value in $B_{i+1}$, but $B_{i+2}$  also contains $B_{i+1}$ and so on so it would be practically impossible to change all successive blocks.

Cryptography is also used for another important mechanism in distributed systems: delegating access rights. and many more applications.

### 6. Scalability
Scalability of a system can be measured along at least three different dimensions.
- **Size scalability**: we can easily add more users and resources to the system without any noticeable loss of performance.
- **Geographical scalability**: users and resources may lie far apart but the fact that communication delays may be significant is hardly noticeable.
- **Administrative scalability**: a system can still be easily managed even if it spans many independent administrative organizations.

#### Size scalability
If more users or resources need to be supported, we are often confronted with the limitations of centralized services. e.g. many services are centralized in the sense that they are implemented by a single *server* running on a specific machine in a distributed system.

In this case, there are essentially three root causes for becoming a bottleneck:
- The computational capacity, limited by the CPUs, even a modern high-end system will eventually run into problems if the number of requests increases beyond a certain point.
- The storage capacity, including the I/O transfer rate, e.g. a poorly designed centralized search engine. much of the processing time will be determined by the relatively slow disk accesses and transfer of data between disk and main memory.
	- adding more or higher-speed disks will prove not to be a sustainable solution.
- The network between the user and the centralized service, e.g. a video-on-demand service that needs to stream high-quality video to multiple users., it may hit the limits of the network capacity of its own outgoing transmission lines.

**Analyzing size scalability** 
(More detailed Explanation) [[Size Scalability Analysis]] 
At a conceptual level, a centralized service can be modeled as the simple queuing.
Often, we may assume that the queue has an infinite capacity, meaning that there is no restriction on the number of requests that can be accepted for further processing.
Strictly speaking, this means that the arrival rate of requests is not influenced by what is currently in the queue or being processed.

To understand how the system behaves over time, we determine the probability $p_k$ that exactly $k$ requests are in the system (either waiting in line or actively being serviced) at steady state.
The fraction of time $p_k$ that there are k requests in the system is equal to:
$$p_k=(1-\frac{\lambda}{μ})(\frac{\lambda}{μ})^k$$ 
Where:
- $\lambda$ - is the arrival rate of requests in r/sec
- μ - is the processing capacity of the service in r/sec

If we define the *utilization* U of a service as the fraction of time that it is busy, then clearly, $\frac λ μ$ 
$$U = \sum_{k> 0} p_k = 1 − p_0 = \frac λ μ ~~~~~~~~~~⇒ p_k = (1 − U)U^k$$ 
- If $\lambda < \mu$ ($U < 1$), the system reaches a stable equilibrium. The server can, on average, clear requests faster than they arrive.
- If $\lambda \ge \mu$ ($U \ge 1$), the queue grows toward infinity over time; steady state does not exist.

We can then compute the *average number $\bar N$ of requests in the system* as
$$\bar N = \sum_{k\geq0}k\times p_k = \sum_{k\geq0}k\times(1-U)U^k = (1-U)\sum_{k\geq0}k\times U^k = \frac{(1-U)U}{(1-U)^2}=\frac{U}{1-U}$$

What we are truly interested in, is the response time R: how long does it take before the service to process a request, including the time spent in the queue.

To that end, we need the *average throughput* X. Throughput represents completed requests per second. The server works at capacity $\mu$ only when busy (fraction $U$), and at rate $0$ when idle (fraction $1 - U$):
$$X = U · μ  + (1 − U) · 0 = \frac λ μ · μ = λ$$
- $U · μ$ - server at work
- $(1-U)·0$ - server at idle

*Little's Law* is a fundamental operational theorem stating that the average number of items in a stationary queueing system equals the arrival/throughput rate multiplied by the average time an item spends in the system:
Using Little’s formula, we can then derive the response time as:
$$\bar{N} = X \cdot R = \lambda \cdot R \implies R = \frac{\bar{N}}{\lambda}$$
Substituting $\bar{N} = \frac{U}{1 - U}$ and $U = \frac{\lambda}{\mu}$:
$$R = \frac{\frac{\lambda / \mu}{1 - U}}{\lambda} = \frac{1}{\mu(1 - U)}$$
Because the raw service time for an isolated request is $S = \frac{1}{\mu}$, we substitute $S$ directly into the equation:
$$R = \frac{S}{1 - U} \implies \frac{R}{S} = \frac{1}{1 - U}$$

**Note**
>if U is small, the response- to-service time ratio(delay penalty) is close to 1, meaning that a request is virtually instantly processed, and at the maximum speed possible.

>However, as soon as the utilization comes closer to 1, we see that the response-to-server time ratio quickly increases to very high values, effectively meaning that the system is coming close to a grinding halt. 
>This is where we see scalability problems emerge.

From this simple model, we can see that the only solution is bringing down the service time S.

```
R/S (Latency Multiplier)
     |
 20x |                                       *
     |                                      *
 10x |                                    *
     |                                 *
  5x |                             *
  2x |                   *
  1x | * * * * * * * * *
     +-----------------------------------------
       0%       50%            80%   90%   99%  100%
                        Utilization (U)
```

#### Geographical scalability
One of the main reasons why it is still difficult to scale existing distributed systems that were designed for LANs is that many of them are based on *synchronous communication*.
- w/c means, a party requesting a service (a client) blocks until a reply is sent back from server.
-  This approach generally works fine in LANs, where communication between two machines is often at worst a few hundred microseconds. 
- However, in a wide-area system, the inter-process communication may be hundreds of milliseconds.

Another problem that hinders geographical scalability is that communication in WANs is inherently much less *reliable* than in LANs.
- we generally also need to deal with limited bandwidth.
- the effect: solutions developed for LANs cannot always be easily ported to a wide-area system.

Yet another issue in WA systems is that we generally have only very limited facilities for multipoint comms. In WA systems, we need to develop separate services such as naming and directory services and also make themselves scalable.

#### Administrative scalability
- how to scale a distributed system across multiple, independent administrative domains.
- A major problem that needs to be solved is that of conflicting policies regarding resource usage (and payment), management, and security.

E.g. Scientists have been seeking solutions to share expensive equipment through computational grids, which construct a global decentralized system as a federation of local distributed systems.
- **Trust within a Domain**: Users trust their system administrators because components are tested and certified, and measures are taken to prevent tampering within a single domain.
- **Lack of Trust across Domains**: This trust does not naturally extend across domain boundaries.
- **Security Measures for Expanding Distributed Systems**:
	- Protect the distributed system against malicious attacks from the new domain (e.g., limited access, restricted resources).
	- Protect the new domain against potential threats from the distributed system (e.g., foreign code downloading, unauthorized access).

- As a counterexample of distributed systems spanning multiple administrative domains that apparently do not suffer from administrative scalability problems, consider modern file-sharing peer-to-peer networks. 
- A more modern application (that has yet to prove itself in terms of scalability) are blockchains. 
- What these decentralized systems have in common is that end users, and not administrative entities, collaborate to keep the system up and running. 

#### Scaling techniques
In most cases, scalability problems in distributed systems appear as performance problems caused by limited capacity of servers and network.
Simply improving their capacity (e.g., by increasing memory, upgrading CPUs, or replacing network modules) is often a solution, referred to as **scaling up**.

When it comes to scaling out, that is, expanding the distributed system by essentially deploying more machines, there are basically only three techniques we can apply: *hiding communication latencies*, *distribution of work*, and *replication*.

**Hiding communication latencies**
- applicable in the case of geographical scalability.
- The idea: try to avoid waiting for responses to remote-server requests as much as possible.
- e.g. when a s service has been requested at a remote machine, an alternative to waiting for a reply is to do another useful work at the requester's side.
- Essentially, constructing the requesting application to use only Asynchronous communication.

- However some applications just can't make use of async communication, e.g. interactive applications. 
- In such cases a better solution is to reduce the overall communication. e.g. moving some part of the computation that would be done on the server to the client instead.
	- a good example is checking for syntactic errors on a Form.

**Partitioning and Distribution** 
Involves taking a component or other resource, splitting it into smaller parts, and subsequently spreading those parts across the system.
- A good example of partitioning and distribution is the DNS. The DNS name space is hierarchically organized into a tree of domains, which are divided into nonoverlapping zones.
	- The names in each zone are handled by a single name server. (Z1, Z2, Z3)
	- To resolve a hostname into a network address (such as flits.cs.vu.nl), a query moves down the hierarchy: higher-level zone servers successively direct the request to lower-level servers until the authoritative server returns the host's actual IP address.

- As another example, consider the World Wide Web. The Web is physically partitioned and distributed across a few hundreds of millions of servers, each handling often a number of Websites, or parts of Websites. 
- It is only because of this distribution of documents that the Web has been capable of scaling to its current size.

**Replication** 
Considering that scalability problems often appear in the form of performance degradation, it is generally a good idea to actually replicate components or resources, etc., across a distributed system.
Replication not only increases availability, but also helps to balance the load between com- ponents, leading to better performance.
Moreover, in geographically widely dispersed systems, having a copy nearby can hide much of the communication latency problems mentioned before.

**Caching** 
A special form of replication, although the distinction between the two is often hard to make or even artificial.
In contrast to replication, caching is a decision made by the client of a resource and not by the owner of a resource.

*Drawbacks to caching and replication* 
- Caching and replication leads to consistency problems.
- To what extent inconsistencies can be tolerated depends on the usage of a resource.
	- e.g. a regular website vs a e-shop or a bidding website.
- The problem with strong consistency is that an update must be immediately propagated to all other copies.
- If two operations happen concurrently, a race condition occurs.
- The "Global Ordering Problem" - all replicas must execute conflicting operations in the exact same sequence, but we have no shared physical clock, there is overhead & bottlenecks on comms.

If we can tolerate inconsistencies, we may reduce the need for global synchronization, but tolerating inconsistencies is application dependent.


Comparing scaling techniques:
1. **Size (Easiest):** Solved with money, just upgrade or add more hardware.
2. **Geographical (Harder):** Bound by physics, network latency forces data replication, which creates complex consistency conflicts.
3. **Administrative (Hardest):** Bound by humans, code and hardware cannot resolve politics, differing laws, or lack of trust across organizations.

**1.3 Classification of distributed systems** // It looks like we skipped this part and directly went to chapter 3 of the book.


# CH 2: Processes
## Threads
Although processes form a building block in distributed systems, practice indicates that the granularity of processes as provided by the operating systems on which distributed systems are built is not sufficient.
Threads offer a finer granularity which makes building distributed applications easier and also gives us better performance.

**Introduction to Processes** 
To execute a program, an OS creates a number of *Virtual Processors* each one for running a different program, and to keep track of these virtual processors the OS keeps a "**Process Table**", containing registry values, memory maps, open files etc... jointly called a "**Process Context**".
- different from the hardware's "**Processor Context**", w/c handles hardware interrupts.

An OS has to ensure that independent processes cannot maliciously affect the correctness of each other's behavior. (It makes the fact that multiple processes may be sharing the CPU and other resources transparent.)
- Concurrency transparency comes at a price, creating separate address spaces for each process, switching between processes (context switch). 
- Apart from saving the data as currently stored in various registers (including the program counter and stack pointer), the operating system will also have to modify registers of the Memory Management Unit (MMU) and invalidate address translation caches, such as in the Translation Lookaside Buffer (TLB).
- And if there are more processes than it can hold in memory at a time, it might swap to disk.

**Introduction to Threads** 
Like a process, a thread executes its own piece of code, independently of other threads. However, threads don't attempt to achieve a high degree of concurrency transparency, w/c results in less performance overhead of context switching.
- a *thread context* often contains only *processor context*(HW context) and some other info for thread management like, if it is blocked on a mutex so it won't be selected for execution.
- Information that is not strictly necessary to manage multiple threads is generally ignored. For this reason, protecting data against inappropriate access by threads within a single process is left entirely to application developers. 
- Processor context is contained in a thread context, and that, in turn, a thread context is contained in a process context.
- Because threads are not automatically protected against each other the way processes are, development of multithreaded applications requires additional intellectual effort.

**Thread usage in non-distributed systems** 
In a single-threaded process, a blocking call blocks the whole program.
- Multi-threading solves this because we can have multiple threads doing different parts of the process, like one for user interaction and another for updating the UI, etc..
- Multi-threading also allows parallelism, each thread is assigned to a different CPU or core, while shared data are stored in shared main memory.
- When properly designed, such parallelism can be transparent: the process will run equally well on a uniprocessor system, albeit slower.

- Multithreading is also useful in the context of large applications. Such applications are often developed as a collection of cooperating programs, each to be executed by a separate process.
	- In Unix, this is implemented through the IPC, but the drawback of all IPC mechanisms is that communication often requires relatively extensive context switching.
	- the two processes have separate address spaces, so the kernel must mediate. 
		- **S1 (user → kernel):** Process A traps into the kernel (system call); MMU switches to kernel-mode memory permissions and TLB is flushed.
		- **S2 (A → B):** OS saves A's full context, schedules B, loads B's context (registers, page tables, etc.).
		- **S3 (kernel → user):** Process B returns to user mode; MMU switches back to user-mode permissions and TLB is flushed again.

- Instead of using processes, an application can also be constructed such that different parts are executed by separate threads.
	- Communication between those parts is entirely dealt with by using shared data. 
	- Thread context switching can sometimes be done entirely in user space.
- Finally, there is also a pure software engineering reason to use threads: many applications are simply easier to structure as a collection of cooperating threads.

**The cost of a context switch:** 
- Measuring context-switch overhead is hard; clock interrupts are a common proxy (triggered every 0.5–20 ms).
- **Direct overhead** = actual context-switch time (~0.5–1 µs) + handler work (~0.5–7 µs). Relatively small.
- **Indirect overhead** = cache perturbation from the interrupt; can be ~80% of total overhead.
- The interrupt's handler evicts useful cache blocks (LRU), leaving "holes"; reloading them causes cascading evictions, degrading application performance long after the switch itself.

#### Thread Implementation
- Threads are often provided in the form of a thread package, providing operations to create and destroy threads, as well as operations on synchronization variables like mutexes and condition variables.
Two approaches to implement a thread package:
1. a thread library that is executed entirely in user space.
2. have the kernel be aware of threads and schedule them.

- a user-level thread library has many advantages.,
	- it is cheap to create and destroy threads.
	- switching thread context can often be done in just a few instructions.
		- basically, only the CPU registers need to be stored and reloaded. no need to flush TLB, do CPU accounting and so on.

- A major drawback of user-level threads comes from deploying the many- to-one threading model, multiple threads are mapped to a single schedulable entity. (a blocking system call will block the entire process)
- This problem can mostly be circumvented by using kernel-level threads, which use "one-to-one" threading model in which, every thread is a schedulable entity.
	- the price is that every threaded operation (creation, deletion, synchronization, etc.) have to be carried out by the kernel through a system call.
	- this would make thread context switching as expensive as switching process contexts.

- However, because the performance of context switching is generally dictated by ineffective use of memory caches, and not by the distinction between the many-to-one or one-to-one threading model, many operating systems now offer the latter model, if only for its simplicity.

As a final note, threads are one way to organize concurrent execution, but apps often use concurrent processes instead (e.g., Apache Web server spawns multiple single-threaded processes that communicate via IPC). Processes have a key advantage: **hardware-enforced data-space isolation**, out-of-bounds access triggers a hardware exception handled by the OS. Threads share memory, so the developer must manually manage concurrent access, with no hardware protection.

#### Threads in distributed systems
An important property of threads is that they can provide a convenient means of allowing blocking system calls without blocking the entire process. This property makes threads particularly attractive to use in distributed systems, as it makes it much easier to express communication in the form of maintaining multiple logical connections at the same time.

**Multithreaded Clients** 
To hide WAN latency, distributed systems initiate communication and proceed with other work. Multithreaded Web browsers illustrate this: after fetching the HTML, separate threads fetch images/assets over blocking connections in parallel, displaying content progressively so users aren't stuck waiting for the whole page.

**Multithreaded servers** 
Although there are important benefits to multithreaded clients, the main use of multithreading in distributed systems is found at the server side. 
- multithreading simplifies server code considerably, 
- and makes it much easier to develop servers that exploit parallelism to attain high performance, even on uniprocessor systems.

A server can be: e.g.
1. A multithreaded file server
2. single-threaded file server OR
3. to run the server as a big single-threaded finite-state machine.
	- instead of blocking on disk access request, it schedules an asynchronous (non-blocking) disk operation for which it will later be interrupted by the OS.
	- this doesn't follow the "sequential process" the 2 others do.

Threads make it possible to retain the idea of sequential processes that make blocking system calls and still achieve parallelism.
- Blocking system calls make programming easier as they appear as just normal procedure call.

| Model                   | Characteristics                       |
| ----------------------- | ------------------------------------- |
| Multithreading          | Parallelism, blocking system calls    |
| Single-threaded process | No parallelism, blocking system calls |
| Finite-state machine    | Parallelism, nonblocking system calls |
-  We can also use processes instead of threads to organize a server, which has the benefit of protection against accidental access to shared data by the OS. However, if there is a lot of IPC, we may see a performance degradation compared to threads.

## Virtualization
Threads and processes can be seen as a way to do more things at the same time. Even in single core computers they give us the illusion of of simultaneity/ parallelism.

Virtualization is basically doing the pretending for CPUs that threads do but for other resources as well.

**Virtualization in DS** 
One of the most important reasons for introducing virtualization, back in the 1970s, was to allow legacy software to run on expensive mainframe hardware. The software included the operating system it was developed for.
- this stopped becoming an issue as hardware became more powerful and the number of OS flavors decreased.
- But in late 1990s, 1st the HW and low level systems software changes reasonably fast but the higher level apps (middleware and apps) were more stable, it brought a situation where legacy software can not be maintained in the same pace as the platform it relies on.
	- Virtualization can help here by porting the legacy interfaces to the new platforms.

- Additionally, networking changed how system admins maintain large and heterogenous servers, each running different apps. At the same time the various resources should be easily accessible to these apps. 
- Virtualization can help by letting each application run on its own virtual machine, possibly including the related libraries and operating system, which, in turn, run on a common platform.

#### Levels of Virtualization (where the boundary sits)
These are the **interfaces** at which virtualization can happen, from lowest to highest. They describe *what* is being virtualized, not how.

1. **ISA Level**: interface between hardware and software, the instruction **set** architecture (machine instructions). 
	- Two sub**sets**:
		1. *Privileged instructions* - executable only by the OS (kernel mode).
		2. *Non-privileged (General) instructions* - executable by any program (user mode).

2. **Hardware Level**: the physical hardware itself, below the ISA.
	- Provides VMs with virtual CPUs, memory, and I/O.
	- Early example: IBM VM/370 (1960s). Modern example: Xen hypervisor for x86 servers.

3. **Operating System Level**: system calls offered by an OS.
	- Creates isolated containers on a single server, that behave like independent servers.
	- e.g. Docker, Solaris zones.

4. **Library Support Level**: library calls forming an API, hiding system calls.
	- Instead of virtualizing hardware (level 1) or the whole OS (level 2), you virtualize only the application runtime/API. e.g. Examples: WINE (Windows apps on UNIX), `vCUDA` (GPU acceleration inside VMs).

5. **Application Level**: the end-user applications themselves, running on top of the library/API layer.
	- Examples:  Java Virtual Machine (JVM), Microsoft .NET CLR.

> [!note] 
> The book only lists the 3, ISA, OS and Library levels, the 5 here is from the teacher's slides.
> Though one can assume the remaining two (HW and App) are included in ISA and Library respectively.

#### Types of Virtualization (how it is implemented)
These are the **architectural approaches**, independent of the level above. They describe *how* virtualization is built.

**Two approaches to virtualization:** ![[Pasted image 20261109120144.png]]
1. **Process VM**: a runtime provides an abstract instruction set for a *single process* (e.g., JVM interpreting bytecode, or Wine emulating Windows on Unix). Must also mimic system calls.
2. **Native VMM**: a layer directly on top of hardware offering the full ISA, allowing multiple guest OSes to run concurrently and independently on one platform. Handles device drivers itself. e.g. KVM(Kernel-based Virtual Machine), VMware (ESXi).
3. **Hosted VMM**: a variant of the native approach that runs *on top of a host OS* instead of bare metal, reusing the host OS's facilities (drivers, etc.) while getting special privileges. Popular in data centers/clouds. e.g. VirtualBox.

> [!note]
>**Why VMs matter** (Rosenblum & Garfinkel): They improve reliability/security by isolating entire applications/environments (a failure or attack no longer takes down the whole machine) and improve portability by decoupling software from hardware, making full environments movable between machines.

####  VMM (Virtual Machine Monitor)
A Hardware-level virtualization adds a layer between real hardware and OS. (Native VMM )
It manages hardware resources of the system and interprets program access to the hardware.
- It enables multiple OS instances to run on the same hardware.

**A VMM must provide:** 
1. An *Identical environment* to the original source.
2. A minor performance decrease.
3. Complete control of all system resources.

**Performance matters** 
- Pure emulators are too slow for real use, but 
- Efficient VMMs execute the majority of instructions directly on hardware.
- Only exceptional cases require VMM intervention.

**Responsibilities of a VMM** 
1. Allocate HW resources to programs/VMs efficiently.
2. Prevent unauthorized access to resources not assigned to a VM.
3. Reclaim and redistribute resources when VMs terminate or underutilize them.
4. Monitor resource usage to ensure fair sharing among VMs.
5. Support performance isolation and security between VMs.

#### OS-Level Virtualization
WHY OS- level?
- HW- level VMs are slow to initialize and store.
	- Slow performance
	- Low density
	- Need for para-virtualization (a technique where the guest OS is modified to know it's running in a VM, so it could makes direct `hypercalls` to the original hypervisor, instead of being emulated)

- OS-level virtualization provides faster, more resource-efficient solution.
- Each VE has: Processes, file system, user accounts Network interfaces, IPs, routing tables, firewall rules
- All VEs share the same OS kernel -> called single-OS image virtualization.

**Advantages of OS-Level** 
- Minimal startup/shutdown costs
- High scalability
- Hosts and VMs can be synchronized when needed.
- Faster initialization of VMs for cloud environments.

**Limitations** 
- All VMs must belong to the same OS family(d/t distros of the same OS), but not d/t OSs. 
- Resource duplication can incur significant overhead if not managed carefully.
- Often considered a secondary choice compared to HW-assisted virtualization.

#### Containers
Virtual machines offer a means to run applications relying on a specific operating environment, including its instruction set and operating system, to run independently across different platforms. 
However, often we see that applications are relatively stable when it comes to the used instruction set and operating system, yet do rely on specific libraries and other support software.
- In these cases, what we really want is to allow different applications to run side-by-side, each using its own environment of support software. This is what **containers** do.

A **container** can be thought of a collection of binaries (also called images) that jointly constitute the software environment for running applications.

Each container sees itself as an independent machine: Own IP address, Isolated filesystem, Isolated process tree.

A **container** virtualizes the software environment for an application, giving it its own view of directories, libraries, and dependencies (like a `chroot` subdirectory acting as root in Linux).
- chroot ("change root") is a Unix/Linux system call/command that changes the root directory (/) of a process to a different directory.
- A naive `chroot`-style copy isn't enough: processes across containers need **isolation**, copying full environments is **inefficient** (shared libs duplicated), and the host OS needs **resource control** over its own resources.
- Linux solves these with three mechanisms:
	1. **Namespaces** - give each container's processes their own view of identifiers (PID, network, mount points, etc.), isolated from other containers.
	2. **Union file system** - layers file systems so containers share read-only base layers but get their own writable top layer (efficient).
	3. **`cgroups`**(control groups) - enforce resource limits (CPU, memory, I/O) on process groups.

In the end, a container can be thought of an archive of files that are placed somewhere in a filesystem, together with a specific stack of common, shared, existing read-only subdirectories.

**Problems Containers Solve** 
Containers bundle an application with parts of its OS environment(dependencies, libraries, and runtime).
- *Configuration Management*: we test apps in the same environment they run in production.
- *Infrastructure Management*: we run multiple containers on a single machine.

#### Docker
A popular tool for building, managing and running containers.
**Docker Hub** - provides standardized images.
Docker supports massive deployment with minimal effort.
Real world examples: AWS ECS, Kubernetes, Azure Container Instances.

**Docker Registry Concepts** 
- *Registry*: Stores container images online (e.g., Docker Hub, `JFrog`, AWS, Azure). 
- *Repository*: Named location in a registry for a type of image. 
- *Tag*: Identifies a specific version of an image (e.g., `ubuntu:jammy`).

- Fully qualified image name: `registry/repository:tag` 

**Key commands** 
```
docker image ls -> list images
docker container ls -a  -> list all containers
docker run --rm IMAGE  -> auto-delete an image after run
docker system prune -> delete non-running containers.
docker container stop CONTAINERI D  -> Stop container
```

Container = image + writable filesystem layer.
Each container runs as an isolated VM.
Containers provide strong isolation for resources, ensuring that each application runs independently. With its own CPU, memory, disk, and network allocation.

#### virtual machines Vs. containers
**Performance** 
- Obvious ones criteria includes CPU and memory usage, likewise, various I/O measurements.

*Linux containers (LXC) against Linux virtual machines (KVM) by `Sharma`* 
- baseline shows containers favored against containers, but the difference is not big, except for I/O, here VMs perform significantly less than containers.
	- mainly because in traditional I/O the OS plays a crucial role, it has to execute many privileged instructions (w/c can only run in kernel mode. w/c VMs have to translate to the real HW).
- to what extent the performancee of one application influences that of another?
	- this aspect boils down to the question how well scheduling resources among competitors actually is.
	- in general containerization has more difficulty isolating independent applications and scheduling for CPU usage as well as for disk performance is handled better through VMs.

#### Applications of VMs in DS
The most important application of VMs in DS lies in Cloud Computing. three types of services
- **Infrastructure-as-a-Service (IaaS)** covering the basic infrastructure 
- **Platform-as-a-Service (PaaS)** covering system-level services 
- **Software-as-a-Service (SaaS)** containing actual applications

Virtualization plays a key role in IaaS. Instead of renting out a physical machine, a cloud provider will rent out a virtual machine (monitor) that usually shares the HW with others.

 **Example: Amazon Elastic Compute Cloud, or simply EC2's Underlying VM/cloud concepts (ignoring Amazon specifics):** 
- **AMI = boot disk image**: A pre-built, installable package (OS kernel + services) that you launch to create a running VM, equivalent to booting from a disk.
- **Instance = the running VM**: Created by launching an image; you configure its resources (CPU, memory, storage, network, platform).
- **Location transparency**: You don't know/control which physical machine runs your VM, only roughly which region.
- **Networking**: Each VM gets a private IP (internal comms) and a public IP (external access), mapped via NAT.
- **Transient vs. persistent storage**: Local disk attached to a VM is lost when it stops; persistent data requires attaching external/virtual block storage (mountable like a hard disk, survives restarts, re-attachable to other VMs).
- **IaaS value proposition**: Lets you build entire distributed systems of networked VMs with configurable resources, accessible over the internet, without owning/maintaining physical hardware.

## Clients
**Networked User Interfaces** 
Two ways client machines provide the means for users to interact with remote servers:
1. For each remote service, the client will have a separate counterpart that contact the service over the network.
	- e.g. a  calendar running on a smartphone needing to synchronize with a remote, possibly shared calendar.
2. To provide direct access to remote services by offering only a convenient user interface. (thin client)
	- effectively the client is a terminal with no need for storage, leading to an app-neutral solution

**Virtual desktop environment** 
As cloud computing further matured, it became opportune to actually turn the cloud into a virtual desktop environment for end users. The only thing needed was the client-side software to access that desktop environment. e.g. Google's chrome OS.

**Client-side software for distribution transparency** 
- **Client software** is more than just UI, it includes local processing, communication, and components for distribution transparency.
- **Access transparency** is handled by a **client stub**, generated from the server's interface definition. The stub exposes the same interface as the server but hides architecture differences and the actual communication: it turns local calls into messages to the server and converts replies back into return values (RPC-style).
- **Location/migration/relocation transparency** relies on a good **naming system** and often client-side cooperation (e.g., client notified of server relocation, middleware transparently rebinds).
- **Replication transparency** can be client-side: requests are forwarded to all replicas, and the client software collects responses and returns a single result to the application.
- Servers are often *less* transparent than clients, for performance and correctness reasons.
- **Failure transparency** is typically handled by **client middleware**: it can retry connections to a server, fail over to another server after repeated failures, or return **cached data** from a previous session (e.g., Web browsers showing cached pages when a server is unreachable).
- **Concurrency transparency** is handled mainly by **intermediate servers** (e.g., transaction monitors) and requires little client-side support.

## Servers
#### General design issues
A server is a process implementing a specific service on behalf of a collection of clients. 
n essence, each server is organized in the same way: it waits for an incoming request from a client and subsequently ensures that the request is taken care of, after which it waits for the next incoming request.

**Concurrent versus iterative servers** 
- *Iterative server* - the server itself handles the request and if necessary, returns a response to the requesting client.
- *Concurrent server* - passes the requests to a separate thread or another process, after which it waits for the next incoming request. e.g. a multithreaded server
	- an alternative implementation for CS is to fork a new process for each new incoming request. (used in many UNIX systems), 
	- The thread or process that handles the request is responsible for returning a response to the requesting client.

**Contacting a server: end points** (summary)
- Clients contact servers through **end points (ports)**; each server listens on a specific port.
- **Well-known services** use globally assigned ports (e.g., FTP = 21, HTTP = 80, assigned by IANA), the client only needs to find the machine's network address (via name services).
- **Dynamic services** get ports assigned by the OS at runtime; clients must first **look up** the port via a **daemon** on the server's machine that tracks each service's current port (the daemon itself listens on a well-known port).
- To avoid resource waste from many idle server processes, a **superserver** (e.g., Unix `inetd`) can listen on multiple ports and **fork a process per request**, which exits when done.

**Interrupting a server** 
- Problem: a client may need to cancel an in-progress server operation (e.g., abort a large file upload).
- Naive approach: client exits abruptly, breaking the connection; server eventually tears it down assuming a crash.
- Better approach: send **out-of-band data** processed before other client data:
	- Option A: separate **control endpoint** for urgent data, with normal data on a lower-priority endpoint.
	- Option B: send urgent data over the **same connection** (e.g., TCP urgent data), interrupting the server (e.g., via a signal in Unix) to inspect and handle it.

**Stateless vs. stateful servers** 
- **Stateless**: keeps no client state (or only soft state with expiry); easy recovery after crash; Web server example. State can be simulated (open/read/close per request) or offloaded to client (cookies). Soft state = server maintains state only for a limited time, then discards it (client must poll after expiry).
- **Stateful**: keeps persistent client state (e.g., file lock tables); better performance but complex crash recovery (must restore full state). Session state is temporary per user; permanent state lives in databases.  
