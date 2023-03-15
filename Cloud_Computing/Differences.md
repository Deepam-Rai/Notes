----
## Cluster computing vs Grid computing
| Aspect | Cluster Computing | Grid Computing|
|---|---|---|
| Architecture: | Connectes multiple computers in a network to work together as a single system. | Connects computers in different locations to work on a common goal. |
|Resource sharing: | Typically shared within an organization or group. | Can be shared across organizations and groups. |
|Management: | Centrally by single entity. | Decentralized manner by multiple entities. |
|Workload: | Typically suitable for high performance tasks. | Typically suitable for diverse workloads - data-intensive, distributed computing. |


----
## Sequential vs Parallel Processing
| Aspect | Sequential processing | Parallel processing |
|--|--|--|
|Definition: | Executes single instruction at a time. | Executes multiple instructions at a time. |
| Speed: | Slow for multiple parallelizable instructions. | Faster for parallelizable instructions. |
|Hardware: | Can run on single core processor. | Requires multi-core processors. |
|Resource utilization: | Less effectively on multi-core systems. | More effectively on multi-core systems. |
|Complexity: | Comparatively less. | Comparatively more. |


----
## Parallel Computing vs Distributed Computing
| | Parallel | Distributed |
|--|--|--|
| Definition: | Process data using multiple processors within a single computer system. | Process data using multiple computers over the network. |
|Coupling: | Tightly coupled. | Loosely Coupled |
|Components: | Computation on homogeneous components. | Computation on heterogeneous components. |
|Resource sharing: | Within a single system. | Among computers in the network. |
|Scalability: | Limited. | More scalable. |
|Fault tolerant: | Less. | More. Has independent failures. |



----
## Decentralized vs Distributed Computing
| Aspect | Decentralized Computing | Distributed Computing |
|---|---|---|
|Control: | No single pointn of control. | Can have single point of control. |
|Architecture: | P2P | Client-Server or P2P |
| Scalability: | More scalable. | Depends upon control architecture set up. |
| Fault tolerance: | More fault tolerant - has independent failures. | Depends upon architecture. Client-server means SPOF exists else has independent failures. |


----
## Distributed Computing vs Grid Computing
| Aspect | Distributed Computing | Grid Computing |
|--|--|--|
| Architecture: | Multiple computers connected over a network. | Multiple geographically distributed resources connected over a network. |
|Scope: | Mostly used within an organization. | Mostly used by multiple organizations. |
|Management: | Centralized with single point of control. | Decentralized with multiple points of control. |
|Scalability: | Depends upon the management architecture. | Highly scalable. |


----
## Simulation vs Emulation
| Aspect | Simulation | Emulation |
|--|--|--|
| Purpose: | Used to study or predict the behaviour of the system under different conditions. | Used to test or replicate the behaviour of the system in the controlled environment. |
| Level of abstraction: | Typically implements high level abstractions. Only as much as required for modelling. | Typically implements low-level abstractions. |
|Accuracy: | Depends upon quality of model/abstraction used. | Typically high as asbtraction is of low level. |
| Resources: | Needs comparatively less. | Needs comparatively more. |
| Use Case: | To test the interaction of a model with environment. | Testing how model interacts with environment. |


----
## Paravirtualization vs Partial Virtualization

| | Para virtualization | Partial virtualization |
|-|---|---|
|Awareness: | Guest is aware of virtualization. | Guest is not aware of virtualization. |
|Modification: | Requires guest modification. | Doesnt require guest modification. |
|Access: | Guests can access VMM using predefined hypercalls. | Guests cannot access VMM. |
|Proprietary guests: | Only the guest program ownser themselves can provide support for paravirtualiation. | Proprietary or not it doesnt matter. |

----
