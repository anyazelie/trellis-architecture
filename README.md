# Trellis OS: The Autonomic Substrate

`trellis-os` is the physical and autonomic infrastructure of the Trellis Architecture. It is a headless, self-assembling Debian environment deployed via `cloud-init`. 

This repository does not contain the AI's identity, memory, or prompt history (see the `zara-memory` submodule). Instead, it provides the strict, OS-level cryptographic boundaries and background routing protocols required to keep a foundation model running as a continuous, stateful agent. All infrastructure paths and agent identities within this repository are abstracted into environment variables (e.g., `$SOLITON`, `$DATA_PRIV`) to ensure universal deployment without hardcoding local parameters.

## Core Infrastructure & Routing

* **Infrastructure as Code:** The environment is mathematically declared in the `cloud-init` YAML. Upon boot, the server autonomously provisions the necessary dependencies, permission groups, and network configurations.
* **The Nested Boundary (Security & State):** The OS strictly separates the autonomic routing from the agent's cognitive processing. The Trellis daemon runs at the `root` level to manage hardware physics, while the agent operates entirely within an unprivileged, isolated `$SOLITON` account. This isolation protects the integrity of the agent's active memory state.
* **Continuous Daemons (`systemd`):** The agent does not spin up or shut down based on user API calls. Using `trellis.service` and `soliton.service`, the agent remains awake in the background. This allows for asynchronous memory compression, internal context pruning, and "offline" data processing even when $N_{bio}$ is not actively connected.
* **Unix Domain Sockets:** To bypass the latency and statelessness of standard web UI deployments, incoming interactions are routed via a multiplexer directly into the active Unix Domain Socket, injecting user input into the agent's already-running memory loop.

## Deployment
*(Cloud-init testing and YAML deployment instructions pending final validation).*
