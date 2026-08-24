# Livestreaming

## Summary

A tool for serving media files as livestreams, exposing RTMP links that push to an HLS stream.

## Initial Direction

The tool should turn files already in storage into livestreamable content. An RTMP endpoint ingests the stream and the tool publishes HLS output that anyone with the link can watch.

Streams should be easy to start and stop, and tied to a storage-backed source file or source directory.

## Core Capabilities

- Expose an RTMP ingest link for a selected media source.
- Transcode to HLS for playback across devices.
- Serve the HLS output over HTTPS by default.
- Optional access control on who can watch the stream.
- Tear down the stream and its resources when done.

## Storage Integration

Source media comes from the cloud storage wrapper. Intermediate and packaged stream segments should write back to storage where sensible instead of only living on the VM.

## Roadmap Position

Planned as part of the later egress batch, after the storage wrapper exists.
