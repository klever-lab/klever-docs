# Server Provisioning

## Instance Lifecycle

Upon receiving a provision command, a node creates an LXC container with the specified hardware resources. The instance:

- Joins the Tailscale mesh network.
- Registers its hostname.

Upon container destruction, the instance is removed from the Tailscale network.

## Workload Scheduling

Workload placement accounts for resource requirements: containers are scheduled across available nodes based on CPU, memory, and storage limits.

Provisioning parameters specify the container hostname and resource allocations defined by the assigned workload.
