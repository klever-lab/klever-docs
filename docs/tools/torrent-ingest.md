# Torrent Ingest

## Summary

A service for downloading BitTorrent payloads directly into cloud storage.

## Architecture

BitTorrent client workers execute in cloud compute instances, assembling payloads and writing completed files directly to target paths in the cloud storage wrapper without transferring data through client network connections.

## Core Capabilities

- Initiate and manage BitTorrent transfer tasks.
- Persist completed downloads into designated cloud storage directories.
- Integrate with the cloud storage wrapper for path resolution and quota tracking.
