
Server consodilation: Technique for aggregating multiple services and applications originally deployed on different servers on one physical server.

Three major components of virtualized environment:
1. Host
2. Vritualization layer
3. Guest

----
# Characteristics of virtualized environments
1. Increased Security
	1. Control and filter the activity of the guest.
	2. Can hide resources and sensitive informations.
2. Managed Execution
	1. Sharing: Full utilization.
	2. Aggregation: Group of hosts represented as single host. eg. cluster manager.
	3. Emulation: A completely different environment can be emulated.
	4. Isolation: No interference. Separation of host and the guest.
	5. Performance tuning: By controlling the resources provided.
	6. Virtual machine migration: Stop the execution; move image to another machine; resume the execution.
3. Portability

----
# Taxonomy of virtualization techniques
Virtualization mainly used to emulate
1. Execution environments
	1. Process-level
	2. System-level
2. Storage
3. Networks

## Execution virtualization
Aims to emulate execution environment. Execution of programs(OS, applications, any program).  
### Machine Reference Model
1. Applications
2. API: Application Programming Interface
3. Libraries
4. ABI: Application Binary Interface
5. OS
6. ISA: Instruction Set Architecture
7. Hardware
### Hardware-level virtualization/System virtualization
Exposes ISA to virtual machines.

#### Hypervisors
Recreates the hardware environment
1. **Type-I/Native VM**: Runs directly on top of hardware; Interacts directly with ISA interface exposed by hardware.
2. **Type-II/Hosted VM**: RUns on top of OS; Interacts through ABI.


##### Organization of VM Managers
1. Dispatcher
	- Entry point.
	- Reroutes instructions to one of two modules.
1. Allocator
	- Decides system resources to be provided to VM.
	- Invoked whenever instruction issued demands change in machine resources.
1. Interpreter
	- Consists of interpreter routines: executed whenever privileged instructions are executed.

##### VMM Criteria to efficiently support virtualization
1. Equivalence:  Execution in VM should exhibit same behaviour as execution on physical host.
2. Resource Control: Host should be in complete control.
3. Efficienfy: Statistically dominant fraction of the machine isntructions should be executed withtou intervention from VM managers.

##### Properties of Hardware instructions to efficient support virtualization.
>For any conventional third-generation computer, a VMM may be constructed if the set of sensitive instructions for that computer is the subset of the set of privileged instructions.

>A conventional third-generation computer is recursively virtualizable if:
>- If it is virtualizable.
>- A VMM without any timing dependencies can be constructed for it.

> A hybrid VMM may be constructed for any conventional third-generation machine in which the set of user-sensitive instructions is a subset of the set of privileged instructions.


#### Hardware Virutalization techniques
1. Hardware assisted virtualization: When hardware provides architectural support.
2. Full virtualization: Able to run program, that can access hardware too, without any modification on VMM as if it was run on raw hardware.
3. Paravirtualization
4. Partial virtualization

#### OS level virtualization
- Separated execution environments for applications.
- There is no VMM or hypervisor, virtualization done within a single OS.
- OS kernel allows for multiple isolated user space instances.

### Programming language level virtualization
- Usually a VMM executing byte code(compilation output) of a program.
- Gives program portability.
- JIT(Just In Time): Byte code compiled to underlying machine code upon method call.
- CLI(Common Language Infrastructure): stack based - operations performed based on execution stack. (another option is register-based)

### Application level virtualization
Strategies:
1. Interpretation: Every source instruction is interpreted and emulate. Low startup cost but huge running cost.
2. Binary translation: Every source code translated to native instructions with equivalent functions.
Examples: Wine, WABI, Crossover, etc.

## Other types of virtualization

### Storage virtualization
Decoupling physical organization of hardware from logical representation.  
Example: SAN(Storage Area Network).

### Network virtualization
- External Network virtualization: Aggregate multiple networks into a single network.
- Internal network virtualization: Network like functionality to OS partition.

### Desktop virtualization
Abstracts desktop environment. Access desktop remotely using client-server approach.

### Application server virtualization
some shit

----
# Virtualization and Cloud computing
> Server consolidation: Aggregating different servers into one server so that the resources can be used efficiently.

> VM migration: Moving an instance of virtual machine from one VMM to another.

> Live migration: Temporarily stopping the execution and migration of VM instance, and resuming it again.

## Pros and Cons of virtualization
