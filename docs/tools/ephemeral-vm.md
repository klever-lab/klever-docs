# Ephemeral VM

## Summary

A tool for spinning up ephemeral virtual machines that users can connect to however they choose.

## Initial Direction

The VM can be headless or include a graphical environment, depending on the user's needs.

The tool should focus on temporary cloud environments that are easy to create, access, use, and tear down.

The VM should be configurable based on the user's workload. Users should be able to choose resource profiles such as high-memory machines, smaller cheaper machines, or other available options exposed by supported cloud providers.

## Core Capabilities

- Start an ephemeral VM.
- Choose headless or non-headless operation.
- Configure machine resources.
- Mount selected storage directories.
- Connect using the user's preferred access method.
- Tear down the VM when finished.

## Connection Model

Supported connection methods should be first-class rather than treated as afterthoughts.

The tool should allow simple headless environments without browser or graphical support. At the lowest level, this can feel similar to using EC2: create a machine, connect to it, use it, and shut it down.

Higher-level workflows can build on top of that baseline to make more advanced cloud computing tasks easier.

## Storage Integration

The VM tool should integrate directly with the cloud storage wrapper.

Users should be able to select storage directories and mount them into the VM, allowing the environment to work directly with files managed by the shared storage layer.

## Provider Options

The tool should support machine options from existing cloud providers rather than hiding all infrastructure choices behind a single fixed VM type.

The tool should eventually expose raw provider options directly. Presets can help with common workflows, but advanced users should be able to reach the underlying controls.

In addition to direct provider passthrough, the tool should provide an "instant" or on-demand mode. Starting a VM should feel as fast as possible — ideally near-instantaneous, where a user can click a button and immediately see connection details for a ready-to-use machine. Reducing or eliminating wait time for provisioning and connection is a priority even if the underlying provider requires setup.
