# Galaga

Galaga is a user-owned, version-controlled personal operating system for Codex.
It helps Codex build an enduring understanding of how a person works, then use
that understanding to improve decisions and actions over time.

The initial user is a hands-on startup CTO. Galaga is designed around two
output pillars:

- **Communication:** decide what communication should happen, then act in the
  appropriate medium.
- **Tasks:** decide what work deserves attention, then act on committed work.

Galaga runs jobs. A job may be triggered manually or on a schedule. Bootstrap
jobs establish an initial personal model; update jobs review new evidence and
improve it. Users can inspect, redirect, pause, or manually run the system at
any time.

## Repository model

Galaga separates personal artifacts from framework files:

- Unsuffixed pillar and context files, such as `COMMUNICATION.md`, are private,
  user-owned artifacts intended to evolve with the user.
- Suffixed files, such as `COMMUNICATION-SPEC.md`,
  `COMMUNICATION-BOOTSTRAP.md`, and `COMMUNICATION-UPDATE.md`, are public
  framework files that define desired outcomes and reusable workflows.
- `.agents/skills/` contains thin, repo-scoped entrypoints for running Galaga
  jobs with Codex.
- `.galaga/` contains local runtime state and cached source material. It is
  ignored by Git and should be safe to inspect or delete.

```text
.
├── AGENTS.md
├── .agents/skills/
├── pillars/
│   ├── communication/
│   └── tasks/
├── context/
├── utilities/
└── .galaga/          # local and gitignored
```

The root `AGENTS.md` is the navigation and ownership contract for agents
working in this repository.

## Status

Galaga is in early product definition. The checked-in files capture the
current product model and create a battle-testable starting point. They are
expected to change as real usage exposes better structures and workflows.

No scheduled jobs are activated by this repository alone. Users must choose
sources, permissions, cadence, notification behavior, and external-action
authority before enabling recurring work.

## License and personal data

The framework, skills, specifications, job definitions, scripts, and
documentation in the public Galaga project are licensed under Apache-2.0.

Personal data, memories, journals, profiles, writing samples, goals, and other
user-created content in a private repository remain the property of their
respective users. Personal artifacts must never be included in an upstream
Galaga contribution without explicit, informed user direction.
