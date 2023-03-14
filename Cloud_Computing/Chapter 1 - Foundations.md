
# Introduction
Utility computing
Cloud computing

> Vision of cloud computing: IT services are traded as utilities in open market without technological or legal barriers.

----
# Cloud computing at a glance
## Defining a cloud
> Cloud computing is a model for enabling ubiquitous, convenient, on-demand network acess to a shared pool of configurable computing resources(e.g., networks, servers, storage, applications and services) that can be rapidly provisioned and released with minimal management effort or service provider interaction.

- Has utility oriented approach.
- Uses pay-per-use strategy.

#### OSSM
1. On Demand
2. Self Service
3. Scalable
4. Measured

Reese criteria for service to be of cloud computing style:
1. Accssible via non-proprietary web browsers or web API.
2. Zero capital expenditure for getting started.
3. Pay-per-use model.


## Advantages
1. Offload some work-loads to cloud based systems.
2. No excessive up-front cost - helps startups to translate their ideas to business results.
3. Valid when needed large one-time use computing power.
4. System developers can concentrate on the business logic rather than managing complexity of infrastructure and scalability.
5. Accessible from everywhere, anytime and any device.
6. Reduces operational cost - turns to utility cost.
7. Increased agility and reduced need for capacity planning.

## Cloud computing deployment models
1. Public
	- Third party, multitenant cloud infrastructure and services. Subscription basis.
2. Private/Enterprise
	- Public cloud model but within own domain for internal and/or partner use.
3. Hybrid
	- Mixed of public and private. Leasing public cloud when private cloud is insufficient.

## Cloud computing reference model(XaaS)
1. Saas: Software-as-a-Service
	- Applications and services.
2. PaaS: Platform-as-a-Service
	- Scalable and elastic runtime environments.
3. IaaS: Infrastructure-as-a-Service
	- Hardware, storage and networking.
![XaaS](../Images/Cloud%20Computing/XaaS.png)


## Challenges
1. Finding the optimum lease policy - by both provider and consumer.
2. Security: Confidentiality, secrecy and protection of data. Trust on provider.
3. Legality: RIghts that third parties(including government) have to data.

----
# Historical developments
Core technologies for realization of cloud computing
1. Distributed systems
2. Virtualizations
3. Web 2.0
4. Service orientation
5. Utility computing
![XaaS](../Images/Cloud%20Computing/Cloud%20Computing%20History.png)

## Distributed systems
>Clouds are basically large distributed computing facilities that make their services available to third parties on demand.

> **Distributed system** is collection of independent computers that appears to its users as a single system.

Properties of distributed systems:
1. heterogeneity
2. openness
3. transparency
4. continuous availability
5. independent failures
6. scalability
7. concurrency

### Milestones that have led to cloud computing
1. Mainframe compuing
	- large computing facilities leveraging multiple processing units.
	- batch processing.
	- cannot be considered distributed systems.
1. Cluster computing
	- Used comoddity hardware.
	- contribution in evolution of tools and frameworks for distributed computing.
	- scalable.
1. Grid computing
	- aggregation of heterogeneous computing nodes.

## Virtualization
- Confers degree of customization and control with minor impact on performance.
- Creates virtual environments.
- Isolation and executing of applications with finer control on resources they access.

## Web 2.0
>It is the primary interface through which cloud computing delivers its services.
- Brings interactivity and flexibility.
- Extremely dynamic.
- Loose coupling.

## Service oriented computing
> It is the core reference model for cloud computing systems.  

Supports
1. rapid
2. low-cost
3. flexible
4. interoperable
5. evolvable
applications and systems.  
>Service: An abstraction representing a self-describing and platform-agnostic component that can perform any function - from simple function to complex business process.

Service should be;
1. loosely coupled
2. programming lanuage independent
3. reusable
4. location transparent

Services are composed and aggregated into **Service-oriented architecture(SOA)**.  

> **Quality of Service(QoS):** identifies a set of functional and non-functional attributes that can be used to evaluate the behaviour of service from different perspectives.

> Saas: Software-as-a-Service

## Utility-oriented computing
> It is a vision of computing that defines a service-provisioning model for compute resources such as storage, compute power, applications and infrastructure that are packaged and offered on a pay-per-use basis.


----
# Building cloud computing environments
Encompasses both development of applications and systems that leverage cloud computing solutions and creation of frameworks, platforms, infrastructure delivering cloud computing solutions.

## Application development
- dynamically scalable on demand.
- e.g., Web Applications, enterprise applications, resource-intensive applications.

## Infrastructure and system development
Needs to know the core technologies:
1. Distributed systems
2. Virtualization
3. service orientation
4. web 2.0

## Computing platforms and technologies

### Amazon Web Services (AWS)
> Comprehensive cloud IaaS service ranging from virtual compute, storage and networking to complete computing stacks.
- Elastic Compute Cloud (EC2)
	- Customizable virtual hardware including GPU and cluster instances.
- Simple Storage Service (S3)
	- persistent storage on demand
- AWS console
	- comprehensive web-portal for accessing AWS services
- Web services API
	- available for several programming languages
- Also supports: networking, caching, DNS, databases(relational an not), etc.

### Google AppEngine
> Scalable runtime environment mostly devoted to executing web applications.
- Offers: in-memory caching, scalable data store, job queues, messaging, cron tasks.
- Appengine SDK
	- replicates production time environment and help test and profile applications.

### Microsoft Azure
> Its cloud operating system and a platform for developing applications in the cloud.
- scalable runtime environment for web applications and distributed applications.
- Roles:
	- Web role: hosts applications
	- Worker role: workload processing
	- Virtual machine role: completely customizable environment
- Also supports: storage(relational data and blobs), networking, caching, content delivery, etc.

### Hadoop
> Apache Hadoop is an open-source framework that is an implementation of Google's MapReduce and is suitable for processing large data sets on commodity hardware.
- map: transforms and synthesizes the input data
- reduce: aggregates the map outputs.
- map-reduce can be pipelined.

### Force.com and Salesforce.com
> Force.com: is a cloud computing platform for developing social enterprise applications.  
> SalesForce.com:  is SaaS build on top of Force.com and provides solution for CRM(Customer Relationship Management).
- Ready to use blocks of components.
- Complete customization of application.
- Completely hosted on cloud.

### Manjrasoft Aneka
> Cloud application platform for rapid creation of scalable applications and their deployment on various types of clouds in seamless and elastic manner.
- Provides abstractions to choose from: distributed threads, tasks, map-reduce.
- Service manages most of runtime activities: scheduling, execution, accounting, billing, storage and QoS.

----
# Footnotes
> **dot-com bubbles:** Its a phenomenon that started in 1990's and reached its apex in 2000, where a large number of companies that based their companies on online services and e-commerce started expanding quickly but later were not able to sustain it, resulting in their bankruptcy.  
> They either couldnt gather revenue enough to cover their expenses or they never reached the critical customer mass to sustain their business.

