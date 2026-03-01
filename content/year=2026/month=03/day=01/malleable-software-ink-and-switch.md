---
download_date: "2026-03-01T19:38:49.000Z"
source_url: "https://www.inkandswitch.com/essay/malleable-software/"
added_by: "Ju"
source_type: "general"
title: "Malleable Software: Restoring User Agency in a World of Locked-Down Apps"
---

# Malleable Software: Restoring User Agency in a World of Locked-Down Apps

**Authors:** Geoffrey Litt, Josh Horowitz, Peter van Hardenberg, and Todd Matthews
**Published:** June 2025
**Organization:** Ink & Switch

## Overview

This essay presents a vision for computing that empowers users to reshape their tools rather than passively accepting rigid applications.

## Core Thesis

The authors argue that personal computing has evolved into locked-down "appliances" when it should remain malleable "clay." They propose that modern computing infrastructure—from programming languages to app stores—treats users as passive recipients rather than active co-creators. Their vision: "tools that users can reshape with minimal friction to suit their unique needs."

## Key Design Patterns

### 1. Gentle Slope from User to Creator

Drawing on MacLean et al.'s research, the authors advocate for systems where customization difficulty increases gradually rather than presenting sudden "cliffs." Spreadsheets exemplify this: users can begin simply viewing cells and progress to complex formulas without abandoning the same tool.

The gradient works in both directions—simplifying programming languages OR gradually exposing more power within familiar interfaces. HyperCard's level system demonstrated how explicit modes could guide users progressively deeper into modification capabilities.

### 2. Tools, Not Apps

The essay critiques applications as "specialized gadgets" (like avocado slicers) rather than general-purpose instruments. When software siloes data, users must manually coordinate across isolated programs. The authors advocate for composable tools operating on shared data—like how the desktop filesystem enables multiple applications to edit the same file.

Examples of shared-data approaches include:
- Database builders like Airtable enabling multiple views of unified data
- Webstrates supporting real-time collaboration across different editors
- Compound-document systems like OpenDoc embedding multiple editors within one document

### 3. Communal Creation

Individual customization has limits. Communities—departments, companies, families—need shared solutions. The authors highlight how "local developers" emerge naturally in organizations, and how free-software communities demonstrate that distributed creation at multiple skill levels can succeed.

This approach supports what Shirky called "situated software": tools built for specific communities rather than global audiences, reducing complexity and enabling responsiveness.

## The Limitations of Current Approaches

The essay acknowledges existing customization mechanisms while explaining their constraints:

- **Settings**: Only expose developer-anticipated options
- **Plugins**: Require authorized extension points; difficult transition to creating one's own
- **Modding**: Demands reverse-engineering; breaks with updates; fragile across versions
- **Open source**: Access to code doesn't eliminate friction; requires significant expertise and environment setup
- **AI-assisted coding**: Generates isolated applications; doesn't address composability or tweaking existing tools

As the authors note, even AI assistance "alone does not address all the barriers." Generating one-off applications differs fundamentally from modifying existing integrated tools.

## Ink & Switch Prototypes

The research team has explored malleability across the computing stack:

### Infrastructure Projects

**PushPin** demonstrated document functional reactive programming (DFRP)—decoupling data from UI by backing React components with synchronized Automerge documents. This enabled defining alternative views of existing data without rebuilding infrastructure.

**Cambria** addressed schema compatibility by supporting live translation between different data formats across tools, avoiding destructive migrations.

**Farm** hosted software code itself as synced data, enabling real-time sharing and collaborative editing of tools.

**Patchwork** integrated version control concepts accessible to non-engineers, treating both documents and code as first-class editable artifacts. The team uses it internally for writing, whiteboarding, and software development—a "bootstrapping" approach revealing opportunities for improvement through actual use.

Within Patchwork, they built contextual tools (word counters, structure viewers) that emerged from identified needs during essay writing, demonstrating how malleable environments naturally surface customization opportunities.

### Dynamic Documents

**Potluck** allowed users to enrich plaintext notes with interactive behavior (recipe scaling, timers) by writing pattern detectors and formulas—keeping unstructured entry while optionally layering computation.

**Embark** applied this to travel planning using hierarchical outlines, embedding maps and calendars that maintained rich awareness of surrounding document context. Hovering a location highlighted it across views, creating cohesion impossible with restricted embedding models.

## Remaining Challenges

The authors acknowledge substantial obstacles:

**Privacy and security**: How do untrusted modifications of data-accessing tools avoid harm? Current prototypes focus on trusted collaborating groups.

**Business models**: How do developers monetize composable tools versus applications?

**Cultural shift**: Computing culture must value user agency and environmental adaptation, not just polish and ease of initial use.

## Vision for Change

The authors invite different stakeholders to participate: researchers reimagining computing metaphors; platform developers treating users as capable participants; product makers empowering customization rather than dictating all decisions.

They acknowledge that malleable software may lack corporate polish but will develop the character of evolving spaces: "bearing witness to past uses and carrying traces of its past decisions, even as it evolves to meet the needs of the day."

The fundamental argument: everyone deserves "the right to evolve their digital environments" as an expression of creative potential and agency in an increasingly code-defined world.
