# Guaranine

## Summary

Guaranine is a self-hosted cloud platform written in Python that runs on dedicated hardware to provide virtual machines, containers, storage, and serverless functions.

It also functions as a host configuration management agent, maintaining host OS configuration and Tailscale mesh network connectivity.

## Core Capabilities

- **Provisioning** — provisions LXC instances with specified resource allocations and schedules workloads based on node capacity.
- **Serverless Functions** — executes event-driven compute units on local hardware.
- **Storage** — provides persistent file and object storage across cluster nodes.
- **Config Management** — applies declarative NixOS configurations from [klever-lab/nixos](https://github.com/klever-lab/nixos) and maintains active Tailscale VPN connections.

## Status

Early development. See [Architecture](architecture.md) and [Server Provisioning](provisioning.md) for architectural and scheduling specifications.
