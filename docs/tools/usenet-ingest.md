# Usenet Ingest

## Summary

A service for downloading NNTP/Usenet binaries directly into cloud storage.

## Architecture

NNTP download workers execute in cloud compute instances, verifying and assembling binaries before writing completed files directly to the cloud storage wrapper without transferring data through client network connections.

## Core Capabilities

- Initiate and monitor NNTP/NZB download tasks.
- Verify archive integrity and assemble multi-part binaries.
- Persist completed files into designated cloud storage directories.
- Integrate with the cloud storage wrapper for path resolution and quota tracking.
