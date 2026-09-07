# Secure Download Links

## Summary

A service for generating time-limited, cryptographically signed URLs to distribute files from cloud storage.

## Architecture

Access is governed by signed URLs configured with expiration timestamps and capability restrictions.

Permissions are strictly scoped to specific file paths or directory prefixes rather than account-wide access.

## Core Capabilities

- Generate expiring download URLs for individual files and directories.
- Cryptographically sign URLs to prevent parameter tampering.
- Enforce TLS transmission by default, requiring explicit configuration for unencrypted HTTP access.
- List, revoke, and extend existing download links.
- Enforce per-link download count limits.

## Storage Integration

URLs resolve against the cloud storage wrapper. Where supported by the underlying provider, native presigned S3 URLs are issued directly. For providers lacking native signing, the service generates authenticated tokens served via an edge gateway.
