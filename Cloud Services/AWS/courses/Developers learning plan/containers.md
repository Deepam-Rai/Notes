>**Container:** is a standardized unit of software.

- Form of virtualization implemented at OS level.
- Lightweight, standalone packages with all runtime dependencies.
- Useful for microservice architecture.

# Docker
- lightweight container virtualization platform.
- **portable** runtime application environment.

**Dockerfile**: Text document containing series of instructions on building an image.
- Each line creates a new layer.
- **Multi-stage**: Break build into stages ( each `FROM` starts a new stage) where its possible to selective copy artifacts from one stage to another.

**Container Image**: Read-only, portable, immutable template.
- A blueprint for a Container.
- Can be stored in a registry.

**Container:** An instance of Container Image.


# Container Security

Risks:
- Segregation(Confidentiality):
	- Container to Container
	- Process to Process
	- Container to Outside
- Access
	- Who/When/Where
	- Logging
	- Start/Stop
	- Content
- Resource Usage

Namespaces:
- PID-Namespace
- CPU/Memory-Namespace (cgroup)
- Network-Namespace
- User-Namespace
- FS/Mount-Namespace
- IPC-Namespace
- UTS-Namespace

Characteristics:
- Namespaces are of tree structure starting from`root`. Parent namespace can access child namespace. Different branches cannot access each other.