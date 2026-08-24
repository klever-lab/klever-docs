# Jellyfin Server

## Summary

A tool for deploying a Jellyfin media server in the cloud, pointed at the user's storage.

## Initial Direction

Deploys should be simple: pick a library, pick storage directories, and get a working media server. No manual config, no fiddling with the Jellyfin admin panel.

The server should be ephemeral enough to spin up for a watch session and tear down when done.

## Core Capabilities

- Deploy a Jellyfin server with sensible defaults.
- Point media libraries at selected storage directories.
- Expose the server over HTTPS with a real domain or tunnel.
- Restrict access to the user's own accounts.
- Tear the server down when finished.

## Storage Integration

Libraries mount directly from the shared storage layer via the cloud storage wrapper. Transcoding should write back into storage when it needs disk space, rather than requiring a large local disk on the VM.

## Roadmap Position

Planned as part of the later egress batch, after the storage wrapper exists.
