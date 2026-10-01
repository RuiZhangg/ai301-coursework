# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

<!-- 2-3 lines. Who is talking when you comment on an issue: your
experience level stated plainly, what you are doing in this repo, what
readers can expect from you. This is the register your rules protect. -->

I am a new contributor on github, but I am still
responsible for what I post. I am here to reproduce the issue first, show
my evidence, and then attempt a fix. Maintainers should expect direct,
plain updates from me, not hype or vague claims.

## Rules I write by

<!-- 3-5 rules, drafted from the lecture's slide-12 moment. Each rule
needs a wrong/right pair from your own hand: one line you might
actually have written that breaks the rule, and the line you would
post instead. The pair is what makes a rule executable; a rule without
one is a wish.

Format each rule like this:

### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->

### Rule: Name the exact thing

Do not say "this bug" when I can name the version, behavior, command, or
file. A maintainer should know which issue I am talking about without
scrolling up.

- Wrong: "I can work on this bug."
- Right: "Picking this up: the dependency audit tool is missing, and I am checking the `agent/tools/` pattern before writing the repro note."

### Rule: Promise the next artifact, not the outcome

I should not promise a fix, a merge, or a timeline. I can promise the next
piece of evidence I am about to produce.

- Wrong: "I can fix this by tomorrow, please assign me."
- Right: "Repro report on the way; I will include the environment, steps, and output I see."

### Rule: Let evidence set the confidence level

If I have not reproduced it yet, I should not sound like I have. If I
cannot reproduce it, I should say that and show what I tried.

- Wrong: "Confirmed, everything in the issue is accurate."
- Right: "I reproduced this on Python 3.12 with the current main branch; log below."

### Rule: Sound like me, not a template

Be respectful, but skip the overexcited project praise and canned bot
phrases. Clear is better than polished.

- Wrong: "Amazing project!! I am very excited to contribute and would love to be assigned."
- Right: "First contribution here, so I am starting with a repro report before attempting the fix."

## Things I never post

<!-- A short list. Promises you cannot keep, tones you refuse,
shortcuts you know you reach for when tired. The skill quotes this
list back at you when a draft crosses it. -->

- "Please assign me" as the whole claim.
- "I will fix this by tomorrow" or any deadline I do not fully control.
- "Confirmed" without environment, steps, and an artifact.
- Generic praise that could be pasted into any repo.
- AI-assisted work without reading, testing, and following any disclosure
  rule the repo gives me.
