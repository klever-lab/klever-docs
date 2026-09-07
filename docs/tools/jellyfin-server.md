# Jellyfin Server

## Summary

A service for deploying an ephemeral Jellyfin media server instance connected to directories in the cloud storage wrapper.

## Architecture

Deployment is automated: selecting source media directories provisions and configures an instance without requiring manual server administration.

Instances support transient lifecycles, enabling on-demand provisioning and teardown per viewing session.

## Core Capabilities

- Automated deployment of pre-configured Jellyfin instances.
- Mount media libraries from selected cloud storage wrapper directories.
- Expose web interfaces over TLS via automated DNS or encrypted tunnels.
- Enforce authenticated user access controls.
- Teardown and resource release upon session completion.

## Storage Integration

Media directories mount from the shared cloud storage wrapper. Transcoding scratch space streams temporary segments to storage or transient disks rather than requiring persistent local instance storage.
