---
download_date: "2026-03-01T19:01:33.000Z"
source_url: "https://agentation.dev/"
added_by: "Ju"
source_type: "general"
title: "Agentation: Visual Feedback Tool for AI Agents"
---

# Agentation: Visual Feedback Tool for AI Agents

## Overview
Agentation is a desktop-only tool that converts UI annotations into structured context for AI coding agents. Users can click elements, add notes, and share the output with AI tools like Claude Code or Cursor.

## Key Features

**Core Functionality:**
- Click any UI element to highlight and annotate it
- Hover to see element names
- Generate formatted markdown output for AI agents
- Copy annotations for pasting into AI tools

**What Agents Receive:**
The tool provides agents with "CSS selectors to grep your codebase, React component names to find the right file, computed styles to understand current appearance, and your feedback with intent and priority."

## How It Works

**For Users (5 Steps):**
1. Activate the toolbar icon (bottom-right corner)
2. Hover over elements to see names
3. Click to add annotations
4. Write feedback and submit
5. Copy and paste into your agent

**For Agents:**
With MCP integration, agents can query annotations without manual copy-paste, ask clarification questions, and resolve feedback programmatically.

## Technical Options
- **MCP Integration:** Real-time agent synchronization (skip copy-paste)
- **Webhooks:** Push annotations to external services
- **API:** Custom integration building

## Installation
`npm install agentation`

## Licensing
Free for individuals and internal company use. Commercial license available for redistribution.
