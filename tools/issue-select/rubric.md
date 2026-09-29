# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Repo alive | Repo facts: archived flag, last push, latest release, last 5 commits. | Pass if not archived and there is a human commit/push in 90 days or a release in 180 days. No release is okay if commits are fresh. | required |
| Maintainer path | Maintainer response sample, issue opener, and owner/member/collaborator comments. | Pass if a maintainer opened/commented on the issue, replied in the sample within 90 days, or recently merged human PRs. | required |
| Not taken | Assignees, linked PRs, and comments saying claim/working/opened PR. | Pass if no assignee, no open linked PR, and no active recent claim. Old claims pass only if abandoned, unassigned, or years stale. | required |
| No claim history trap | Linked PRs and long comment threads. | Pass unless there are multiple abandoned PRs/claims and no maintainer has reset the issue for new work. | required |
| Ready to start | Issue body, comments, labels, and maintainer clarification. | Pass if the expected change is clear enough to start. Fail vague feature wishes with no spec, maintainer signal, or chosen asset/behavior. | required |
| Policy allows it | Repo-facts contribution policy. | Pass if AI is silent, allowed, or allowed with review/testing/disclosure. Fail outright AI bans or strong AI warnings for this exact work type. | required |
| Scope fit | Issue body and comment thread. | Prefer one small bug or small new feature, with the scope clearly defined in the issue. Mark fail for megaissues, tracking lists, codebase-wide cleanup, or years of design debate. | preferred |
| First-issue signal | Labels, issue body, and comments. | Prefer `good first issue`, `help wanted`, acceptance criteria, file hints, or maintainer guidance. | preferred |

## Verdict rule

Accept the issue only if every required check passes. Reject it if any
required check fails or is unclear, because if I cannot verify a required
signal from the bundle then I should not call it a good first issue.
Preferred checks never change the verdict; they only help rank the issues
that already passed all the required checks.
