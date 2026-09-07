# Config Management

## Operational Role

In addition to executing platform services, Guaranine functions as a host configuration agent with two responsibilities:

- **Apply declarative NixOS configurations** from [klever-lab/nixos](https://github.com/klever-lab/nixos).
- **Maintain Tailscale VPN connectivity** to ensure continuous inter-node reachability.

The host operating system is NixOS, defined as code. Guaranine reconciles host state against the repository configuration while concurrently listening for and executing platform commands on port 48584.

## Node Consistency

Without centralized base machine images, the configuration management service maintains deterministic node configurations and active network connections across physical hosts.
