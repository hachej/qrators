---
download_date: "2026-03-01T14:08:03.000Z"
source_url: "https://github.com/rtk-ai/rtk"
added_by: "Ju"
source_type: "general"
title: "rtk - Rust Token Killer"
---

# rtk - Rust Token Killer

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**High-performance CLI proxy to minimize LLM token consumption.**

[Website](https://www.rtk-ai.app) | [GitHub](https://github.com/rtk-ai/rtk)

rtk filters and compresses command outputs before they reach your LLM context, saving 60-90% of tokens on common operations.

## Token Savings (30-min Claude Code Session)

Typical session without rtk: **~150,000 tokens**
With rtk: **~45,000 tokens** → **70% reduction**

## Key Features

- **Smart Filtering**: Removes noise (comments, whitespace, boilerplate)
- **Grouping**: Aggregates similar items (files by directory, errors by type)
- **Truncation**: Keeps relevant context, cuts redundancy
- **Deduplication**: Collapses repeated log lines with counts

## Installation

```bash
brew install rtk  # macOS/Linux
# OR
curl -fsSL https://raw.githubusercontent.com/rtk-ai/rtk/refs/heads/master/install.sh | sh
```

**Verify installation:**
```bash
rtk --version   # Should show "rtk 0.22.2"
rtk gain        # Should show token savings stats
```

## Quick Start

```bash
# Initialize for Claude Code (RECOMMENDED: hook-first mode)
rtk init --global

# Test it works
rtk git status  # Should show ultra-compact output
rtk init --show # Verify hook is installed
```

## Auto-Rewrite Hook

The hook transparently intercepts Bash commands and rewrites them to their rtk equivalents before execution (e.g., `git status` → `rtk git status`).

**Result**: 100% rtk adoption, zero token overhead in Claude's context.

## Commands

**Files**
```bash
rtk ls .                        # Token-optimized directory tree
rtk read file.rs                # Smart file reading
rtk grep "pattern" .            # Grouped search results
```

**Git**
```bash
rtk git status                  # Compact status
rtk git diff                    # Condensed diff
rtk git push                    # → "ok ✓ main"
```

**Testing**
```bash
rtk test cargo test             # Show failures only (-90% tokens)
rtk pytest                      # Python tests (failures only)
rtk go test                     # Go tests (NDJSON format)
```

**Analytics**
```bash
rtk gain                        # Summary stats
rtk gain --graph                # ASCII graph of last 30 days
rtk discover                    # Find missed savings opportunities
```

## Documentation

Full documentation at [rtk-ai/rtk](https://github.com/rtk-ai/rtk)

## License

MIT License
