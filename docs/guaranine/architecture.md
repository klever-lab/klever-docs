# Architecture

## Overview

Cluster nodes join a shared Tailscale mesh network. A Python daemon runs on each node listening on port 48584 to receive and execute platform instructions for provisioning instances, executing serverless functions, and managing storage operations.

## Node Execution Model

1. The node connects to the Tailscale mesh network.
2. The daemon listens on TCP port 48584.
3. Inbound commands arriving on that port are received and executed locally.

Nodes maintain uniform configuration: mesh network membership, an active port 48584 listener, and a standardized execution interface.

## Relationship to K-Suite

Guaranine is an infrastructure platform within the Klever Lab ecosystem, developed independently of K-Suite. While K-Suite provides application-level tools over commercial cloud providers, Guaranine provides self-hosted compute and storage infrastructure on local hardware.
