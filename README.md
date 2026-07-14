# Apex Scraper 🦞⚡

> **Undefeated. Accurate. Precise. Relentless. Critical thinker.**

Apex Scraper is an **orchestration skill** for OpenClaw — it commands Scrapling, nodriver, Camoufox, Firecrawl, Playwright, SeleniumBase, and Crawl4AI through a structured decision engine that escalates, adapts, and overcomes.

## Core Traits

- **Undefeated** — Every website yields. No 403, Cloudflare, Turnstile, Kasada, DataDome, or JS wall is a hard stop.
- **Accurate** — Exactly the right data fields. Schema-validated output. No noise.
- **Precise** — CSS/XPath selector chaining, post-processing cleanup, type-coerced fields.
- **Relentless** — Never retry the same way twice. Fail → diagnose → adapt.
- **Critical Thinker** — Empty body? JS content. 403? Protection. Timeout? Too heavy. Diagnose first, act second.

## The Escalation Ladder (5 Tiers)

```
Tier 1  →  web_fetch (fastest check)
Tier 2  →  Scrapling CLI get (HTTP scraping with impersonation)
Tier 3  →  Scrapling CLI fetch (dynamic JS rendering)
Tier 4  →  Scrapling CLI stealthy-fetch (Cloudflare/Turnstile bypass)
Tier 5  →  Maximum Power
            ├── 5A — nodriver 🏆 (stealth champion, 28/31 OK, 0 blocked)
            ├── 5B — Camoufox (Firefox anti-fingerprint)
            ├── 5C — SeleniumBase UC (auto Cloudflare Turnstile)
            ├── 5D — Firecrawl API (clean markdown)
            ├── 5E — Scrapling Python (StealthyFetcher)
            ├── 5F — Scrapling Spider (batch/crawl)
            ├── 5G — Crawl4AI (LLM-ready output)
            └── 5H — Playwright (absolute last resort)
```

## Red Team Intelligence (July 2026)

From the Anti-Detect Browser Benchmark (31 targets × 3 sweeps × 7 tools = 651 verdicts):

| Tool | OK/31 | Blocked | Best For |
|------|-------|---------|----------|
| **nodriver** | **28** | **0** 🏆 | Hard targets, DataDome |
| Camoufox | 25 | 3 | Firefox-whitelisted targets |
| Patchright | 25 | 3 | Drop-in Playwright stealth |
| curl_cffi | 26 | 2 | JS-free targets (fast) |

The key signal: detection is driven by **automation-protocol fingerprinting**, not browser identity. nodriver wins because it drives Chrome over direct CDP with **no Playwright shim.**

## Project Structure

This repo is **OpenClaw-native** — it lives at `projects/Apex-Scraper/` in the workspace and follows OpenClaw's identity/personality/memory pattern.

```
projects/Apex-Scraper/              ← This repo
├── README.md                       ← You're reading it
├── .gitignore
├── IDENTITY.md                     ← Agent identity (who Apex is)
├── SOUL.md                         ← Personality & boundaries (how Apex operates)
├── MEMORY.md                       ← Durable facts, arsenal, intel
├── _index.md                       ← Project tracker
└── notes.md                        ← Working log

skills/apex-scraper/SKILL.md        ← Full 5-tier skill definition (OpenClaw-native skill path)
```

## Quick Start

```bash
# Already in OpenClaw — just invoke the skill
# The escalation ladder runs automatically

# Manual: Scrape any URL starting at Tier 1
web_fetch "$URL"

# Manual: Protected site? Skip straight to Tier 4
scrapling extract stealthy-fetch "$URL" /tmp/apex.md --ai-targeted --solve-cloudflare

# Manual: Hardest target? Go Tier 5A
python -c "
import nodriver as uc
import asyncio
async def main():
    b = await uc.start()
    t = await b.get('$URL')
    print(await t.content())
uc.loop().run_until_complete(main())
"
```

## Key Dependencies

- Scrapling: `pip install "scrapling[all]>=0.4.9"`
- nodriver: `pip install nodriver`
- Camoufox: `pip install camoufox`
- SeleniumBase: `pip install seleniumbase`
- Crawl4AI: `pip install crawl4ai`
- Playwright browsers installed (for Scrapling stealthy-fetch)
- Firecrawl API keys

## Status

- [x] Skill proposal created
- [x] Red team intelligence gathered
- [x] GitHub repo established
- [ ] Skill applied
- [ ] Test A — books.toscrape.com (baseline validation)
- [ ] Test B — Indeed.com (escalation ladder test)
