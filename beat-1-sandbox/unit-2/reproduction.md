# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**

RuiZhangg

---

## Posted upstream

**Claim comment**

link: https://github.com/codepath/pathreview-ai301-fa26-s1/issues/20#issuecomment-5920972786

comment:
Picking this up as my first contribution here. I’m going to start by reading the existing agent/tools/ pattern and how tools are registered in agent/orchestrator.py, then work on a DependencyAuditTool for requirements.txt, package.json, and pyproject.toml that flags dependencies more than one major version behind. I’ll post notes from my setup/testing before opening a PR.

<!--
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/20",
  "checks": [
    {"name": "Environment pinned", "grade": "unclear", "evidence": "not yet applicable: claim-only draft"},
    {"name": "Steps rerunnable", "grade": "unclear", "evidence": "not yet applicable: claim-only draft"},
    {"name": "Artifact fits outcome", "grade": "unclear", "evidence": "not yet applicable: claim-only draft"},
    {"name": "Outcome honest", "grade": "unclear", "evidence": "not yet applicable: claim-only draft"},
    {"name": "Repo conventions", "grade": "pass", "evidence": "CONTRIBUTING step 4: 'Comment on the issue to let others know you're working on it'; no AGENTS.md or AI-disclosure rule for comments"},
    {"name": "Claim useful", "grade": "pass", "evidence": "names the behavior ('flags dependencies more than one major version behind') and the next step ('post notes from my setup/testing'); no assign request or deadline"},
    {"name": "Maintainer helpers", "grade": "unclear", "evidence": "not yet applicable: claim-only draft"}
  ],
  "verdict": "accept"
} -->

**Reproduction comment**

link: https://github.com/codepath/pathreview-ai301-fa26-s1/issues/20#issuecomment-5925834843

comment:
I finished local setup and checked whether this behavior already exists.

Environment:
- macOS 26.5.1 arm64
- repo `main` at `f89c06f`
- Python 3.13.12, Node 22.14.0, npm 10.9.2
- `make setup` completed
- npm reported 15 vulnerabilities during setup, but that seems separate from this feature request.

Checks run:
```bash
grep -R "requirements.txt\|package.json\|pyproject.toml" -n \
  --exclude-dir=.venv \
  --exclude-dir=node_modules \
  --exclude-dir=.git .
```
Relevant findings:
- agent/tools/tech_detector.py uses requirements.txt and package.json only as tech-stack indicators.
- ingestion/parsers/repo_analyzer.py uses them only to infer tools like pip, npm, and Node.js.
- ingestion/parsers/skill_extractor.py uses them only as text evidence for Python / JavaScript skills.
- I did not find code that parses dependency versions from requirements.txt, package.json, or pyproject.toml.
- I did not find code that compares dependency versions or flags packages more than one major version behind.
Expected:
- An agent tool parses supported dependency files and reports dependencies that are more than one major version behind.
- The tool is wired into agent/orchestrator.py.
Actual:
- Current code detects dependency files as tech-stack hints only.
- No existing dependency-version audit behavior appears to be implemented.
Conclusion:
I can reproduce this as a missing feature, not as a runtime failure.




## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

I did one full run:

> agreement: 19/20 scored items  (bar: 18/20: PASS)

**Package analysis**

I looked at `pkg-03`, the only mismatch in the run:

> pkg-03  accept  reject   NO     failed: Repo conventions

My rubric rejected it, while the gold label accepted it. The package was otherwise a
strong repro: it used the current version and named the version difference:

> Environment: ripgrep 15.2.0 (cargo install), Arch Linux (x86_64). The issue was filed against 13.0.0; behavior is unchanged on 15.2.0.

It also followed the maintainer's trigger note:

> the incomplete part of the description: it is not just adjacent matches, the `--replace` flag is also required to trigger it

The reason my rubric rejected it was the repo policy line:

> AI-assisted coding is welcome with a human in the loop who understands the work; comments to maintainers must be written by humans in their own words, and AI-generated comments may be hidden

I think the rubric/model read that too strictly as a repo-conventions failure. The
gold label treated the claim as acceptable because it sounded specific and human:

> I'd like to take a run at this one as a first contribution. Reproduced on current 15.2.0 (report below), and per the pointer above I'll start reading the standard printer in grep-printer to see where line numbers are computed for adjacent replaced matches.

**Check rationale**

The check that caused the miss is:

> | Repo conventions | Repo-facts contribution policy, templates, AGENTS/AI policy, claim comment, and repro report. | Pass if required templates and AI rules are followed, or the repo is silent. Treat this course package as AI-assisted work; fail if a policy requires AI-use disclosure in comments/issues and the package gives none. | required |

I wrote it this way because a repro comment is not ready just because the technical
proof is good. If a repo has posting rules, templates, or AI-use disclosure rules,
the comment has to respect those too. The important wording is "requires AI-use
disclosure"; that is meant to separate strict disclosure rules from softer "write
comments in your own words" guidance.

**Trade-offs**

The trade-off is that this check makes the repro-check more conservative
about posting upstream. That is good when a repo has a hard rule, because I would
rather revise my comment before posting than make maintainers deal with something
that violates their contribution policy. The cost is that I have to read the policy
carefully, not just search for the word "AI." A repo can require disclosure, or it
can simply say comments should be human-written:

> comments to maintainers must be written by humans in their own words, and AI-generated comments may be hidden

Those should not be treated the same. In practice, this check slows me down a little
before posting, but it forces the right habit: check the repo's rules, decide whether
there is an actual disclosure requirement, and only then post the repro.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
