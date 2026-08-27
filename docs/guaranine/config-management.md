# Config Management

## Role

Beyond its cloud features, Guaranine acts as a configuration management agent for the physical machine it runs on. Two duties:

- **Apply NixOS config** from [klever-lab/nixos](https://github.com/klever-lab/nixos).
- **Maintain the Tailscale VPN connection** so the mesh stays up and nodes stay reachable.

The host OS is NixOS, managed as code. Guaranine makes sure each machine stays in line with that config while still doing its day job of serving cloud-platform commands on port 48584.

## Why This Matters

In a cloud made of your own hardware, there is no image registry or base AMI keeping nodes consistent. The config management duty fills that role: every box stays identical and connected without manual attention.
