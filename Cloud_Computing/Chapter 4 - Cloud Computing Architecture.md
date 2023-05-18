> CC is a utility-oriented and internet centric way of delivering IT services on demand.

## Cloud Reference Model
![Cloud Reference Model](../Images/Cloud%20Computing/Cloud_Reference_Model.png)


## Common cloud service models
1. SaaS
	- Applications accessible anytime anywhere via  web services.
	- Characteristics:
		1. Application access
		2. centrally manages
		3. one-to-many: naturally multitenant
		4. delivered on contract
	- Product Type: Web applications and services.
	- Elastic scaling is automatic.
	- e.g., salesforce.com, google apps, QuickBooks,etc
	- Concerns:
		- Data residing in cloud - legality.
		- users do not own the solution.
		- SaaS is multi-tenant.
	- Mashups: collection of services joined to create an overall solution.
	- e.g., CRM, ERP, SalesForce.com, google sheets, social networking sites, ...
	- SaaS 2.0: focus on rapid achievement of business objectives; no new tech introduced.
2. PaaS
	1. Characteristics:
		1. Runtime framework
		2. abstraction
		3. automation
		4. cloud services
	2. Category:
		1. PaaS-I
			- Web hosted runtime environment for development and deployment of application.
			- e.g., Forece.com
		2. PaaS-II
			- Runtime environment for scaling web applications.
			- e.g., Google AppEngine, Heroku, AppScale,...
		3. PaaS-III
			- Middleware and programming model for developing distributed applications.
			- e.g., Microsoft Azure, Aneka, etc
	- All categories can provide either just Middleware or Middleware + Infrastructure.
	- Provides development and deployment platform for applications.
	- Includes hardwares(servers and disks), OS, tools, administrative tools.
	- Product type: Programming APIs, frameworks, deployment systems.
	- **Vendor lock-in:** The product might becomes too much dependent on specific provider environment, making it difficult to change vendor.
	- Elastic scaling is done using APIs.
	- e.g., windows Azure, Google App Engine, Aneka,...
3. IaaS/HaaS
	1. Types:
		1. IaaS: Provides both management layer and physical infrastructure.
		2. IssS (M): Provides only management layer.
	2. Layers:
		1. User interface
			- Web Services, REST API, Portals
		2. Software management infrastructure: (Infrastructure or Storage or Network management)
			- VM management: Pricing/Billing, scheduling, monitoring, reservation,...
		3. Physical infrastructure
			- Datacenter, clusters, virtual resources from external IaaS provider(if present),...
	- Provides virtualized hardwares.
	- Workload partitioning, application isolation, sandboxing, hardware tuning possible.
	- Includes machines, storage, network resources.
	- Product Type: VMM infrastructure, Storage management, Network management.
	- Elastic scaling is done using APIs.
	- e.g., Amazon EC2 and S3, GoGrid,...

![XaaS](../Images/Cloud%20Computing/XaaS.png)

----
# Types of Clouds

## Cloud deployment models
1. Private cloud
	- owned by specific entity
	- normally used by just the entitiy and its customers, partners.
	- The underlying technology may reside on or off - site.
	- Its costly. Capital investment, maintenance cost, staffs, etc.
1. Public cloud
	- Available for use for general public.
	- Offered by some other organization.
	- Its cheap. Least capital investment, no maintenance cost pay-as-you-use model.
	- Trust issues.
1. Community cloud
	- shared by multiple organizations.
2. Hybrid cloud
	- mixture of above clouds.

## Open challenges
1. Cloud interoperability and Standards
2. Security, Trust and Privacy
3. Scalability and fault tolerance