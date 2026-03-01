---
download_date: "2026-03-01T19:38:49.000Z"
source_url: "https://www.inkandswitch.com/essay/malleable-software/"
added_by: "Ju"
source_type: "general"
title: "Malleable Software: Restoring User Agency in a World of Locked-Down Apps"
---

# Malleable Software: Restoring User Agency in a World of Locked-Down Apps

**Authors:** Geoffrey Litt, Josh Horowitz, Peter van Hardenberg, Todd Matthews
**Published:** Ink & Switch, June 2025

## Overview

This essay presents a vision for computing systems that empower users to reshape their digital tools rather than passively accepting them as fixed products.

## Core Argument

The authors contend that modern software has become rigid and inflexible. As they observe, "when your tools don't work the way you need them to, you submit feedback and hope for the best." Instead, they propose **malleable software**—tools that users can adapt with minimal friction to suit their unique needs.

The contrast is striking: physical spaces naturally invite modification (a guitar maker arranging tools, a home cook organizing a kitchen), but digital environments resist change. The essay uses the example of an index card wall board that was abandoned when a team switched to rigid web-based project tracking software—a shift that paradoxically reduced the team's flexibility despite adding remote collaboration capabilities.

## Three Core Design Patterns

### 1. **Gentle Slope from User to Creator**

Rather than forcing users to choose between passive consumption or complete programming expertise, the authors advocate for systems offering incremental customization steps. They reference Allan MacLean's research on "User-Tailorable Systems," which emphasizes avoiding sharp "cliffs" in learning requirements.

Spreadsheets exemplify this principle—users can start by viewing cells, progress to editing formulas, and eventually write complex calculations. Each step requires only modest additional skill.

### 2. **Tools Over Applications**

Apps function like "avocado slicers"—specialized gadgets suited to one task. A knife, by contrast, handles many purposes. The authors advocate breaking up monolithic applications into composable tools that share underlying data.

The desktop filesystem demonstrates this principle: different programs can edit the same file, enabling flexible workflows. Modern examples include Airtable and Notion, where multiple views of shared data allow complementary interactions.

### 3. **Communal Creation**

Rather than expecting every individual to build systems from scratch, the authors emphasize local communities collaboratively developing shared solutions. Drawing on free software traditions, they highlight how "local developers" in organizations can guide colleagues up customization slopes.

This approach acknowledges that not everyone needs advanced technical skills—just enough community members with appropriate expertise to maintain shared tools.

## Limitations of Current Approaches

The essay evaluates existing customization strategies:

- **Settings**: Limited to pre-anticipated options
- **Plugins**: Require authorized extension points that developers must design
- **Modding**: Permissionless but brittle; creates maintenance burdens when underlying systems change
- **Open source**: Theoretically editable but practically requires substantial expertise
- **AI-assisted coding**: Useful for generating new isolated applications but doesn't address composability or modifying existing locked-down tools

## Ink & Switch Prototypes

The authors share research prototypes exploring malleability infrastructure:

**PushPin** explored treating tools as UI components backed by synchronized JSON documents, enabling multiple interfaces for shared data.

**Cambria** addressed schema compatibility by enabling tools to read and write data in preferred formats while maintaining live translation between schemas.

**Patchwork** stores both user data and software code in collaborative documents, supporting version control and bootstrapping—the team uses Patchwork internally for their own work, including writing this essay.

**Dynamic document projects** (Potluck, Embark) explored enriching text and outline documents with interactive behavior without requiring traditional programming.

## Key Insights from Practice

The authors note that opportunities for improvement emerge naturally within malleable systems. While developing this essay, they created a Section Word Counter tool when they needed to track section lengths—it took minutes rather than requiring formal project planning. The tool integrated seamlessly into existing workflows and could be shared simply via link.

They also found that "AI assistance complements malleable environments" effectively. Rather than replacing human agency, AI can accelerate tool creation when combined with infrastructure supporting persistence and collaboration.

## Barriers Remaining

The essay identifies substantial unresolved challenges:

- **Privacy and security**: How to support extensibility while protecting against malicious modifications
- **Business models**: Sustainable funding for composable tools rather than monolithic applications
- **Cultural shifts**: Cultivating user desire for agency and customization

## Conclusion

The authors argue that "everyone deserves the right to evolve their digital environments." While acknowledging the daunting scale of change required, they invite researchers, platform developers, and software makers to reimagine computing around user agency. They note that malleable software may lack corporate consistency but gains "the kind of charm of an old house" through organic evolution reflecting genuine needs.
