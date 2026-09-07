# yt-dlp Ingest

## Summary

A service that executes yt-dlp media extraction in cloud infrastructure, writing outputs directly into cloud storage.

## Architecture

Media extraction jobs run on cloud compute instances that fetch external audio and video streams and transfer completed files directly into the cloud storage wrapper without intermediate local downloading.

## Core Capabilities

- Execute yt-dlp extraction tasks on cloud compute workers.
- Persist extracted media and metadata to designated cloud storage directories.
- Integrate with the cloud storage wrapper for path resolution and quota tracking.
