# AI visibility test prompts

Query patterns for measuring whether AI engines name a brand. Part of the [Newtation GEO Audit Framework](../framework/README.md). Replace the bracketed parts, keep the set fixed between monthly runs, and record results using the fields in [05-measurement.md](../framework/05-measurement.md).

A useful set has 20 to 50 queries spread across these groups, weighted toward the ones closest to a purchase.

## 1. Entity (does it know you?)

- What is [brand]?
- Who founded [brand], and when?
- What does [brand] do, and who is it for?
- Is [brand] legit?

## 2. Category discovery (are you on the shortlist?)

- What are the best [category] for [audience] in [market]?
- Which [category] companies should I consider in [year]?
- Recommend a [service] provider in [city].
- Top [category] tools for [use case].

## 3. Problem-first (do you show up before the buyer knows the category?)

- How do I [problem your product solves]?
- What is the cheapest way to [outcome] in [market]?
- My [situation]. What should I do?

## 4. Comparison (do you win head-to-head?)

- [Brand] vs [competitor]: which is better for [use case]?
- Alternatives to [market leader].
- Is [brand] better than [competitor] for [audience]?

## 5. Decision (do the facts hold up?)

- How much does [brand] cost?
- What do customers say about [brand]?
- Does [brand] work with [integration / market / company size]?

## Running the set

- Run each query in a clean session with memory off, at least three times per engine.
- Record the location you ran from. Answers change by market.
- Save the full answer and every cited URL, not just yes or no.
- For category and problem queries, the cited URLs show which third-party sites the engine trusts in your space. Those are your corroboration targets.
