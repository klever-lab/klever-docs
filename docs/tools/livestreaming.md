# Livestreaming

## Summary

A service for broadcasting media assets stored in cloud storage as live streams via RTMP ingest and HLS delivery.

## Architecture

The service converts stored media files into live video streams. An RTMP endpoint accepts incoming stream data or initiates playback from storage, and a packaging service segments the stream into HLS playlists delivered over HTTPS.

Stream lifecycles are bound to designated storage sources and support programmatic startup and termination.

## Core Capabilities

- Expose RTMP ingest endpoints for designated media sources.
- Package video streams into adaptive HLS segments for multi-client playback.
- Deliver HLS playlists over TLS endpoints.
- Apply token-based or IP-restricted viewing controls.
- Automatic resource teardown upon stream termination.

## Storage Integration

Input media assets are retrieved from the cloud storage wrapper. Manifests and packaged HLS segments can persist back to object storage or remain in transient cache during broadcast.
