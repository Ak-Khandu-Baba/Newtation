# 3. Structure

**The question:** is the page machine-verifiable, or only readable by a person?

Structured data does not make a model cite you. It makes your facts cheaper to check, which matters when a model is choosing between sources it is more or less sure about. Structure also covers the plain HTML underneath: headings, semantic elements and internal links.

## Checklist (0–20)

| Check | Points | Pass condition |
|---|---:|---|
| Page-type schema | 5 | Each important page has schema that matches what it is: `Article`, `Service`, `Product`, `FAQPage`, `HowTo`, `LocalBusiness`, `Person`. |
| Connected graph | 4 | Schema across pages references the same `@id`s (publisher, author, organization) instead of redefining them. |
| Heading hierarchy | 3 | One `h1`, logical `h2`/`h3` nesting, headings that describe their section. |
| Author and date signals | 3 | Articles carry `author`, `datePublished` and `dateModified`, and the visible page agrees. |
| Schema matches the page | 3 | Everything in the markup is visible on the page. Markup that claims things the page does not say erodes trust. |
| Internal linking | 2 | Key pages are linked from the homepage or main navigation with descriptive anchor text. |

## How to test

- Extract all JSON-LD from a page and check it parses, validates, and describes what a reader actually sees.
- Check that the `Organization` `@id` is identical on every page.
- Disable CSS and read the page. If the structure still makes sense, crawlers will likely read it correctly too.

See [templates/faq.jsonld](../templates/faq.jsonld) and [templates/article.jsonld](../templates/article.jsonld).
