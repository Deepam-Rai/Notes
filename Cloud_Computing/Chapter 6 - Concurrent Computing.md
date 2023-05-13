
**Throughput computing:** focuses on delivering high volumes of computation in the form of transactions.  

**Multiprocessing:** is execution of multiple programs in a single machine.  

**Multithreading:** relates to possibility of multiple instruction streams within a same program.  

Concurrent programming largely relates to multithreading. It can be extended to distributed context too.  

----
# Parallelism for single-machine computation

Multiprocessing uses multiple processing units within a single machine.  

**Assymetric multiprocessing:** involves concurrent use of different processing units that are specialized to perform different functions.  
- GPUs is an application of assymetric processing.

**Symmetric multiprocessing:** features the use of similar or identical processing units to share the computation load.  
- multicore technology is application of symmetric processing.
- A single processor with multiple cores.
	- Each core has its own L1 cache.
	- L2 cache is common to all cores.
- Has become significant after physical constrain imposed on frequency scaling(increasing clock frequency).

**Non-Uniform Memory Access(NUMA)**  defines specific architecture for accessing a shared memory between processors.  

**Clusterd multiprocessing** uses multiple computers joined together as a single virtual computer.  

Multiprocessing:
1. is just one technique to achieve parallelism.
2. leverages parallel hardware architectures.

# Programming applications with threads

**Implicit threading:** underlying APIs use internal threads to perform specific tasks.  

**Explicit threading:** use of threads within the system by application developers.

> **Thread:** is a single control flow, which is a logical sequence of serial instructions, within a process.
- Threads within same process share memory space and execution context.
- Each thread has it's own local storage.
- They may have different lifetimes.

**Context switch:** The process of temporarily stopping the execution of one process, saving all the information in the registers and replacing it with the informated related to another process.  

**Main thread:** the main process thread of the running program.  

Relationship between process and threads:
![Relationship between process and threads](../Images/Cloud%20Computing/process_and_threads.png)

----
## Thread APIs

### POSIX threads
Portable Operating System Interface for UNIX(POSIX) is a set of standards related tothe application programming interfaces for a portable development of applications over the Unix operating system flavors.  
- defines creation, termination,waiting for thread completion operations.
- threads can have attributes.
- also has semaphores, conditions, reader-writer locks, etc to support synchronization.
- C: `pthread.h`

### java an .NET
- Object oriented approch.
- manages or logical threads on top of a virtual machine. This are mapped to physical threads by the runtime environment.
- Common operations: start, stop, suspend, resume, abort, sleep, join and interrupt.
- mutexes, critical regions, reader-writer locks, etc implementations are provided by means of class libraries or additional libraries.

----
## Techniques for parallel computation with threads

**Decomposition:** is a technique that aids in understanding whether a problem is divided into components(or tasks) that can be executed concurrently.  

### Domain decomposition
**Domain decomposition** is the process of identifying patterns of functionally repetitive, but independent, computation on data.  

**Embarassingly parallel** are the problems where synchronization of threads is not required.  
- Assumes it is possible to isolate an independent unit of work.
- Not inherently sequential.

**Master-slave model:**  
- system divided into two major code segments.
- one code segment contains the decomposition and coordination logic.
- another code segment contains the repetitive computation to perform.
- master thread creates as many slave threads as required.
- master threads composes the collection of results from the slave threads to get the final result.

Example: Matrix multiplication.

### Functional decomposition
**Functional decomposition** is the process of identifying functionally distinct but independent computations.  

- focus on type of computation rather than on the data manipulation.
- separation defined by distinct logic operations.
- Might require composition/aggregation phase.

Example: solving $f(x) = \sin(x) +\cos(x)+\tan(x)$.  

### Computation vs communication

The decomposition techniques are based on the assumption that the computations are independent. Less communication among threads generally means more throughput.

----
# Multithreading with Aneka
Decomposition techniques can leverage clouds for execution of units of work.   

- Need to redesign the application.
- Latency is more.
- amount of effort required often depends on the facilities offered by the middleware managing the distributed infrastructure.

**Aneka** is a middleware for managing clusters, grids, and clouds, provides developers with advanced capabilities for implementing distributed applications.  

## Thread programming model
It is the abstraction of distributed thread, Aneka thread, which mimics behaviour of local threads but executed over a distributed infrastruture.  

## Aneka thread vs normal threads

| | Aneka thread | Normal thread|
|--|--|--|
| Scope: | Distributed system. | A single system. |
|Interface Compatibility:| Doesnt support suspend/resume/sleep/interrupt instead uses join. | Supports all. |
|Context: | Lives in context of distributed application. | Implicitly belong to hosting process and their range of action. |
| States: | More states. | Comparatively less states. |
| State transition control: | Mostly by middleware. | Mostly by developer. |
| Synchronization facility: | join operation. | monitors, semaphores, reader-writer locks, etc. |
| Thread priority: | Doesnt support. | Supports. |


