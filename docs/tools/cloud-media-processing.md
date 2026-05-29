# Cloud Media Processing

## Summary

A tool that runs ffmpeg on your files in the cloud.

## Initial Direction

This is the second tool in the suite. It works with the cloud storage wrapper.

The point is speed. Instead of running media jobs on your own computer, you run them on powerful cloud machines with fast storage. Big files get processed faster, and your own machine stays free.

Think of it less as a simple ffmpeg button and more as a temporary workspace in the cloud. The tool starts up a short-lived cloud machine, pulls in your files, gives you ffmpeg, and lets you work.

## Core Capabilities

- Pick files stored through the cloud storage wrapper.
- Run ffmpeg jobs in the cloud.
- Use powerful GPU machines when it helps.
- Take advantage of fast transfers between storage and the machine doing the work.
- Run batch jobs across many files.

## Command Modes

The tool has two modes:

- Guided mode for common tasks, with safe defaults.
- Raw mode for advanced users who want to type ffmpeg commands directly.

Guided mode points you to good presets and ready-made commands for common tasks:

- Resizing media.
- Re-encoding media.
- Moving the moov atom.
- Merging files.

Anything more complex, like special video filters, happens in raw mode.

## Workspace

Raw mode gives you full control inside a short-lived cloud machine.

You can:

- Run ffmpeg directly.
- Create temporary files.
- Create temporary folders.
- Chain several steps together.

The machine is temporary and tied to your session.

## Open Question: One Job or a Full Session

There are two ways to run the work:

- One job: start a machine, pull in the files, run the command, send the results back to storage, then shut down.
- Full session: start a machine and let the user run commands for as long as they want.

Which one we pick depends on how hard it is to build, how we keep costs down, the experience we want, and how much hands-on control the first version really needs.

## First Milestone

The first version should prove the one-job model.

The flow:

1. Start a machine for one job.
2. Pull in the chosen files from storage.
3. Run the ffmpeg command or guided preset.
4. Send the results back to storage.
5. Shut the machine down.

The full session can come later.

## Batch Processing

The tool should support grouping many files into a single batch media processing workflow, such as running ffmpeg against 1,000 files overnight.

Batch processing must be cheaper than running the same work as many individual jobs. If the system cannot make bulk processing more cost-efficient, batch processing should not be supported.
