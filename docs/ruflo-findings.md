# Ruflo Findings

## Overview

Ruflo is a TypeScript/Node project for multi-agent AI orchestration around Claude Code and MCP. The repository describes Ruflo as a system that coordinates specialized coding agents, persistent memory, task planning, swarm execution, federation, and plugin-based workflows.

The current package metadata still uses the package name `claude-flow`, with the CLI exposed as `claude-flow`. The public-facing README presents the project as Ruflo, describing it as the successor/rebrand of Claude Flow.

## Main Purpose

Ruflo aims to give Claude Code a coordination layer:

- Agent and swarm orchestration for coding, testing, review, security, docs, and architecture work.
- MCP tools for agents, memory, tasks, hooks, configuration, sessions, federation, and system status.
- Persistent and vector-backed memory for recalling patterns across sessions.
- Plugin packaging for Claude Code, including core, swarm, autopilot, federation, memory, security, docs, browser, and workflow plugins.
- Optional web UI and goal-planning surfaces connected to the same agent/MCP concepts.

## Repository Signals

- `README.md` calls Ruflo "Multi-agent AI orchestration for Claude Code."
- `package.json` identifies the npm package as `claude-flow`, version `3.6.27`, with Node `>=20.0.0`.
- `AGENTS.md` defines the project mental model: `claude-flow` records coordination, state, and memory, while the AI coding agent still performs the actual file edits, commands, tests, and implementation work.
- The repo includes both legacy `v2` code and newer `v3` packages and modules.

## Notable Areas

- `bin/`: CLI entry points.
- `v3/mcp/`: MCP server, transports, tool registry, and tool implementations.
- `v3/@claude-flow/`: package-oriented V3 modules for CLI, MCP, memory, browser, shared utilities, and neural components.
- `ruflo/src/`: web UI, MCP bridge, deployment, config, and service-oriented runtime files.
- `plugins/` and `plugin/`: plugin-related packaging and marketplace assets.
- `tests/`: unit, integration, RVF, Docker regression, security, and MCP-related tests.

## Practical Interpretation

Ruflo is best understood as an agent coordination framework rather than a replacement for the coding agent itself. Its orchestration layer can track tasks, spawn or coordinate agents, store memory, and expose MCP tools, but implementation work still happens through the active coding agent and local tool execution.
