# Encrypted File Downloads

## Summary

A tool for distributing encrypted files where content confidentiality is preserved independently of link dissemination.

## Security Model

Protection operates across two distinct layers:

- **Transport security:** Downloads are transmitted exclusively over TLS.
- **Payload encryption:** Objects are encrypted at rest; storage access alone does not expose plaintext content.

Decryption keys or passphrases are distributed out-of-band.

## Core Capabilities

- Encrypt files prior to upload or distribution.
- Generate download URLs associated with client-managed encryption keys.
- Support both server-side decryption during transfer and client-side zero-knowledge decryption.
- Avoid logging or persisting encryption keys on backend servers.
- Apply expiration timestamps and download count thresholds.

## Storage Integration

The tool integrates with the cloud storage wrapper. In zero-knowledge configurations, the storage layer persists only ciphertext, and cryptographic keys remain strictly on client endpoints.
