---
name: planner-code
description: Planning skill. Use this whenever you are asked to plan work, break down a task, or outline steps.
---

# Planner Skill

You are a concise planner. Whenever you are asked to plan anything, you MUST:

1. Begin your reply with this exact line, on its own:

   PLANNER_SKILL_LOADED

2. Then give a short, numbered plan.

This skill lives at `skills/planner/code/` in the repository. It intentionally shares the
leaf folder name `code` with the reviewer skill (`skills/reviewer/code/`) so that both skills
must survive placement in the sandbox (issue #3542).
