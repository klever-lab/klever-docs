# Ephemeral VM

## Summary

A service for provisioning transient virtual machines with configurable access protocols and automated lifecycle management.

## Initial Direction

Instances support headless environments (SSH) or graphical environments (remote desktop). Resource configurations are selectable to match workload requirements, including compute-optimized, memory-optimized, or cost-optimized instance classes exposed by supported cloud providers.

## Core Capabilities

- Provision transient virtual machines.
- Select headless or graphical display environments.
- Configure CPU, memory, and accelerator allocations.
- Mount target paths from the cloud storage wrapper.
- Connect via SSH, WebRTC, or graphical remote desktop protocols.
- Automated instance teardown upon session completion.

## Connection Architecture

Connection protocols are integrated as core interfaces:

- **Headless mode:** Direct SSH access for command-line execution.
- **Graphical mode:** Remote desktop sessions for browser-based or client-based GUI interaction.

The baseline lifecycle covers provisioning, connection handshake, execution, and termination.

## Storage Integration

The VM service mounts directories directly from the cloud storage wrapper via FUSE or network block devices, enabling workloads to operate on shared storage objects with local filesystem semantics.

## Provider Configuration and Provisioning Latency

The service exposes underlying provider instance specifications alongside pre-configured resource profiles.

To minimize instance provisioning delays, an on-demand pool mode maintains pre-warmed instances, returning connection credentials immediately upon request and absorbing underlying cloud initialization overhead.
