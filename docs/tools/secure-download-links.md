# Secure Download Links

## Summary

A tool for generating links that let other people download files from your storage, securely.

## Initial Direction

The core primitive is a signed, expiring link: only the holder can download, and the link stops working after a chosen time.

Links should be scoped to the exact file or directory they were created for, never to the whole account.

## Core Capabilities

- Generate expiring download links for files and directories.
- Sign links so they cannot be forged or modified.
- Support HTTPS by default and allow plain HTTP only as an explicit choice.
- List, revoke, or extend existing links.
- Optional per-link limits, such as a maximum number of downloads.

## Storage Integration

Links resolve directly against the cloud storage wrapper. For providers that support them, presigned URLs should be the underlying mechanism; otherwise the tool signs its own URLs and serves through a gateway.

## Roadmap Position

Planned as part of the later egress batch, after the storage wrapper exists.
