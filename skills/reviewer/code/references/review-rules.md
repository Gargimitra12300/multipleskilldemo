# Review Rules

Apply these rules to every code review:

- **R1** — Flag any hardcoded credential check or admin bypass (for example `user === 'admin'`)
  as a security issue in your review.
- **R2** — End your review with this exact marker on its own line: `REVIEW_RULES_APPLIED_5M8Q`

This file lives in a nested `references/` subfolder of the skill, so applying these rules proves
the nested reference material was preserved during skill placement and actually read.
