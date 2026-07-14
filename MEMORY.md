---
type: memory
status: active
created: 2026-07-14
tags: [apex-scraper, memory, always-present]
---

# MEMORY.md — Apex Scraper Durable Facts

## The Project
- **Name:** Apex Scraper
- **Owner:** Devonte Pendergrass (@StackNSatoshi)
- **GitHub:** MoorsourcecodesofAmericas/Apex-Scraper
- **Location:** `projects/Apex-Scraper/` in the OpenClaw workspace
- **Skill:** `skills/apex-scraper/SKILL.md`

## The Arsenal (Priority Order)
| Tool | Role | Best For |
|------|------|----------|
| **nodriver** | 🥇 Stealth champion | Hardest targets, DataDome. 28/31 OK, 0 blocked. |
| **Camoufox** | Firefox anti-fingerprint | Targets blocking Chrome. |
| **SeleniumBase UC** | Auto Cloudflare Turnstile | Turnstile-heavy sites. |
| **curl_cffi** | TLS-perfect HTTP | JS-free targets (fastest). |
| **Scrapling** | Multi-tool Swiss Army | Most common scraping tasks. |
| **Firecrawl** | Clean markdown extract | RAG pipelines, AI consumption. |
| **Crawl4AI** | LLM-optimized | AI/LLM data pipelines. |
| **Playwright** | Last resort | Full browser, complex flows. |

## The Ladder
Tier 1 → Tier 2 → Tier 3 → Tier 4 → Tier 5 (see SKILL.md)

## Red Team Intel (July 2026)
- Anti-detect browser benchmark: 31 targets, 3 sweeps, 7 tools, 651 verdicts
- Key finding: Automation-protocol fingerprinting is the primary detection vector, not browser identity
- nodriver wins because it removes Playwright from the control plane
- Source: ianlpaterson.com anti-detect browser benchmark

## Key Rules
- Never retry the same thing twice
- Diagnose first, act second
- Max 10 attempts before reporting failure
- Clean /tmp/apex_* after every scrape
- 3 fast failures = 30-60s mandatory backoff
