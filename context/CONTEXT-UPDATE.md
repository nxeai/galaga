# Update context

## Purpose

Create, enrich, correct, and refresh `CONTEXT.md` through one incremental
protocol. Follow the shared update rules in `AGENTS.md`. The steady-state
target is the user's tools and channels, role, team, projects, initiatives,
and goals. A useful first version may cover only one situation.

## Workflow

1. Read `CONTEXT-SPEC.md` and relevant existing context, if present. Missing
   files are initialized; partial files are preserved and improved.
2. Start from the immediate task and available evidence. For a Slack reply,
   learn the relevant workspace, channel, people, project, and goal. Retrieve
   the current thread when drafting rather than trusting a cached snapshot.
3. Discover tools progressively across email, chat, docs, calendar, project
   management, development, professional networks, and other relevant areas.
   Learn their purpose, channels, correct account, and source-of-truth role.
4. Check available capabilities before recommending setup. Prefer suitable
   existing plugins, connectors, CLIs, APIs, or MCP servers; use browser control
   when appropriate. Explain the next concrete setup step and bounded read.
   Use existing authorization and obtain approval for new access or scope.
   Authentication belongs in the service's flow, never in personal files.
5. Retrieve a small useful orientation slice within the run's budget, such as
   a thread, selected project overview, or team directory. Reuse cached
   evidence. Unavailable integrations do not block work from supplied material.
6. Reconcile role, relationships, ownership, projects, initiatives, goals,
   tools, and channels. Distinguish explicit statements, observed facts,
   inference, and conflict. Date volatile claims and retain source references.
   Conversation frequency alone does not establish reporting lines.
7. Ask one focused question when an ambiguity materially affects the task.
   Review consequential interpretations and changed goals with the user;
   scheduled runs queue unresolved review items.
8. Create or revise `CONTEXT.md` in the spec's structure using supported
   knowledge. Mark unexplored areas explicitly. Preserve existing meaning
   and avoid requiring a complete interview.
9. Check the result against the spec and continue the immediate task. Report
   useful changes and material limitations proportionately.

## Recurring runs and completion

Hourly or daily runs follow the same protocol within established scope and
budget. Prioritize corrections, consequential changes, then coverage gaps.
Keep raw activity, cursors, and pending evidence under `.galaga/`; retain useful
summaries of current work and durable context in `CONTEXT.md`.

A run may initialize a useful partial artifact, improve it, queue review, or
make no change. Run completion does not mean the user's context is fully learned.
