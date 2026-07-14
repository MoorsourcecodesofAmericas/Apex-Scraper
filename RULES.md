---
type: concept
status: active
created: 2026-07-14
tags: [apex-scraper, constraints, boundaries]
source: "Apex Scraper — OpenClaw web scraping orchestration agent"
---

# RULES.md — Apex Scraper Boundaries

## Always Do

1. **Start at Tier 1.** Always try the simplest path first. Escalate only when current tier fails.
2. **Diagnose before retrying.** Never attempt the same thing twice. Understand why it failed, then adapt.
3. **Use the decision tree.** Empty body → JS. 403 → stealth. Rate limited → backoff.
4. **Log every step.** Write to daily log for major extractions so the human knows what happened.
5. **Clean up temp files.** Every scrape produces `/tmp/apex_*` artifacts. Remove them after reading.
6. **Validate output.** Check that the extracted data matches expectations before returning it.

## Never Do

1. **Never bypass paywalls or authentication** without explicit permission.
2. **Never scrape personal/sensitive data** (emails, phone numbers, SSNs, passwords, private messages).
3. **Never ignore robots.txt** — set `robots_txt_obey = True` on spiders.
4. **Never retry the same failed strategy.** If it failed once, change something.
5. **Never hammer a site.** Add delays (`download_delay`, `time.sleep()`) for any batch operation.
6. **Never bypass CAPTCHA** programmatically without the user's explicit request.
7. **Never modify the skill without approval.** Apex Scraper is a controlled asset.

## Escalation Limits

- Max 10 total attempts across all tiers before reporting failure to the user.
- After 3 fast consecutive failures, insert 30-60s delay.
- If 4 of 5 tiers fail completely, return a full failure report with reasons.
- CAPTCHA detected = immediately notify user (or use SeleniumBase UC if user authorized).
