----
History:  
![History](../../Images/Cloud%20Computing/Cloud%20Computing%20History.png)


Business drivers for adopting cloud computing/
Advantages of cloud computing:
1. Offload work-loads to cloud based systems.
2. No excessive up-front cost - helps startups to translate their ideas to business results.
3. Valid when needed large one-time use computing power.
4. System developers can concentrate on the business logic rather than managing complexity of infrastructure and scalability.
5. Accessible from everywhere, anytime and any device.
6. Reduces operational cost - turns to utility cost.
7. Increased agility and reduced need for capacity planning.


> **Main principle:** Offering computing, storage and software on demand.

> Vision of cloud computing: IT services are traded as utilities in open market without technological or legal barriers.

Characteristics of Cloud:
1. O: On demand
2. S: Scalable
3. S: Self Service
4. M: Measured

Desired features
1. Self-service
2. On demand
3. Metering and Billing
4. Elasticity
5. Customization
6. Security
7. Virtualization support
8. Interface to other clouds
9. dynamic resource allocation
10. high availability and data recovery
11. Automatic scaling and load balancing
12. Service level agreement (commitment to delivery)

----
## Virtualizaton
Backbone of Cloud computing.  

Detailed notes [here](../Chapter%203%20-%20Virtualization.md).  

Three major components of virtualized environment:
1. Host
2. Vritualization layer
3. Guest

Advantages
1. Sharing and efficient use of resources.
2. Portability and self-containment - enabling migration - moving instances from one VMM to another.
3. Recovery: Can save the instances states backups.
4. Isolation: sandbox environments.
5. Encapsulation
6. Hardware Independence
7. Managed execution and isolation - secure and controllable environments.
8. Easy allocation and partitioning of resources.
9. Fine tuning resources to meet effective quality of service.
10. Reducing cost of maintenance.

Disadvantages:
1. Decrease in performance because of virtualization layer.
2. Some features cannot be exposed by abstraction layer thus becoming inaccessible.
3. Implications for security -phishing.
4. Not all applications are well suited.
5. Added overhead makes performance slower.

#### Hypervisors
>They are VMM(Virtual Machine Manager) that creates, monitors and manages virtual environments.

1. **Type-I/Native VM**: Runs directly on top of hardware; Interacts directly with ISA interface exposed by hardware.
2. **Type-II/Hosted VM**: RUns on top of OS; Interacts through ABI.

#### Terms
> Server consolidation: Aggregating different servers into one server so that the resources can be used efficiently.

> VM migration: Moving an instance of virtual machine from one VMM to another.

> Live migration: Temporarily stopping the execution and migration of VM instance, and resuming it again.


----
## Recent trends in Computing
1. Grid computing
	1. Collection of computer resources from multiple locations to reach a common goal. ![grid computing](../../Images/Cloud%20Computing/grid_computing.png)
	2. Can be thought of as a distributed system with non-interactive workloads that involve a large number of files.
2. Cluster computing
	1. A loosely or tightly connected computers that work together so that, in many respects, they can be viewed as a single system.
	2. Unlike grid computers, computer clusters have each node set to perform same task. ![Cluster Computing](../../Images/Cloud%20Computing/cluster_computing.png)
3. Distributed computing
	1. Distributed systems: is a software system in which the components located at the network nodes communicate and coordinate their actions by passing messages.
	2. Distributed computing: where the computation can be broken down into units and executed on heterogeneous elements concurrently.
4. Utility computing
	1. It is a service provisioning model in which computing resources and infrastructure is availed to customers as needed and charged for specific usage rather than a flat rate.
5. Cloud computing
	1. It is the practice of using a nework of remote servers hosted to store, manage and process data.

Differences between computing models: [Differences](../Differences.md).

----
## XaaS
![XaaS](../../Images/Cloud%20Computing/XaaS.png)

Examples:
- SaaS: salesforce.com, google docs, facebook, instagram, reddit, stackoverflow, etc.
- PaaS: Heroku, Windows Azure, Google app engine, force.com, etc.
- IaaS: AWS, IBMSmartCloud, Eucylaptus, Windows Server Hyper V, etc.

More detail [here](../Chapter%204%20-%20Cloud%20Computing%20Architecture.md).  

----
## Hosting Models
1. Public
	1. 3rd party, multi-tenant, available on subscription basis.
2. Private
	1. An infrastructure within company's own data center.
3. Hybrid
	1. Leasing public cloud when private is not enough.

----
## Challenges
1. Security, privacy and trust.
2. Data lock-in and Standardization
	1. Data lock-in??
	2. Vendor lock-in: Once we start using services of a vendor our system are designed according to their API which is mostly proprietary. This causes difficulty in changing vendor.
3. Availability, Fault tolerance and disaster recovery
4. Resource management and energy-efficiency


