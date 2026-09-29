# Unit 1 — Issue Selection

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/20

**Verdict output**

Ranked read-out — all four accepted

1. #20 — DependencyAuditTool — best fit. New feature in the agent system (your stated expertise), pure backend, zero UI. Decisive extra: docs/CONTRIBUTING.md has an "Adding a New Agent Tool" walkthrough whose worked example is literally agent/tools/dependency_audit_tool.py — the exact file this issue asks for — and agent/tools/ already holds five sibling tools plus base.py to pattern-match. Nobody has touched it: no assignee, no comments, no PRs.

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/20",
  "checks": [
    {"name": "Repo alive", "grade": "pass", "evidence": "archived=False; last push 2026-09-16 (12 days before today), human commits by Aburke225; no releases but commits are fresh"},
    {"name": "Maintainer path", "grade": "pass", "evidence": "Issue opened 2026-09-10 by Aburke225, author_association COLLABORATOR"},
    {"name": "Not taken", "grade": "pass", "evidence": "assignees=[], 0 comments, no linked or cross-referenced PRs in the timeline"},
    {"name": "No claim history trap", "grade": "pass", "evidence": "Timeline holds only four 'labeled' events from the opener; no prior PRs or claims"},
    {"name": "Ready to start", "grade": "pass", "evidence": "Body names the parse targets (requirements.txt/package.json/pyproject.toml), the rule (>1 major version behind), and both files; agent/tools/base.py and 5 sibling tools exist"},
    {"name": "Policy allows it", "grade": "pass", "evidence": "docs/CONTRIBUTING.md has no AI clause; no AI_POLICY.md; PR template has no AI-disclosure checkbox — silence passes"},
    {"name": "Scope fit", "grade": "pass", "evidence": "One new tool file plus an orchestrator registration; est. 5-8 hours; not an umbrella or tracking issue"},
    {"name": "First-issue signal", "grade": "pass", "evidence": "'Relevant files' hints, plus CONTRIBUTING.md 'Adding a New Agent Tool' uses 'dependency_audit_tool.py' as its example; label is tier-2, not good-first-issue"}
  ],
  "verdict": "accept"
}
```

---

## Eval iterations

**Run history**

I did one full run:

> agreement: 18/20 scored items  (bar: 18/20: PASS)

**Issue analysis**

I looked at `issue-05`. The final run recorded the mismatch like this:

> issue-05  reject  accept   NO     graded accept

So my rubric accepted it, while the gold label rejected it. I can see why my rubric
got pulled toward `accept`: the repo looked alive and reviewable:

> - repo: sympy/sympy (14832 stars, archived: no)

> - last push to any branch: 2026-08-04

> opened by oscarbenjamin (COLLABORATOR) on 2025-12-21, state open, labels: Easy to Fix, good first issue, typing

The issue also sounded beginner-friendly in places:

> PRs are welcome both big and small (better to start small) that add type annotations to parts of the codebase where it makes sense to do so

But the gold label makes sense because the real issue is much wider than one first
contribution. The title itself says:

> Adding more type annotations to the codebase

And later the issue shows how large that space is:

> Symbols exported by "sympy": 39643

**Check rationale**

The check I would connect to this mistake is:

> | Scope fit | Issue body and comment thread. | Prefer one small bug or small new feature, with the scope clearly defined in the issue. Mark fail for megaissues, tracking lists, codebase-wide cleanup, or years of design debate. | preferred |

I made this check `preferred` because I did not want scope alone to throw out every
issue that is a little messy. A real repo issue can still be usable when it has
some rough edges. But for `issue-05`, that leniency is exactly where the rubric was
too forgiving: the issue had good labels and an active maintainer, but it was still
an umbrella for many possible typing PRs.

**Trade-offs**

The trade-off is that keeping scope as `preferred` can let a broad issue through if
the other required checks pass. `issue-05` is the example I accept:

> There is a long discussion in gh-17945 about adding type annotations to the sympy codebase

> this issue is about incrementally adding more type annotations

That is useful work, but it is not one clearly bounded first issue. The current
rubric chooses not to make scope a hard gate, so I can pass the eval bar while still
knowing this is the kind of false accept it may miss.

---

## Selection rationale

**Selection rationale**

1. Issue #20 fits my interests because it is a focused backend agent-tool feature. The 5-8 hour estimate also feels doable if I follow the existing sibling tools.

2. The verdict correctly caught the strongest signals: active repo, accepted policy, clear files, and a concrete task. I also weighed that `dependency_audit_tool.py` appears in the contributing guide example, so this has a clearer implementation path than the caching or tone-check issues.

3. Claiming should be fine because this class allows multiple students to claim the same issue. The main risk is not the claim; it is that the run warned PRs may sit without review.
