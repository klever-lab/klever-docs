# Server Provisioning

## Provisioning A Server

When instructed to provision, a machine creates an LXC instance with the specified resources. That instance:

- Gets added to the Tailscale network.
- Has its hostname saved.

If the server is ever destroyed, it is also removed from the Tailscale network.

## Workload Distribution

Provisioning takes resource requirements into account — workloads are distributed across machines based on what each workload needs and what each node has available.

Spin-up options include the hostname; resource sizing comes from the workload being placed.
