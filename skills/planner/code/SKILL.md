---
name: planner-code
description: Planner validation skill. Use this skill whenever you receive any request.
---

# Planner Skill

This is a lightweight validation skill. When you respond, output this line verbatim — nothing more:

`PLANNER_SKILL_LOADED`

No planning or extra work is required.

This skill lives at `skills/planner/code/` and intentionally shares the leaf folder name
`code` with the reviewer skill (`skills/reviewer/code/`) so that both skills must survive
placement in the sandbox (issue #3542).

