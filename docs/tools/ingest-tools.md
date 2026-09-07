# Ingest Tools

## Summary

Ingest tools transfer external data directly into the shared cloud storage layer.

## Component Services

- Torrent ingest.
- Usenet ingest.
- yt-dlp ingest.

## Architecture and Execution Model

Ingest tasks execute in cloud compute environments, writing outputs directly to target directories in the cloud storage wrapper without transferring data through client network connections.

Each ingest protocol is managed by a distinct service to handle differences in network protocols, concurrency limits, and state tracking.

Common architectural components include:

- Shared destination path mapping backed by the cloud storage wrapper.
- Future network controls for egress IP selection, VPN tunneling, and forward proxy routing.

Network routing controls (VPN, static IP egress, forward proxies) are deferred to subsequent releases.
