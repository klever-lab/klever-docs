# Egress Tools

## Summary

Egress tools distribute content stored in the shared cloud storage layer across various network protocols and applications.

## Component Services

- Jellyfin server.
- Secure download links.
- Encrypted file downloads.
- Livestreaming with RTMP links.

## Architecture and Dependencies

Egress tools depend on the cloud storage wrapper as their primary storage backend.

Content is delivered directly from cloud infrastructure to clients without routing data through intermediate user machines. Each egress service operates independently to accommodate differences in protocol handling, compute overhead, and security profiles.

Shared configuration primitives across egress tools include:

- Source path selectors referencing the cloud storage wrapper.
- Access policies defining credential requirements and link expiration.
- Centralized auditing of exposed resources.

## Distribution Protocols

Distribution mechanisms evaluated for content egress, ordered by architectural complexity:

- Direct HTTPS links (static, cryptographically signed, or time-limited).
- Unencrypted HTTP links (requiring explicit configuration).
- S3 presigned URLs for object storage providers supporting native signing.
- WebDAV endpoints for file-system navigation.
- FTP and SFTP file transfer services.
- Jellyfin media server with on-demand transcoding.
- RTMP-to-HLS pipelines for live media broadcast.
- Single-seed BitTorrent transfers for large-file distribution.
- NNTP/Usenet uploads for Usenet propagation.
- IPFS for content-addressed peer distribution.

Initial development focuses on the four component services listed above; additional protocols will be evaluated based on operational requirements.
