# Context specification

## Purpose

`CONTEXT.md` should give a fresh Codex agent the smallest durable set of goals
and personal background needed to make better communication and task
decisions. It should prevent repeated reconstruction without becoming an
exhaustive dossier or a duplicate of operational systems.

Keep context in one artifact until real usage shows that splitting it would
improve navigation or reduce context cost. Use the required structure below so
a fresh agent can find the same kinds of context quickly.

## Required structure

`CONTEXT.md` must contain these top-level sections in this order. A section may
say that information is unknown or not yet provided, but it should not be
silently omitted. Add subsections when they materially improve navigation.

### 1. Snapshot

A compact orientation: who the user is, their current situation, the scope of
this context, and when it was last meaningfully reviewed. This should help an
agent decide which later sections are relevant, not summarize the whole file.

### 2. Job

Cover the user's current role and work environment, including:

- title or function, organization, and relevant company or team stage;
- responsibilities, recurring concerns, and what success looks like;
- scope of ownership, decision authority, and important constraints; and
- current work context that changes how the role should be understood.

### 3. Goals

Cover the outcomes the user is actively trying to produce, including:

- current goals and their relative priority;
- time horizon, motivation, and observable signs of progress or completion;
- durable direction versus temporary priorities; and
- tensions, tradeoffs, dependencies, and explicit non-goals.

Do not turn every active task into a goal. Prefer outcomes that should shape
decisions across multiple pieces of work.

### 4. People

Cover relationships that materially affect the user's decisions or actions,
including as applicable:

- manager or other authority figures;
- direct reports and the responsibilities they own;
- peers, collaborators, and internal stakeholders;
- customers, partners, investors, advisors, or other external stakeholders;
  and
- team and organizational structure needed to understand those relationships.

For each person or group, retain only the role, relationship, ownership,
relevant goals, and interaction context that helps Galaga reason well. Avoid
contact details, personal trivia, speculation, and sensitive information that
does not earn its cost.

### 5. Tools and systems

Begin with a compact tool registry using these columns:

| Field | What it captures |
| --- | --- |
| Category | Email, chat, docs, calendar, project management, development, professional network, or another meaningful function. |
| Tool | Product or system name. |
| Purpose and authority | What the user uses it for and what information it is the source of truth for. |
| Account or workspace | Only the organization, workspace, profile, or environment distinction needed to select the right place. |
| Access | Current approved access path and status, such as plugin, connector, CLI, API, MCP, browser control, manual, or not connected. Date volatile access claims. |
| Boundaries | Relevant scope, exclusions, permission limits, or workflow caveats. |

Consider the user's full working environment, including:

- tools and services used for email, chat, documents, calendar, planning,
  development, professional presence, execution, and records;
- the source of truth for important kinds of information;
- relevant repository, workspace, account, or environment boundaries; and
- approved access methods, current access status, retrieval expectations, and
  workflow caveats.

Name systems and explain their purpose. Do not copy their contents or store
credentials, secrets, or tokens. Record durable access context, not permission
to perform a future retrieval or action; current authorization must still be
obtained when required.

### 6. Boundaries and standing context

Cover durable context that applies across the other sections, including:

- privacy and sensitivity boundaries;
- limits on autonomy, approval, and external action;
- stable constraints and risks; and
- other enduring facts that materially affect communication or task decisions.

Keep detailed writing preferences in `communication/COMMUNICATION.md` and task
operating preferences in `tasks/TASKS.md`. Include only the cross-cutting
context needed to understand or apply them.

### 7. Open questions

Track unexplored tools, channels, teams, projects, initiatives, and goals here,
along with consequential gaps and freshness concerns. Partial coverage is a
valid initial state, not a reason to delay the user's task.

List consequential gaps, conflicts, or potentially stale claims that still
need user review. Remove an item when it is resolved and update the relevant
section.

## Scope and exclusions

Keep large source material, credentials, raw activity history, and disposable
intermediate analysis out of the artifact. Point to authoritative systems
instead of copying their contents.

## Evidence and authority

Explicit user statements and corrections are strongest. Observed behavior,
existing documents, and system configuration are evidence, not automatic
intent. Preserve uncertainty and distinguish current fact, user preference,
aspiration, inference, and stale or unverified information.

Context helps an agent reason; it does not grant permission to retrieve from a
source, act in a system, contact a person, or expose personal information.
Immediate user instructions and current facts take precedence.

## Quality criteria

Successful context is:

- **Complete:** every required section is present and covers the applicable
  minimums above or explicitly identifies what is not yet known.
- **Relevant:** each entry can materially improve a likely decision or action.
- **Current:** time-sensitive claims are dated, qualified, or removed.
- **Navigable:** an agent can find what it needs without loading everything.
- **Compact:** it avoids raw history, repetition, and cheaply retrieved facts.
- **Honest:** it preserves provenance, uncertainty, tensions, and exceptions.
- **User-owned:** consequential interpretations and goals receive user review.
- **Safe:** it minimizes sensitive detail and never expands action authority.

## Evaluation and repair

When the user's intent is to fix, clean up, improve, optimize, or otherwise
bring `CONTEXT.md` closer to this specification, first verify that every
required section is present, navigable, and adequately populated or explicitly
marked unknown. Put retained information in the correct section while
preserving supported meaning, provenance, and uncertainty. Remove duplication,
stale or unsupported claims, unnecessary sensitive detail, and content that
belongs in another personal artifact or should be retrieved on demand. Do not
invent context to fill gaps; mark material gaps or ask the user.

Then evaluate whether representative communication and task scenarios improve
when the relevant context is available. The artifact is useful only when its
context cost is justified by better decisions or less reconstruction.
