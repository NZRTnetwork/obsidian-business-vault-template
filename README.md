# Obsidian Business Vault Template

A structured Obsidian knowledge vault for solo operators, micro-businesses, and small remote teams. Built from a real production system — NZRT Network uses this exact structure to run a 9-agent AI virtual organisation.

## What This Solves

Most Obsidian users start with a flat folder of notes and end up with chaos. This template gives you:

- A consistent **frontmatter schema** so every note is queryable and filterable
- A **service code system** that tags notes to the business system they belong to
- A **role code system** that assigns ownership of every note
- A **MOC (Map of Content) pattern** so navigation never breaks as the vault grows
- A **HOME.md convention** — every folder has an index note
- **Wikilink conventions** — full path + display text, always

## Who This Is For

- Solo operators running multiple systems (CRM, ERP, wiki, project mgmt)
- Small remote teams who need a shared knowledge base
- Anyone using Obsidian for business documentation, not just personal notes
- Claude Code users who want their vault to work with AI agents

## What's Included

```
obsidian-business-vault-template/
├── CLAUDE.md                    # AI agent instructions for this vault
├── HOME.md                      # Master vault index (copy of template)
├── schema.md                    # Frontmatter schema, codes, conventions
├── Templates/
│   ├── New Note.md              # Default note template
│   ├── Project.md               # Project tracking template
│   ├── Meeting.md               # Meeting notes template
│   ├── SOP.md                   # Standard operating procedure template
│   └── System Reference.md      # Technical system reference template
├── Example Structure/
│   ├── HOME.md                  # Example domain HOME (MOC)
│   ├── 01 - Overview/
│   │   └── Overview.md
│   └── 02 - Reference/
│       └── Reference.md
└── .obsidian/
    └── (minimal config — snippets, templates path)
```

## Quick Start

1. Download or clone this repo
2. Open the folder as a new Obsidian vault (`Open folder as vault`)
3. Read `schema.md` — understand the frontmatter conventions before creating notes
4. Copy your domain folders into the structure (Dolibarr/, GitHub/, Nextcloud/, etc.)
5. Update `HOME.md` with your vault map

## The Schema (Frontmatter)

Every note should have this frontmatter:

```yaml
---
tags: [<domain-tag>, <org-tag>, <service-code>, <note-type>]
aliases: [Human readable name, Alternative name]
role: <role-code>        # who owns/maintains this note
created: YYYY-MM-DD
status: draft|review|active|complete|archived
type: MOC|guide|reference|config|adr|schema
related:
  - "[[path/to/related-note|Display Name]]"
---
```

## Service Code System

Assign one service code per note as a tag. This lets you filter all notes related to a system:

| Code | System |
|------|--------|
| `000MST` | Master / vault root |
| `000DOL` | Dolibarr ERP |
| `000GIT` | GitHub / version control |
| `000LLM` | AI / LLM tooling |
| `000NCL` | Nextcloud |
| `000WEB` | WordPress / web |
| `000INF` | Infrastructure |
| `000K8S` | Kubernetes |

Add your own codes for your systems — keep them 6 characters, uppercase.

## Role Code System

Assign ownership of every note:

| Code | Who |
|------|-----|
| `xc` | Admin / owner |
| `pam` | Marketing |
| `cas` | Sales / CRM |
| `fin` | Finance |
| `han` | HR |
| `ema` | Documents / EDM |
| `dai` | Analytics |
| `dan` | DBA / infra |

Rename these to match your team. The pattern is what matters, not the specific codes.

## Wikilink Convention

Always use full path from vault root + display text:

```
[[Domain/Subfolder/Note Name|Human Readable Title]]
```

Never use bare `[[Note Name]]` — breaks when files move.

## HOME.md Convention

Every folder gets a `HOME.md` — the index for that domain. Type: `MOC`. Links to every note in the folder. This is how you navigate without relying on search.

## Works With Claude Code

Include a `CLAUDE.md` at vault root to give AI agents context about your vault structure. The included `CLAUDE.md` is a template — fill in your own org details.

## Real-World Usage

This template is extracted from [NZRT Network](https://nzrtnetwork.com)'s production vault — a 9-agent AI virtual organisation running Dolibarr ERP, Nextcloud, and WordPress, all documented in this structure.

## License

MIT — use freely, adapt for your business.

---

*Built by NZRT Network · [nzrtnetwork.com](https://nzrtnetwork.com)*
