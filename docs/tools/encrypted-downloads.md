# Encrypted File Downloads

## Summary

A tool for sharing files where the content stays encrypted, even if the link leaks.

## Initial Direction

Two complementary layers:

- Encryption in transit: every download is served over TLS, never plain HTTP.
- Encryption of content: the file is encrypted at rest so that storage access alone does not reveal it.

Sharing should be possible with nothing more than a password or a key phrase, exchanged out of band.

## Core Capabilities

- Encrypt files before they are stored or served.
- Generate download links protected by a user-chosen password or key.
- Decrypt on the fly for the person downloading, or hand out the encrypted blob and key separately for true zero-knowledge sharing.
- Never log or store the passwords or keys used to protect files.
- Optional auto-expiry and download limits, matching the secure download links tool.

## Storage Integration

Encryption works with the cloud storage wrapper. For zero-knowledge sharing, the wrapper stores only ciphertext and the key never leaves the user's machine.

## Roadmap Position

Planned as part of the later egress batch, after the storage wrapper exists.
