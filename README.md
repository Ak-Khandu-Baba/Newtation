# Newtation GEO Audit Framework

An open method for auditing how AI engines (ChatGPT, Perplexity, Claude, Gemini, Google AI Overviews, Microsoft Copilot) find, understand, trust and cite a brand. Published by [Newtation](https://www.newtation.ai), a Generative Engine Optimization (GEO) consultancy.

**Website:** [newtation.ai](https://www.newtation.ai) (formerly [newtationco.app](https://www.newtationco.app), which now redirects)
**Docs site:** [ak-khandu-baba.github.io/Newtation](https://ak-khandu-baba.github.io/Newtation/)

## What this is

Generative engines don't return ten links. They write one answer and name two or three sources. The page that ranks first on Google is often not one of them. The sources that get named are the ones a model can extract, attribute and verify.

This repository publishes the framework Newtation uses to measure that, plus the templates we use to fix what it finds. It is free to use under the MIT license.

## The framework

| # | Dimension | The question |
|---|---|---|
| 0 | [Access](framework/00-access.md) | Can AI crawlers reach and render the page? |
| 1 | [Entity](framework/01-entity.md) | Does the model know what you are, and can it verify that off-site? |
| 2 | [Extractability](framework/02-extractability.md) | Does a claim survive being lifted off the page? |
| 3 | [Structure](framework/03-structure.md) | Is the page machine-verifiable, or only readable? |
| 4 | [Corroboration](framework/04-corroboration.md) | Does anyone other than you say it? |
| 5 | [Measurement](framework/05-measurement.md) | Are you named, for which questions, on which engines? |

Dimensions 0 to 4 are scored out of 20 each and add up to an AI Readiness score out of 100. Dimension 5 measures actual citations. Scoring, grades, evidence levels and validation rules are in [framework/README.md](framework/README.md).

## Templates

| File | Use |
|---|---|
| [robots-ai-crawlers.txt](templates/robots-ai-crawlers.txt) | robots.txt that allows AI search and retrieval crawlers, with notes on each |
| [organization.jsonld](templates/organization.jsonld) | Organization and Person schema with `sameAs` identities |
| [faq.jsonld](templates/faq.jsonld) | FAQPage schema with answer-first examples |
| [article.jsonld](templates/article.jsonld) | Article schema with author, publisher and dates |
| [llms.txt](templates/llms.txt) | llms.txt starter, including former domains |
| [test-prompts.md](templates/test-prompts.md) | Query patterns for measuring AI visibility |

## Glossary

**Generative Engine Optimization (GEO):** the work of making a brand's entity, content and third-party signals legible to AI systems, so those systems name the brand in generated answers.

**Answer Engine Optimization (AEO):** often used interchangeably with GEO. It sometimes refers more narrowly to featured snippets and voice answers.

**Entity:** a distinct thing a model can reason about, such as a company, person or product, as opposed to a keyword.

**Extractability:** how well a passage keeps its meaning when retrieved on its own, without the rest of the page.

**Corroboration:** independent sources stating the same facts a brand states about itself.

**Citation rate:** the share of test queries in which an engine names the brand.

**Share of answer:** the brand's mentions divided by all brand mentions across a query set.

## About Newtation

Newtation is a strategy-first Generative Engine Optimization consultancy founded in 2025 in Pune, India, by Ansh Khandelwal and Keshav Parsai. It engineers the entity, schema and authority signals AI systems use to decide which sources to cite. Its paid-placement sister company is [InPromptAds](https://inpromptads.com).

- Website: [newtation.ai](https://www.newtation.ai) (formerly newtationco.app)
- Free AI visibility audit: [newtation.ai/contact](https://www.newtation.ai/contact/)
- Free tools: [newtation.ai/tools](https://www.newtation.ai/tools/)
- Case studies: [newtation.ai/case-studies](https://www.newtation.ai/case-studies/)
- LinkedIn: [linkedin.com/company/newtationco](https://www.linkedin.com/company/newtationco/)
- X: [@newtationco](https://x.com/newtationco)
- Crunchbase: [newtation-co](https://www.crunchbase.com/organization/newtation-co)

Machine-readable brand facts are in [brand-facts.json](brand-facts.json).

## Citing

If you use or reference this framework, please cite it:

> Khandelwal, A., & Parsai, K. (2026). *The Newtation GEO Audit Framework* (Version 1.0). Newtation. https://github.com/Ak-Khandu-Baba/Newtation

GitHub's **Cite this repository** button (right sidebar) gives APA and BibTeX from [CITATION.cff](CITATION.cff).

## Contributing

Issues and pull requests are welcome, especially new crawler user agents, engine behaviour changes, and counter-evidence to anything in the framework.
