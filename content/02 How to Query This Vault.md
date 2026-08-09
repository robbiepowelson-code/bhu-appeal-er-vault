---
title: How to Query This Vault
tags: [index]
---

# How to Query This Vault

## Global search (Cmd-Shift-F)

- `"reasonable accommodation"` — exact phrase across all 2,197 ER pages.
- `path:Declarations shelter` — the word *shelter* only within declarations.
- `path:"Orders & Rulings" ADA` — what the district court said about the ADA.
- `tag:#prado notice` — search only Prado-case documents.
- `file:(ER 0097) irreparable` — search inside a specific document (the summary-judgment order).

## Frontmatter queries

Every document note carries metadata you can filter on: `type`, `case`, `filed`, `docket`, `er_start`/`er_end`, `volume`, `cite`, `filed_by`, `parent`. With the Dataview plugin installed you can run, e.g.:

```dataview
TABLE cite, filed, docket FROM "Documents/Declarations" WHERE case = "BHU" SORT filed DESC
```

## Finding the exact cite

Each search hit sits under an `## ER-###` heading — that number is the ER page. The proper record cite is `volume-ER-page` (each note's header line shows its volume), e.g. text on ER-402 in Volume 3 is cited **3-ER-402**.

## Typical opposition-brief workflows

- **Rebut a factual claim in the City's opening brief:** search [[City's Opening Brief (26-2755, 26-2823)]] for the claim, note what the City cites, open that ER note, then search neighboring documents (same docket entry, opposing declarations) for contrary evidence.
- **Build the standard-of-review record:** search `path:"Orders & Rulings"` for the district court's findings — findings reviewed for clear error are your friends.
- **Collect witness statements on a topic:** search `path:Declarations <topic>` and log each hit in [[Evidence Log]].
- **Trace a docket entry:** search the two Docket Sheet notes for the docket number to see the full procedural context.
