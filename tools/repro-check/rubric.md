# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Environment pinned | Repro report environment record, compared with the issue target and repo-facts bug template. | Pass if it names the tested version plus OS, and includes runtime/toolchain/commit/tag when that matters. If the issue targets latest/main or a specific version, the report must match it or call out the difference. | required |
| Steps rerunnable | Repro report steps, commands, inputs/config, and starting state. | Pass if a stranger could try the same repro from the text. Fail private repos, unshared config/files, missing drivers/settings, or steps that skip the issue's trigger. | required |
| Artifact fits outcome | Output/log/screenshot/video/test artifact, read against the issue and the report's claimed outcome. | Pass if a reproduced report shows the reported bug, or a cannot-reproduce report shows the actual attempt and result. Fail artifacts showing a different error, only setup success, or no artifact at all. | required |
| Outcome honest | Claim comment and repro report wording, checked against the artifact. | Pass if the report says only what the evidence supports. Fail "confirmed", "guaranteed", or root-cause claims when the package does not prove them. | required |
| Repo conventions | Repo-facts contribution policy, templates, AGENTS/AI policy, claim comment, and repro report. | Pass if required templates and AI rules are followed, or the repo is silent. Treat this course package as AI-assisted work; fail if a policy requires AI-use disclosure in comments/issues and the package gives none. | required |
| Claim useful | Claim comment, issue context, and repro report link/summary. | Pass if the claim names the behavior or version and says the next evidence step. Fail boilerplate assign-me comments, promised deadlines, or reservation requests. | required |
| Maintainer helpers | Control runs, reduced test cases, full logs, screenshots, or notes about what differed. | Prefer extra proof that shortens triage, but do not require it when the core evidence is already checkable. | preferred |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->

Accept if every applicable required check passes. Reject if any applicable
required check fails or is unclear. In claim-only live mode, only grade the
claim and repo-convention checks for the verdict; repro-report checks can
stay unclear as not yet applicable. Preferred checks never change the
verdict.
