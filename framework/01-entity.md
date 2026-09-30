# 1. Entity

**The question:** does the model know what you are, and can it verify that somewhere other than your own site?

Models reason about entities (a company, a person, a product) rather than keywords. If a model cannot tell your brand apart from a similarly named one, or holds conflicting facts about it, it will hedge or name someone it is more certain about.

## Checklist (0–20)

| Check | Points | Pass condition |
|---|---:|---|
| One canonical definition | 4 | A single sentence of the form "X is a [category] that [does what] for [whom]" appears on the homepage and matches everywhere else. |
| Organization schema | 4 | JSON-LD `Organization` with a stable `@id`, `name`, `url`, `logo`, `description`, `foundingDate`, `founder` and `address`. |
| `sameAs` identities | 4 | `sameAs` links to profiles a model can check independently: LinkedIn, Crunchbase, Wikidata, X, GitHub, industry directories. |
| Fact consistency | 4 | Name, founding date, founders, location and category agree across the site, profiles and directories. |
| People are entities too | 2 | Founders or authors have `Person` schema with `jobTitle`, `worksFor` and their own `sameAs`. |
| Disambiguation | 2 | If the name is shared with anything else, the site says clearly which one you are (category, location, domain). |

## How to test

- Ask each engine "What is [brand]?" and "Who founded [brand]?" with no other context. Record whether it knows, whether it is right, and which sources it cites.
- List every public profile of the brand and compare the facts field by field. Mismatched founding years and old domains are the usual culprits.
- Validate the JSON-LD with the Schema.org validator and check that `@id` values match across pages.

## Domain changes

When a brand moves domains, the old domain lives on in directories, press and model training data. Handle it on purpose:

- 301 every old URL to its new equivalent.
- State the change in plain text somewhere crawlable ("Newtation, formerly at newtationco.app, is now at newtation.ai").
- Update every profile you control, then the directories you do not.

See [templates/organization.jsonld](../templates/organization.jsonld).
