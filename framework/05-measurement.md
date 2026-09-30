# 5. Measurement

**The question:** for the questions your buyers ask, which engines name you, how do they describe you, and who do they name instead?

Measurement is the outcome the other four dimensions exist to move. It is reported per engine and per query, not as a single score, because a single number hides the part that matters: *which* questions you lose and to whom.

## What to record

For each query × engine pair:

| Field | Example |
|---|---|
| Query | best SBLC providers in Dubai |
| Engine and mode | ChatGPT (search on), Perplexity, Gemini, AI Overviews |
| Date | 2026-09-30 |
| Brand named? | Yes / No |
| Position in answer | First named, listed, or footnote-only |
| How described | Quote the sentence that names the brand |
| Accuracy | Correct / partly wrong / wrong |
| Competitors named | The other brands in the answer |
| Sources cited | Every URL the engine cites |

## Metrics

- **Citation rate:** share of queries where the brand is named, per engine.
- **Share of answer:** brand mentions divided by all brand mentions across the query set.
- **First-named rate:** share of answers where the brand is named first.
- **Source overlap:** which cited domains appear across many answers. These are the corroboration targets.
- **Accuracy rate:** share of mentions that describe the brand correctly.

## Method notes

- Answers vary between runs. Run each query at least three times per engine and record the majority result, or report the range.
- Use clean sessions with no memory or personalisation, and record the location, because answers change by market.
- Keep the query set fixed across monthly runs so changes reflect the brand, not the questions.
- Publish the prompt, the date and the full answer when you use a result as evidence. Anyone should be able to re-run it.

See [templates/test-prompts.md](../templates/test-prompts.md) for query patterns.
