# Cloud Storage Wrapper

## Summary

A tool that lets you upload files to cloud storage and download them later, with sensible security set up for you.

## Initial Direction

This is the first tool in the suite.

Cloud storage is normally fiddly to set up. This tool puts a clean layer on top so you don't have to deal with the provider's settings yourself.

We make clear choices about which providers to support. We may add more over time, but we won't try to support every cloud platform.

The tool is API-first. We build the core API by hand. The command-line tool and web app sit on top of that API, and we can lean on LLMs to help build those parts.

## Core Capabilities

- Upload files to cloud storage.
- Download files from cloud storage.
- Set up the right security.
- Handle the settings needed to store files safely.

## First Milestone

Build the smallest version of the API that proves the tool works and can connect to the next tool in the suite.

Keep the first version small. Things like sharing, permissions, extra file details, or a full file manager can wait until the next tool actually needs them.

The storage wrapper should become the shared file layer for the rest of the suite. Other tools should be able to import, export, or mount user-selected files and directories from it.

## Storage Backends

The storage layer is built around S3.

Where we start:

- BYOK: connect your own S3-compatible account if you have one.
- Backblaze as the default, billed to you at cost.
- rclone support, so you can connect other providers like Google Drive or Dropbox.

## Post-POC Features

- Semantic search across stored files.
- Tagging for stored files and directories.

Semantic search should eventually cover both file contents and file metadata, including names and other descriptive fields.

Automatic semantic profiling should be a first-class feature. The system should be able to analyze stored files and generate useful semantic metadata instead of relying only on manual organization.
