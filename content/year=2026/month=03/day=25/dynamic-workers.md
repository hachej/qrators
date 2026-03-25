---
download_date: "2026-03-25T00:00:00.000Z"
source_url: "https://blog.cloudflare.com/dynamic-workers/?utm_campaign=cf_blog&utm_content=20260324&utm_medium=organic_social&utm_source=twitter/"
added_by: "Ju Hurault"
source_type: "general"
title: "Sandboxing AI Agents, 100x Faster"
---
# Sandboxing AI Agents, 100x Faster

## Overview

Cloudflare has introduced Dynamic Workers, now in open beta for paid Workers users. This feature enables secure execution of AI-generated code using lightweight isolates—JavaScript sandboxes that are approximately 100 times faster than traditional containers.

## Key Technical Advantages

**Performance**: Dynamic Workers leverage V8 isolates, which startup in milliseconds and consume only megabytes of memory, compared to containers requiring hundreds of milliseconds and megabytes to initialize.

**Scalability**: The system supports unlimited concurrent sandboxes without rate limits. As the documentation notes, you can "handle a million requests per second, where every single request loads a separate Dynamic Worker sandbox."

**Global Distribution**: One-off Dynamic Workers typically execute on the same machine as their parent, eliminating latency from distributed coordination. The platform operates across hundreds of Cloudflare locations worldwide.

## How It Works

Developers pass AI-generated code to the Dynamic Worker Loader API, specifying modules, compatibility dates, and environment access:

- Code runs in isolated JavaScript environments
- External APIs are accessed via TypeScript interfaces or HTTP with credential injection
- Security boundaries are enforced through Cap'n Web RPC protocols

## Language and API Considerations

The implementation is JavaScript-based, with TypeScript interfaces preferred over REST APIs for efficiency. According to the article, "TypeScript is designed to be concise. With very few tokens, you can give your agent a precise understanding of your API."

## Security Architecture

Cloudflare's isolate-based platform incorporates multiple defense layers developed over eight years, including V8 patch deployment within hours, custom secondary sandboxes, and dynamic tenant cordoning based on risk assessments.

## Helper Libraries

Three support packages are available:

- **@cloudflare/codemode**: Constructs purpose-built sandboxes for model-generated code
- **@cloudflare/worker-bundler**: Handles module bundling with npm dependency resolution
- **@cloudflare/shell**: Provides virtual filesystem access with persistent storage

## Pricing

During beta, Dynamic Workers are free. Standard pricing is $0.002 per unique Worker loaded daily, plus standard CPU and invocation costs—typically negligible compared to inference expenses for code generation.

## Use Cases

Organizations including Zite are leveraging Dynamic Workers for customer-facing automation platforms, generating CRUD applications and backend logic on-demand with isolated, secure execution environments.
