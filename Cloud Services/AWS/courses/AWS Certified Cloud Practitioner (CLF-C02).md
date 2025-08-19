
Exam prep materials:
- https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf
- https://aws.amazon.com/certification/certified-cloud-practitioner/
- https://d1.awsstatic.com/whitepapers/aws-overview.pdf
- https://docs.aws.amazon.com/whitepapers/latest/how-aws-pricing-works/abstract-and-introduction.html
- https://aws.amazon.com/premiumsupport/plans/
- https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Sample-Questions.pdf


----

# Cloud Concepts

>**Cloud computing:** is the on-demand delivery of IT resources through a cloud services platform via the internet with pay-as-you-go pricing.

## Define benefits of the cloud

Advantages of cloud computing:
1. **Trade fixed expense for variable expense**: Instead of heavy upfront expense pay only when you use it.
2. **Benefits from massive economies of scale**: AWS can achieve higher economies of scale which leads to lower variable cost to its users, which a single user typically cannot get on its own..
3. **Stop guessing capacity**: No more expensive idle resources or limitation by resources capacity.
4. **Increase speed and agility**: New IT resources are only clicks away which leads to faster experimentation and developments.
5. **Stop paying for running and maintaining data centers**: Focus on business.
6. **Go global in minutes**: Advantage of global infrastructure of AWS.

### Deployment models
1. On-premise
2. Hybrid
3. Cloud

## Identify design principles of the AWS cloud

### AWS well architected framework

6 pillars:
1. **Operational excellence**: Focus on running and monitoring systems to deliver business value and continually improve processes and procedures.
2. **Security**: Protect information, system and assets while delivering business value through risk assessments and mitigation strategies.
3. **Reliability**: Ensure a workload performs its intended function correctly and consistently when it's expected to.
4. **Performance efficiency**: Use computing resources efficiently to meet requirements and maintain that efficiency as demand changes and technologies evolve. 
5. **Cost optimization**: Run systems to deliver business value at the lowest price point.
6. **Sustainability**: Minimize the environmental impacts of running cloud workloads.

## Understand benefits of and strategies for migration to cloud

### Cloud adoption framework
6 core perspectives:
1. **Business**: Ensure that IT aligns with business needs and IT investments links to key business results. Roles: business managers, finance managers, budget owners, strategy stakeholders, etc.
2. **People**: Support development of organization wide change management strategy for successful cloud adoption. Roles: HR, staffing, people managers, etc.
3. **Governance**: Focuses on skills and processes to align IT strategy with business strategy. Roles: CIO, program managers, enterprise architects, business analysts, portfolio managers, etc.
4. **Platform**: Principles and patterns for implementing new solutions on the cloud. Roles: CTO, IT managers, solution architects, etc.
5. **Security**: Security objectives for visibility, auditability, control and flexibility. Roles: CISO, IT security managers, IT security analysts, etc.
6. **Operation**: Enable, run, use, operate and recover IT workloads to the level agreed with business stakeholders. Roles: IT operations managers, IT support managers.

### Cloud migration strategy
6 strategies:
1. **Rehosting**: Lift and shift.
2. **Replatformaing:** Lift, tinker and shift. Tinker application a little to realize tangible benefit of cloud.
3. **Refactoring/re-architecting**: Re-architect and develop application using cloud native features.
4. **Repurchasing**: Moving from traditional license to software-as-a-service model.
5. **Retaining**: Keeping business critical applications at the source environment.
6. **Retiring**: Removing applications that are no longer needed.

### Resources to support the cloud migration journey

#### AWS Snow family
> Collection of physical devices that helps to physically transport data in and out of AWS.

1. **Snowcone**: 2 CPUs, 4GiB memory, 14TB storage.
2. **Snowball**:
	1. **Storage optimized**: 80 TB HDD, 1 TB SATA SDD for block volumes. 40 vCPUs, 80 GiB memory, supports sbe1( ~C5) instances
	2. **Compute optimized**: 80 TB HDD, 28 TB NVMe SSD for EBS compatible block volumes. 104 vCPUs, 416 GiB, optional NVIDIA Tesla V100 GPU, runs sbe-c and sbe-g equivalent to C5, M5a, G3 and P3 instances.
3. **Snowmobile**: Upto 100 petabytes.


## Understanding concepts of cloud economics

### Aspects of cloud economics
- https://d1.awsstatic.com/whitepapers/introduction-to-aws-cloud-economics-final.pdf
AWS economics:
- Global operation
- High availability
- Low cost due to high volume
- Only pay for what you use
- Economies of scale
- Financial flexibility

#### Pricing models
1. **On demand**: pay for compute capacity by hour.
2. **Reserved**: Reserved capacity, less cost.
3. **Spot instances**: bid for unused EC2 instances for Spot Price: set by Amazon EC2 and fluctuates.

### Cost savings of moving to the cloud
