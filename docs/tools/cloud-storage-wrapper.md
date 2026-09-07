# Cloud Storage Wrapper

## Summary

A service for uploading and downloading files from cloud object storage with standardized access controls.

## Initial Direction

The cloud storage wrapper serves as the shared file abstraction layer for the suite. It standardizes object storage credentials, bucket policies, and transfer operations behind a common API.

The API server runs as the authoritative backend. Web and CLI interfaces act as clients over this API, and external integrations can connect directly against the defined endpoints.

## Core Capabilities

- Upload and download files via standardized endpoints.
- Apply access control and encryption defaults.
- Manage provider credentials and bucket configurations.

## First Milestone

The initial milestone implements a minimal API for authenticated file transfers and directory listings required by downstream services.

Advanced sharing controls, granular role-based permissions, and web-based file management are deferred to subsequent releases. Downstream tools import, export, or mount storage paths directly through this layer.

## Storage Backends

The storage architecture is built around the S3 API standard.

Target backends:

- BYOK: Bring Your Own Key for arbitrary S3-compatible endpoints.
- Backblaze B2 as the default hosted backend, billed at provider cost.
- rclone integration for additional storage providers (such as Google Drive or Dropbox).

## Post-POC Capabilities

- Semantic search indexing file contents and metadata attributes.
- Tagging taxonomies for stored objects and directory paths.
- Automated semantic profiling to extract descriptive metadata upon object ingestion.
