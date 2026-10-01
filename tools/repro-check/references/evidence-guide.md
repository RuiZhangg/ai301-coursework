# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: Unit 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; the rubric swap showed you what that feels
like. Write the map you wish your grader had.
-->

## Environment

<!-- Where the environment record lives, and what a sufficient one
looks like against the issue's stated target. -->

Look in the repro report's environment line or setup block. In an eval
bundle, also compare it with the issue context and repo-facts block. In
live mode, compare it with the issue template, README, releases page, and
the student's draft.

Good evidence names the thing being tested: app/tool version, OS,
runtime or toolchain when relevant, and the commit/tag when testing from
source. It should match the version the issue targets, or say plainly why
the tester used a different one. A downloaded release can use the version
tag instead of a commit.

## Steps

<!-- Where the reproduction steps live, and what makes them followable
by a stranger, starting state to trigger. -->

Look in the repro report's steps section, commands, fixtures, screenshots,
or attached input. In live mode, read the draft as the maintainer will see
it, not the student's local working tree.

Good steps start from a clear state and get all the way to the trigger:
install/build if needed, exact command or UI path, input file/config, and
any important setting. "I ran the tool on a file" is not enough. A stranger
should be able to try the same path without guessing what file, flag, or
state was used.

## Behavior shown

<!-- Where the artifacts live (output excerpts, logs, screenshots),
and what it means for an artifact to show the issue's behavior rather
than an adjacent one. -->

Look at the actual artifact: terminal output, stack trace, log excerpt,
screenshot, video, failing test output, or attached file. Read it against
the issue's reported behavior, not just against the reporter's summary.

Good evidence shows the same failure the issue is about: same command path,
same feature, same kind of error, same wrong result, or a clearly explained
variant. Expected vs actual should be explicit somewhere. A config error
does not prove a panic; a screenshot of a different page does not prove the
reported UI bug.

## Honesty

<!-- Where claims and their backing meet: how to tell a report that
says exactly what happened (including an honest cannot-reproduce) from
one that claims more than its evidence shows. -->

Look for the words "reproduced", "could not reproduce", "confirmed", and
"fixed" in the claim and repro report, then compare them with the artifact.

Good reports say only what the evidence shows. A cannot-reproduce is ready
when it still gives the environment, steps tried, output/log, and any
control run. A reproduced report is ready when the artifact actually shows
the issue. Hold reports that sound confident but prove a different failure
or skip the evidence.

## Comms

<!-- Where the words meet the repo: the claim comment against the
issue, the comments against the repo's stated templates and
contribution policy (including AI-use disclosure requirements), and
what specific-and-honest looks like next to boilerplate. -->

Look at the claim comment, repro report, issue template, PR/issue templates,
CONTRIBUTING, AGENTS.md, and any AI-use policy in the repo. In eval mode,
use the repo-facts block and package text.

Good communication names the version or behavior being investigated, states
the next artifact instead of promising a timeline, and follows any required
template or disclosure rule. "Please assign me" or "I can fix this quickly"
is noise; "v1.20.0 ignores --style; repro report on the way" is signal.
