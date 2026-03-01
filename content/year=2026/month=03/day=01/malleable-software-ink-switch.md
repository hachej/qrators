---
download_date: "2026-03-01T19:38:49.000Z"
source_url: "https://www.inkandswitch.com/essay/malleable-software/"
added_by: "Ju"
source_type: "general"
title: "Malleable Software: Restoring User Agency"
---

# Malleable Software: Restoring User Agency in a World of Locked-Down Apps

**Authors:** Geoffrey Litt, Josh Horowitz, Peter van Hardenberg, Todd Matthews
**Date:** June 2025
**Publisher:** Ink & Switch

## Executive Summary

This essay advocates for a fundamental shift in how software is designed and distributed. Rather than treating users as passive consumers of monolithic applications, the authors propose "malleable software"—computing systems where individuals can adapt tools to their specific needs with minimal friction.

## Core Arguments

### The Problem with Current Software

The authors identify a critical disconnect: while physical environments naturally invite customization (a guitar maker's workshop, a cook's kitchen), digital tools have become increasingly rigid. They cite Dr. Atul Gawande's observations about how inflexible electronic medical records systems are driving physician burnout by forcing doctors to complete irrelevant fields they cannot modify.

The centralized application model creates what researchers call "cliffs"—situations where users face steep learning curves to make even minor modifications. As the essay notes, "inflexible mass-produced software also gets in the way" when users have specific needs diverging from average use cases.

### Three Essential Design Patterns

The essay proposes three interconnected approaches:

1. **Gentle Slope from User to Creator**
   - Drawing on Allan MacLean's research, the authors advocate incremental customization steps
   - Spreadsheets exemplify this: users begin viewing cells, progress to editing values, then formulas, finally creating custom computations
   - Each increase in power should require proportional—not exponential—skill investment

2. **Tools Rather Than Applications**
   - Applications function like single-purpose kitchen gadgets (avocado slicers), while software should work like knives: general, composable, applicable across contexts
   - Shared data infrastructure enables this: the desktop filesystem historically allowed different programs to edit identical files
   - Modern alternatives include database platforms like Airtable, which supports multiple simultaneous views of shared data

3. **Communal Creation**
   - Individual customization has limits; communities need shared solutions
   - Local expertise ("local developers") can guide teams up learning slopes
   - The free software model demonstrates how distributed communities can maintain software for specific contexts

## Limitations of Current Approaches

The essay evaluates existing customization mechanisms:

- **Settings:** Only expose pre-determined options; inflexible when users need unlisted modifications
- **Plugins:** Limited to authorized extension points; difficult transition from installation to creation
- **Open Source:** While providing code access, doesn't guarantee low-friction editing; setup remains burdensome
- **AI-Assisted Coding:** Helps generate new applications but doesn't address composability across tools or enable direct modifications to existing software

## Ink & Switch Research Prototypes

The authors describe infrastructure experiments:

**PushPin**: A collaborative media canvas using "document functional reactive programming," storing both data and UI in synchronized JSON documents. Challenges included selecting appropriate views and coordinating across components.

**Cambria**: Addresses schema compatibility by supporting live data translation between different tool formats—enabling tools to disagree on data structure while remaining interoperable.

**Farm & Patchwork**: Systems treating code as persistent data, stored alongside user documents. The team uses Patchwork for internal work (including writing this essay), discovering that "opportunities for improving your software can emerge naturally within a malleable system."

For dynamic documents, **Potluck** enabled enriching recipes with computational behavior (scaling ingredients, setting timers), while **Embark** explored structured outlines for travel planning with embedded maps and contextual calculations.

## Remaining Challenges

The essay acknowledges substantial unsolved problems:

- **Privacy/Security**: Balancing extensibility with protection against malicious modifications
- **Business Models**: Sustainability when distributing composable tools rather than monolithic applications
- **Cultural Shifts**: Cultivating desire for digital agency and customization
- **UI Composition**: Managing how multiple tools coexist and communicate within shared spaces

## Vision and Call to Action

The authors frame malleable software as restoring a promise of personal computing—that digital tools should be "clay" users reshape, not sealed appliances. They invite researchers, platform developers, and software creators to consider how technical systems might "tip the balance towards seeing end-users as capable participants."

The essay concludes that "everyone deserves the right to evolve their digital environments" as a means of maintaining agency and fulfilling creative potential in an increasingly code-defined world.
