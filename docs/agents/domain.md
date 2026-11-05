# Domain Docs

How the engineering skills should consume this repo's domain documentation when exploring the codebase.

## This project: where the glossary and decisions live

This repo is an Obsidian vault for the SGE (school management system, IPCAG N.º 12008 / BGO). It has **no `GLOSSARY.md` and no `docs/adr/`**: those roles are filled by existing notes, and each kind of information has exactly one home (see `01 - Projetos/SGE - IPCAG 12008 BGO/00 - Navegacao/00.3 - Proposta de Organizacao Documental.md` §2).

| Role in these skills | File in this vault |
| :--- | :--- |
| Glossary (ubiquitous language) | `01 - Projetos/SGE - IPCAG 12008 BGO/10 - Especificacao/01 - Dominio e Regras.md` §1 |
| Business rules `RN-xx`, RBAC, state machines | same file, §2–§4 |
| ADRs / decisions (`DEC-xxx`) and open questions (`Q-xxx`) | `01 - Projetos/SGE - IPCAG 12008 BGO/30 - Decisoes/12 - Registo de Decisoes e Questoes em Aberto.md` |
| ID numbering rules (RN, DOF, épicos) | `01 - Projetos/SGE - IPCAG 12008 BGO/00 - Navegacao/00.2 - Mapa de Integracao v2.0.md` |

Rules for `/domain-modeling` and the skills that use it:

- **Do not create `GLOSSARY.md` or `docs/adr/`.** Add new terms to DOC-01 §1 and new decisions as `DEC-nnn` entries in REG-12, using the templates in REG-12 §4.
- Notes in `99 - Arquivo/` are history only. Never treat them as the source of truth; `Fontes Integradas v2.0/` (C03–C16) was merged into DOC-01…05.
- Write in European/Angolan Portuguese, like the rest of the vault.

The generic layout below applies only if the code later lives in its own repo.

## Before exploring, read these

- **`GLOSSARY.md`** at the repo root, or
- **`GLOSSARY-MAP.md`** at the repo root if it exists: it points at one `GLOSSARY.md` per context. Read each one relevant to the topic.
- **`docs/adr/`**: read ADRs that touch the area you're about to work in. In multi-context repos, also check `src/<context>/docs/adr/` for context-scoped decisions.

If any of these files don't exist, **proceed silently**. Don't flag their absence; don't suggest creating them upfront. The `/domain-modeling` skill (reached via `/grill-with-docs` and `/improve-codebase-architecture`) creates them lazily when terms or decisions actually get resolved.

## File structure

Single-context repo (most repos):

```
/
├── GLOSSARY.md
├── docs/adr/
│   ├── 0001-event-sourced-orders.md
│   └── 0002-postgres-for-write-model.md
└── src/
```

Multi-context repo (presence of `GLOSSARY-MAP.md` at the root):

```
/
├── GLOSSARY-MAP.md
├── docs/adr/                          ← system-wide decisions
└── src/
    ├── ordering/
    │   ├── GLOSSARY.md
    │   └── docs/adr/                  ← context-specific decisions
    └── billing/
        ├── GLOSSARY.md
        └── docs/adr/
```

## Use the glossary's vocabulary

When your output names a domain concept (in an issue title, a refactor proposal, a hypothesis, a test name), use the term as defined in `GLOSSARY.md`. Don't drift to synonyms the glossary explicitly avoids.

If the concept you need isn't in the glossary yet, that's a signal: either you're inventing language the project doesn't use (reconsider) or there's a real gap (note it for `/domain-modeling`).

## Flag ADR conflicts

If your output contradicts an existing ADR, surface it explicitly rather than silently overriding:

> _Contradicts ADR-0007 (event-sourced orders), but worth reopening because…_
