---
title: Operating Systems
---
# CH 1: Introduction

**What is an Operating System?**
A program that acts as an intermediary between a user of a computer and the computer hardware.
- It is an extended machine/ hides details and provides only a virtual machine
- it is a resource manager/ distributes space and time between programs

**Computer System Components**
1. **Hardware** – provides basic computing resources (CPU, memory, I/O devices).
2. **Operating system** – controls and coordinates the use of the hardware among the various application programs for the various users.
3. **Applications programs** – define the ways in which the resources are used to solve the computing problems of the users (database systems, video games, business programs).
4. **Users** (people, machines, other computers).

**Operating System Objectives**
- **Convenience** – Top Down View – Virtual Machine : hiding the hardware, providing easy UI
- **Efficiency** – Bottom Up View – Resource Manager : controlled allocation of resources
- **Ability to Evolve**: effective development, testing, and introduction of new system W out interference to the existing services.
- **Protection**: allow only authorized access to data, computation, services, etc.


#### History of Operating Systems: Phases

1. Phase 1: Hardware is expensive, humans are cheap
	- Single task and single-user systems
	- Batching systems
2. Phase 2: Hardware is cheap, humans are expensive 
	- Time sharing: Users use cheap terminals and share servers
3. Phase 3: Hardware is very cheap, humans are very expensive 
	- Personal computing: One system per user 
	- Distributed computing: a collection of independent computers
4. Phase 4: Ubiquitous computing/Cloud computing 
	- Software as a service (SaaS), Platform as service(PaaS), infrastructure(IaaS)

#### Operating System Services
A process is a program in execution. it is also an active entity while a program is passive.
1. Process Management:
	- Process creation and deletion, suspension and resumption
	- Provision of mechanisms for: process synchronization, process communication
2. Memory Management:
	- keeping track of memory being used.
	- Decide which processes to load when memory space becomes available.
	- Allocate and deallocate memory space as needed
3. File Management:
	- File & directory creation and deletion
	- Mapping files onto secondary storage
	- File backup on stable (nonvolatile) storage media.
4. Secondary-Storage Management
	- Free space management
	- Storage allocation
	- Disk scheduling
5. I/O Management:
	- OS provides some means to perform I/O.
6. Protection System
	- controlling access of programs, processes, or users to use both system and user resources.
	- distinguish between authorized and unauthorized usage.
	- specify the controls to be imposed.
	- provide a means of enforcement.

**A View of Operating System Services**
![[Pasted image 20250226211820.png]]

---
#### System Calls

Provides an interface to the services made available by an operating system.
e.g. to read and copy from one file to another:
```
Acquire input file name
	Write prompt to screen
	Accept input
Acquire output file name
	Write prompt to screen
	Accept input
Open the input file 
	if it doesn't exist, abort
Create Output file
	if file exist, abort
Loop
	Read from input file
	Write to output file
Until read fails
Close the output file
Write completion message to screen
Terminate normally
```

**Mode of operation**:
- **User mode**: system is executing on behalf of a user application.
- **Kernel/ Privileged**: OS gains control of the computer. At boot we start in Kernel mode and the OS is loaded and it Starts user applications in user mode
This separations prevents harmful instructions to be limited to the user mode.

System calls mostly accessed by programs via a high-level API rather than direct system call use.
e.g. Windows API, POSIX API for UNIX, and Java API for the JVM.

The API sits between the user application and the System calls.

e.g. of system calls for win and Linux
- `CreateProcess()` for win and `fork()` for Linux
- `ExitProcess()` for win and `exit()` for Linux etc...


#### Operating System Structure

General-purpose OS is very large program, therefore need to be structured well.
Various ways:
- Simple structure (monolithic)
- Layered
- Microkernel
- Module
- Hybrid

**Simple / Monolithic /**
e.g. MS-DOS
- No well defined structures : no user and kernel modes, access to everything.
- Advantage: efficient performance
- Disadvantage: difficult to maintain, vulnerable to malicious programs.

**Layered Approach**
OS is divided to layers each built on the lower layers.
The lowest layer (Layer 0) is the hardware and the Highest layer (Layer n) is the UI.
With modularity, layers are selected such that each uses functions (operations) and services of only lower -level layers
- Advantage: Easy debugging
- Disadvantage: Difficult to define the layers because a layer can only access the lower layers.
	- less efficient: each layer adds overhead to the system call.

**Microkernel System Structure**
Structures the OS by removing all nonessential components from the kernel and implementing them in user space.
Mach is an example of microkernel, the Mac OS X kernel (Darwin) is partly based on Mach.
Communication takes place between user modules using message passing.
It moves the File system, drivers etc.. to the user mode. keeping mem. management, scheduling ...

- Benefits: Easier to extend a microkernel -> new services are added to user space not kernel.
	- Easier to port the OS to new architectures -> fewer changes.
	- More reliable and secure. {less code running in kernel mode}
- Detriments: Performance Overhead of user space to kernel communication.

**Modules**
loadable kernel modules: the kernel has a set of core components and links in additional services via modules.
- Each core component is separate
- Each talks to the others over known interfaces 
- Each is loadable as needed within the kernel
Overall, similar to layers but with more flexible- because any module can call any other module e.g. Linux, Solaris, etc.

**Hybrid Systems**
Combines multiple approaches to address performance, security, and usability issues.

- **Linux and Solaris** are monolithic (for performance reasons) in kernel address space, plus modular for dynamic loading of functionality.

**Windows** mostly monolithic, has behavior of microkernel, and also provide support for dynamically loadable kernel modules

**Apple Mac OS X** uses hybrid structure, a layered system:
- Top layer: Aqua- GUI; Cocoa programming environment
- Below is kernel consisting of::
	- Mach microkernel: for memory management, RPCs and IPC 
	- BSD Unix component: for networking and file systems
	- I/O kit: for development of device drivers
	- dynamically loadable modules (called kernel extensions)

![[Pasted image 20250226221147.png]]



# CH 2: Processes and Threads
#### The Process Concept

**Program** 
- Sequence of instructions defined to perform some task.
- a passive entity, a file and list of instructions/ executable.
- becomes a process when loaded to memory.

**Process** 
- a program in execution. it needs resources such as CPU, memory, files, I/O...
- an active entity/ an instance. with the `PC` specifying the next instruction & with other resources.
A Process includes:
- the code \ Text section
- Program Counter/ PC: address of the next instruction
- Stack: temp data | fun. parameters, return addresses & local variables |
- Data Section : contains global variables
- Heap: dynamically allocated memory at runtime


#### Types of Processes
Sequential Processes & Concurrent Processes

1. **Sequential Process**:
	At any point in time, at most one process is being executed.
2. **Concurrent Process**: 2 Types
	1. **True Concurrency** (Multiprocessing): processes are executed simultaneously in a multiprocessor environment. "Real Parallelism"
	2. **Apparent Concurrency** (Multiprogramming): processes are executed in parallel in a uniprocessor environment by switching from one process to another. 
	- "Pseudo parallelism" : fast context switching gives an illusion of parallelism

### Process Creation

Events that cause Process Creation
- **System Initialization**/ startup: both foreground (interact with users) and background processes (no particular user just some have some specific function).
- A running process doing a system call to create another process to help with its job.
- A user requesting to create a new process. e.g. open a document
- Initiation of a batch job (on large mainframes).

**Parent process** create **children processes**, which, in turn create other processes, forming a tree of processes. each identified by a **Process identifier (PID)** 

Resource Sharing Options:
- child obtains its resources from the OS
- child shares a subset of parent's resources
- parents partition resources among their children

Execution options 
- Parent and children execute concurrently
- Parent waits until children terminate

Two address-space possibilities for the new process:.
- The child process is a duplicate of the parent (it has the same program and data as the parent).
- The child process has a new program loaded into it.


#### Process State
During its lifetime, a process passes through a number of states.
The most important states are: Ready, Running, Blocked (waiting).

1. **New**: A process that has just been created but not yet been admitted to the pool of executable processes by the OS.
	- Information concerning the process is already maintained in memory but the **code is not loaded** and **no space has been allocated** for the process.
2. **Ready**: not currently executing but that is ready to be executed as soon as the OS dispatches it.
3. **Running**: being executed.
4. **Blocked (Waiting)**: waiting for the completion of some event. e.g. an I/O operation.
5. **Exit (Terminated)**: Released from the pool of executables by the OS, either halted or it aborted.
	Conditions:
	- **Normal Exit**: finished its work
	- **Error Exit**: due to a bug. or any types of exceptions
	- **Fatal Error**: e.g. Compiler exits b/c "no such file exists"
	- Killed by another process

![[Pasted image 20250227111746.png]]

### Control Table
OS is an that entity that manages the use of system resources by processes. to do this it needs information about the current status of each process and resources.

The operating system constructs and maintains tables of information, called control tables. 4 major:
1. Memory tables
	- keep track of both main and secondary (virtual) memory.
	It includes information like:
	- Allocation of main & secondary memory to processes
	- Any information needed to manage virtual memory
2. I/O tables
	- status of an I/O operations and location in memory being used as source or destination.
3. File tables
	- info about the existence & location of files on secondary memory, status, and other attributes.
4. Process tables
	- the location of each process and the attributes of each process(PID and process state)
	- each entry in the process table is called **Process Image**

The tables must be linked or cross-referenced in some fashion.
To create the tables, the operating system must have some knowledge of the basic environment, such as how much main memory exists, what are the I/O devices and what are their identifiers...

#### Process Control Block (PCB)
It represents each process in the OS.
It mainly serves as the repository for any information that may vary from process to process.

Information associated with each process:
- **Process state**: may be new, ready running, waiting, halted, and so on.
- **Program counter**: indicates the address of the next instruction to be executed
- **CPU registers**: Values of the CPU registers when the process was last running.
- **CPU-scheduling info**: includes a process priority, pointers to scheduling queues, and any other scheduling parameters.
- **Memory-management info**: details of memory allocation (e.g., base and limit registers, page/segment tables).
- **Accounting information**: Includes CPU usage, process time, etc.
- **I/O status information**: includes the list of I/O devices allocated to the process, a list of open files, and so on.

| **Process state**        |
| ------------------------ |
| **Process number** (PID) |
| **program counter**      |
| **registers**            |
| **Memory limits**        |
| **List of open files**   |
| **......**               |

#### Process Switching/ Context switch
Occurs when a running process is interrupted and the operating system assigns another process to the running state and turns control over to that process.

A running process may be interrupted by:
- **Interrupt**: An event that occurs outside the process and that is recognized by the processor (clock interrupt, I/O interrupt)
- **Supervisor Call**: A procedure call used by user programs to call an operating system function. 
- **Trap**: An error or ***exception*** condition generated within the currently running process.

Switching requires doing a state save of the current process and a state restore of a different.
Context-switch time is ***overhead***: the system does no useful work while switching.

#### Process Scheduling
The Objective of **multiprogramming** is to have some process running at all times (to maximize CPU utilization.)
The objective of **time sharing** is to switch the CPU among processes so frequently.
To meet these objectives Process scheduler selects among available processes for next execution on CPU.

Process scheduler maintains scheduling queues of processes 
- **Job queue** – set of all processes in the system
- **Ready queue** – set of all processes residing in main memory, ready and waiting to execute
- **Device queues** – set of processes waiting for an I/O device
- Processes migrate among the various queues

**Queuing Diagram** is a common representation of Process Scheduling.
- **Rectangles** represents queues (ready and device queues),
- **Circles** represents resources that serve queues,
- **Arrows** indicates flows of process in the system
![[Pasted image 20250227123421.png]]


#### Schedulers
- **Long-term scheduler** (or job scheduler) – selects which processes should be brought into the ready queue. invoked infrequently (seconds/ minutes)
- **Short-term scheduler** (or CPU scheduler) – selects which process should be executed next and allocates CPU. sometimes is the only scheduler in the system. invoked frequently (milliseconds)
The L.T scheduler controls the degree of multiprogramming. (the no of processes in memory)

Processes can be described as either:
- I/O-bound processes - spends more time doing I/O than computation. short CPU bursts
- CPU-bound processes - -------------------------- computations; very long CPU bursts
The L.T scheduler selects a good mix of both I/O and CPU bound processes.

**Addition of medium-term scheduling**
M.T scheduler can be added if the degree of multi programming needs to be decreased.
- Remove process from memory, store on disk, bring back in from disk to continue execution: **swapping**.
- Swapping may be necessary to improve the process mix or when additional memory is required.

#### Process Termination
A process terminates when it finishes executing and asks the OS to delete it (using `exit()`)
- process may return a status (typically an integer) to its parent process (via the wait() system call)
- Process' resources are deallocated by operating system.
Parent may terminate the execution of children processes for the following reasons:
- Child has exceeded allocated resources(the parent must have a mechanism to inspect the state of its children)
- Task assigned to child is no longer required
- The parent itself is exiting. (cascading termination from the bottom)



---
## The Thread Concept

**Processes and Threads**
Process holds two characteristics:
A. Resource ownership: to hold the data defined in the PCB.
B. Scheduling/ execution: has execution state and dispatching priority, and is the entity that is scheduled and dispatched by the OS.
- These two characteristics are independent and could be treated independently by the OS.
Processes are used to group resources together, threads are the **entities scheduled for execution on the CPU**.

The **unit of dispatching** is usually referred to as a **thread**, while the unit of resource ownership is usually still referred to as a *process or task*.
A process is a collection of one or more threads and associated system resources.

#### Multithreading
A technique in which a process, executing an application, is divided into threads that can run concurrently. `independent tasks`.
It can make programs more responsive and interactive, e.g. printing and typing, web requests

A single thread of execution per process is referred to as a single-threaded approach. E.g. MS-DOS.

In multithreaded processes the processes share code, data, and files as single-threaded does but they have separate registers and stacks.

Shared and Private Items

| Per Process Items          | Per thread items |
| -------------------------- | ---------------- |
| Address space              | Program counter  |
| Global variables           | Registers        |
| Open files                 | Stack            |
| Child processes            | State            |
| pending alarms             |                  |
| Signal and signal handlers |                  |
| Accounting info            |                  |

#### Benefits of Threads
The key benefits of threads derive from the performance implications:
- It takes far less time to create a new thread than create a new process.
- E.g. in Solaris creating a thread is 30x faster than creating a process, and 5x faster than context switching.
- it is also faster to terminate a thread than a process. also faster is to switch b/n threads than processes.
- They enhance efficiency in communication between d/t programs. e.g. threads in the same process share memory and files.


#### Multicore Programming
Each core in a CPU appears as a separate processor to the OS.
Multithreaded programming provides a mechanism for more efficient use of multiple cores and improve concurrency.
-----------------------------------------------> Time

| Single Core | $T_1$ | $T_2$ | $T_3$ | $T_4$ | $T_1$ | $T_2$ | $T_3$ | $T_4$ | .... |
| ----------- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ---- |

| Core 1     | $T_1$ | $T_3$ | $T_1$ | $T_3$ | $T_1$ | $T_3$ | ... |
| ---------- | ----- | ----- | ----- | ----- | ----- | ----- | --- |
| **Core 2** | $T_2$ | $T_3$ | $T_2$ | $T_3$ | $T_2$ | $T_3$ | ... |
**Parallelism** implies a system can perform more than one task simultaneously. 
**Concurrency** supports more than one task by allowing all the tasks to make progress.
- possible to have concurrency without parallelism.

Multicore system challenges include:
- **Dividing tasks**: examining apps to find areas that can be divided into separate, concurrent tasks.
- **Balance**: ensure that the tasks perform equal work of equal value
- **Data splitting**: data accessed and manipulated by the tasks must be divided to run on separate cores.
- **Data dependency**: When one task depends on data from another, programmers must ensure that the execution of the tasks is synchronized.
- **Testing and debugging**: many different execution paths are possible.
Multicore systems will require an entirely new approach to designing software systems.


#### User-Level and Kernel-Level Threads
Threads can be managed in the kernel or user space
1. **Kernel Space**: thread management is done by the kernel
	Advantage:
	- The operating system is aware of the existence of multiple threads. When a thread blocks, the operating system chooses the next one to run, either from the same process or a different one.
	- each kernel-level thread can run in parallel on a multiprocessor system.
	Disadvantage:
	- Thread management is slow (requires a mode switch to the kernel)
	- Creating a user thread requires creating the corresponding kernel, has effect on performance, restrict the number of threads supported by the system
	e.g. Virtually all contemporary OSs: win, Linux, Mac, Solaris.
2. **User Space**: thread management is done by the application and the **kernel** is not aware of the multiple threads.
	- The user space has a thread table. and thread management (specially switching) is much faster.
	Advantage:
	- can be implemented on an OS that doesn't support threads.
	- allow each process to have its own customized scheduling algorithm.
	Disadvantage:
	- if one thread in that process blocks (for example, waiting for I/O like reading from a file), the OS blocks the entire process, including all its threads.
	- Once a thread starts running, no other thread in the process can run unless the current thread voluntarily yields control, as user-level threading typically does not support preemptive scheduling.
	- cannot take advantage of multiprocessing: kernel assigns one process to only one processor at a time.
3. **Combined Approach**: 
	- Thread creation is done completely in user space
	- Multiple ULTs from a single application are mapped onto some <= number of KLTs. The kernel is aware of only the kernel-level threads and schedules those.
	- e.g. Solaris prior to version 9
	![[Pasted image 20250227134507.png]]

### Thread Libraries
Thread library provides programmer with API for creating and managing threads.
Two primary ways:
1. Library entirely in user space with no kernel support
	- All code and data structures for the library exist in user space
	- Invoking a function in the library results in a local function call in user space and not a system call.
2. Kernel-level library supported by the OS
	- code and DSs exist in kernel space.
	- invoking a function in the API results in system call to the kernel.

Three main Thread Libraries:
- POSIX `Pthreads` (either a UL or KL library)
- Windows (a Kernel-level library)
- Java (implemented using the thread library on the host: windows or `Pthreads`)

### Implicit Threading
When programmers create a program with a number of threads it is **Explicit Threading**.

**Implicit Threading**: creation and management of threads by the compilers and run time libraries.
Three Main approaches:
1. Thread Pools
2. OpenMP
3. Grand Central Dispatch

##### Thread Pools
Creating a new thread for each request has potential problems:
- time to create a thread, and the thread being discarded once it completes its work.
- this could lead to large number of threads and could exhaust the system.
Solution:
- create a number of threads at startup and place them in a pool, where they sit and wait for work
Advantages:
- faster than waiting to create a thread
- number of threads in the application(s) is bound to the size of the pool.
##### OpenMP
a set of compiler directives as well as API for programs written in C, C++, or FORTRAN that provides support for parallel programming.

Developers insert compiler directives into their code at parallel regions, and these directives instruct the OpenMP run-time library to execute the region in parallel.

When OpenMP encounters the directive “`#pragma omp parallel`”, it creates as many threads as there are processing cores in the system.

##### Grand Central Dispatch
GCD allows to identify sections of code to run in parallel.
- A technology for Apple's Mac OS X and iOS operating systems
GCD identifies blocks- a self-contained unit of work. 
- Specified by a caret `^` inserted in front of `{ }`. e.g. `ˆ{ printf("I am a block"); }`
GCD schedule blocks by placing them in one of the dispatch queues
- Assigned to available thread in thread pool when removed from queue

Two types of dispatch queues: 
- **Serial/ main queue** – blocks removed in FIFO order one by one, the removed block must complete execution before another block is removed
	- are useful for ensuring the sequential execution of several tasks
- **Concurrent queue** – removed in FIFO order but several blocks may be removed at a time, allow multiple blocks to execute in parallel 
	- Three system wide queues with priorities low, default, high

### Threading Issues
- Semantics of `fork()` (creates a duplicate of a process) and `exec()` (replaces the process in memory with a new one) system calls
- Signal handling
	- Synchronous (Internal Errors) and asynchronous (External events)
- Thread cancellation of target thread
	- Asynchronous(immediately) or deferred(at a safe checkpoint)
- Thread-local storage - private copies of global data, preventing unintended data sharing and race conditions between threads.
- Scheduler Activations - mechanism that efficiently maps user-level threads to kernel threads.


---
# CH 3: Process Synchronization

## Concurrency
Processes can execute concurrently or in parallel.
The fundamental design issue in the management of multiple processes is concurrency: simultaneous execution of multiple processes.

Concurrency arises in three different contexts 
- **Multiple applications**: concurrently running applications.
- **Structured applications**: an application structured as a set of concurrent processes (threads).
- **OS structure**: OS implemented as a set of processes or threads.

Concurrent access to shared data may result in data inconsistency. Maintaining data consistency requires mechanisms to ensure the orderly execution of cooperating processes.

E.g. Consider two process, P3 and P4, that share two variables $b=1$ and $c=2$ 
- P3 executes $b= b+ c$ and P4 executes $c= b + c$ 
	- If P3 executes first, value of $b=3$ and $c=5$. 
	- If P4 executes first, value of $b=4$ and $c=3$ 

### Race Condition
Occurs when multiple processes or threads read and write data items so that the final result depends on the order of execution of instructions in the multiple processes

Assume that simultaneously process A and process B decide they want to queue a file for printing
There are two globally shared variables
- `Outfile`: points to the next file to be printed 
- `Infile`: points to the next free slot in the directory

- Process A reads `infile` and stores the value 7 in its local variable (`x=infile`)
- An interrupt occurs and the CPU decides that process A has run long enough so it switches to process B. Process B reads `infile` and stores the value 7 in its local variable `(y=infile`) 
- Process B stores the name of its file in slot 7 and adjusts `infile` to be 8 
- Eventually process A runs again, it checks x and finds 7 there, and writes its file name in slot 7, erasing the name process B just put there, it updates `infile` to be 8.
- The printer will now print the file of process A, process B file will never get any output

### Critical Region

Part of a program where shared resource is accessed is called critical region or critical section.
It is the ability to exclude (prohibit) all other processes from using a shared variable or file while one process is using it.

Four conditions to provide mutual exclusion:
- No two processes simultaneously in critical region
- No assumptions made about speeds or numbers of CPUs
- No process running outside its critical region may block another process
- No process must wait forever to enter its critical region.

**Mutual Execution with Busy Waiting**
while one process is busy updating shared memory in its critical region, no other process will enter its critical region and cause trouble.

Types:
- Disabling Interrupts
- Lock Variables
- Strict Alternation
- Peterson’s Solution
- TSL Instruction

1. **Disabling Interrupts** - simplest
	- each process disables all interrupts just after entering its critical section and re-enables them just before leaving it.
	- generally unattractive because it is unwise to give user processes the power to turn off interrupts
		- e.g. a process/ the programmer might forget re-enabling the interrupts. causes freezes.
	- Disabling interrupts is often a useful technique within the operating system itself. but not generally appropriate.
2. **Lock Variables**
	- a software solution.
	- Assume a single shared variable called `lock` initially set to 0
	- when a process enters a critical section it sets `lock` to 1, and all other processes wait until it becomes 0.
	Disadvantage:
	- if one process reads `0`, but before it sets it to 1 it is interrupted and another process runs and sets it to 1. when process 1 is back it already checked so it just 'sets' `lock` to 1 and enters critical region at the same time causing race condition.
3. **Strict Alternation** 
	requires that the two processes strictly alternate in entering their critical regions.
	An integer `turn`, initially 0, keeps track of whose turn it is to enter the critical region and examines or updates the shared memory.
	- Initially, process 0 inspects turn, finds it to be 0, and enters its critical region.
	- Process 1 also finds to be 0 (but its turn is 1) and therefore sits in a tight loop continually testing turn to see when it becomes 1. 
	- When process 0 leaves the critical region, it sets turn to 1, to allow process 1 to enter its critical region.
  ```
  While(turn!=0) /*wait*/; 
  Critical_region(); 
  turn=1;
  Noncritical_region();
   ```
   Taking turns is not a good idea when one of the processes is much slower than the other.
	 This situation violates condition 3 of implementing mutual exclusions: process 0 is being blocked by a process not in its critical region. (it must wait for turn=1, can't enter even if P0 is not in C.R)
	   
	 turn can be 1 even when Process 1 is not in its critical region because Process 0 set it that way after exiting, assuming Process 1 might want to go next — even if it doesn’t.
	
   Continuously testing a variable waiting for some value to appear is called **busy waiting**. and it wastes the processors time.

4. **Peterson’s Solution**
	- Combines the idea of taking turns with the idea of lock variables.
	- Before entering its critical region each process calls `enter_region` with its own process number, 0 or 1, as parameter
		- w/c cause to wait if not safe to enter
		- when done calls `leave_region` to allow other process to enter
	- Initially, neither is in C.R
		- then process 0 calls `enter_region` and is allowed.
		- it indicates interest by setting its array element & sets turn to 0.
		- if P1 calls `enter_region` it will wait until `interested[0]` becomes false.
	- if consider the case that both processes call `enter_region` almost simultaneously 
		- Both will store their process number in `turn`.
		- Whichever store is done last is the one that counts; the first one is lost. 
		- Suppose that P1 stores last, so `turn=1`. 
		- When both processes come to the while statement, process 0 executes it zero times and enters its critical section. Process 1 loops and does not enter its critical section. // why we need {turn == process} in the while loop
		![[Pasted image 20250305185441.png]]
5. **TSL Instruction** 
	- requires a little help from the hardware
	- Many multiprocessor computers have an instruction: TSL RX, LOCK
	- TSL (Test and Set Lock) is an indivisible atomic instruction that copies the content of a memory location into a register and stores a non-zero value at the memory location.
		- Indivisible mean no other processor can access the memory word until the instruction is finished.
	- In TSL, we use a shared variable, `lock`, to coordinate access to shared memory.
	- When lock is 0 the process may set it to 1 using TSL instruction and executes its critical section. When it is done, the process sets lock back to 0.
	- also uses `enter_region` and `leave_region` to coordinate these.
	![[Pasted image 20250305185949.png]]


## Sleep and Wakeup
Both Peterson’s solution and the solution using TSL are correct.
- But both have the defect of requiring busy waiting which wastes CPU time and which can also have unexpected effects, like the priority inversion problem.
**Priority inversion problem:**
- Consider H and L, high and low priority processes.
- scheduling rule: H runs whenever it is in the ready state
- but if L is in critical region H is blocked and is busy-waiting. but since L is never scheduled while H is running {priority}, L never gets the chance to leave its critical region, so H loops.

Now let us look at some inter-process communication primitives that block instead of wasting CPU time when they are not allowed to enter their critical regions.
- `Sleep`: It is a system call that causes the caller to block, i.e. be suspended until another process wakes it up.
- `Wakeup`: It is a system call that causes the process specified by the parameter to wake up.
An example of how these primitives can be used let us consider the producer-consumer problem (also known as the bounded buffer problem).

#### Producer-Consumer Problem
A producer and a consumer share a common fixed size buffer.
When the producer wants to put in an item to the buffer it checks and if it is full it goes to sleep to be awaken when the consumer has consumed. if it is not full it adds the item and increments `count`.
The same for the consumer in that if the buffer is empty it goes to sleep to be awaken when item is produced. if not it consumes and decrements `count`.

```C
#define N 100                         /* number of slots in the buffer */
int count = 0;                        /* number of items in the buffer */

void producer(void){
    int item;
    while (TRUE) {                    /* repeat forever */
        item = produce_item();         /* generate next item */
        if (count == N) sleep();       /* if buffer is full, go to sleep */
        insert_item(item);             /* put item in buffer */
        count = count + 1;             /* increment count  */
        if (count == 1) wakeup(consumer); /* was buffer empty? */
    }
}
void consumer(void){
    int item;
    while (TRUE) {                    /* repeat forever */
        if (count == 0) sleep();       /* if buffer is empty, go to sleep */
        item = remove_item();          /* take item out of buffer */
        count = count - 1;             /* decrement count */
        if (count == N - 1) wakeup(producer); /* was buffer full? */
        consume_item(item);            /* print item */
    }
}
```
Race condition can occur because access to count is unconstrained.: Consider:
- Buffer is empty and consumer reads it but at that instant scheduler stops the consumer and starts the producer.
- the producer increments the count and sees it to be 1 so it sends a wakeup call to the consumer.
- but the consumer is technically not asleep so the signal is lost, and when the consumer continues running it goes to sleep. and when the buffer fills up the producer also goes to sleep.
- Both are asleep forever. Deadlock.
A quick fix is to add the rules by adding `wakeup-waiting` bit.
- when a `wakeup` is sent the bit is set. if the process tries to sleep while the bit is set it will be blocked.
- But this can not be a general solution especially with random number of processes.

#### Semaphores
Solve the lost-wakeup problem.
A semaphore is a new integer variable type that counts the number of wakeups saved for future use.
A value `0` indicates no `wakeups` were saved and any `+ve` value indicates 1 or more wakeups pending.
Two operations were proposed: up and down (generalizations of wakeup and sleep, respectively).
- **DOWN**: `if (semaphore > 0) semaphore-- `, `if (semaphore == 0) sleep before completing the down operation.` 
	- checking, updating and sleeping is a single indivisible **atomic operation**. can't be blocked.
- **UP**: `semaphore++`, if 1 or more processes are sleeping on that semaphore before completing their down operation, one is chosen and allowed to complete the down operation. also atomic.
 
The solution uses three semaphores:
- **full**, initially 0, to count the number of full slots,
- **empty**, initially equal to number of slots in buffer, to count the number of empty slots and
- **mutex**, initially 1, to make sure the producer and the consumer do not access the buffer at the same time. is used for mutual exclusion.
full and empty are used for synchronization.
Semaphores that are initialized to 1 and are used by two or more processes to ensure that only one of them can enter its critical region at the same time are called binary semaphores.
```C
#define N 100                           /* number of slots in the buffer */
typedef int semaphore;           /* semaphores are a special kind of int */
semaphore mutex = 1;               /* controls access to critical region */
semaphore empty = N;                        /* counts empty buffer slots */
semaphore full = 0;                          /* counts full buffer slots */

void producer(void){
    int item;
    while (TRUE) {                      /* TRUE is the constant 1 */
        item = produce_item();      /* generate something to put in buffer */
        down(&empty);                   /* decrement empty count */
        down(&mutex);                   /* enter critical region */
        insert_item(item);              /* put new item in buffer */
        up(&mutex);                     /* leave critical region */
        up(&full);                      /* increment count of full slots */
    }
}
void consumer(void){
    int item;
    while (TRUE) {                      /* infinite loop */
        down(&full);                    /* decrement full count */
        down(&mutex);                   /* enter critical region */
        item = remove_item();           /* take item from buffer */
        up(&mutex);                     /* leave critical region */
        up(&empty);                     /* increment count of empty slots */
        consume_item(item);             /* do something with the item */
    }
}
```

Problem: 
- Semaphores are too low-level and error prone.
- a small change as a line switch can make a big difference.
	- e.g.
```c
down(&mutex);  // Lock the shared resource first
down(&empty);  // Then check for an empty slot (if there is none wait)
//this would cause a deadlock. b/c the producer wouldn't be able to produce
```
	

#### Mutex
Simplified version of semaphore: used when count is not needed.
only for managing mutual exclusion to some shared resource or piece of code.
Useful in thread packages that are implemented entirely in user space.

- Integer value 0 represent unlocked and all other values represent locked.
Thread(process) calls `mutex_lock` to access critical region and calls `mutex_unlock` when exit the critical region.
```assembly
mutex_lock:
    TSL REGISTER,MUTEX        | copy mutex to register and set mutex to 1
    CMP REGISTER,#0           | was mutex zero?
    JZE ok                    | if it was zero, mutex was unlocked, so return
    CALL thread_yield         | mutex is busy; schedule another thread
    JMP mutex_lock            | try again later
ok: RET                       | return to caller; critical region entered

mutex_unlock:
    MOVE MUTEX,#0             | store a 0 in mutex
    RET                       | return to caller
```

#### Monitors
A monitor is a higher level of synchronization primitive proposed by Hoare and Branch Hansen to make writing a correct program easier.
Procedures, variables and data structures that are all grouped together in a special kind of module or package.

**Rules associated with monitors**
- processes can call procedures in a monitor but cannot access the monitors internal data structures.
- Only one procedure can be active in a monitor at any instant. Monitors are programming language constructs. so the compiler treats them differently.
- Compiler implements mutual exclusion.
Monitors use condition variables, along with two operations on them, `WAIT` and `SIGNAL` to block and wake up a process.

`WAIT`
- When a monitor procedure discovers that it can not continue(e.g., the buffer is full), it does a WAIT on some condition variable that causes the calling procedure to block.
`SIGNAL`
- A process can wake up its sleeping partner by doing a SIGNAL on the condition variable that its partner is waiting on
- then it must exit the monitor immediately, the `SIGNAL` statement must be the last line.

```
monitor example
	integer i;
	condition e;

	procedure producer();
	...
	end;
	procedure consumer();
	...
	end;
```
Limitations:
- only one monitor procedure active at one time.
- Monitors are a programming language concepts.
- Most languages do not have monitors(E.g. C)
- They were designed for CPUs that will have access to a common memory – can not be implemented in distributed systems.


#### Concurrency Problems
Enforcement of mutual exclusion creates additional control problems
- Deadlock
- Starvation

##### Deadlock
- permanent blocking of a set of processes competing for system resources or communicate with each other.
- a difficult phenomenon to anticipate and there are no easy general solutions to this problem

Example: 
- consider P1 and P2 & two resources R1 and R2
	- suppose each need both resources to do some operation, the OS might assign each 1 R.
	- and both would be waiting for the next R forever. Deadlock.

##### Starvation
a process is ready to execute but is continuously denied access to a processor in deference to other processes.
E.g. suppose that there are three processes P1, P2, and P3 and each require periodic access to resource R. If the operating system grants the resource to P1 and P2 alternately, P3 may indefinitely be denied access to the resource, thus starvation may occur.


#### Classical IPC Problems
1. **Dinning - Philosopher problem**:
	- 5 Philosophers in a circular table and 5 plates with 5 forks in between.
	- `take_fork` waits until the specified fork is available and then seizes it.
	Problem: 
	1. Suppose that all five philosophers take their left forks simultaneously. None will be able to take their right forks, and their will be **deadlock**.
		Solution:
		- After picking left, check for right. if not available put back left and wait for some time.
		- This also raises a problem: ->
	2. -> If all the philosophers could start the algorithm simultaneously, Picking up their right forks were not available, putting down their left forks, waiting, picking up their left forks again simultaneously, and so on, forever. This situation is called **starvation**.
		Solution: 
		- wait a random time instead. But this does not always work.

```c
#define N 5                /* number of philosophers */
void philosopher(int i)    /* i: philosopher number, from 0 to 4 */
{
    while (TRUE) {
        think();           /* philosopher is thinking */
        take_fork(i);      /* take left fork */
        take_fork((i+1) % N); /* take right fork; % is modulo operator */
        eat();             /* yum-yum, spaghetti */
        put_fork(i);       /* put left fork back on the table */
        put_fork((i+1) % N); /* put right fork back on the table */
    }
}
```


```c
#define N 5 /* number of philosophers */
#define LEFT (i+N-1)%N /* number of i's left neighbor */
#define RIGHT (i+1)%N /* number of i's right neighbor */
#define THINKING 0 /* philosopher is thinking */
#define HUNGRY 1 /* philosopher is trying to get forks */
#define EATING 2 /* philosopher is eating */
typedef int semaphore; /* semaphores are a special kind of int */
int state[N]; /* array to keep track of everyone's state */
semaphore mutex = 1; /* mutual exclusion for critical regions */
semaphore s[N]; /* one semaphore per philosopher */

void philosopher(int i) /* i: philosopher number, from 0 to N-1 */
{
    while (TRUE) { /* repeat forever */
        think(); /* philosopher is thinking */
        take_forks(i); /* acquire two forks or block */
        eat(); /* yum-yum, spaghetti */
        put_forks(i); /* put both forks back on table */
    }
}
void take_forks(int i)  /* i: philosopher number, from 0 to N-1 */
{
    down(&mutex);       /* enter critical region */
    state[i] = HUNGRY;  /* record fact that philosopher i is hungry */
    test(i);            /* try to acquire 2 forks */
    up(&mutex);         /* exit critical region */
    down(&s[i]);        /* block if forks were not acquired */
    // It remains blocked until another philosopher calls 
    // `up(&s[i])`, signaling that it can now eat()
}

void put_forks(int i)  /* i: philosopher number, from 0 to N-1 */
{
    down(&mutex);       /* enter critical region */
    state[i] = THINKING; /* philosopher has finished eating */
    test(LEFT);         /* see if left neighbor can now eat */
    test(RIGHT);        /* see if right neighbor can now eat */
    up(&mutex);         /* exit critical region */
}

void test(int i)  /* i: philosopher number, from 0 to N-1 */
{
if (state[i] == HUNGRY && state[LEFT] != EATING && state[RIGHT] != EATING) {
		state[i] = EATING;
		up(&s[i]);
	}
}

```
useful for modeling process that are competing for exclusive access to a limited number of resources, such as I/O devices.

2. **The Readers and Writers Problems**
The readers and writers problem, models access to database.
A data set is shared among a number of concurrent processes
- Readers – only read the data set; they do not perform any updates 
- Writers – can both read and write

**Problem** – allow multiple readers to read at the same time, But Only one single writer can access the shared data at the same time with 0 readers.
- no writers allowed when reading.

Shared Data
- Semaphore `mutex` initialized to 1
- Semaphore `db` initialized to 1
- Integer `readcount` initialized to 0

```c
typedef int semaphore;
semaphore mutex = 1;  /* controls access to 'rc' */
semaphore db = 1;     /* controls access to the database */
int rc = 0;        /* # of processes reading or wanting to*/ //reader count

void reader(void) {
    while (TRUE) {    
        down(&mutex);       /* get exclusive access to 'rc' */
        rc = rc + 1;        /* one reader more now */
        if (rc == 1) down(&db); /* if this is the first reader block the
				         writer from accessing the database by locking it */
        up(&mutex);         /* release exclusive access to 'rc' */
        read_data_base();   /* access the data */
        down(&mutex);       /* get exclusive access to 'rc' */
        rc = rc - 1;        /* one reader fewer now */
        if (rc == 0) up(&db); /* if this is the last reader unlock db... */
        up(&mutex);         /* release exclusive access to 'rc' */
        use_data_read();    /* noncritical region */
    }
}

void writer(void) {
    while (TRUE) {    
        think_up_data(); /* noncritical region */
        down(&db);       /* get exclusive access */
        write_data_base(); /* update the data */
        up(&db);         /* release exclusive access */
    }
}
```
 **Behavior:**
- **Multiple readers can read concurrently.**
- **Writers must wait if there are active readers or other writers.**
- **Writers get exclusive access to avoid inconsistency.**

Readers-Writers Problem Variations 
- First variation – no reader kept waiting unless writer has permission to use shared object 
- Second variation – once writer is ready, it performs write
- Both may have starvation leading to even more variations
- Problem is solved on some systems by kernel providing reader-writer locks


**The Sleeping Barber Problem**
It models a barbershop with one barber, one barber chair, and a waiting room with chairs.
- The barber works when customers are present.
- If no customers are waiting, the barber sleeps in the barber chair.
- When a customer arrives, they check if the barber is sleeping.
- If the barber is sleeping, the customer wakes them and gets a haircut.
- If the barber is busy, the customer checks for available waiting chairs.
- If a chair is available, the customer sits and waits.
- If no chairs are available, the customer leaves.
- The problem focuses on coordinating the barber and customers to avoid race conditions and deadlocks.
  Solution
```c
#define CHAIRS 5  /* # chairs for waiting customers */

typedef int semaphore;  /* use your imagination */

semaphore customers = 0;  /* # of customers waiting for service */
semaphore barbers = 0;    /* # of barbers waiting for customers */
semaphore mutex = 1;      /* for mutual exclusion */
int waiting = 0;          /* customers are waiting (not being cut) */

void barber(void) {
    while (TRUE) {
        down(&customers);  /* go to sleep if # of customers is 0 */
        down(&mutex);      /* acquire access to 'waiting' */
        waiting = waiting - 1;  /* decrement count of waiting customers */
        up(&barbers);      /* one barber is now ready to cut hair */
        up(&mutex);        /* release 'waiting' */
        cut_hair();        /* cut hair (outside critical region) */
    }
}
void customer(void) {
    down(&mutex);  /* enter critical region */
    if (waiting < CHAIRS) {  /* there are  free chairs */
        waiting = waiting + 1;  /* increment count of waiting customers */
        up(&customers);  /* wake up barber if necessary */
        up(&mutex);  /* release access to 'waiting' */
        down(&barbers);  /* sit and wait if # of free barbers is 0 */
        get_haircut();  /* be seated and be serviced */
    } else {
        up(&mutex);  /* shop is full; do not wait */
    }
}
```




# Ch-4 SCHEDULING
#### What is Scheduling?
Scheduling refers to a set of policies and mechanisms to control the order of work to be performed by a computer. Part of the OS responsible for scheduling is called **The Scheduler.** and it uses a **Scheduling Algorithm** to do so.

**Dispatcher**:- a module of the OS that gives control of the CPU to the process selected by the short term scheduler. this involves
- Switching Context
- Switching to user mode
- Jumping to the proper location in the user program to restart that program.
**Dispatch Latency**: time to stop one process and to start another one.

Process Behavior:
- A process is Burst of CPU usage alternate with periods of I/O wait
	- a CPU bound process - Long burst with short I/O wait
	- I/O bound process - Short CPU burst with long I/O wait

#### Types of scheduling
1. **Non-Preemptive** - Run to completion method ^nps
	- a process runs until it terminates or blocks itself to wait for some event.
	- Is Simple and was used in early batch systems
	- It may be well reasonable for some dedicated systems. But Not Generally.
2. **Preemptive** - allows temporary suspension to wait in the ready state.
	- Pre-emption might occur by: arrival of new processes, Interrupt and Clocked Interrupt
	- Suitable for general purpose systems with multiple users.

### Scheduling Criteria
1. To Maximize:
	- Efficiency / CPU Utilization - percentage of time CPU is utilized.
	- Throughput - Number of processes completed per unit time.
2. To Minimize:
	- Turn Around Time - Time from submission to Completion. 
		- Waiting to get into memory + waiting in the ready queue + Execution + I/O wait
	- Waiting Time - sum of time spent in the ready queue.
	- Response Time - time from submission to first response.


**Overhead**
Overhead refers to the extra time and system resources consumed by the operating system to manage and switch between processes rather than executing the actual processes. This includes tasks such as:
- **Context Switching:** Saving and loading process states when switching from one process to another.
- **Scheduler Decision Making:** Running the scheduler algorithm to determine which process should run next.
- **Maintenance of Data Structures:** Managing queues, lists, or other structures that track process states and priorities.
- **Interrupt Handling:** Responding to interrupts that may affect scheduling decisions.

## Scheduling Algorithms
### 1. First Come First Served Scheduling (FCFSS)
- A process that requested the CPU first keeps CPU until it is done [N.P.S](#^nps). and the process in the ready queue the longest is given the CPU next.
- It uses Non-Preemptive scheduling and it's selection function is **Waiting Time**.

**Example**: consider P1, P2, P3 arrive at **time 0** with CPU burst 24, 3, 3 respectively. 
Case 1: in order P1, P2, P3

| Process          | P1  | P2  | P3  |
| ---------------- | --- | --- | --- |
| Service Time     | 24  | 3   | 3   |
| Response Time    | 0   | 24  | 27  |
| Turn Around Time | 24  | 27  | 30  |
Average R.T = $(0+24+27)/ 3 = 17$
Average T.A.T = $(24 + 27 + 30)/ 3 = 37$
Throughput = $3/30 = 1/10$

Case 2: in order P3, P2, P1

| Process          | P3  | P2  | P1  |
| ---------------- | --- | --- | --- |
| Service Time     | 3   | 3   | 24  |
| Response Time    | 0   | 3   | 6   |
| Turn Around Time | 3   | 6   | 30  |
Average R.T = $(0+3+6)/ 3 = 3$
Average T.A.T = $(3 + 6 + 30)/ 3 = 13$
Throughput = $3/30 = 1/10$

**Example 2**: (with variable arrival time) The following processes arrive at time 0, 3, 8, 11 respectively

| Process   | P1  | P2  | P3  | P4  |
| --------- | --- | --- | --- | --- |
| Arrival T | 0   | 3   | 8   | 11  |
| S.T       | 3   | 5   | 3   | 100 |
| R.T       | 0   | 0   | 0   | 0   |
| T.A.T     | 3   | 5   | 3   | 100 |
A.R.T = 0
A.T.A.T = $(3+5+3+100)/4 = 27.25$
Throughput = $4/111$


##### FCFSS: Advantages and Drawbacks
ADV:
- simplest of all N.P.S algorithms
- minimum overhead and no starvation. 
- is often combined with priority scheduling to provide efficiency.

DRS:
- Poor CPU and I/O utilization: CPU will stay Idle when a process is blocked by an I/O operation.
- Poor and Unpredictable Performance - dependent on arrival time
- Unfair CPU allocation - for big operations, all others will have to wait. this works better for long processes.


### 2. Shortest Job First Scheduling (SJFS)
- Process with shortest expected processing time (Burst) is selected next.
- It's selection function is **Execution Time** and it also uses **N.P.S**
Is used frequently in Long-term Scheduling.

**Example**: consider P1, P2, P3 arrive at **time 0**.

| Process          | P3  | P2  | P1  |                                  |
| ---------------- | --- | --- | --- | -------------------------------- |
| Service Time     | 3   | 3   | 24  | i.e. P2 or P3 are selected first |
| Response Time    | 0   | 3   | 24  | b/c they have the shortest S.T   |
| Turn Around Time | 3   | 6   | 30  |                                  |
Average R.T = $(0+3+6)/ 3 = 3$
Average T.A.T = $(3 + 6 + 30)/ 3 = 13$
Throughput = $3/30 = 1/10$

**Example 2:** 

| Process          | P1  | P2  | P3  | P4  | P5  |
| ---------------- | --- | --- | --- | --- | --- |
| Arrival Time     | 0   | 2   | 4   | 6   | 8   |
| Service Time     | 3   | 6   | 4   | 5   | 2   |
| Response Time    | 0   | 1   | 7   | 9   | 1   |
| Turn Around Time | 3   | 7   | 11  | 14  | 3   |
![[Pasted image 20250319121623.png]]
Average R.T = $(0+1+7+9)/ 5 = 3.6$
Average T.A.T = $(3 + 7 + 11 + 14 + 3)/ 5 = 7.6$
Throughput = $5/20$

**Example 2**:

| Process          | P1  | P2  | P3  | P4  | P5  |
| ---------------- | --- | --- | --- | --- | --- |
| Arrival Time     | 0   | 2   | 3   | 8   | 10  |
| Service Time     | 7   | 10  | 5   | 1   | 2   |
| Response Time    | 0   | 13  | 4   | 4   | 3   |
| Turn Around Time | 7   | 23  | 9   | 5   | 5   |
![[Drawing 2025-03-19 12.05.20.excalidraw.png]]
Average response time = $(0+13+4+4+3)/5 = 4.8$
Average turn around time = $(7+23+9+5+5)/5=9.8$
Throughput = $5/25$

##### SJFS: Advantage and Drawback
**ADV**: 
- produces optimal average T.A.T and average R.T
- There is minimum overhead.

DRS:
- Starvation - longer processes will get pushed indefinitely if there is a supply if shorter processes
- Variability of Response Time is increased, especially for longer processes


### 3. Shortest Remaining Time Scheduling (SRTS)
- Process with the shortest expected remaining time gets the CPU.
- If a process arrives and has a shorter burst than what is left of the currently running process, the new process gets the CPU.
- It Is the Preemptive (**P.S**) version of SJF and uses `remaining execution time` as its selection Function.

**Example**: consider P1, P2, P3 arrive at **time 0**, 2, 4.

| Process          | P1  | P2  | P3  |
| ---------------- | --- | --- | --- |
| Arrival Time     | 0   | 2   | 4   |
| Service Time     | 3   | 8   | 4   |
| Response Time    | 0   | 3   | 0   |
| Turn Around Time | 3   | 13  | 4   |
Average response time = $(0+1+0)/3= 0.33$
Average turn around time = $(3+13+4)/3= 20/3$
Throughput = $3/15$

**Example 2**: processes arrive at time 0, 2, 4, 6, 8 respectively

| Process          | P1  | P2  | P3  | P4  | P5  |
| ---------------- | --- | --- | --- | --- | --- |
| Arrival Time     | 0   | 2   | 4   | 6   | 8   |
| Service Time     | 3   | 8   | 4   | 5   | 2   |
| Response Time    | 0   | 1   | 0   | 4   | 0   |
| Turn Around Time | 3   | 20  | 4   | 9   | 2   |
![[Drawing 2025-03-19 12.05.20.excalidraw 1.png]]
Average response time = $(0+1+0+4+0)/5 = 1$
Average turn around time = $(3+20+4+9+2)/5=7.6$
Throughput = $5/20$

##### SRTS Advantages and Drawbacks
**ADV**:
- superior turnaround time than SJFS b/c short jobs are given immediate preference.

**DRS:**
- Risk of starvation of longer processes
- High overhead due to frequent process switch
Difficulty with SJFS: time to figure out remaining time for each process

### 4. Round Robin Scheduling (RRS)
- a time block called **quantum** or time slice is defined. a clock interval is generated at periodic intervals. when the interrupt occurs the running process is placed in the ready queue, and the next process is selected on a FCFS basis.
- The CPU is allocated for a program up to one quantum at a time. when a process finishes its quantum it is placed in the ready queue, when it is requesting I/O it is added to the waiting queue.
- The ready queue is treated as a circular queue.
- It uses **P.S** and has quantum as its selection function.

Example: 
Consider the following processes arrive at time 0, 2, 4 respectively; quantum=4

| Process | P1  | P2  | P3  |                                           |
| ------- | --- | --- | --- | ----------------------------------------- |
| $T_a$   | 0   | 2   | 4   |                                           |
| $T_s$   | 3   | 7   | 4   | P2 starts at T-3                          |
| $R.T$   | 0   | 1   | 3   | P2 is interrupted atT-7 after one quantum |
| $T_r$   | 3   | 12  | 7   | P2 continues at T-11 up-to T-14           |
Average response time = $(0+1+3)/3 = 4/3$
Average turn around time = $(3+12+7)/3 = 22/3$
Throughput = $3/14$

**Example 2**: 
Consider, quantum=4

| Process | P1  | P2  | P3  | P4  |
| ------- | --- | --- | --- | --- |
| $T_a$   | 0   | 3   | 4   | 7   |
| $T_s$   | 7   | 5   | 9   | 10  |
| $R.T$   | 0   | 1   | 4   | 8   |
| $T_r$   | 15  | 17  | 25  | 24  |
![[Drawing 2025-03-19 12.05.20.excalidraw 2.png]] 
The queue is after execution.

Average response time = $(0+1+3)/3 = 4/3$
Average turn around time = $(3+12+7)/3 = 22/3$
Throughput = $3/14$

At T-4, while P1 is exiting P3 also comes in and we decided the one coming from the outside {P3} should get priority to join the ready queue.

##### RRS Features and Drawbacks
**FET**: 
- Oldest, simplest, fairest and most widely used preemptive scheduling.
- Reduces the penalty that short processes suffer with FCFS.

**DRS**:
- CPU-bound processes tend to receive unfair portion of CPU time, which results in poor performance for I/O bound processes.
- It makes implicit assumption that all processes are equally important.
- Maximum overhead due to frequent process switch.

**Difficulty**:
- The length of the quantum should be decided carefully. 
	because frequent context switches cost time. / low CPU utilization. though it may results in faster response time/ Interactivity.  and vice versa for a longer quantum. 
- A quantum around 100ms is often reasonable compromise
- To enable interactivity, a maximum response time (MR) can be specified, and the quantum (m) can be computed dynamically as follows 
	$m = MR/n$ , where $n$ is number of processes. A new $m$ is calculated when the number of processes changes.


### 5. Priority Scheduling
- Each process is assigned a priority and the runnable process with the highest priority is allowed to run. (smallest integer = highest priority)
- Equal-priority processes are scheduled in FCFS order.
- Priorities defined in two ways: 
	- Internal-use some measurable quantity or quantities to compute the priority of a process 
		E.g. time limits, memory requirements, the number of open files, and the ratio of average I/O burst to average CPU burst have been used in computing priorities 
	- External-set by criteria outside the operating system. 
		E.g. importance of the process, the type and amount of funds being paid for computer use, the department sponsoring the work, and other, often political, factors

Example: Consider the following processes arrive at time 0

| Process  | P1  | P2  | P3  | P4  | P5  |
| -------- | --- | --- | --- | --- | --- |
| Priority | 2   | 4   | 5   | 3   | 1   |
| $T_s$    | 3   | 6   | 4   | 5   | 2   |
| $R.T$    | 2   | 10  | 16  | 5   | 0   |
| $T_r$    | 5   | 16  | 20  | 10  | 2   |
Average response time = $(2+10+16+5+0)/5 = 6.6$
Average turn around time = $(5+16+20+10+2)/5=10.6$
Throughput = $5/20= 0.25$


##### Advantages and Drawbacks of Priority Scheduling
**ADV**:
- considers the fact that some processes are more important than others

**DRS**:
- Starvation can occur on low priority tasks.
	- Solution: **Aging** - as time progresses increase the priority of the process.


### Multilevel Queues Scheduling (MLQS)
It is used for situations for which processes can be classified into different groups:
- System processes 
- Interactive processes
- Batch processes

The ready queue is partitioned into several separate queues 
Each processes is assigned to one queue permanently, based on some property of the process such as memory size, process priority, process type, etc.
- Each queue has its own scheduling algorithm.

There must be some kind of scheduling between the queues:
- Commonly implemented as **fixed-priority preemptive scheduling**, i.e. system processes have absolute priority over the interactive processes and interactive processes have absolute priority over the batch processes. Lowest priority processes may be starved.


## Algorithm Evaluation
The first problem is defining the criteria to be used in selecting an algorithm. CPU utilization, response time, or throughput?
To select an algorithm, we must first define the relative importance of these elements.

Our criteria may include several measures, such as these: 
- Maximizing CPU utilization under the constraint that the maximum response time is 1 second 
- Maximizing throughput such that turnaround time is (on average) linearly proportional to total execution time.

### Deterministic Modeling
- One major class of evaluation methods is analytic evaluation. It uses the given algorithm and the system workload to produce a formula or number to evaluate the performance of the algorithm for that workload.

**Deterministic modeling** is one type of analytic evaluation. This method takes a particular predetermined workload and defines the performance of each algorithm for that workload.

For Example: Consider all programs arrive at time 0. With their Burst time in `ms`.
1. P1 - 10      
2. P2 - 29
3. P3 - 3        
4. P4 - 7
5. P5 - 12
Consider FCFS, SJF, and RR (quantum = 10 milliseconds). Which algorithm would give the minimum average waiting time?

For FCFS 

| P1     | P2                | P3     | P4      | P5      |
| ------ | ----------------- | ------ | ------- | ------- |
| 0 - 10 | 10 ------------39 | 39 -42 | 42---49 | 49---61 |
| $0$    | $10$              | $39$   | $42$    | $49$    |
Thus, the average waiting time is $(0 + 10 + 39 + 42 + 49)/5 = 28$ milliseconds.

For SJF

| P3    | P4     | P1       | P5        | P2                 |
| ----- | ------ | -------- | --------- | ------------------ |
| 0 - 3 | 3---10 | 10----20 | 20-----32 | 32--------------61 |
| $0$   | $3$    | $10$     | $20$      | $32$               |
Thus, the average waiting time is (10 + 32 + 0 + 3 + 20)/5 = 13 milliseconds.

For RR

| P1      | P2       | P3    | P4      | P5       | P2       | P5    | P2       |
| ------- | -------- | ----- | ------- | -------- | -------- | ----- | -------- |
| 0----10 | 10----20 | 20-23 | 23---30 | 30----40 | 40----50 | 50-52 | 52----61 |
| $0$     | $32$     | $20$  | $23$    | $40$     |          |       |          |
**Finish Times and Turnaround Times** (arrival time = 0 for all):
- **P1:** Finishes at 10, Turnaround = 10, Waiting = 10 − 10 = 0
- **P3:** Finishes at 23, Turnaround = 23, Waiting = 23 − 3 = 20
- **P4:** Finishes at 30, Turnaround = 30, Waiting = 30 − 7 = 23
- **P5:** Finishes at 52, Turnaround = 52, Waiting = 52 − 12 = 40
- **P2:** Finishes at 61, Turnaround = 61, Waiting = 61 − 29 = 32 , 29 = burst of P2
$(0 + 32 + 20 + 23 + 40)/5 = 23$ milliseconds.

We can see that, in this case, the average waiting time obtained with the SJF policy is less than half that obtained with FCFS scheduling; the RR algorithm gives us an intermediate value.

Deterministic modeling is fast and provides exact numbers for comparing scheduling algorithms, though it requires precise input data and only applies to those specific cases. It’s mainly used for illustrating scheduling methods and providing examples. 
When processing requirements are known, deterministic modeling can help choose an algorithm and reveal trends that can be further analyzed. For example, it shows that if all processes and their times are known at time 0, the SJF policy always minimizes waiting time.

### Queueing Models
Processes that are run vary from day to day, so there is no static set of processes (or times) to use for deterministic modeling.
What can be determined, however, is the distribution of CPU and I/O bursts. These distributions can be measured and then approximated or simply estimated.
The result is a mathematical formula describing the probability of a particular CPU burst.

As an example, let n be the average queue length (excluding the process being serviced), let W be the average waiting time in the queue, and let $\lambda$ be the average arrival rate for new processes in the queue.
We expect that during the time W that a process waits, $\lambda$ × W new processes will arrive in the queue. If the system is in a steady state, then the number of processes leaving the queue must be equal to the number of processes that arrive. Thus,
$$
n = \lambda \times W
$$
This is known as Little's Formula. is particularly useful because it is valid for any scheduling algorithm and arrival distribution. we can use it to solve for one of the 3 variables.

### Simulations
Programming a model of the computer system.
The simulator has a variable representing a clock. As this variable’s value is increased, the simulator modifies the system state to reflect the activities of the devices, the processes, and the scheduler.
The distributions can be defined mathematically (uniform, exponential, Poisson) or empirically.
A distribution-driven simulation may be inaccurate.

#### Implementation
Even a simulation is of limited accuracy. 
The only completely accurate way to evaluate a scheduling algorithm is to code it up, put it in the operating system, and see how it works. 

The major difficulty with this approach is the high cost.

The most flexible scheduling algorithms are those that can be altered by the system managers or by the users so that they can be tuned for a specific application or set of applications.

Another approach is to use APIs that can modify the priority of a process or thread. The Java, POSIX, and Windows API provide such functions. The downfall of this approach is that performance-tuning a system or application most often does not result in improved performance in more general situations.


# CH - 5: Deadlocks

Processes are granted exclusive access to devices that can only be used by one process at a time.
We refer to these devices generally as **resources**. it can be a hardware or an information.

Sequence of events required to use a resource:
1. Request the resource
2. Use the resource
3. Release the resource

Ex: Suppose a process holds resource A and requests resource B, and at the same time another process holds B and requests A.
- Both processes are blocked and remain so, This is called a **DEADLOCK**.

Resource Types: 
- Preemptable resources - can be taken away from a process with no ill effects. E.g. RAM
- Non-Preemptable resources - will cause the process to fail if taken. E.g. CD-recorder
In general deadlocks involve non-preemptable resources.

**Formal Definition**:
	A set of processes is deadlocked if each process in the set is waiting for an event that only another process in the set can cause.
	Usually the event is release of a currently held resource.

When deadlock occurs none of the processes can … 
- Run 
- release resources
- be awakened


### Conditions for Deadlock
A deadlock situation can arise ONLY if the following four conditions hold simultaneously
- **Mutual Exclusion**: only one process at a time can use the resource.
- **Hold and Wait Condition**: Processes currently holding resources granted earlier can request new resources.
- **No Preemptive Condition**: Resources can't be taken away from a process.
- **Circular Wait Condition**: There must be a circular chain of two or more processes each waiting for a resource held by the next member of the chain.

#### Deadlock Modeling
Modeled using directed graphs. (Resource Graphs)
Two nodes: Processes (circles) and Resources (square)
 - An arc form a resource to a process means the resource is currently held by that process.
 - An arc from a process to a resource means the process is currently blocked waiting for that resource.

Example: we have processes A, B, C and resources R1, R2, R3. The request are:
**A**
- A1: requests R1
- A2: requests R2

**B**
- B1: Requests R2
- B2: Requests R3

**C**
- C1: Requests R3
- C2: Requests R1

If we use round robin scheduling algorithm the requests will be executed as A1 → B1 → C1 → A2 → B2 → C2
![[Pasted image 20250407081958.png]]
- If there is any cycle in the graph that means there is a deadlock.

### Methods for Handling Deadlocks

Four strategies are used for dealing with deadlocks.
1. Ignore the problem
2. Detect and Recover
3. Dynamically avoid deadlock by careful resource allocation
4. Prevent, by structurally negating one of the four required conditions

##### 1. Ignore the problem
**The Ostrich Algorithm**
- Simplest Approach
- Stick your head in the sand and pretend there is no problem at all.
	- Mathematicians do not accept it
	- Engineers accept with constraints - frequency of deadlocks
- Reasonable if
	- Deadlocks occur very rarely
	- Cost of prevention is High
- E.g. UNIX and Windows take this approach

##### 2. Detection and Recovery
- Keeps a resource graph to check for cycles every time a resource is requested and released, 
- If a cycle exists, one process in the cycle is killed.
- One method is: the system selects a process with a long wait time for termination.

##### 3. Deadlock Recovery
Deadlock recovery strategies:

- **Recovery through preemption:** Involves taking a resource from another process. Feasibility depends on the type of resource
- **Recovery through rollback:** Periodically checkpoint a process and use its saved state to restart it if it's deadlocked.
- **Recovery through killing processes:** Terminate one process in the deadlock cycle, releasing its resources to other processes. Choose a process that can restart from the beginning.

##### 4. Deadlock Avoidance
We can avoid deadlocks, but only if certain information is available in advance.
- Process declare the maximum number of resources of each type that it may need
- Construct an algorithm that ensures that the system will never enter a deadlocked state
- 
The Banker’s algorithm considers each request as it occurs and sees if granting it leads to a safe state. If it does, the request is granted; otherwise, it is postponed until later.

**The Banker's Algorithm:** 
1. Each process requests resources, but the system only grants them if it’s sure it won’t lead to a deadlock.
2. The system checks if there will still be enough resources available for all other processes to finish safely after granting the request.
3. If granting the resources might lead to a deadlock, the system temporarily denies the request and waits for resources to be released.

Think of it like a banker who only lends money if they’re sure they’ll still have enough for other customers!
Safety check:
- The banker analyzes whether resources are sufficient to meet the needs of the process requesting the most (closest to its maximum demand).
- If resources are granted and this process eventually releases its allocated resources after finishing, the system assumes those resources are "repaid."
- The banker continues this analysis for all processes to ensure every process can complete and release its resources.

If all processes can finish without creating a deadlock, the state is considered safe, and the initial resource (that started the check) request can be approved.

**Safe state**
A state is safe if the system can allocate all resources requested by all processes ( up to their stated maximums ) without entering a deadlock state.

Safe State: All processes can complete eventually without causing a deadlock.
Unsafe State: At least one process may not complete, potentially leading to a deadlock.

Terminology:
"Has" - Allocation
"Max" - Max needed
"need" - actual need = max - allocation
"work" - available → = work + allocation , after a process is done

only if there is a process that satisfies Need ≤ Work, for a resource can the state be safe and start execution until it becomes unsafe or it finishes safely
	! [ ] (https://youtu.be/2V2FfP_olaA?si=VhxICUA433XYYeIC)]
e.g. from the video, ABC are resources initially 332
only Allocation, max and initial available are given
1. calculate the need of each process
2. check for each process if work ≤ need
	1. for P0 (743 ≤ 322) it fails
	2. for p1 (122≤322) it succeed and new work = 332 + 200 = 5 3 2
	3. for p2 (600≤532) it fails
	4. for p3 (011≤532) it succeeds and new work = 532 + 211 = 7 4 3
	5. for p4 (431≤532) it succeeds and new work = 743 + 002 = 7 4 5
	6. for p0 (743≤745) it succeeds and new work = 745 + 010 = 7 5 5
	7. for p2 (600<755) it succeeds and final work = 755 + 302 = 10 7 5

| Processe | Allocation | Max | Available <br>(Work) | Need<br>(Max-Allocation) |
| -------- | ---------- | --- | -------------------- | ------------------------ |
|          | ABC        | ABC | ABC                  | ABC                      |
| P0       | 010        | 753 | 332                  | 743                      |
| P1       | 200        | 322 |                      | 122                      |
| P2       | 302        | 902 |                      | 600                      |
| P3       | 211        | 222 |                      | 011                      |
| P4       | 002        | 433 |                      | 431                      |
Algorithm
1. Find a process whose remaining resource needs are less than or equal to the available resources (A).
2. If no such process exists, the system may deadlock.
3. If found, assume the process gets its needed resources and finishes.
4. Mark it as finished and add its resources back to A.
5. Repeat from step 1.
6. If all processes finish, the system is in a safe state.
7. If not, it's unsafe and may deadlock.


##### 5. Deadlock Prevention
Avoidance is hard b/c it requires information about future requests w/c is not known.

Prevention Works by ensuring that at least one of the four necessary condition for deadlocks can not hold.
1. **Attacking the Mutual Exclusion Condition**
	Principle: avoid assigning resource when not absolutely necessary. Let the process to use resources simultaneously.
	E.g. Consider a printer that only one process can use at a time (mutual exclusion). To attack this condition, we **avoid exclusive access** by making the printer **sharable**.
	**Solution:**  
	Instead of a physical printer, use a **virtual printer** that writes to a file. Multiple processes can write to different files at the same time.
	**Disadvantage**: This solution cannot be used for every resource. E.g. a mutex lock cannot be simultaneously shared by several processes
2. **Attacking the Hold and Wait Condition**
	Idea: Don’t let a process hold resources while waiting for more.
	- Force processes to request all needed resources at once.
	Problems: Most processes do not know that resources they need before running. 
	- Leads to **low resource utilization** and **starvation**.
	Variation: - process must give up all resources, then request all at once.
3. **Attacking the No Preemption Condition**
	Idea: Take resources away from processes when needed. Not Feasible
	**Problem:**
	- **Not all resources can be safely preempted** (e.g., a printer in the middle of printing).
	- Preempting can cause **data inconsistency or loss**.
4. **Attacking the Circular Wait Condition**
	**Idea:** Prevent circular chain of resource requests.  
	**Example:** Impose a global order on resource requests (e.g., always request resources in increasing order: R1 → R2 → R3).
	In order to request resource $R_j$, a process must first release all $R_i$ such that i <= j.

Summary

| Condition        | Approach                        |
| ---------------- | ------------------------------- |
| Mutual Exclusion | Spool/Buffer everything         |
| Hold and Wait    | Request all resources initially |
| No Preemption    | Take resources away             |
| Circular wait    | Order resources numerically     |



# CH - 6: Memory Management

Program must be brought into memory and placed within a process for it to be run.
Ideally programmers want memory that is large, fast & non volatile.
*The memory hierarchy*:
- **Cache**: Smallest, fastest, and most expensive memory, closest to the CPU.
- **Main Memory (RAM)**: Larger than cache, good speed & moderate price, typically holding gigabytes of data.
- **Disk Storage**: The slowest & cheapest, providing terabytes of persistent storage for applications and files.

Part of the operating system that manages memory is called the **memory manager (MM)**.
Main functions:
- Keeping track of in use and free memory
- Allocating and de-allocating memory
- Managing swapping between memory and disk

A good MM:
- allows all processes to run
- Its own memory overhead must be reasonable.
- Its time overhead is reasonable.

### Basic Memory Management
Memory management systems can be divided into two basic classes based on their approach to virtual memory: those with and without memory swapping & paging.
- **Mono-programming** – Only one process will be in the memory in addition to the operating system.
- **Multiprogramming** - It allows multiple programs to run in parallel. Divides the memory among concurrently running processes and the operating system.

**Mono-Programming**
Three simple ways of organizing memory:  "numbers are approximations from a diagram"
1. OS in 1/3 RAM and other to User Program -> mainframes and mini-computers, old
2. OS in 1/3 ROM and other to User Program -> embedded systems
3. Device Drivers in 1/6 of ROM, 2/6 to OS in RAM, other 3/6 to User Program -> early personal systems


### Memory Partitioning

There are two partitioning options:
- Fixed partitioning – partitioning is done before the processes comes to memory 
- Dynamic partitioning – partitioning is done when processes request memory space

1. **Fixed Partition**
- Oldest and simplest method of partitioning.
- Variations:
	**Equal Sized Fixed Partitions**: Any process that fits can be loaded into any partition.
	- **Advantages**: Simple to implement, minimal overhead.
	- **Problems**: Internal fragmentation (unused memory within a partition) and process size limitations.

	**Unequal Sized Fixed Partitions**: Two schemes for allocation:
	- **Multiple Queues**: Each partition has its own queue, and a process is loaded into the smallest available partition that fits.
		- **Advantage**: Reduces internal fragmentation.
		- **Disadvantage**: Some partitions may remain unused.
	- **Single Queue**: Processes are assigned to the smallest available partition, optimizing partition usage.
		- **Advantage**: More efficient partition usage.
		- **Disadvantage**: Small processes may be delayed due to searching for best fit.
	- **Summary:**
		- **Advantages**: Simple, minimal overhead.
		- **Disadvantages**: Internal fragmentation, limited number of active processes, and process size limitations.

2. **Dynamic partitioning**
	- Partitions are created **dynamically** during memory allocation with **variable sizes**.
	- Processes are allocated **exactly the amount of memory** they require.
	- Processes are **swapped** as needed.
	**Problem:**
	- Dynamic partitioning can lead to **external fragmentation**, where small, unusable holes form in memory over time as processes are loaded and unloaded.
		![[Pasted image 20250412191547.png]]
	
	**Solution to External Fragmentation:**
	- **Compaction**: Combines these small, useless memory holes into one large free block.
	    - **Problem**: Compaction requires a significant amount of **CPU time**, which can slow down the system.
	**Summary:**
	- **Advantages**:
	    - Better memory utilization since processes get exactly what they need.
	- **Disadvantages**:
	    - More complex memory management.
	    - **Compaction overhead** to handle external fragmentation.

### Relocation and Protection
Multiprogramming introduces two big problems – protection and relocation

Protection: 
- Programs in other processes should not be able to reference memory locations in a process for reading or writing purposes without permission.
- A user program shouldn’t be able to address a memory area which is not in its partition.
	- A user process must not access any portion of the OS. 
	- Usually a program in one process can not branch to an instruction in another process. 
	- Without permission, a program in one process cannot access the data area of another process.

Relocation:
- Location of a program in main memory is unpredictable due to loading, swapping and compaction.
- To solve this problem, a distinction is made among several types of addresses.
- There are two types of addresses:
	- Logical address: It is a reference to a memory location independent of the current assignment of data to memory. 
	- Physical/absolute address: An actual locator in the main memory

- A user Program never sees the Physical address
- The memory-mapping hardware converts logical addresses into physical addresses.

##### Logical vs. Physical Address Space
The concept of a logical address space that is bound to a separate physical address space is central to proper memory management.
- Logical address – generated by the CPU.
- Physical address – address seen by the memory unit

Logical and physical addresses are: 
- The same in compile-time and load-time address-binding schemes; 
- They differ in execution-time address-binding scheme. In that case the logical address is referred to as virtual address.

- **Logical address space** is the set of all logical addresses generated by a program
- **Physical address space** is the set of all physical addresses corresponding to a given logical address space.

**Memory-Management Unit (MMU)**
Hardware device that runs at runtime & maps virtual addresses to physical address.


##### Relocation techniques
two possible solutions for relocation problems
1. Static Relocation
	- When a process is loaded into memory, all **relative memory references** are replaced with **absolute addresses** based on the **base address** of the loaded process.
	- This method is applied to processes that are always assigned to the **same partition** (e.g., in the case of unequal-sized fixed partitions with multiple process queues).
	**Problem:**
	- **Protection Issue**: Static relocation does not address protection problems. A **malicious program** could potentially create a new instruction and jump to it, bypassing memory protection mechanisms.
2. Dynamic Relocation
	- When a process is assigned for execution, the **base register** is loaded with the starting address of the program, and the **limit register** is loaded with the ending address of the partition.
	- The **base** and **limit registers** are protected by hardware, ensuring they cannot be modified by user programs.
	- Hardware mechanisms are used to **translate relative addresses** into physical addresses during instruction execution.

	**How it Works for User Processes:**
	- *Address Translation*: When a user process accesses memory, it generates a logical address (relative to its own start). The CPU's hardware (Memory Management Unit or MMU) automatically adds the value from a base register (which holds the process's physical starting address) to this logical address, converting it into a physical address.
	- *Bounds Checking*: The MMU simultaneously compares the logical address against a limit register (defining the process's allocated size). If the logical address is outside these bounds, a memory access violation interrupt is triggered, and the operating system intervenes to handle the error, often terminating the process.
	- This process ensures that a program can't accidentally or maliciously access memory outside its assigned area.

	**Advantages:**
	- **Relocation**: Dynamic relocation allows processes to be loaded into different memory locations, offering flexibility.
	- **Protection**: It protects against invalid memory access, as addresses are checked against the limit register, preventing unauthorized access.

	**Summary:**
	- **Advantages**: Solves both the **relocation** and **protection** problems.
	- **Disadvantages**: Requires hardware support for base and limit registers.

##### Swapping
- A **process** can be temporarily swapped **out of memory** to a **backing store** (e.g., disk) and then brought back into memory when needed for continued execution.
- This allows the **total physical memory space** of all processes to exceed the system's actual physical memory.

**Memory Management Approaches:**
1. **Swapping**: Processes are brought into memory in their *entirety*, run for a while, then swapped back out to disk. This is a simple technique but can cause delays due to swapping. - this is old and now it is paging.
2. **Virtual Memory**(modern): Allows programs to run even if only *part of them* is in main memory. It gives the illusion of a larger amount of memory than physically available. It typically achieves this by dividing memory into fixed-size pages and then swapping individual pages (via **paging**) between RAM and disk on demand.

**Memory Allocation:**
- Memory allocation changes as processes **enter** and **leave** memory. This dynamic management helps optimize memory usage.

**Process Structure and Memory Allocation**
A process has three major sections:
1. **Stack** (for function calls, local variables).
2. **Data** (global variables, static variables).
3. **Code** (program instructions).

**Fixed Partitions:**
- In fixed partitioning, the space allocated to a process is usually larger than what it needs, allowing it to **expand** if necessary.

**Dynamic Partitions:**
- With dynamic partitioning, processes are allocated exactly the memory they need, but this creates an overhead when the process grows or shrinks, as it requires **moving** and **swapping** to accommodate changes.

If a process runs out of the extra space allocated to it, either 
- It will have to be moved to a hole with enough space or 
- Swapped out of memory until a large enough hole can be created or
- Kill the process


#### Memory Usage Management
There are two ways to keep track of memory usage

1. **Bitmaps**
	Memory is divided into fixed size allocations.
	Each allocation unit is represented with a bit in the bit map.	 0 = free, 1 = allocated
	![[Pasted image 20250421171143.png]]
	can be represented by:

| 11110011 |
| -------- |
| 11111001 |
| ...      |
The size of the allocation unit is an important design issue.
- The smaller the allocation unit, larger bitmap size -> results in memory and CPU overhead, searching will take more time.
- If large then the internal fragmentation will be high.

2. **Linked List** 
	Each segment is either a process(P) or a hole(H) between two processes and contains a number of allocation units.
	
	**Each entry in the list consists of**
	- Segment type: P/H (1bit)
	- The address at which it starts
	- The length of the segment
	- A pointer to the next entry
	Ex: the above bitmap example can be represented using linked lists as:
	Head -> `[p][0][4][]-> [H][20][2][]-> [P][30][7][]-> [H][65][2][]-> [P][75][4][]-> [H][95][6][]-> ` 
	
	The list is kept sorted by address. Sorting this way has the advantage of easily updating when processes terminates or is swapped out. 
	A terminating process normally has two neighbors, except when it is at the very beginning or end of the list.
	When a process and holes are kept on a list sorted by address, several algorithms can be used to allocate memory for a newly created process.
	
**Memory Allocation (Placement) Algorithms**
- W/c free block to allocate.
1. First Fit:
	- start scans from the beginning and choose the first that can fit.
	- Disadvantage: Searching From the Start always may result in slow performance.
2. Next Fit:
	- start scan from the last placement and choose the next that can fit.
	- Disadvantage: It may cause the last section of memory to be quickly fragmented
3. Best Fit:
	- It searches the entire list of available holes and chooses the lock that is closest in size to the request.
	- Disadvantage: External fragmentation and slower because it scans the whole list.
4. Worst Fit:
	- It searches for the largest available hole, so that the hole broken off will be big enough to be useful.
	- Disadvantage: It is as slow as best fit
5. Quick Fit:
	- It maintains separate list for some of the more common size requests.
	- Advantage: Finding a hole of the required size is extremely fast
	- Disadvantage: When a process terminates or is swapped out, finding its neighbors to see if a merge is possible is expensive.
		- Free blocks are stored in **separate size-based lists**.
		- These lists **don’t track where blocks are located in memory** relative to each other.
		- So, when you free a block, the system has no quick way to check if the **neighboring memory blocks** are also free.
		- To merge, the system might need to **search through multiple lists** or **scan memory**, which is **slow and costly**.



#### Virtual Memory
*Problem*: A process may be larger than the available main memory. 
[Full Gemini Conversation about Memory](https://g.co/gemini/share/dc5b3085a28e)

**Overlays (Early Solution)**:
- Program is manually divided into modules by the programmer.
- The main program handles loading/unloading modules as needed.
- **Drawbacks**:
    - Programmer must know exact memory size.
    - Time-consuming and error-prone.

**Virtual Memory (Modern Solution)**
- OS automatically manages memory.
- Only active parts of a program are kept in **main memory**; the rest stays on **disk**.
- Allows large programs (e.g., 512 MB) to run on smaller physical memory (e.g., 256 MB).
- Uses **virtual addresses** generated by the program w/c form a **Virtual Address Space**.
- **Memory Management Unit (MMU)** maps virtual addresses to **physical addresses**.
- Efficient and transparent to the programmer.

#### Paging and Segmentation
There are two virtual memory implementation techniques 
- Paging
- Segmentation

**Paging**
- **Paging** divides the **virtual address space** into fixed-size blocks called **pages**.
- **Physical memory** is divided into **page frames**, which are the same size as pages.
- Common page/frame size: Power of 2 (e.g., 512B to 16MB).
- **Transfers between memory and disk** happen in units of pages.
- Paging allows non-contiguous memory allocation, improving memory utilization.
- The **compiler or Memory Management Unit (MMU)** handles the division of processes into pages.
		![[Pasted image 20250421180628.png]]
Examples:
1. When the program tries to access address 0 using the instruction - MOVE REG, 0
	 The MMU sees that this virtual address falls in page 0 (0-4095), which according to its mapping is page frame 2 (8192 to 12287). It thus transforms the address to 8192 and outputs address 8192 onto the bus.
2. MOVE REG, 8196 is effectively transformed in to MOVE REG, 24580
3. MOVE REG, 4250, ? In to: 4250
4. Move REG, 20580, ? In to: 12388 

**Example**: Address Bits = 16, Page size = 4K, Logical address = 8196. The following figure shows the internal operation of the MMU with 16 4K pages. split into a 4-bit page number and a 12-bit offset.
	![[Pasted image 20250421181110.png]]

Gemini response without image given:
**Given:**
* **Address Bits:** 16 bits (meaning a 16-bit virtual address space).
* **Page Size:** 4 KB (4096 bytes).
* **Logical Address:** 8196 (decimal).

---

Step 1: Determine Page Offset and Virtual Page Number (VPN)

First, the MMU needs to divide the logical address into its two components: the Virtual Page Number (VPN) and the Page Offset.

* **Page Size (P):** 4 KB = 4096 bytes.
* **Bits for Page Offset:** To represent 4096 unique bytes within a page, we need $\log_2(4096)$ bits.
    $4096 = 2^{12}$, so the **Page Offset requires 12 bits.** 

* **Bits for Virtual Page Number (VPN):** The total address space is 16 bits.
    Total Address Bits - Page Offset Bits = VPN Bits
    $16 - 12 = 4$ bits. So, the **VPN requires 4 bits.**

Now, let's convert the Logical Address `8196` (decimal) into binary and apply this division:

* **Logical Address in Binary:**
    `8196` decimal = `0010 0000 0000 0100` binary (16 bits)

    * **Virtual Page Number (VPN):** The first 4 bits.
        `0010` (binary) = `2` (decimal).
        So, **VPN = 2**.

    * **Page Offset:** The last 12 bits.
        `0000 0000 0100` (binary) = `4` (decimal).
        So, **Page Offset = 4**.

This means the process is trying to access the 4th byte within its 2nd virtual page (remember, pages are often zero-indexed, so VPN 0, VPN 1, VPN 2...).

---

Step 2: MMU Consults the Page Table

The MMU now takes the **Virtual Page Number (VPN = 2)** and uses it as an index to look up an entry in the process's **Page Table**.

Let's assume the following hypothetical Page Table entries for this process:

| Virtual Page Number (VPN)                                 | Valid Bit | Physical Page Frame Number (PPFN) |
| :-------------------------------------------------------- | :-------- | :-------------------------------- |
| 0                                                         | 1         | 5                                 |
| 1                                                         | 1         | 8                                 |
| **2**                                                     | **1**     | **10**                            |
| 3                                                         | 0         | (Disk Address)                    |
| ... (and so on up to VPN 15, as there are 4 bits for VPN) |           |                                   |

In this example, the MMU finds the entry for VPN 2. It sees:
* **Valid Bit = 1**: This means the page is currently in physical memory.
* **Physical Page Frame Number (PPFN) = 10**: This indicates that virtual page 2 is located in physical page frame 10.

Step 3: MMU Constructs the Physical Address

Now that the MMU has the Physical Page Frame Number, it combines it with the original Page Offset to form the final physical address.

* **Physical Page Frame Number (PPFN):** 10 (decimal).
* **Page Offset:** 4 (decimal).

To construct the physical address:
1.  Shift the PPFN left by the number of offset bits (12 bits), effectively multiplying it by the page size.
    $10 \times 4096 = 40960$ (decimal)
    Or, in binary, append 12 zeros to the PPFN (binary representation of 10 is `1010`):
    `1010` `0000 0000 0000` (this would be 16 bits for the frame base)

2.  Add the Page Offset to this base address.
    $40960 + 4 = 40964$ (decimal)

    Or, in binary:
    `1010` `0000 0000 0000` (Physical Frame Base)
    `0000 0000 0100` (Page Offset)
    --------------------------
    `1010 0000 0000 0100` (Physical Address)

* **Result:** The **Physical Address** is `40964` (decimal).

MMU Operations Summary:
1.  **Input:** Logical Address `8196` (decimal).
2.  **Decomposition:** MMU splits `8196` into:
    * Virtual Page Number (VPN) = `2`
    * Page Offset = `4`
3.  **Page Table Lookup:** MMU uses VPN `2` to find the corresponding entry in the Page Table.
4.  **Validity Check:** MMU verifies the Valid Bit. In this case, it's `1`, so the page is in memory.
5.  **PPFN Extraction:** MMU extracts the Physical Page Frame Number (PPFN) = `10`.
6.  **Physical Address Construction:** MMU combines `PPFN 10` with `Page Offset 4` to form the Physical Address: `40964`.
7.  **Memory Access:** The CPU then accesses physical memory location `40964`.

If the Valid Bit had been `0`, a Page Fault interrupt would have been generated instead, and the OS would have handled loading the page from disk.




**Page Tables**
- The **Operating System** maintains a **page table** to map **virtual addresses** to **physical addresses**.
- Page tables are stored in **main memory**.
- The OS also keeps a list of **free frames**—unoccupied page frames in memory.

**Each Page Table Entry Contains**:
1. **Present-bit**:
    - Indicates whether the page is currently in **main memory**.
2. **Modified-bit (Dirty bit)**:
    - Shows whether the page has been **altered** since it was loaded.
    - If not modified, there's **no need to write it back to disk** during replacement.
3. **Frame Number**:
    - Points to the **physical frame** where the page is stored (if present).


**Page Size** 
There are two issues: 
- The smaller the page size, the less number of internal fragmentation which optimizes the use of main memory.
- The smaller the page size, the greater the number of pages and thus the larger the page table.

Paging(cont’d)
- If an instruction in a process tries to access an address in unmapped page
	- The MMU causes the CPU to generate an interrupt, called **page fault**
	- The OS puts the interrupted process in a blocking state and takes control
	- The OS chooses a page(page frame) to remove from memory and updates its contents back to the disk if it is modified since its last load

##### Page Replacement Algorithms (PRA)
When a **page fault** occurs, the OS must **replace a page** in memory to load the needed one. **Page Replacement Algorithms** decide **which page to remove**.

**Optimal (OPT) PRA**
- Replaces the page that will **not be used for the longest time** in the future.
- **Best performance**, but **impractical** since future references are unknown.

**First-In First-Out (FIFO) PRA**
- Replaces the **oldest** page (the one loaded first).
- **Simple** and easy to implement.
- **Drawback**: Frequently used pages may be removed, leading to poor performance.

**Least Recently Used (LRU) PRA**
- Replaces the page that was **least recently used**.
- Based on the assumption that pages used recently will likely be used again soon.
- **Good performance**, but **hard to implement efficiently** in hardware.

**Second Chance PRA**
- **Improves FIFO** by using a **reference bit (R-bit)**.
- Pages are in FIFO order. When selected:
	- If R-bit = 0 → replace it.
	- If R-bit = 1 → **give it a second chance** (clear R-bit and move it to end of queue).
- Prevents frequently used pages from being removed too quickly.

**Clock PRA**
- **Circular version** of Second Chance.
- Pages arranged like a **clock**.
- A "hand" moves to inspect pages:
	- If R-bit = 0 → replace the page.
	- If R-bit = 1 → clear it and move hand forward.
- **Efficient implementation** of Second Chance.
	**Clock = Second Chance with a circular, pointer-based approach**.
	- It’s faster and more efficient, especially for systems with large numbers of pages.


#### Segmentation
**Segmentation** is a **memory management scheme** that matches the user’s logical view of memory. Unlike paging, which divides memory into fixed-size blocks, segmentation divides programs into **logical, variable-sized units**.
**Key Concepts**:
- A **program** is a collection of **segments**, such as:
    - Main program, functions, procedures, methods
    - Objects, stacks, arrays, local/global variables, symbol tables
- Segments are of **unequal size** and **dynamically sized**.
- Each segment has its **own virtual address space**, starting from **0 to max**.
- Segments can reside in **non-contiguous** memory locations.
- The OS maintains a **segment table** per process and a **free segment list**.
- Helps manage **growing data structures** (like stacks or arrays).
- **No internal fragmentation** (as segment sizes vary based on need).

**Benefits**:
- Reflects the **logical structure** of programs.
- Makes it easier to apply **protection and sharing** on a per-segment basis.
- Avoids the need for **contiguous memory allocation**.

**Example**:
Assume a program with the following segments:
1. **Code (Main program)** – 20 KB
2. **Global Variables** – 10 KB
3. **Stack** – 15 KB
4. **Heap** – 25 KB
These segments will be stored in different memory areas, and each segment will be accessed using:
`Virtual address = (segment number, offset)`
So, if the stack is Segment 2, and we want to access the 5th byte in the stack, the address is:
`(2, 5)`
This is then translated by the **segment table** into a physical address.
	![[Pasted image 20250421184311.png]]


| Consideration                                                      | Paging                                                                         | Segmentation                                                                                            |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Need the programmer be aware that this technique is being used?    | NO                                                                             | YES                                                                                                     |
| How many linear address space are there?                           | 1                                                                              | Many                                                                                                    |
| Can the total address space exceed the size of physical memory?    | Yes                                                                            | Yes                                                                                                     |
| Can procedures and data be distinguished and separately protected? | No                                                                             | Yes                                                                                                     |
| Can tables whose size fluctuates be accommodated easily?           | No                                                                             | Yes                                                                                                     |
| Is sharing of procedures b/n users facilitated?                    | No                                                                             | Yes                                                                                                     |
| Why was this technique invented?                                   | To get a large linear address space without having to buy more physical memory | To allow programs and data to be broken up into logically independent address spaces and to aid sharing |

| **Aspect**                 | **Paging**                                           | **Segmentation**                                   |
| -------------------------- | ---------------------------------------------------- | -------------------------------------------------- |
| **Memory Division**        | Divides memory into fixed-size blocks (pages/frames) | Divides memory into variable-size logical segments |
| **Unit Size**              | Fixed size                                           | Variable size                                      |
| **Purpose**                | Manages physical memory efficiently                  | Matches the programmer's logical memory structure  |
| **Address Format**         | (Page number, Offset)                                | (Segment number, Offset)                           |
| **Logical View**           | Does **not** reflect logical program structure       | Reflects logical program components                |
| **Fragmentation Type**     | May cause **internal fragmentation**nm               | May cause **external fragmentation**               |
| **Ease of Growing Data**   | Difficult (fixed size)                               | Easy (segments can grow dynamically)               |
| **Translation**            | Uses a **page table**                                | Uses a **segment table**                           |
| **Contiguity Requirement** | No (non-contiguous allocation allowed)               | No (but segments are contiguous within themselves) |
| **Protection & Sharing**   | Page-level                                           | Segment-level                                      |
| **Example Unit**           | 4KB page                                             | Stack, function, array, object                     |


# CH-7: File Systems
### Files
**File Naming**
A file is an abstraction used to store and retrieve information on a disk, with the file name serving as a key identifier.
Many operating systems use file extensions (e.g., .txt, .html) to indicate file types. But In systems like UNIX, extensions are just conventions, while in Windows, they are used to associate files with specific programs.

**File Structure**
Three common types:
1. *Byte Sequence*: No inherent structure, the system treats this as raw data and the meaning is imposed by the user program. UNIX and Windows.
2. *Record Sequence*: Files consist of fixed-length records, each record has an internal structure. File operations work at record level, one record at a time. 
	- e.g. OLD mainframes with Punched cards.
3. *Tree Structure*: Files organized in a tree with records containing key fields, allowing fast searching for records based on keys. used in some large mainframes for commercial data processing.

**File Types**
1. *Regular Files*: ASCII files, Binary files
2. *Special Files*: Character special files - for serial I/O devices and Block special files - Represent disk devices for block-based data transfer.

**File Access**
Early operating systems used sequential access for files, from start to finish w/c is suitable for magnetic tape storage. But disks made random access possible.

There are two ways to specify the reading position in random-access files:
- Specify the starting position with each read operation.
- Use a seek operation to set the current position and then read sequentially from there. 
The second method is used in UNIX and Windows.

**File Attributes** / Metadata
Attributes can include:
- Access control: who can access the file (sometimes includes passwords)
- Flags: bits like hidden, archive (for backups), and temporary (auto-deleted after use).
- Key-related fields: for files with searchable records (e.g., key length/position).
- Timestamps: creation, access, and modification times.
- Size info: current size, and sometimes maximum size (in older systems).

**File Operation**
Different systems provide various operations to manage storage and retrieval. Common file system calls include:
- Create, Delete, Open, Close, Read, Write, Append, Get & Set attributes, Rename
- Seek - Repositions the file pointer for random-access files to a specific location.

### Directories
Directories are special files that store references to other files or directories. There are two types of directory structures:
They can be Single-Level Or Hierarchical.

**Single-Level Directory Systems**
A single-level directory stores all files in one place. This simple structure was used in early computers and some embedded devices like cameras.
Advantages:
- Simple to implement
- Easy to search (only one place)

Disadvantages:
- No way to group related files
- Filename conflicts
- Not scalable

**Hierarchical Directory Systems**
Organizes files in a tree-like structure with directories and subdirectories. This model supports thousands of files and multiple users.
*Advantages*:
- Better file organization
- Supports multiple users
- Avoids filename conflicts

**Path Names**
In a hierarchical file system, files can be referenced using two types of path names: 
*Absolute Path Names*: the complete path from the root directory to the file.
- example, `/usr/ast/mailbox` indicates that the root directory contains a subdirectory `usr`.
- Absolute paths always start from the root and are unique across the system.

*Relative Path Names*:  are based on the working directory (or current directory).
- if in `usr/ast/` we can just say `mailbox` to refer `/usr/ast/mailbox`.

Relative paths are more convenient but functionally equivalent to absolute paths.

*Special Directory Entries: "." and ".."*
Most hierarchical file systems include two special entries in every directory:
- `.(dot)`:  Refers to the current directory
- `.(dotdot)`:  Refers to the parent directory, except in root, where it points to itself.

**Directory Operations in Operating Systems**
While implementations vary across operating systems, UNIX-like systems provide a standard set of operations, which include:
1. *Create (`mkdir`)* → Makes a new directory at a specified path,  with . and ..
2. *Delete (`rmdir`)* → Removes an empty directory.  
3. *Open Directory (`opendir`)* → Opens a directory handle to read its contents.  
4. *Close Directory (`closedir`)* → Releases the directory handle after use. ensures proper cleanup.
5. *Read Directory (`readdir`)* → Retrieves the next entry (file/subdir) in an open directory.  Unlike raw file reading (read), `readdir` abstracts the internal directory structure, returning entries in a standardized format.
6. *Rename (`rename`)* → Changes the name or location of a directory.  
7. *Link (`link`)* → Creates a hard link to a file (not directories). allowing a file to appear in multiple directories. the file's i-node tracks the links.
8. *Unlink (`unlink`)* → Deletes a file/hard link (or symbolic/soft link).  

*Symbolic/Soft links* 
Advantages:
- Can link across different disks or even remote systems.
- Can reference directories (unlike hard links in many systems).

Disadvantages:
- Slightly slower access (requires path resolution).
- If the target is deleted, the `symlink` becomes a "dangling" reference.


### File System Implementation
Implementers focus on storage, space management, efficiency, and reliability.

##### File-System Layout
- Disks are divided into partitions, each with an independent file system.
- The MBR (Master Boot Record) in sector 0 boots the computer and contains the partition table, listing partition start/end addresses. The active partition's first block, the boot block, loads the OS.
1. **Disks → Partitions**  
	 - A disk is split into separate sections called **partitions**, each with its own file system.
2. **Master Boot Record (MBR)**  
	 - The *first sector (sector 0)* of the disk.  
	 - Contains:  
		 - *Boot code* (to start the computer).  
		 - *Partition table* (lists where each partition starts/ends).  
3. **Boot Block** 
	- The *first block* of the active partition.
	- Loads the *operating system (OS)* when the computer starts.
4. **Superblock**  
	 - Stores *critical file system info* (like a "header" for the partition).  
	 - Includes:  
		 - File system type (e.g., NTFS, ext4).
		 - Total blocks, free blocks, `inode` count.  
	- Loaded into *memory* when the partition is accessed.
5. **Free Space Management**  
	 - Tracks which disk blocks are *free/used* (using a *bitmap* or *linked list*).  
6. **`Inodes`**  
	 - Stores *metadata* (permissions, size, owner) for *each file/directory*.  
7. **Root Directory** 
	 - The *top-level folder* (`/` in Linux, `C:\` in Windows).
8. **Files & Directories**  
	 - The *actual data* stored in the remaining blocks.

| **Disk Layout**   | **What It Does**                    |
| ----------------- | ----------------------------------- |
| *MBR*             | Boots PC + lists partitions         |
| *Boot Block*      | Loads the OS                        |
| *Superblock*      | File system "settings"              |
| *Free Space Mgmt* | Tracks empty/full blocks            |
| *Inodes*          | File metadata (not the actual data) |
| *Root Dir*        | Starting point of all files         |
| *Files/Dirs*      | Your actual documents, photos, etc. |

##### Implementing Files
The main challenge is tracking which disk blocks belong to which file.
**Contiguous Allocation**: Files occupy consecutive blocks. simple and fast for sequential reads but suffers from external fragmentation. file size must be known at creation.
**Linked-List Allocation**: Files are linked list of blocks via pointers. no Ext. fragmentation, But slow for random access (traversing list).
**Linked-List Allocation with FAT (File Allocation Table)**: Pointers are moved to an in-memory table (FAT). Faster random access. It requires the entire FAT to be in memory always.
**I-node (Index Nodes)**: Each file has an `inode` containing metadata and disk block addresses. The `inode` table is on disk but moved to RAM for open files. Efficient as only needed for open files, size independent of disk size. For large files exceeding `inode` address capacity, the last address can point to a block of more addresses
(indirect blocks).

##### Implementing Directories
Directories map file names to the information needed to locate data (`inode` number, starting block). They also store file attributes.
1. **Purpose**  
	 - Maps filenames → `inode`/block locations + stores attributes.  
2. **Storage Methods**  
	 - **Directory Entry**: Filename + disk addresses/attributes (simple but inflexible).  
	 - **`Inode`-Based**: Filename + `inode` number (attributes stored in `inode` → more flexible). 
3. **Handling Long Filenames**  
	 - **Fixed max length**: Wastes space.  
	 - **Variable-length entries**: Flexible but causes fragmentation and spanning multiple pages. 
	 - **Heap storage**: Filenames stored separately (efficient but needs heap management). 
4. **Searching**  
   - **Linear**: Slow for large dirs.  
   - **Hash table**: Faster but complex.  
   - **Caching**: Speeds up repeated lookups.  

##### Shared Files
Allowing a file to appear in multiple directories (creating a DAG, Directed Acyclic Graph).
- **Hard Links**:  
	- Multiple directories entries point to the **same `inode`**.
	- Changes appear everywhere; file deleted only when **link count = 0**.  
	- Ownership stays with creator. 

- **Symbolic (Soft) Links**:  
	- Shortcut file storing the **path** to the target.  
	- Works across filesystems; breaks if target is deleted.  

*Challenges*:  
- Complex paths (DAGs) confuse backups/traversal.  

**Difference**: Hard links = same file, soft links = path pointers.


### FILE-SYSTEM MANAGEMENT AND OPTIMIZATION
##### Disk-Space Management
**Block Allocation**: Files are typically stored in fixed-size blocks rather than contiguously to avoid file movement issues upon growth.
**Block Size Trade-offs**:
- *Large blocks*: Waste space for small files (internal fragmentation).
- *Small blocks*: Lead to more disk I/O (seeks and rotational delays), reducing performance.
- *Performance vs. Space*: A 4KB block size offers a better balance; however, performance and space utilization are inherently in conflict. Small blocks are bad for performance but good for disk space utilization.

**Keeping Track of Free Blocks**:
- *Linked List*: Each block holds numbers of many free blocks, with a pointer to the next block in the list.
	- ***Optimization***: Instead of single blocks, track runs of consecutive free blocks (e.g., "Block 1000, 50 free blocks").
	- Pros: Simple, efficient for large free regions.
	- Cons: Can waste space if the disk is fragmented.
- *Bitmap*: A bit for each disk block (1 for free, 0 for allocated). Space-efficient than Linked list (e.g., 130,000 1KB blocks for a 1TB disk) unless the disk is nearly full. 

**Optimizations and Trade-Offs**
- *Caching in Memory*: Keep one block of pointers (linked list) or part of the bitmap in RAM to reduce disk I/O.
- *Bitmap Allocation Strategy*: Allocate blocks from the same bitmap region to reduce disk-arm movement.
- *Splitting Pointer Blocks*: To avoid frequent disk writes, keep the in-memory block half-full (split when full).

	**Example**: Memory block holds 4 out of 5 (max) pointers.
	- 3 new pointers arrive (from a deleted file).
	- Split the total 7 pointers:
	- Keep 4 in memory (i.e., "half full").
	- Write the other 3 into a new block on disk.
	This way:
    - The memory block always has space for new frees or allocations. and less I/O.

##### File-System Backups
**Efficiency Considerations**: 
- *Selective Backup*: Only back up necessary data (e.g., exclude executable binaries, temporary files, device files like /dev).
- *Incremental Dumps*: Backup only files modified since the last full or incremental dump to save time. Recovery becomes more complex.
- *Compression*: Can save space but increases risk (a single bad spot can corrupt an entire file/tape).
- *Active File Systems*: Difficult to back up consistently. Solutions include rapid "snapshots" that freeze the file system state by copying critical data structures, allowing leisurely backup.
- *Non-technical Issues*: Security of backup media (off-site & physical security).

**Backup Strategies**:
- *Physical Dump*: Copies disk blocks sequentially from block 0 to last. Simple, fast, but inflexible (cannot skip directories, do incremental dumps, or restore individual files). Needs to be aware of bad blocks and system-specific internal files (e.g., paging files).
- *Logical Dump*: Recursively dumps specified directories and files modified since a base date. More flexible, allowing incremental backups and individual file/directory restoration.

**UNIX Four-Phase Algorithm**:
*Phase 1*: Marks all modified files and all directories (modified or not) in a bitmap via a recursive tree walk.
*Phase 2*: Unmarks directories that contain no modified files or directories under them (can be combined with Phase 1). This ensures only necessary directories for restoration are dumped.
*Phase 3*: Dumps all marked directories in numerical i-node order, prefixed by their attributes.
*Phase 4*: Dumps all marked files, also prefixed by their attributes.

Tricky Issues: Reconstructing the free block list, handling hard links (dumping only once), dealing with file holes (not dumping zero-filled blocks), and avoiding special files/named pipes.

**Restoration Process**:	
- Start with an empty file system.
- Restore full backup first, then incremental backups in order.
- Rebuild free-block list (not stored in backups).


##### File-System Consistency
System crashes can leave the file system in an inconsistent state (e.g., modified i-nodes, directories, or free list blocks not written to disk).
**Utility Programs**: `fsck` (UNIX) or `sfc` (Windows) check and repair consistency, often run at boot after a crash.
**Block Consistency Checks**: Uses two tables with counters: one for blocks in files, one for blocks in the free list.
- *Missing Blocks*: Block not in either table. Added to the free list.
- *Duplicate Blocks in Free List*: Block appears multiple times in the free list. Free list is rebuilt.
- *Duplicate Data Blocks*: Same block used by two or more files. A free block is allocated, contents copied, and the copy inserted into one of the files.

**Directory Consistency Checks**:
Uses a table of counters per file, incremented by directory entries. Compare these with the link counts in i-nodes.
- *i-node Link Count Too High*: File is not in any directory but i-node count is non-zero. Wastes space; i-node count is corrected.
- *i-node Link Count Too Low*: Potentially catastrophic; if a file has multiple links but i-node count is too low, removing one link could prematurely free the i-node and its blocks.
**Other Checks**: Validating directory format, i-node numbers, suspicious permissions (e.g., outsiders having more rights than owner), large directories, and SETUID files owned by superuser in user directories (security risk).

##### File-System Performance
**Caching (Buffer Cache)**: check all read requests to see if the needed block is in the cache. If it is, the read request can be satisfied without a disk access. If the block is not in the cache, it is first read into the cache and then copied to wherever it is needed.
Keep blocks in memory and hash tables for quick lookup of those blocks.
- *Modified LRU Replacement Algorithms* - prioritizes consistency. Critical blocks are written to disk immediately if modified, regardless of LRU position, to prevent file system corruption on crash. Blocks unlikely to be needed soon are put at the front of the LRU list.

***Write-Through vs. Write-Back***:
- *Write-through (older Windows)*: All modified blocks written to disk immediately. More reliable, but more disk I/O.
- *Write-back (UNIX)*: Modified blocks are collected in cache and written periodically (e.g., by `sync` system call or update daemon every 30 seconds). More efficient, but higher risk of data loss on crash. Modern systems like NTFS use journaling for reliability.

***Integration with Page Cache***: Attractive when memory-mapped files are supported, treating file blocks and pages uniformly.

**Block Read Ahead**: Anticipates sequential reads by pre-fetching the next block into the cache. Works well for sequentially accessed files; can hurt performance for randomly accessed files. File system tracks access patterns (sequential/random mode) to decide.

**Reducing Disk-Arm Motion**:
- *Block Allocation*: Allocate related blocks close together, ideally in the same cylinder or cylinder group.
- *Cylinder Groups*: Divide disk into groups, each with its own i-nodes, blocks, and free list. New files attempt to allocate blocks in the same cylinder group as their i-node to minimize seeks.
- *i-node Placement*: Placing i-nodes in the middle of the disk or within cylinder groups reduces average seek time to data blocks.

**Solid-State Disks (SSDs)**: No moving parts, so random access is as fast as sequential. Eliminates disk-arm motion issues.
But:
- Limited write cycles (wear leveling needed).
- Random access = sequential access (no need for disk-arm optimizations).

**Defragmenting Disks** 
Rearranges files to make them contiguous and consolidates free space, improving performance on traditional hard disks by reducing fragmentation.
*Process*: Moves fragmented files to contiguous free space, then fills the newly freed contiguous space with other files.
*Effectiveness*: Windows systems often benefit from defragmentation (defrag utility). Linux file systems (e.g., ext2/ext3) are less prone to fragmentation due to their block allocation strategies.
*SSDs*: Defragmentation is counterproductive for SSDs; it offers no performance gain and shortens their lifespan due to limited write cycles. 
Unmovable files (paging, hibernation, journaling logs) can complicate partition resizing.



# CH-8: Input Output Management

I/O devices vary so widely in their function and speed, varied methods are needed to control them.
The following are functions of the operating system as I/O manager:
- Control all the computer I/O devices.
- Issue commands to I/O devices, catch interrupts and handle errors.
- Provide an interface between the device and the rest of the system.

##### Principles of I/O Hardware
Two types of I/O device:
**Block Devices** (such as disks):
- Store info in fixed size blocks, each with its own address. with common blocks 512 - 32k bytes.
- each block can be read or written independently.

**Character Devices** (such as printers, mouse and NIC):
- delivers or accepts a stream of characters with no block structure.
- Not addressable and has no seek operation.

I/O devices have components:
- Mechanical component and Electronic component (device controller).

Controller's Task
- Convert serial bit stream to block of bytes
- Perform error correction as necessary
- Make available to main memory

Each controller has a few registers used for communicating with the CPU.

##### Memory-Mapped I/O
Controller has one or more registers for data and control signals. 
Processor communicates with control register in one of those methods:
- Separate I/O and memory space
- Memory-mapped I/O- device-control registers are mapped into the address space of the processor
- Hybrid

##### Direct Memory Access (DMA)
A technique for moving fata directly between memory and I/O without the CPU's intervention. needed b/c controllers can be slow and waste the CPU's time.

Without DMA reading from disk: 
- controller reads the block from the drive, bit by bit until all is in buffer.
- the controller computes checksum to verify no read error
- Controller causes an interrupt
- The OS reads the block from buffer a byte or word at a time to store into memory

Problem: Since the OS controls the loop of reading it wastes the CPU time. 

With DMA:
- CPU programs the DMA so it knows what to transfer where.
- Tasks the DMA to read data to its buffer and verify checksum.
1. CPU programs the DMA
2. DMA requests transfer from controller to memory
3. Data is transferred
4. Ack sent back to DMA
5. interrupt the CPU when done.

##### Principles of I/O Software
Goals and issues of I/O software:
**Device Independence**: to write programs that can read files without having to modify the program for each different device types.
**Uniform Naming**: the name of a file or a device should simply be a string or an integer and not dependent on the device in any way.
**Error handling**: In general, errors should be handled as close to the hardware as possible (Controller level). only if not able to deal with should the upper layers know.
**Transfer**: two types of transfer modes – Synchronous (Blocking) and Asynchronous (interrupt –driven).
- waiting until finished or doing something else wile waiting.

**Buffering**: data coming off a device can not be stored in final destination. e.g. in a packet from a network it needs to be examined first.

Device Types: Two types
- **Sharable** (disk) - can be used by multiple users
- **Dedicated** (tape drives) - single user until done.


##### Layers of I/O Software
- **Interrupt Handler** (Bottom) - A process starts I/O → blocks until completion.
	- Interrupt occurs → handler processes it → unblocks the waiting process.

- **Device driver** - device-specific code for controlling I/O device.
	- Translates OS requests into device-specific commands (registers, signals, timing).
	- Only the driver knows hardware details (e.g., disk sectors, mouse movements).
		Steps in carrying out I/O requests:
	1. *Translate Request* - Convert abstract command → hardware-specific details (e.g., block number → disk head/track/sector).  
	2. *Send to Device* - Write commands into the device’s registers.
	3. *Driver Blocks* - Sleeps until the device finishes (interrupt arrives).  
	4. *Interrupt Wakes Driver* - Device signals completion → driver unblocks.  
	5. *Check for Errors* - Verify success; pass data to OS if needed.  
	6. *Repeat or Wait* - Process next queued request or sleep again.  

- **Device independent OS software** - large fraction of I/O software. 
	- provide a *uniform interface* to the user-level software.
	- *Device Naming* – responsible for mapping symbolic devices names onto the proper driver.
	- *device-independent block size* 
	- *Buffering* - until the rest of the data are written. 
	- *Device protection* – prevent users from accessing devices that they are not entitled to access.
	- *Allocating and releasing dedicated devices*: It is up to the OS to examine requests for devices usage and accept or reject them.
	- *Error reporting*: if the driver fails to read the error it reports to the higher software.

- **User-level software** - small portion of the I/O software 
	- System calls, including the I/O system calls, are normally made by library procedures.  
	- example how the I/O system works during reading by an application:
	- *Step 1*: the user program produce a system call for reading from a file
	- *Step 2*: the device-independent software looks in the block cache; if the needed block is not there it calls the device driver.
	- *Step 3*: driver issues the request to the hardware and the blocks waiting.
	- *Step 4*: when done the hardware generates an interrupt.
	- *Step 5*: interrupt handler is run to discover what happened, extracts the status and wakes up the sleeping process to finish the I/O request.

# CH-9: Storage Management

### Disk Hardware
All real disks are organized into *cylinders*, each one containing many *tracks*.
Each of the *tracks* then will be divided into *sectors*.
The set of tracks that are at one arm position makes up a cylinder.
Common platters range 3.5”, 2.5”, and 1.8”

**Disk Access Time**
HDDs rotate at 60 to 250 times per second
The time required to read or write a disk block is determined by three factors:
- *Transfer rate* is rate at which data flow between drive and computer
- *Positioning time* is time to move disk arm to desired cylinder (*seek time*) and time for desired sector to rotate under the disk head (*rotational latency*)
Seek time dominates the other two times.
*Head crash* results from disk head making contact with the disk surface. BAD

### Disk Arm Scheduling Algorithm
The OS maintains queue of requests for each I/O operation
- **First Come First Served** (FCFS): Accept a request one at a time and carries them out in that order.
	- E.g. 1. Consider a disk queue with requests for I/0 to blocks on cylinders: 1, 36, 16, 34, 9, 12 
	- Head starts at 11, Service order: 1,36,16,34,9,12, Arm motion required: 10, 35, 20, 18, 25, 3, Total= 111 cylinders.
	- Simple and fair
- **Shortest Seek First** (SSF) - It handles the closest (the least disk arm movement) request next, to minimize seek time.
	- E.g. 1 Consider a disk queue with requests for I/0 to blocks on cylinders: 1, 36, 16, 34, 9, 12
	- Head starts at 11, Service order: 12,9,16, 1, 34, 36, Arm motion required: 1, 3, 7, 15, 33, 2 , Total= 61
	- Provides efficiency but might cause starvation/ not fair
- **SCAN (Elevator)** Algorithm - arm goes in one direction until no outstanding requests in that direction then it switches direction.
	- Direction bit 1= up, 0=down
	- E.g. Track initial position: 11, Track request: 1, 36, 16, 34, 9, 12, Direction bit: 1 Service order: 12, 16, 34, 36, 9, 1, Disk arm motion: 1, 4, 18, 2, 27, 8, Total= 60 cylinders
- **C-SCAN (Modified Elevator)** Algorithm - when it reaches the end it just returns to the beginning of the disk without servicing any requests
	- more uniform wait time than SCAN.
	- Treats cylinders as circular lists. It reduces the max delay experienced by new requests.
	- Service order: 12, 16, 34, 36, 1, 9

***Selecting Disk- Scheduling Algorithm***
SSF is common and has a natural appeal because it increases performance over FCFS
SCAN and C-SCAN perform better for systems that place a heavy load on the disk.
- Less starvation

Performance depends on the number and types of requests.


### Disk Management

**Disk Formatting**: 
- *Low-level (physical) formatting* - Prepares the raw disk surface by dividing it into sectors (blocks) that the disk controller can read and write.
	- May include techniques like **sector sparing** to handle bad blocks.
	- When the disk detects a bad sector, it replaces or "spares" it with a good sector from a reserved, known as the spare pool. It is transparent to OS.

- *Partitioning* - Splits the disk into groups of cylinders (e.g., C: and D: drives).
	- Each partition can have its own file system and operating system.

- *Logical Formatting* ("Making a File System") - Writes OS file system structures (e.g., FAT, NTFS, ext4) to the partition.
	- Includes structures like superblocks, i-nodes, and directory entries.

**Boot Block**:
- A special area of the disk that helps load the operating system.
- Typically located in the first sector of the boot partition.

**Bootstrap Program**
- Stored in ROM (Read-Only Memory).
- Initializes hardware components (CPU registers, memory, disk controllers) during system startup
- Loads the OS from the boot block into memory

**Boot Partition**
- The partition that contains the operating system kernel and essential device drivers.
- Must be accessible at boot time.

**Master Boot Record (MBR)**
- Located in the first sector of the disk.
- Contains the partition table and bootloader code for legacy BIOS systems.
- Used by Windows and other OSes to initiate the boot sequence.


![[Pasted image 20250526150324.png]]














