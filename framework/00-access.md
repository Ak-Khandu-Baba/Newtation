# 0. Access

**The question:** can AI crawlers reach the page and read its content?

This is a gate, not a lever. A model cannot cite what its crawler never saw. Many sites that "rank fine on Google" fail here because they block AI user agents by accident, or render their content only in client-side JavaScript that retrieval crawlers do not execute.

## Checklist (0–20)

| Check | Points | Pass condition |
|---|---:|---|
| Root domain health | 4 | Root returns 200 over HTTPS with no redirect chain longer than one hop. |
| AI crawlers allowed | 4 | `robots.txt` does not block GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot, Claude-SearchBot, PerplexityBot, Google-Extended or Bingbot for pages you want cited. |
| Content in initial HTML | 4 | The main content is present in the server response, without running JavaScript. |
| Sitemap | 3 | An XML sitemap exists, is referenced in `robots.txt`, and lists the pages you want cited with accurate `lastmod` dates. |
| No soft blocks | 3 | No bot challenge, cookie wall, or geo-block on the content for crawler traffic. |
| llms.txt | 2 | A `/llms.txt` file exists and describes the site accurately. Low weight: support across engines is inconsistent. |

## How to test

- Fetch the page with `curl -A "GPTBot"` and search the raw HTML for a sentence from the main content. If it is missing, the content depends on JavaScript.
- Read `robots.txt` line by line. A broad `Disallow: /` under `User-agent: *` blocks every crawler not listed separately.
- Check that the domain the brand uses everywhere else (bio links, directory listings, old press) resolves to the current site. Domain migrations leave old links behind; each should 301 to the equivalent new page, not the homepage.

## Common failures

- A CDN or security plugin challenges unfamiliar user agents, so AI crawlers get a challenge page instead of content.
- A single-page app returns an empty `<div id="root">` to anything that does not run JavaScript.
- A robots.txt copied from an old template blocks `GPTBot` or `Google-Extended` without anyone remembering why.

See [templates/robots-ai-crawlers.txt](../templates/robots-ai-crawlers.txt) for a starting point.
