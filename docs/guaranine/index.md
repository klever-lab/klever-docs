# Guaranine

`named after the failed homelab with my boy froggy.`

## Summary

Guaranine is a cloud platform, not a homelab. It runs on top of your own hardware and provides typical cloud features: virtual machines, containers, storage, and serverless functions. Simple, written in Python, and it is my AWS at home.

It also acts as a configuration management agent for the machine it runs on — keeping the host OS configured and the VPN connection alive.

## What It Does

- **Provisioning** — spins up servers (LXC instances) with specified resources and distributes workloads based on resource requirements.
- **Serverless Functions** — run small units of code on your own hardware.
- **Storage** — a place to put things, like any other cloud.
- **Config Management** — applies the NixOS config from [klever-lab/nixos](https://github.com/klever-lab/nixos) and maintains the Tailscale VPN connection.

## Status

Early stage. The concept below is the plan; see the Architecture and Provisioning pages for how the pieces fit together.
