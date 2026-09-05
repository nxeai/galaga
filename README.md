# Galaga

Galaga is a personal operating system for Codex. I am building it to automate
my job (startup CTO) while still staying in control.

Galaga is named after the arcade game: work arrives in recurring waves, the
system learns how to handle them, and the human stays in control.

> [!CAUTION]
> **Do not use Galaga if you do not trust AI systems, OpenAI, Codex, or any
> connected service with the data and actions you place in scope.** AI can be
> wrong, misunderstand context, expose information, or take an unintended
> action. Review the code, permissions, data, recommendations, and proposed
> actions for yourself.
>
> **Use Galaga entirely at your own risk.** It is experimental and provided
> without warranties. You are responsible for how you configure and use it and
> for every decision or action you take based on it. I am not liable for your
> choices, outcomes, data loss, disclosure, or other damages arising from its
> use.

## What it does

Galaga maintains three personal artifacts:

- `context/CONTEXT.md` for goals and relevant personal context;
- `communication/COMMUNICATION.md` for communication judgment and writing;
  and
- `tasks/TASKS.md` for deciding, organizing, and executing work.

At a high level, Galaga has two motions:

- **Init:** gather information with the user and establish the personal
  artifacts.
- **Loops:** periodically use new evidence and feedback to improve the
  artifacts and help decide or act within the user's approvals.

The specific jobs, loops, and cadences are still being designed. This
repository enables no schedules or external actions by itself, and the user
can always intervene.

## Use it safely

Create your own **private repository** using Galaga as a GitHub template, then
clone that private repository and open it in Codex. Run the bootstrap skills
for the domains you want, review what they learn, and choose any future job
cadence and action permissions yourself.

Do not use the public Galaga repository as the remote for a working copy that
contains your personal data.

## Personal data

Durable personal data lives only in the three personal artifacts above.
Retrieved source material, intermediate analysis, indexes, and synchronization
state live under `.galaga/`. These files are generated from sources the user
places in scope, used as local context for Galaga jobs, and managed through the
bootstrap and update workflows.

All three personal artifacts and the entire `.galaga/` directory are ignored
by Git. Gitignore is a guard against accidental commits, not access control:
keep your repository private, review changes before pushing, and do not
force-add personal files.

Run [`$delete-my-data`](.agents/skills/delete-my-data/SKILL.md) to inventory and
delete Galaga's local personal artifacts and runtime data. The skill shows the
exact paths first, requires confirmation, and verifies that framework files
were not removed. It does not delete data from original services such as email
or chat.

If Galaga stores personal data anywhere else, that is a bug. Please send a pull
request that fixes the boundary without including the personal data itself.

## Contributing

Feedback and improvements are welcome through pull requests. I do not monitor
GitHub Issues, so please send a focused PR instead.

## License

The public Galaga framework is licensed under [Apache-2.0](LICENSE).
