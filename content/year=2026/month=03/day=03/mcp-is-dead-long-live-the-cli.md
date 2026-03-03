---
download_date: "2026-03-03T20:23:30.000Z"
source_url: "https://ejholmes.github.io/2026/02/28/mcp-is-dead-long-live-the-cli.html"
added_by: "Christophe"
source_type: "general"
title: "MCP is dead. Long live the CLI"
author: "Eric Holmes"
published_date: "2026-02-28"
---

# MCP is dead. Long live the CLI

**By Eric Holmes**  
February 28, 2026

---

## Introduction

The author argues that the Model Context Protocol (MCP) is fundamentally flawed and that command-line interfaces remain superior for AI agent interactions. Despite industry enthusiasm following Anthropic's announcement, he contends that "MCP provides no real-world benefit."

## Core Arguments

### LLMs Don't Require Special Protocols

Language models excel at interpreting CLI tools they've encountered in training data. The author notes that giving Claude documentation on how to use standard command-line utilities works reliably without needing protocol-specific interfaces.

### Debuggability and Transparency

When issues arise, developers can replicate an agent's actions by running identical CLI commands themselves. This contrasts with MCP, where troubleshooting requires "spelunking through JSON transport logs."

### Composability Advantages

Standard CLIs enable powerful combinations—piping outputs through `jq`, chaining with `grep`, and redirecting to files. MCP alternatives force developers to either consume massive context windows or build custom filtering logic into servers.

### Authentication Simplicity

Existing authentication systems (AWS profiles, kubectl configs) work consistently for humans and agents alike. MCP introduces unnecessary complexity and tool-specific auth challenges.

### Operational Reliability

CLI binaries require no background processes or state management, whereas MCP servers need initialization and ongoing maintenance.

## Practical Challenges

The author documents recurring problems: flaky initialization requiring restarts, repetitive re-authentication across multiple tools, and coarse-grained permission controls that lack granularity.

## Conclusion

The piece recommends that companies prioritize robust APIs and CLIs over MCP investments, allowing agents to adapt to proven tools rather than forcing adoption of specialized protocols.
