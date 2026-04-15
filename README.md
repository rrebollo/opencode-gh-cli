# gh-cli Skill for OpenCode

Master the GitHub CLI for pull requests, issues, releases, Actions workflows, and raw API calls.

## What This Skill Does

This is an **OpenCode Skill** that provides agentic patterns for the GitHub CLI (`gh`). Use it when you need OpenCode to:

- Create, review, and merge pull requests
- Manage GitHub issues with triage and linking
- Trigger and manage Actions workflows
- Create releases and manage GitHub API calls
- Query the GitHub API efficiently with token-aware jq filtering
- Work with repositories, forks, and stars

The skill prioritizes **token efficiency** — all patterns use `--jq` filtering, field minimization, and output bounding to reduce LLM token consumption during agentic operations.

### Metadata

| Field | Value |
|-------|-------|
| **Name** | `gh-cli` |
| **License** | MIT |
| **Tested against** | `gh` v2.89.0 |
| **Use case** | Git/GitHub automation, PR management, Actions workflows, API queries |

## Installation

OpenCode automatically discovers skills in these directories:

```
.opencode/skills/<name>/SKILL.md          (project-local)
~/.config/opencode/skills/<name>/SKILL.md (global)
```

Choose one of the three installation methods below:

### Option A: Clone and Copy (Recommended for most users)

```bash
git clone https://github.com/rrebollo/opencode-gh-cli.git
cp -r opencode-gh-cli/skills/gh-cli ~/.config/opencode/skills/
cd ~ && rm -rf opencode-gh-cli
```

The skill is now available to OpenCode. Restart your OpenCode session and it will auto-discover `gh-cli`.

### Option B: Sparse Clone (Minimal disk footprint)

If you want to clone only the skill without the full repository history:

```bash
git clone --filter=blob:none --sparse https://github.com/rrebollo/opencode-gh-cli.git
cd opencode-gh-cli
git sparse-checkout set skills/gh-cli
cp -r skills/gh-cli ~/.config/opencode/skills/
cd ~ && rm -rf opencode-gh-cli
```

### Option C: Git Submodule (For power users with a versioned ~/.config/opencode)

If you manage your OpenCode config as a git repository:

```bash
cd ~/.config/opencode
git submodule add https://github.com/rrebollo/opencode-gh-cli.git skills/gh-cli-repo
ln -s skills/gh-cli-repo/skills/gh-cli skills/gh-cli
git add .gitmodules .
git commit -m "Add gh-cli skill as submodule"
```

Then pull updates with:

```bash
git submodule update --remote
```

## Using the Skill

In OpenCode, the skill is loaded automatically by the agent when relevant. You can:

1. **List available skills** in the TUI with:
   ```
   /skills
   ```

2. **Ask OpenCode to use the skill** in natural language:
   ```
   Use the gh-cli skill to create a PR for this branch
   ```

OpenCode will load the full skill content and use the patterns to execute your request.

## Skill Contents

The skill contains 7 reference documents organized by workflow, plus the core skill definition:

| File | Purpose |
|------|---------|
| `SKILL.md` | Core skill definition, agentic output principles, token efficiency rules |
| `agentic-patterns.md` | Decision tree for token-efficient command selection, minimal field catalog, output bounding |
| `pr-workflows.md` | PR creation, viewing, reviewing, merging, branches, advanced patterns |
| `issue-workflows.md` | Issue creation, listing, editing, triaging, linking branches |
| `actions-and-ci.md` | Run management, workflow triggers, secrets, variables, caches, advanced patterns |
| `repo-management.md` | Repo clone/create/fork/edit, releases, attestations |
| `search-and-query.md` | Search qualifiers, REST API, GraphQL queries, pagination |
| `output-formatting.md` | Full JSON field reference, jq operators, Go templates |

## How OpenCode Discovers Skills

See the [OpenCode Skills Documentation](https://opencode.ai/docs/skills/) for:

- How to write your own skills
- Permission and permission override syntax
- Skill naming rules and validation
- Troubleshooting skill loading

## License

MIT — See `LICENSE` file for details.

## Contributing

Found a bug or want to improve the skill? Open an issue or PR:

https://github.com/rrebollo/opencode-gh-cli/issues

## Related

- [OpenCode Documentation](https://opencode.ai/docs/)
- [GitHub CLI Manual](https://cli.github.com/manual/)
- [OpenCode Ecosystem](https://opencode.ai/docs/ecosystem/)
