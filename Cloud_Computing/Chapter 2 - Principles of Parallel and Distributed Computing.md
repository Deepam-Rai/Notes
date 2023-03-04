
# 2.1 Eras
Models of computing:
1. Sequential: Began 1940s
2. Parallel: Began 1950s
Key Elements of computing:
1. Architectures
2. Compilers
3. Applications
4. Problem Solving Environments
Every aspect of an era went through _Research And Development, Commercialization, Commoditization_.


# 2.2 Parallel vs. distributed computing
| Parallel Computing | Distributed Computing |
| -- | -- |
|Tightly coupled systems. | Wider class of systems including tightly coupled.|
| Computation divided into several processors with shared memory. | Computation broken into units and executed concurrently on different computing elements. |
| Typically homogenous computing elements. | Typically implies heterogeneous computing elements. |


----
# 2.3 Elements of parallel computing

## 2.3.1 Parallel Processing
> **Definition: Processing of multiple tasks simultaenously on multiple processors.**

Parallel Programming: Programming on a multiprocessor system using the divide-and-conquer technique.

Factors influencing development of parallel processing:
- Increasing computational requirements
- Sequential architectures reaching physical limitations
- Hardware improvements in pipelining, superscalar are nonscalable
- Vector processing, highly parallelizable works well for certain kind of problems.
- Parallel processing technology is mature and thus commercializable.
- Developments in networking technology - better for heterogenous computing.

## 2.3.2 Hardware architectures for parallel processing
Based upon the number of instruction and data streams that can be computed simultaenously, computing systems are categorized as:
1. Single Instruction, Single Data systems (SISD): aka sequential. Eg, IBM PC, Macintosh.
2. Single Instruction, Multiple Data (SIMD): Eg, Cray's vector processing machine and Thinking Machines' cm
3. Multiple Instructions, Single Data (MISD): Useful where different computation is done on same data
4. Multiple Instructions, Multiple Data (MIMD): 
	- Each PE(Processing Element) has its own data streams.
	- PEs work asynchronously.
	- Types: Shared Memory MIMD - tightly coupled  Distributed memory MIMD - loosely coupled - uses IPC.

|Shard Memory MIMD | Distributed Memory MIMD|
| -- | -- |
| Tightly coupled. | Loosely coupled. |
| Communication takes place through shared memory. | Communication takes place through Inter Process Communication.|
| Data modified by one PE in shared memory is visible to all. | Each PE have own memory. |
| Easier to program. | Comparatively difficult to program. |
| Comparatively less tolerant to failures, a failure can affect entire system. | Comparatively more failure tolerant.  Failure are component wise. |
| Less likely to scale due to memory contention | Scalable. |
| Eg. Silicon Graphics machine, Sun/IBM's SMP | |


## 2.3.3 Approaches to parallel programming
1. Data parallelism: Split data and run a PE on each split using same instruction. Suitable for SIMD.
2. Process parallelism: A process with multiple but distinct activities that can be carried out in separate processors.
3. Farmer-and-worker model: Master-slave model.

## 2.3.4 Levels of parallelism
Based upon the lump of codes that can be parallelized
| Grain Size | Code Item | Parallelized By |
| -- | -- | -- |
| Large | Heavy weight processes | Programmer |
| Medium | Function or Procedure | Programmer |
| Fine | Loop or Instruction Block | Parallelizing compiler |
| Very fine | Instruction | Processor |

## 2.3.5 Laws of caution
1. Speed of computation increases as square root of system cost.
2. Speed of parallel computer increases as log of number of processors.

----
# 2.4 Elements of distributed computing
> Definition: A distributed system is one in which the components located at networked computers communicates and coordinate their actions only by passing of messages.


## 2.4.2 Components of a distributed system

1. Applications
2. Middleware layers: this is what actually enables distributed computing.
4. OS and Hardware
They confirm to a standard at all levels hiding the heterogeneity of the underlying systems and giving coherent and uniform environment.   

## 2.4.3 Architectural styles of distributed computing

Components: A unit of software that encapsulates a function or feature of the system.  
Connectors: A communication mechanism that allows cooperation and coordination among components.  

Classes of architectural styles:
1. Software architectural styles
2. System architectural styles

### 2.4.2.2 Software architectural styles
- Based on the logical arrangement of software components.
- Provides intuitive view of whole system.
- Tells interaction patterns among components.

1. Data centered Architectures: acess to shared data is the core-characteristic.
	1. Repository: Central data structure and collection of independent components.
		1. Databases: Knowledge sources, Blackboard, Control(triggers and procedures).
		2. Blackboard System
2. Data flow architectures: Availability of data controls the computation.
	- Types based upon - how control is exerted, degree of concurrency among components, topology for flow of data
		1. Batch sequential style
		2. Pipe and filter style: connected by FIFO.
3. Virtual machine architectures: Characterized by the presence of an abstract execution environment - virtual machine.
	1. Rule Based Style: Represents abstract execution environment as an inference engine.
		- Eg, Network Intrusion Detectino Systems(NIDS), process control devices.
	2. Interpreter style: Presence of engine that is used to interpret pseudo-program expressed in format acceptable for interpreter.
		- Interpretation constitutes execution of program itself.
	- Decouples the applications with underlying software, hardware.
	- Slowsdown the performance, some underlying features  might not be available.
4. Call & return architectures: Characterized by chain of method calls whose overall execution and composition identify the execution of one or more operation.
	1. Top-Down style: Divide-and-conquer; invoking subprograms and procedures
		- Components: procedures and subprograms
		- Connections: method calls or invocation; encompasses RPC(Remote Procedure Call).
	2. Object Oriented style: OOPs
		- Systems specified in terms of classes and implemented in term of objects.
		- Decoupling of data and operations.
	3. Layered style: different layers - different level of abstraction
		- Specific protocols and interfaces define adjacent layers interactions.
		- Components: Layers
		- Connections: Interfaces and protocols
		- Users typicall interact with highest abstraction layer.
		- Modular design, easy decomposition, encapsulation, lack of extensibility.
		- Eg, International Standards Organization/Open Systems Interconnections(ISO/OSI), TCP/IP stack,etc.
5. Architectural styles based on independent components: system in terms of independent components that have their own life cycles and interacts with each other to perform  activities.
	1. Communicating Processes
		- Components: Independent processes
		- Communication: IPC(Inter Process Communication)
	2. Event Systems
		- Events: published by components and triggers the callbacks set by other components on it.
		- Components: loosely connected, published events, sets callbacks for events.

### 2.4.3.3 System architectural styles
1. Client/Server
	- Communication: using protocol, unidirectional(request/response)
	- Operations: Server(listen, response), Client(request, accept)
	- Client design models:
		1. Thin-client model: load of data processing and transformation put on server. Client mostly just retrieving and returning the data.
		2. Fat-client model: client also does data processing and transformation. Server mostly just concerned with management of access of data.
	- Conceptual Layers/Tiers/Components: Presentation, Application, Data Storage. Based upon this architectures:
		1. Two-tier: Just client and server following fat-client model.
		2. N-tier: client - server/client - server/client - ... - server.
1. Peer-to-peer
	- Component: peers - both client and server.
	- Decentralized, scalable, difficult management.
	- Eg, BitTorrent, Gnutella, Skype, etc.

| Components | Thin-client model | Fat-client model |
|--|--|--|
| Presentation | Client | Client |
| Application | Server | Client |
| Data storage | Server | Server |


----
## 2.4.4 Models for interprocess communication

### 2.4.4.1 Message-based communication
Message: Any discrete amount of information passed from one entity to another.  
1. Message passing: Eg, Message Passing Interface(MPI) and OpenMP.
2. Remote Procedure Call(RPC): triggering the execution code in remote processes. Marshaling of parameteres and values.
3. Distributed objects: Remote invocation of methods exposed by objects. Has complexity of object state management and lifetime. Eg, Common Object Request Broker Architecture(CORBA), Component Object Model(COM, DCOM, COM+), Java Remote Method Invocation (RMI), .NET Remoting.
4. Distributed objects and active agents: Objects with their own control threads, explicit use of messages to trigger exevution of methods, more complex semantics attached to messages.
5. Web Services: RPC concept over HTTP. Simple Object Access Protocol(SOAP), Representational State Transfer(REST).

### 2.4.4.2 Models for message-based communication
1. Point-to-point message model: No central infrastructure for message dispatching.
	1. Direct communication: Processed at the time of reception. Agents needs to be alive while sending messages.
	2. Queue based communication: Agents can be offline when sending messages. 
2. Publish-and-subsribe message model: based on notification
	- Publisher: publishes topic events and allows subsribers to register.
	- Subscriber: subscrive to interested topics and events of publishers
	- Strategies:
		1. Push strategy: Publisher holds responsibility to notify all subscribers.
		2. Pull strategy: Subsriber responsibility to check the registered events and topics publishes.
	- Suitable for one to many communication. Publishers and subscribers need not know each other.
1. Request-reply-message model
	- Focus on dynamic of interactions rather than components involved.
	- Apt for point-to-point interactions


----
# 2.5 Technologies for distributed computing

## 2.5.1 Remote Procedure Call
- Fundamental abstraction enabling execution of procedures on client's requests.
- The requested procedure may be out of process boundary, memory address space, system.
- Synchronous patters - calling process thread remains blocked.
- Marshalling and unmarshalling of parameters and return values done by infrastructure.
- Steps for implementation:
		1. Design and implement server procedures that will be exposed for remote invocation.
		2. Register those procedures on clients where it will be available for use.
		3. Design and implement client code that invoke the remore procedure.
-  Pass by reference will not work, RPC should be able to marshall/unmarshall User Defined types, base for IPC.
- Implementations: RPyC, XML-RPC, JSON-RPC, Thrift, CORBA, DCOM, Java RMI, .NET Remoting, etc.

## 2.5.2 Distributed Object Frameworks
 allows objects to be in heterogeneous network and provides abstraction such that they seem to be in same address space.
- It exposes the instances/objects (unlike methods in RPC). Illusion as if the object is local.
- Interaction pattern:
		1. Server maintains registry of active objects made available to other processes.
		2. Client process, using given addressing scheme, obtains reference to artive remote object.
		3. Client invokes the methods on the active objects by calling them through obtained reference.
- proxy: client component that allows them to invoke remote object components.
- skeleton: server component that executes the remotely invoked methods.
- Object activation: creation of remote object
	1. Server-based activation: The object is instantiated by the server and exposed beyond process boundaries.
	2. Client-based activation: Instantiated when client requests for invocation.
- Object lifetime: lease based, one instance at a time.
- Examples: via base library in C# and JAVA
	- CORBA(Common Object Request Broker Architecture)
		- ORB(Object Request Bus): Central object bus; objects registers with ORB the interface its exposing;
		- Interfaces defined in IDL(Interface Definition Language); IDL specification translated to stub-skeleton pair.
		- Communication: lowest level - IIOP(Interbet Inter-ORB Protocol). Portable Object Adapter(POA) - runtime environment where skeletons are hosted and managed.
	- Distributed Component Object Model(DCOM/COM+)
		- By Microsoft before .NET.
		- COM object: a component that encapsulates a set of coherent and related operations; standardizes binary format.
	- Java Remote Method Invocation(RMI)
		- Enables invocation of methods on objects located at different JVMs.
		- stub-skeleton based concept
		- External component RMI registry locates the remote objects.
		- Only interfaces are published.
	- .NET Remoting
		- Client/Server model.
		- The Remoting infrastructure automatically provides proxy generation information on client application domain.

## 2.5.3 Service-oriented computing
Service: Encapsulates a software component that provides a set of coherent and related functionalities that can be reused and integrated into bigger and more complex applications.  

Characteristics of service:
1. Boundaries are explicit
2. Services are autonomous
3. Services share schema and contracts, not class and interface definitions
4. Services compatibility is determined based on policy: separates structural(contracts and schema) compatibility with semantic compatibility(capabilities and requirements).
### 2.5.3.2 Service oriented architecture (SOA)
SOA is an architectural style supporting service orientation. Organizes software system into a collection of interacting services.  
- Service provider: Provider and maintainer of the service.
	- Registries: can be used to publish services with additional - contract details, fees, nature of service,etc.
- Service consumer
- Service orchestration: When data is aggregated from other services or creation of workflow of services.
- Service choreography: Coordinated interaction of services without single point of control.

Guiding features:
1. Service contracts: adhere to given agreement specified in service description document.
2. Loose Coupling: self contained components, minimal dependencies.
4. Abstraction: completely defined by service contracts and description docs, logic hidden.
5. Reusability: ..., leverage third-party services.
6. Autonomy: Consumer need not know the implementation.
7. Discoverability: supplemental metadata in service documents helps discoverability.
8. Lack of state: More reusability and aggregation.
9. Composability: Services can be composed to build complex service.

### 2.5.3.3 Web services
- Allows interoperability across platforms and programming languages.
- Based upon well known and vendor independent standards HTTP, SOAP, XML, WSDL.
- Enables quick composition of services in distributed environment.
- Provides features required by enterprise business applications.
  
- XML: backbone
- SOAP(Simple Object Access Protocol): low level interaction for web services; XML-based language for exchanging structured information in a platform-independent manner.
- WSDL(Web Service Definition Language): providing metadata
- UDDI(Universal Description Discovery and Integration): discovery services

RESTful system (Representational State Transfer)
- client sends requests over HTTP using standard HTTP methods(PUT,GET,POST,DELETE)
- server issues response that includes representation of the resource.
- lightweight alternative to SOAP.