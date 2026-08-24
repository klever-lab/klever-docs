# Egress Tools

## Summary

The egress tools serve content back out of the shared storage layer. Ingest tools bring files in; egress tools get them out again in whatever form someone needs.

## Initial Tools

- Jellyfin server.
- Secure download links.
- Encrypted file downloads.
- Livestreaming with RTMP links.

## Roadmap Position

These tools are planned as a later batch, not part of the initial POC. The storage wrapper comes first; egress tools are the first real consumers of that shared file layer.

## Shared Direction

These tools should serve files directly from the shared storage layer without routing through the user's local machine. The cloud does the serving; the user just gets a link.

Each tool should remain its own separate tool because serving media to a browser, handing out expiring links, encrypting downloads, and livestreaming are different under the hood. Advanced users will understand and expect those differences.

The tools should still share some configuration concepts:

- Common serve-from options backed by the cloud storage wrapper.
- One place to control what files are exposed and how.
- Consistent access controls (who can reach a link, and for how long).

## The Serving Spectrum

The full menu of ways to serve a file, in rough order of simplicity:

- HTTPS direct links (plain, signed, or expiring).
- Plain HTTP links.
- Signed links to files or directories in the storage wrapper.
- S3 presigned URLs for providers that support them.
- WebDAV mounts for browsing storage like a folder.
- FTP and SFTP.
- Jellyfin for a browsable media library with transcoding.
- RTMP-to-HLS for livestreaming media files.
- BitTorrent seeds for distributing large files. Note that seeds here come from a single client, so a download still behaves like a direct download — the torrent client just handles the transport.
- Usenet uploads, for pushing files out to Usenet readers (the mirror of Usenet ingest).
- IPFS for content-addressed sharing.

Not everything on this menu will be built. This is the full landscape; the tools above are the ones we plan to start with, and the rest can be added when a user actually needs them.

Exposure over HTTP versus HTTPS should always be a deliberate choice, never an accident.
