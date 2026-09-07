# Cloud Media Processing

## Summary

A service that executes FFmpeg media transformations in cloud environments on files stored via the storage wrapper.

## Initial Direction

Media processing tasks execute on transient cloud instances equipped with GPU acceleration and high-throughput network access to the storage wrapper, offloading computation and transfer bandwidth from the local client.

## Core Capabilities

- Select source files managed by the cloud storage wrapper.
- Execute FFmpeg processing jobs on transient compute instances.
- Allocate GPU-accelerated instances for hardware encoding and decoding.
- Leverage high-bandwidth internal networks between compute and storage.
- Process multi-file batch workloads.

## Execution Modes

- **Guided mode:** Standard presets for routine transformations (such as transcoding, scaling, container remuxing, and relocating MP4 `moov` atoms).
- **Raw mode:** Direct execution of arbitrary FFmpeg command strings and multi-step scripts within the worker instance.

## Execution Lifecycle

The execution model evaluates two designs:

- **Per-job execution:** Provision an instance, fetch input files from storage, execute the command, write outputs to storage, and terminate the instance.
- **Interactive session:** Maintain an active transient instance for iterative command execution across multiple files.

Evaluation criteria include instance startup latency, compute billing increments, and workflow control requirements.

## First Milestone

The initial release implements the per-job lifecycle:

1. Provision a transient compute worker for a single task.
2. Stage input files from the storage wrapper.
3. Execute the target FFmpeg command or preset.
4. Persist output files to the storage wrapper.
5. Terminate the compute instance.

Interactive sessions are deferred to subsequent releases.

## Batch Processing

The service will support batch execution over large collections of media assets.

Batch execution must achieve higher cost-efficiency and lower aggregate provisioning overhead than equivalent sequential single-job executions to justify deployment.
