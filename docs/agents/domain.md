# Domain Docs

How the engineering skills should consume this repo's domain documentation when exploring the codebase.

**Layout: multi-context.** Each context (sub-project) owns its own `GLOSSARY.md`; a single `GLOSSARY-MAP.md` at the repo root points at them. There is no repo-root `GLOSSARY.md`.

**Nothing exists yet, on purpose.** `GLOSSARY-MAP.md` and the per-context `GLOSSARY.md` files are created lazily — the first time a term or decision actually gets resolved. Until then their absence is normal: proceed silently, do not flag it, and do not create empty placeholders.

## Before exploring, read these

- **`GLOSSARY-MAP.md`** at the repo root — it points at one `GLOSSARY.md` per context. Read each one relevant to the topic you are about to work on.
- **`docs/adr/`**: system-wide decisions. Read the ADRs that touch the area you're about to work in.
- **`<context>/docs/adr/`**: context-scoped decisions for the sub-project you're editing.

If any of these files don't exist, **proceed silently**. Don't flag their absence; don't suggest creating them upfront. The `/domain-modeling` skill (reached via `/grill-with-docs` and `/improve-codebase-architecture`) creates them lazily when terms or decisions actually get resolved.

## File structure

Multi-context repo (this repo):

```
/
├── GLOSSARY-MAP.md                    ← created with the first real entry
├── docs/adr/                          ← system-wide decisions
└── <context>/
    ├── GLOSSARY.md                    ← that context's vocabulary
    └── docs/adr/                      ← context-specific decisions
```

When the first glossary entry is written in a context, create that context's `GLOSSARY.md` and register it in the root `GLOSSARY-MAP.md` in the same change. Keep `GLOSSARY-MAP.md` a pointer file: one line per context, path plus a one-line scope description. It carries no terms of its own.

## Use the glossary's vocabulary

When your output names a domain concept (in an issue title, a refactor proposal, a hypothesis, a test name), use the term as defined in the relevant `GLOSSARY.md`. Don't drift to synonyms the glossary explicitly avoids.

If the concept you need isn't in the glossary yet, that's a signal: either you're inventing language the project doesn't use (reconsider) or there's a real gap (note it for `/domain-modeling`).

## Flag ADR conflicts

If your output contradicts an existing ADR, surface it explicitly rather than silently overriding:

> _Contradicts ADR-0007 (event-sourced orders), but worth reopening because…_
