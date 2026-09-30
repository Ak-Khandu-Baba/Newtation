# The Newtation GEO Audit Framework

Version 1.0 · September 2026 · Maintained by [Newtation](https://www.newtation.ai)

This framework describes how Newtation audits a brand's visibility in AI-generated answers from ChatGPT, Perplexity, Claude, Gemini, Google AI Overviews and Microsoft Copilot. It is the same method we use on client work, published so anyone can run it, check it, or argue with it.

## The core idea

A search engine returns ten links and lets the reader choose. A generative engine writes one answer and names two or three sources. The sources it names are not always the pages that rank best. They are the pages whose claims a model can extract, attribute, and stand behind.

So the audit asks one question in several ways: **when a model answers a buyer's question in your category, can it find you, understand you, trust you, and quote you?**

## The dimensions

| # | Dimension | The question it answers | File |
|---|---|---|---|
| 0 | Access | Can AI crawlers reach and render the page at all? | [00-access.md](00-access.md) |
| 1 | Entity | Does the model know what you are, and can it verify that off-site? | [01-entity.md](01-entity.md) |
| 2 | Extractability | Does a claim survive being lifted off the page? | [02-extractability.md](02-extractability.md) |
| 3 | Structure | Is the page machine-verifiable, or only human-readable? | [03-structure.md](03-structure.md) |
| 4 | Corroboration | Does anyone other than you say it? | [04-corroboration.md](04-corroboration.md) |
| 5 | Measurement | Are you named, for which questions, on which engines? | [05-measurement.md](05-measurement.md) |

Access is a gate. If it fails, the other scores do not mean much, because the model never saw the page. Measurement is the outcome. Dimensions 1 to 4 are the levers.

## Scoring

Each of dimensions 0 to 4 is scored 0 to 20 from its checklist. The five scores add up to an **AI Readiness** score out of 100.

| Score | Grade | What it usually means |
|---|---|---|
| 85–100 | A | Legible and corroborated. Gaps are query-specific. |
| 70–84 | B | Sound foundation, one weak dimension holding it back. |
| 55–69 | C | Readable on-site, under-confirmed off-site. The most common result. |
| 40–54 | D | Structural problems that stop models from using the site. |
| 0–39 | F | Access or entity failure. Fix this before anything else. |

AI Readiness predicts whether a brand *can* be cited. Measurement (dimension 5) shows whether it *is* cited. Report both, because a high score with zero citations points to a corroboration or query-coverage gap, not a technical one.

## Evidence levels

Every finding in an audit should carry one of these labels. The model outputs and crawl tools this work depends on are noisy, and an audit that sounds more certain than its evidence is worse than no audit.

| Label | Use when |
|---|---|
| **Confirmed** | Verified directly, by at least two independent methods where possible. |
| **Strongly supported** | One reliable method plus supporting signals. |
| **Directional** | Derived from sampling or manual scoring. Useful for ranking, not for absolute claims. |
| **Likely** | A reasoned inference from partial evidence. |
| **Unclear** | The evidence conflicts. Say so and name what would settle it. |

## Validation rules

Three rules that prevent most bad audit findings:

1. **Check the root domain first.** Before auditing a subpage, confirm the root domain resolves, returns 200, and is crawlable. A healthy subpage on a broken root domain still gives a model nothing to anchor the brand to.
2. **Never call a page empty from one signal.** If a crawler reports near-zero words, verify with a second method (direct fetch, rendered DOM, search snippet). If content visibly exists, the finding is a *crawl/render mismatch*, not a thin page.
3. **Pick competitors by context, not category.** Order of preference: same geography, same business model, same service type, same pricing format, then broader alternatives. A local business compared against global SaaS brands produces a meaningless rank.

## How to run it

1. Run the Access checks on the root domain and the target pages.
2. Score Entity, Extractability, Structure and Corroboration using each file's checklist.
3. Build a query set with [templates/test-prompts.md](../templates/test-prompts.md) and run it across engines.
4. Record who is named for each query, and report the gap between readiness and actual citations.
5. Prioritise the fixes that close the gap for the queries that carry buying intent.

## Citing this framework

> Khandelwal, A., & Parsai, K. (2026). *The Newtation GEO Audit Framework* (Version 1.0). Newtation. https://github.com/Ak-Khandu-Baba/Newtation

See [CITATION.cff](../CITATION.cff) for BibTeX and other formats.
