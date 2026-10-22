# bruno-collections-catalog

An [OpenCollection](https://www.opencollection.com) API Catalog of every
collection and workspace in the
[bruno-collections](https://github.com/bruno-collections) GitHub org.

The org has not claimed a namespace in the Bruno Registry yet, so the catalog
owner and every entry's namespace is the git host form,
`github.com/bruno-collections`. After a claim, `@bruno-collections` becomes an
alias and these entries keep working.

## Layout

```
catalog.yml          name, scope (org), owner, logo, links, contact, tag vocabulary
<folder>/folder.yml  folder name, order and the category tag its entries inherit
<folder>/<name>.yml  one entry per collection or workspace
```

Nine folders: Getting Started, Authentication, Secrets, Scripting, Protocols,
CI and CD, AI, Bruno Features, Demos and Workspaces. 45 entries: 40
collections and 5 workspaces. A workspace and each collection inside it are
separate entries, because they are separate artifacts.

An entry holds only what a curator decides: listing name, a one-line `summary`,
namespace, type, tags, order, `featured`, `format`, and where the collection
lives under `source`: `git` today, and `registry` once the org publishes to the
Bruno Registry. Adding a location never rewrites the others.

Not listed: the scratch collections in `sample-workspace` (`test`,
`TestFSystem`, `ocyaml`), `oauth1/tests/fixtures/bru` (the same test collection as the
listed YAML copy) and repos with no collection (`bruno-agent-skills`,
`Ubuntu-India-workshop`, `random-dynamic-variables`, `.github`).

## Bundle

```bash
npm run bundle        # catalog.bundled.yml
npm run bundle:json   # catalog.bundled.json
```

Needs `@opencollection/parser` from a sibling checkout of `opencollection`
(`../opencollection`, branch `feat/catalog-spec`) until it is published.
Bundled output is generated on demand and not committed.

## Spec

Format: `https://schema.opencollection.com/catalog/v1.0.0.json`.
