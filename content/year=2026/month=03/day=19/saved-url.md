---
download_date: "2026-03-19T21:18:49.103Z"
source_url: "https://turso.tech/blog/agentfs-just-bash"
added_by: "Ju Hurault"
source_type: "general"
title: "Building AI agents with just bash and a filesystem in TypeScript"
---
The next evolution of SQLite is here! [Read Announcement](https://turso.tech/blog/agentfs-just-bash/blog/beyond-the-single-writer-limitation-with-tursos-concurrent-writes)

[Turso](/)

Get StartedOpen main menu

[Docs](https://docs.turso.tech)[Cloud Pricing](https://turso.tech/blog/agentfs-just-bash/pricing)[Blog](https://turso.tech/blog/agentfs-just-bash/blog)[Changelog](https://github.com/tursodatabase/turso/blob/main/CHANGELOG.md)

[Follow us on GitHub](https://github.com/tursodatabase/turso)[Follow us on X](https://x.com/tursodatabase)[Join us on Discord](https://tur.so/discord)

[Login](https://turso.tech/blog/agentfs-just-bash/signin)Get Started

Jan 2, 2026

# Building AI agents with just bash and a filesystem in TypeScript

![Pekka Enberg](https://turso.tech/blog/agentfs-just-bash/_next/image?url=%2Favatar%2FPekka-Enberg.jpg&w=64&q=75 "Pekka Enberg")Pekka Enberg

![Cover image for Building AI agents with just bash and a filesystem in TypeScript](https://turso.tech/blog/agentfs-just-bash/_next/image?url=%2Fimages%2Fblog%2Fagentfs-just-bash%2Fcover.png&w=3840&q=100)

Bash is one of the most effective tools you can give an AI agent. Foundation models have seen enormous amounts of shell scripting during training, so they're fluent with commands like `grep`, `sed`, `awk`, and `cat`. Give an agent bash access, and it can explore data, process text, and manipulate files without needing custom tools for each task.

The problem is that real bash requires a real shell and filesystem. That means either running on a server with proper isolation, spinning up containers, or accepting the security risk of letting an agent run commands on your machine. None of these options work well if you want to deploy agents in lightweight environments like Cloudflare Workers, or if you want to avoid the cost and complexity of container orchestration.

However, [Malte Ubl](https://x.com/cramforce/status/2004992618913251786) from Vercel recently announced [just-bash](https://github.com/vercel-labs/just-bash), which solves this by reimplementing bash entirely in TypeScript. It's not a wrapper around a real shell—it's a from-scratch implementation of the commands that coding agents actually use: `grep`, `sed`, `awk`, `jq`, `cat`, `ls`, and others. You give it to your agent as a tool. The agent runs shell commands. Those commands execute in your JavaScript process, with no access to your host filesystem.

## [#](#how-it-works-)How it works?

The `just-bash` package implements bash and many of its commands in TypeScript. By default, it uses an in-memory filesystem, but provides a pluggable filesystem interface, which makes an obvious integration point with AgentFS.

The way it all works is when your agent executes a command such as `cat /README.md`, `just-bash` asks AgentFS for the file, and AgentFS reads it from an SQLite database file using Turso. The agent doesn't know it's not running a real shell. But every file lives in a database, every change is captured, and there's no way for the agent to escape to your host filesystem.

## [#](#example--ai-sdk-integration)Example: AI SDK integration

Here's how to wire up just-bash with AgentFS in the [AI SDK](https://sdk.vercel.ai/):

```typescript
import { agentfs } from "agentfs-sdk/just-bash";
import { createBashTool } from "just-bash/ai";
import { streamText } from "ai";

const fs = await agentfs({ id: "ai-agent-1" });
const bashTool = createBashTool({ fs });

const result = streamText({
  tools: { bash: bashTool },
});

```

As you can see, we first open an agentfs filesystem, then create a bash tool using the `just-bash` package, and give that to the AI SDK for the foundation model to use.

While AgentFS is built on top of Turso, the same approach works on Cloudflare Workers via the `agentfs-sdk/cloudflare` integration, which uses Cloudflare's managed SQLite. You use just-bash and AgentFS exactly the same way, just with some Cloudflare Worker APIs:

```typescript
import { DurableObject } from "cloudflare:workers";
import { streamText } from "ai";
import { createBashTool } from "just-bash/ai";
import { AgentFS } from "agentfs-sdk/cloudflare";
import { agentfs } from "agentfs-sdk/just-bash";

export class Agent extends DurableObject {
  private fs = AgentFS.create(this.ctx.storage);

  async chat(message: string) {
    const bashFs = await agentfs({ fs: this.fs });
    const bashTool = createBashTool({ fs: bashFs });

    const result = streamText({
      tools: { bash: bashTool },
    });

    return result.toDataStream();
  }
}

```

## [#](#when-to-use-just-bash)When to use just-bash

AgentFS supports different integration patterns depending on your needs:

**Direct SDK calls** work best when you're building custom tools (a PDF parser, a code analyzer). You call AgentFS directly in your tool implementations, which gives you complete control.

**`agentfs run` or `agentfs mount`** give you the full power of the host system. Mount AgentFS to the filesystem, and your agent can use any tool: git, ffmpeg, language runtimes. This requires system-level setup but imposes no limitations on available commands.

**just-bash** is the middle ground. The agent gets transparent bash access—it thinks it's running shell commands—but everything stays in TypeScript. No containers, no platform-specific configuration, runs anywhere JavaScript runs. The tradeoff is that you're limited to what just-bash implements, which covers common commands but not everything.

For many agent applications, just-bash is the right choice: transparent to the model, contained in your process, deployable anywhere.

## [#](#getting-started)Getting started

The just-bash and Cloudflare Worker integrations are available in AgentFS 0.4.1\. See the [GitHub repository](https://github.com/tursodatabase/agentfs/?tab=readme-ov-file#examples) for complete examples.

Share article

[Twitter / X](https://twitter.com/intent/tweet?text=Check%20out%20this%20awesome%20post%20on%20the%20%40tursodatabase%20blog%3A%20Building%20AI%20agents%20with%20just%20bash%20and%20a%20filesystem%20in%20TypeScript%0A%0A&url=)[Hacker News](https://news.ycombinator.com/submitlink?u=&t=Building AI agents with just bash and a filesystem in TypeScript)[Email](mailto:?subject=Building%20AI%20agents%20with%20just%20bash%20and%20a%20filesystem%20in%20TypeScript&body=Hey!%20%0A%0ACheck%20out%20this%20article%20on%20the%20Turso%20Blog%3A%20)[LinkedIn](https://www.linkedin.com/shareArticle?mini=true&url=)Copy link

Turso Cloud

[Quickstart](https://docs.turso.tech/quickstart)

[Documentation](https://docs.turso.tech)

[Pricing](https://turso.tech/blog/agentfs-just-bash/pricing)

[API Status ](https://status.turso.tech)

[Terms of Use](https://turso.tech/blog/agentfs-just-bash/terms-of-use)

[Privacy Policy](https://turso.tech/blog/agentfs-just-bash/privacy-policy)

[Embedded Replicas](https://docs.turso.tech/features/embedded-replicas)

[Database Branching](https://docs.turso.tech/features/branching)

[Backups & Recovery](https://docs.turso.tech/features/point-in-time-recovery)

[Platform API](https://docs.turso.tech/features/platform-api)

Turso Database

[Changelog](https://github.com/tursodatabase/turso/blob/main/CHANGELOG.md)

[Releases](https://github.com/tursodatabase/turso/releases)

Company

[About](https://turso.tech/blog/agentfs-just-bash/about)

[Contact Us](mailto:info@turso.tech)

[Support](https://docs.turso.tech/support)

[Trust](https://trust.turso.tech)

[Blog](https://turso.tech/blog/agentfs-just-bash/blog)

[RSS](https://turso.tech/blog/agentfs-just-bash/blog/feed.xml)[YouTube](https://www.youtube.com/@tursodatabase)[Discord](https://tur.so/discord)[X](https://x.com/tursodatabase)[Linkedin](https://www.linkedin.com/company/turso)[GitHub](https://github.com/tursodatabase)

© **Turso** 2026
