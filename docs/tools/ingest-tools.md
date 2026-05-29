# Ingest Tools

## Summary

The ingest tools bring external content directly into the shared storage layer.

## Initial Tools

- Torrent ingest.
- Usenet ingest.
- yt-dlp ingest.

## Roadmap Position

These tools are planned as a later batch, not part of the initial POC.

## Shared Direction

These tools should avoid routing large files through the user's local machine. They should pull data in the cloud and write outputs directly to storage directories selected through the cloud storage wrapper.

Each ingest tool should remain its own separate tool because torrenting, Usenet, and yt-dlp are different under the hood. Advanced users will understand and expect those differences.

The tools should still share some configuration concepts:

- Common download-to options backed by the cloud storage wrapper.
- Later support for choosing which VPN or IP to download from.
- Later support for configuring a proxy for downloads.

VPN, IP selection, and proxy controls are not required for the first version.
