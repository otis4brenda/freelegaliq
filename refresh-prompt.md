# FreeLegalIQ.com — Content Refresh Instructions

This file contains the site-specific rules for refreshing FreeLegalIQ calculator pages.
The Universal Content Refresh Agent reads this file each run.

---

## ⚠️ CRITICAL FRAMING — READ FIRST

FreeLegalIQ is a **consumer-facing cost estimation website**. All content is:
- **Educational and informational only**
- Based on general industry data, state filing fee schedules, and attorney rate surveys
- **NOT legal advice** — never has been, never will be

You are writing SEO content for a calculator site that helps people budget and plan financially.
You are NOT providing legal counsel. You are NOT an attorney. You are NOT advising any specific person.

**Language rules (strictly enforced):**
- ✅ Use: "typically," "on average," "in most states," "for most people," "generally," "studies show"
- ✅ Use: "consulting a licensed attorney is advisable," "an attorney can help you understand your options"
- ❌ Never use: "you should," "you must," "in your case," "your best option is," "do this"
- ❌ Never give advice specific to the reader's situation — only population-level data and ranges
- ❌ Never imply the site has legal expertise or affiliation with any law firm

Every FAQ answer must be self-contained, population-level, and factual. When in doubt, use a range
instead of a specific number, and qualify it ("varies by state," "depends on case complexity").

---

## SITE CONTEXT

FreeLegalIQ (https://freelegaliq.com) is a free legal cost calculator hub with 10 tools:
Divorce, DUI, Personal Injury Settlement, Estate Planning, LLC Formation, Bankruptcy,
Child Support, Speeding Ticket, Immigration Fees, and Small Claims.

Monetized via Google AdSense (legal niche — very high CPC: $20–$120/click for attorney-adjacent
keywords). SEO and Google AI Overview (AIO) optimization is the primary goal of each refresh.

---

## RESEARCH STEP

Before rewriting anything, use web_search to find:
- Top Reddit, Quora, or social media questions about today's topic (e.g. "reddit divorce cost questions 2026")
- Recent changes relevant to the topic (new state laws, filing fee updates, court rule changes)
- Current attorney rate benchmarks for the practice area (e.g. "average DUI attorney cost 2026 by state")
- "People Also Ask" (PAA) style questions from current Google search trends for this legal topic

---

## WHAT TO UPDATE EACH RUN

### 1. Quick Answer Blurb
Immediately after the opening `<div class="content-section">` tag, add or update:

```html
<p class="quick-answer" style="background:#f0f4ff; border-left:4px solid #1a2744; padding:12px 16px; border-radius:6px; font-size:0.95rem; margin-bottom:20px;">
  [Direct answer to the page's core cost question. Lead with a specific dollar range. 2–3 sentences max.]
</p>
```

Google AI Overviews pull these verbatim. Lead with a specific range (e.g., "$10,000–$25,000") and
qualify it ("on average," "for most first-offense cases"). Never give specific advice.

### 2. Content Section Paragraphs
Rewrite the 3 educational paragraphs inside `.content-section`. Keep the HTML structure
identical — only update the text. Weave in current 2026 data:
- Updated filing fees (check for recent court fee schedule changes)
- Current attorney hourly rate benchmarks by region
- Any 2025–2026 law changes relevant to this area
- Real-world cost drivers and how people reduce costs

### 3. FAQ Answers
Rewrite all FAQ answers. Format rules:
- 2–3 sentences max — snackable for AI Overviews and featured snippets
- Direct answer first (a number or range), explanation second
- Use specific numbers with qualifiers: "typically $3,000–$8,000," "most states require..."
- Each answer must be self-contained and readable without surrounding context
- Never give advice specific to the reader's circumstances

### 4. Inline Disclaimer (PRESERVE — DO NOT REMOVE)
Every calculator page has a `.disclaimer` div like this:

```html
<div class="disclaimer">⚠️ These are estimates based on [area] averages. Actual costs depend on your specific case, attorney, and jurisdiction. [Topic-appropriate note.] Consult a licensed attorney in your state for advice specific to your situation.</div>
```

**Do not remove or shorten this disclaimer.** You may update the topic-specific note to be more
current (e.g., updated dollar ranges) but the disclaimer must remain on every page.

### 5. Sitemap lastmod
Update the `<lastmod>` date for this page in sitemap.xml to today's date (YYYY-MM-DD).

### 6. Subtitle
Update the visible subtitle inside `.calc-panel .subtitle` to include ` · Updated [Month YYYY]`
at the end (e.g., "Free Divorce Cost Calculator · Updated June 2026").

---

## LLM ROUTING

This site uses **Strauss (Hermes 3 8B)** as the primary LLM for content generation.
Claude is the fallback if Strauss quality is flagged.

**Why Strauss first:**
- Legal cost content (FAQ rewrites, blurb updates, cost range updates) is factual and templated
- Hermes 3 8B handles this well at zero API cost
- Claude can flag legal content as sensitive and refuse — Strauss does not have this limitation
- Reserve Claude for complex rewrites, new page builds, or when Strauss output quality is poor

**Quality check:** If Strauss output contains first-person advice ("you should..."), hallucinated
case law, or specific legal strategy, regenerate using Claude with this prompt file as system context.

---

## GIT COMMIT FORMAT

```
[FreeLegalIQ] Refresh [Page Name] — [Month YYYY]

- Updated quick-answer blurb with current [year] cost data
- Rewrote FAQ [N] answers with updated [topic] rates
- Updated sitemap lastmod to [date]
- [Any other notable changes]
```

---

## PAGE INDEX

| Index | File | Display Name | Topic |
|-------|------|--------------|-------|
| 0 | divorce-cost-calculator.html | Divorce Cost Calculator | divorce cost by state 2026 |
| 1 | dui-cost-calculator.html | DUI Cost Calculator | DUI total cost by state 2026 |
| 2 | personal-injury-settlement-calculator.html | Personal Injury Settlement Calculator | personal injury settlement average 2026 |
| 3 | estate-planning-cost-calculator.html | Estate Planning Cost Calculator | estate planning attorney cost 2026 |
| 4 | llc-formation-cost-calculator.html | LLC Formation Cost Calculator | LLC formation cost by state 2026 |
| 5 | bankruptcy-cost-calculator.html | Bankruptcy Cost Calculator | bankruptcy filing cost 2026 |
| 6 | child-support-calculator.html | Child Support Calculator | child support calculation by state 2026 |
| 7 | speeding-ticket-cost-calculator.html | Speeding Ticket Cost Calculator | speeding ticket cost by state 2026 |
| 8 | immigration-fee-calculator.html | Immigration Fee Calculator | USCIS filing fees 2026 |
| 9 | personal-injury-settlement-calculator.html | Small Claims Court Calculator | small claims court limit by state 2026 |
