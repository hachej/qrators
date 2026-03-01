---
download_date: "2026-03-01T13:25:23.000Z"
source_url: "https://github.com/D4Vinci/Scrapling"
added_by: "Ju"
source_type: "general"
title: "Scrapling: Adaptive Web Scraping Framework"
---

# Scrapling: Adaptive Web Scraping Framework

## Repository Overview

**Repository:** D4Vinci/Scrapling
**Stars:** 19.3k | **Forks:** 1.3k
**License:** BSD-3-Clause
**Created:** October 13, 2024
**Primary Language:** Python

## Description

Scrapling is described as "An adaptive Web Scraping framework that handles everything from a single request to a full-scale crawl." The project emphasizes intelligent element tracking that relocates components when websites change, built-in anti-bot circumvention, and concurrent crawling capabilities.

## Key Features

**Core Capabilities:**
- Scrapy-like Spider API with async parse callbacks
- Configurable concurrent requests with per-domain throttling
- Multi-session support combining HTTP and browser automation
- Checkpoint-based pause/resume functionality
- Streaming mode for real-time item processing
- Automatic blocked request detection and retry logic

**Fetching Options:**
- HTTP requests via Fetcher class with TLS fingerprint impersonation
- Dynamic loading through DynamicFetcher with Playwright support
- Stealthy fetching with Cloudflare Turnstile bypass capabilities
- Session management across HTTP and browser-based requests

**Parsing & Intelligence:**
- CSS selectors, XPath, and BeautifulSoup-style element selection
- Smart element tracking using similarity algorithms
- DOM traversal with parent/sibling/child navigation
- MCP server integration for AI-assisted scraping
- Adaptive selection that relocates elements after website changes

**Performance:**
- Optimized architecture with 92% test coverage
- Full type hints coverage with PyRight/MyPy validation
- 10x faster JSON serialization than standard library
- Memory-efficient implementation with lazy loading

**Developer Experience:**
- Interactive IPython shell with Scrapling integration
- Terminal-based scraping without code
- Auto-generated CSS/XPath selectors
- Complete type coverage for IDE support
- Docker image with pre-installed browsers

## Notable Integrations

The repository lists sponsor partnerships with proxy providers and scraping infrastructure companies, including ThorData, Evomi, SerpApi, and others.

## Documentation & Community

- Documentation: scrapling.readthedocs.io
- Discord community available
- Multiple language README versions (Arabic, Spanish, German, Chinese, Japanese, Russian)
