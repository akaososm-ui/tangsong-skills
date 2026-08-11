---
name: tangsong-skill-github-publisher
description: "Publish local Codex/Agent skill folders to a GitHub skills repository. Use when the user wants to upload, share, package, sync, release, or update a local skill on GitHub; add a skill to an existing public skills repo; prepare a GitHub-ready skill package; update README/VERSION/install commands; or verify that npx skills add can discover the published skill."
---

# Tang Song Skill GitHub Publisher

## Overview

Turn a local skill folder into a GitHub-ready public skill package, then verify that others can install or list it from the target repository.

Default to publishing the complete skill folder, not only `SKILL.md`. Preserve the original local skill unless the user explicitly asks to edit it. Make public-safety checks before pushing.

## Inputs

Accept any of these:

- local skill folder path;
- local `SKILL.md` path;
- skill name that can be resolved under `~/.codex/skills` or `~/.agents/skills`;
- target GitHub repository, such as `owner/repo`;
- existing local publication repository path.

If the target repository is not specified, inspect the current working directory and known local publication repos. For Tang Song's own public skill pack, use `akaososm-ui/tangsong-skills` only when the local repo at `work/tangsong-skills` exists and its remote confirms that repository. For other users, ask for the target repository before pushing.

## Workflow

### 1. Resolve Source And Target

1. Locate the source skill folder. If the user gives a `SKILL.md` path, publish its parent folder.
2. Confirm it contains `SKILL.md`.
3. List all files up to a useful depth with `find`.
4. Identify referenced resources from `SKILL.md`, especially `references/`, `scripts/`, `assets/`, and `agents/openai.yaml`.
5. Resolve the publication repository:
   - prefer an existing local git checkout if the user is already using one;
   - otherwise clone or create a local working copy for the target `owner/repo`;
   - do not create a new GitHub repository unless the user explicitly wants a new repo and GitHub auth has creation permission.

### 2. Validate The Local Skill First

Run:

```bash
python3 "${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py" <skill_dir>
```

If that path does not exist, find the local `quick_validate.py` under the user's skill-creator installation, or fall back to checking:

- YAML frontmatter parses;
- frontmatter contains only `name` and `description`;
- folder name matches `name`;
- `description` is quoted when it contains colon-like punctuation;
- `agents/openai.yaml`, if present, quotes strings and has a default prompt that mentions `$skill-name`.

Fix validation failures in the source only when they are actual skill correctness issues. For public-only wording, change the publication copy instead.

### 3. Copy To A Publication Copy

Copy the full skill folder into:

```text
<repo>/skills/<skill-name>/
```

Do not copy `.git`, caches, generated outputs, temporary files, local logs, or unrelated project material.

If the repo already contains the same skill:

- diff source versus repo copy;
- update only the intended files;
- do not delete user additions unless they are stale generated files and the user asked for cleanup.

### 4. Public-Safety Scan

Before committing, scan the publication copy and repo-level docs for sensitive material:

```bash
rg -n "ghu_|ghp_|secret|password|app_secret|client_secret|Bearer|/Users/|Mobile Documents|手机号|微信号|邮箱|tenant_access_token|api[_-]?key|token" <repo>
```

Classify matches:

- real secrets, private paths, client names, private links, or personal contact info: remove or replace before publishing;
- placeholders such as `<token>` or `/your/path`: acceptable, but mention them in the check result;
- public URLs intentionally included by the user: acceptable if they are not private share links.

Never publish API keys, OAuth tokens, private customer records, unpublished transcripts, or personal vault paths.

### 5. Update Repository Docs

Update the repository README only at the repo level, not inside the skill folder unless that repository already uses per-skill README files.

Include:

- skill name;
- concise use case;
- main outputs;
- install command:

```bash
npx -y skills add owner/repo --skill skill-name -g
```

- all-skills command:

```bash
npx -y skills add owner/repo -g --all
```

- important dependencies, such as GitHub CLI, MCP connectors, Feishu, GetNote, or local tools;
- privacy or license notes when relevant.

If the repository has `VERSION`, bump a patch version for wording-only updates, minor version for a new skill, and major version only for breaking layout or install changes.

### 6. Commit And Push

Before committing:

```bash
git status --short
git diff --stat
```

Then commit with a direct message, for example:

```bash
git add README.md VERSION skills/skill-name
git commit -m "Add skill-name skill"
git push
```

If GitHub auth fails:

- run `gh auth status`;
- if repository creation fails, refresh `repo` scope or ask the user to create an empty repo;
- if push fails, report the exact remote and branch.

### 7. Verify The Published Skill

After pushing, verify both GitHub and install discovery:

```bash
gh repo view owner/repo --json url,visibility,defaultBranchRef,pushedAt
gh api repos/owner/repo/contents/skills/skill-name/SKILL.md --jq '.path + " " + .sha'
npx -y skills add owner/repo --list
```

If possible, verify the specific skill can be listed or installed:

```bash
npx -y skills add owner/repo --skill skill-name --list
```

For release archives, export from the committed state:

```bash
git archive --format=zip --output=<outputs>/repo-version.zip HEAD
```

## Output

Report:

- source skill path;
- GitHub repository URL;
- commit hash;
- version bump, if any;
- validation result;
- sensitive-scan result, distinguishing placeholders from real risks;
- install command for the published skill;
- backup archive path, if created.

Keep the final answer concise. If publishing is blocked by permission, leave a clean local commit or package and say exactly what permission or repository action is needed.

## Common Pitfalls

- Do not upload only `SKILL.md` when it references `references/`, `scripts/`, `assets/`, or `agents/openai.yaml`.
- Do not hardcode one user's absolute path as a general install instruction.
- Do not publish private Feishu, GetNote, Obsidian, customer, or transcript material.
- Do not treat `npx skills add --list` output as optional; it is the practical check that others can discover the skill.
- Do not mutate the source skill for GitHub-specific wording unless the source itself should change.
- Do not mix old renamed skill packages with new canonical names.
