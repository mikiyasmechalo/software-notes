This model represents an **$M/M/1$ queuing system**, the foundational mathematical framework used in computer systems engineering to analyze capacity, bottlenecks, and size scalability.

---

## 1. System Assumptions and Architecture

A centralized service is abstracted into two components: a **waiting line (queue)** of infinite capacity and a **single processing unit (server)**.

```
Incoming Requests (λ) ---> [ Queue: k requests waiting ] ---> [ Server: μ ] ---> Completed Requests

```

The model relies on several core assumptions:

* **Poisson Arrival Process ($\lambda$):** Requests arrive randomly and independently at an average rate of $\lambda$ requests per second. The inter-arrival times follow an exponential distribution.
* **Exponential Service Distribution ($\mu$):** The server processes requests at a maximum average rate of $\mu$ requests per second. Individual service duration $S = 1/\mu$ varies exponentially.
* **Open System & Infinite Queue:** The arrival rate $\lambda$ is completely decoupled from the queue's state. Users continue to send requests regardless of whether the queue is empty or has 10,000 items waiting (no backpressure, dropped packets, or client timeouts).
* **Work-Conserving Discipline:** The server never idles if there is at least one request waiting, processing requests First-In, First-Out (FIFO).

---

## 2. Derivation of State Probabilities and Utilization ($U$)

To understand how the system behaves over time, we determine the probability $p_k$ that exactly $k$ requests are in the system (either waiting in line or actively being serviced) at steady state.

### The Flow Balance Equations

In equilibrium, the rate of transitions into state $k$ must equal the rate of transitions out of state $k$ (a continuous-time Markov birth-death process):

$$\lambda p_k = \mu p_{k+1} \implies p_{k+1} = \left(\frac{\lambda}{\mu}\right) p_k$$

By induction, any state probability $p_k$ can be expressed in terms of the idle probability $p_0$:

$$p_k = \left(\frac{\lambda}{\mu}\right)^k p_0$$

### Server Utilization ($U$)

Server utilization $U$ is defined as the fraction of time the server is busy:

$$U = \frac{\lambda}{\mu}$$

* If $\lambda < \mu$ ($U < 1$), the system reaches a **stable equilibrium**. The server can, on average, clear requests faster than they arrive.
* If $\lambda \ge \mu$ ($U \ge 1$), the queue grows toward infinity over time; steady state does not exist.

Since all probabilities must sum to 1:

$$\sum_{k=0}^{\infty} p_k = p_0 \sum_{k=0}^{\infty} U^k = 1$$

Using the sum of an infinite geometric series $\sum_{k=0}^{\infty} U^k = \frac{1}{1 - U}$ (valid for $U < 1$):

$$p_0 \left(\frac{1}{1 - U}\right) = 1 \implies p_0 = 1 - U$$

Substituting $p_0$ back into the formula yields the probability distribution:

$$p_k = (1 - U)U^k$$

Notice that $p_0 = 1 - U$ is the fraction of time the server is idle. Consequently, the fraction of time the server is busy is:

$$1 - p_0 = 1 - (1 - U) = U$$

---

## 3. Average Number of Requests in the System ($\bar{N}$)

$\bar{N}$ is the expected value of requests in the system across all possible states:

$$\bar{N} = \sum_{k=0}^{\infty} k \cdot p_k = (1 - U) \sum_{k=0}^{\infty} k U^k$$

To evaluate the series $\sum_{k=0}^{\infty} k U^k$, we take the derivative of the standard geometric series formula:

$$\sum_{k=0}^{\infty} U^k = \frac{1}{1 - U}$$

Differentiating both sides with respect to $U$:

$$\frac{d}{dU}\left(\sum_{k=0}^{\infty} U^k\right) = \sum_{k=1}^{\infty} k U^{k-1} = \frac{1}{(1 - U)^2}$$

Multiplying both sides by $U$:

$$\sum_{k=0}^{\infty} k U^k = \frac{U}{(1 - U)^2}$$

Now, substitute this back into the expectation equation:

$$\bar{N} = (1 - U) \cdot \frac{U}{(1 - U)^2} = \frac{U}{1 - U}$$

---

## 4. Throughput ($X$) and Little’s Law for Response Time ($R$)

### Average Throughput ($X$)

Throughput represents completed requests per second. The server works at capacity $\mu$ only when busy (fraction $U$), and at rate $0$ when idle (fraction $1 - U$):

$$X = U \cdot \mu + (1 - U) \cdot 0 = \left(\frac{\lambda}{\mu}\right) \cdot \mu = \lambda$$

In a stable open system with no packet drops, average throughput strictly equals the average arrival rate $\lambda$.

### Little's Law

Little's Law is a fundamental operational theorem stating that the average number of items in a stationary queueing system equals the arrival/throughput rate multiplied by the average time an item spends in the system:

$$\bar{N} = X \cdot R = \lambda \cdot R \implies R = \frac{\bar{N}}{\lambda}$$

Substituting $\bar{N} = \frac{U}{1 - U}$ and $U = \frac{\lambda}{\mu}$:

$$R = \frac{\frac{\lambda / \mu}{1 - U}}{\lambda} = \frac{1}{\mu(1 - U)}$$

Because the raw service time for an isolated request is $S = \frac{1}{\mu}$, we substitute $S$ directly into the equation:

$$R = \frac{S}{1 - U} \implies \frac{R}{S} = \frac{1}{1 - U}$$

---

## 5. The "Hockey Stick" Curve and the Root of Scalability Collapse

The ratio $\frac{R}{S} = \frac{1}{1 - U}$ measures **delay penalty**: how many times longer a request takes compared to its raw processing time.

Total response time decomposes into two parts: time waiting in the queue ($W_q$) and active processing time ($S$):

$$R = W_q + S \implies W_q = R - S = \frac{S}{1 - U} - S = S \left(\frac{U}{1 - U}\right)$$

| Utilization ($U$) | Wait-to-Service Ratio ($\frac{W_q}{S}$) | Total Penalty Factor ($\frac{R}{S}$) | What the User Experiences |
| --- | --- | --- | --- |
| **$0.10$ (10%)** | $0.11\times$ | **$1.11\times$** | Instantaneous response. Server is idle 90% of the time. |
| **$0.50$ (50%)** | $1.00\times$ | **$2.00\times$** | Half the time spent waiting, half being processed. |
| **$0.80$ (80%)** | $4.00\times$ | **$5.00\times$** | Noticeable latency; queue latency dominates processing time. |
| **$0.90$ (90%)** | $9.00\times$ | **$10.00\times$** | Rapid degradation begins; 90% of duration is idle queue wait. |
| **$0.95$ (95%)** | $19.00\times$ | **$20.00\times$** | Severe delays; small traffic spikes cause timeouts. |
| **$0.99$ (99%)** | $99.00\times$ | **$100.00\times$** | Virtual deadlock / system brownout. |

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

### Why Does Latency Explode When Capacity Still Exceeds Load?

A common intuition trap is assuming that if $\lambda = 95$ req/s and $\mu = 100$ req/s, the server has 5% headroom and should perform smoothly.

In reality, arrivals and processing durations are **stochastic (bursty)**:

1. **Bursts form queues:** Even if average arrival is 95 req/s, five requests may arrive in the same 10-millisecond window.
2. **High utilization removes recovery windows:** When $U$ is low (e.g., 20%), the server has frequent idle periods between bursts to drain any accumulated queue back to zero.
3. **Queue accumulation:** At $U = 95\%$, idle periods are rare. A temporary backlog caused by random arrival clustering cannot be cleared before the next cluster arrives, compounding wait times for all subsequent requests.

---

## 6. Architectural Implications: Why Reducing $S$ is the Centralized Solution

In a centralized system, the server's processing rate $\mu$ is bounded by single-machine hardware limits. As incoming traffic $\lambda$ naturally grows with business scale, $U = \lambda \cdot S$ creeps toward $1.0$.

To prevent the system from hitting the asymptotic latency wall, the system designer has three theoretical variables:

1. **Limit Arrival Rate ($\lambda$):** Rejecting traffic (rate limiting, load shedding). This stops the queue from blowing up, but fails business scalability because it turns away users.
2. **Scale Horizontally (Break Centralization):** Moving from a single $M/M/1$ queue to multiple parallel servers ($M/M/c$ or load-balanced clusters). This breaks the single-queue bottleneck.
3. **Reduce Service Time ($S$):** The primary solution **within a centralized architecture**.

### How Lowering $S$ Rescues the System

Because $U = \lambda \cdot S$, reducing $S$ directly reduces $U$, yielding a **double benefit**:

* **Direct speedup:** Lower $S$ decreases the base processing time.
* **Asymptotic drop:** Lower $U$ moves the system leftward away from the vertical knee of the $\frac{1}{1-U}$ curve.

For example, if $\lambda = 90$ req/s and $S = 10\text{ ms}$ ($0.01\text{ s}$):

* $U = 90 \times 0.01 = 0.90$ (90% utilization).
* $R = \frac{0.01}{1 - 0.90} = \frac{0.01}{0.10} = \mathbf{100\text{ ms}}$.

If engineering optimizations cut $S$ by half to $5\text{ ms}$ ($0.005\text{ s}$):

* $U = 90 \times 0.005 = 0.45$ (45% utilization).
* $R = \frac{0.005}{1 - 0.45} = \frac{0.005}{0.55} \approx \mathbf{9.1\text{ ms}}$.

A **$2\times$ reduction in service time** produces an **$11\times$ reduction in total response time**, illustrating how centralized size scalability depends almost entirely on keeping $S$ small enough to maintain operating utilization safely below the hockey-stick inflection zone.

![[Pasted image 20261029210805.png]]