# Architecture

## Overview

Every machine in the cluster joins a Tailscale network. A Python server runs on each machine listening on port 48584 and can receive and execute commands. Those commands relate to the platform features: provisioning servers, running serverless functions, storage.

The machines are the hardware; Guaranine is the layer that turns them into a cloud. It is not the homelab itself — it is what runs on top of one.

## Command Flow

1. Each machine establishes a connection to the Tailscale network.
2. A Python server listens on port 48584.
3. Commands arrive over that port and get executed locally by that server.

This keeps every node identical: same VPN membership, same listener, same command surface. The network is the fabric; the node agent is the executor.

## Relationship to K-Suite

Guaranine is part of the Klever Lab ecosystem but is its own project, separate from K-Suite. Where K-Suite is user-facing tools built around cloud providers, Guaranine is infrastructure — the platform those tools (or anything else) could run on top of.
