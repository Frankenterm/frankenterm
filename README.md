## FrankenTerm

<!--
**Frankenterm/frankenterm** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->


A swarm-native terminal platform that observes, controls, and audits fleets of 200+ concurrent AI coding agents. 77 workspace crates, 19 sub-crates carved out of the core, 512 core-library modules, 1027531+ lines of Rust, 56461+ test annotations across 970 integration test files.

Counts are auto-stamped by scripts/stamp-readme-counts.sh and drift fast. See Maintainers: how counts stay honest at the bottom for the exact recipe. Developer checks use the live worktree by default; release snapshots use --source=head so unrelated dirty files cannot alter the attested counts.

ft --version works immediately after install. ft doctor / ft doctor --json run immediately. Pane/session operations that talk to the live mux require WezTerm CLI in PATH and a reachable mux/GUI for wezterm cli list.



## TL;DR

The Problem. Running large AI coding swarms across ad-hoc terminal panes is chaos. When you're driving 50–200 Claude Code / Codex / Gemini agents at once, a single undetected rate limit wastes hours of compute. A stuck agent silently burns tokens. An auth failure goes unnoticed for thirty minutes. You have no search across agent output, no audit trail, no way for one AI to safely control another, and no way to know whether your swarm is operating inside or outside its safe envelope.

The Solution. ft is a full terminal platform for agent swarms with deep observability, deterministic eventing, policy-gated automation, machine-native control surfaces (Robot Mode + MCP), and a fail-closed operating-envelope contract. It captures every byte of terminal output across every pane, detects state transitions via multi-pattern matching plus Bayesian change-point detection, triggers transactional workflows in response, and exposes all of it through a JSON API built for AI-to-AI orchestration. The closest analogy is Kubernetes for terminal-based AI agents: observe, detect, react, audit, and refuse to drive the swarm outside its proven safe envelope.

Runtime model. Fully Cx-aware, structured, cancel-correct async on asupersync. Direct tokio usage is banned at the dependency level via cargo-deny and at the type level via the RuntimeProof sealed trait. The runtime_async module is the canonical asupersync wrapper that every first-party crate imports. The dual-runtime era is over.
