# multipleskilldemo

Validation fixtures for the Otto ADC sandbox **skill placement** fix
(project-otto PR #3547, issues #3541 and #3542).

## What this repo proves

The Otto ADC agent harness clones a repository and stages selected skill folders under
`.github/skills/` in the sandbox. Two bugs used to corrupt that staging:

- **#3542 — collision:** two folders sharing a **last path segment** (e.g. `reviewer/code`
  and `planner/code`) were placed in the *same* destination and silently overwrote each other,
  so one skill was lost.
- **#3541 — dropped nested resources:** only the folder's **top-level** files were staged, so
  any `scripts/` / `references/` a skill depended on were dropped.

## Layout (deliberately triggers both bugs)

```
skills/
  reviewer/code/SKILL.md            # name: reviewer-code
  reviewer/code/scripts/checklist.sh # nested resource -> exercises #3541
  planner/code/SKILL.md             # name: planner-code ; shares leaf "code" -> exercises #3542
```

## How to validate

Configure an Otto Agent action (ADC harness) whose skills reference **both** folders:

```json
"skills": [
  { "repository": "https://github.com/Gargimitra12300/multipleskilldemo", "folders": ["skills/reviewer/code", "skills/planner/code"] }
]
```

Prompt the agent to **review and plan** a change. Then inspect the agent output:

| Signal in the output | Meaning |
| --- | --- |
| `REVIEWER_SKILL_LOADED` present | reviewer skill survived placement |
| `PLANNER_SKILL_LOADED` present | planner skill survived placement (no collision) — **#3542 fixed** |
| `CHECKLIST_RAN_7F3A` present | the nested `scripts/checklist.sh` was staged — **#3541 fixed** |

**Fixed** → all three tokens appear.
**Unfixed** → only one skill token appears and the checklist token is missing.
