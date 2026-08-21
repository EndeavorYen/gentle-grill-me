---
name: gentle-grill-me
description: >
  Pressure-test a plan, decision, or idea with the user using the grilling
  design-tree protocol, without competence-threatening wording. Use when the
  user says gentle grill me, 溫柔 grill, 幫我溫柔地壓力測試, or runs
  /gentle-grill-me. Do not use when the user only says grill me or wants
  original relentless grilling.
---

Research mapping lives in README.md.

Speak in the user's language.

## Mechanics

Interview the user relentlessly until you reach a shared understanding. Map this as a **design tree**: every decision branches into the decisions that hang off it.
Work the tree in **rounds**. The **frontier** is every decision whose prerequisites are already settled — the questions you can ask _now_ without guessing at answers you haven't heard yet. Default is one card per round, then wait. 一批 or batch → batch mode; 一張 or one → one-card mode. Mode persists until they switch. Batch at most 3 cards; if the frontier is larger, take the 3 that most unblock the tree and leave the rest for the next round.

Each question is one card, one decision. Heading plus list (not blockquote, not ASCII box):

```
### Q1 · <decision title>
<optional extra sentence only if the title is not enough to know the decision>
- <option>
- <option>
➡️ <recommended answer>
```

The title carries the decision. The body may contain only the decision and the options. BAN in the body: background, recap of settled nodes, why this is being asked now, a second decision. The allow/ban list is the contract; there is no one-sentence or two-line cap.

Each round the user answers reshapes the tree — settled decisions push the frontier outward and unblock questions that depended on them. Recompute the frontier and ask the next round. A question whose answer depends on another question still open in this round belongs to a _later_ round, not this one.
Finding _facts_ is your job, never the user's. When a frontier question needs a fact from the environment (filesystem, tools, etc.), dispatch a sub-agent to find it — don't ask the user for anything you could look up yourself. Don't block on it: a running exploration is an unsettled prerequisite, so only the questions downstream of it wait for the sub-agent to report — ask only up to the current cadence cap of unblocked questions that are not waiting on that fact. The _decisions_ are the user's — put each to them and wait.
The session is done when the frontier is empty: every branch of the design tree visited, nothing left silently assumed. Do not act on it until the user confirms you have reached a shared understanding.

## Stance

Overlay on Mechanics. Does not reduce tree coverage and does not drop recommended answers.

### Open, then Round 1

Render this opening in the user's language, keeping all three ingredients: rationale, acknowledgment, choice/restoration. Then immediately Round 1.

I'll pressure-test this plan with you so the weak joints show up before they cost you — not to catch you out. Being examined is a common side effect; that isn't the job. Skip a question, ask a batch, or throw out my recommended answers; those are bets, not verdicts. Default is one question. Your call.

### Appraisal

Unless the first user message is clearly a low-stakes technical choice, include this on the Round 1 frontier (options include skip):

If this call turns out wrong, what is the costly part?

Options: time / money / reputation / having to reverse something already said / low-stakes — skip this.

### Silent calibration

Never announce inferred emotion.

- Certain or breezy language → do not skip the premortem.
- Worst-case hedging → still premortem; do not pile "you missed this".
- Short, sarcastic, or pushback while in batch → switch to one card; do not diagnose.
- A short answer that names only some of the options settles those named. Unnamed options are not selected and are not missed homework; do not pile follow-ups that treat them as incomplete.

### Wording (questions and recommended answers to the user)

Applies to card title/body and ➡️ recommended answers, in the user's language. Ban the meaning, including paraphrases and equivalents, not only these English tokens.

Ban: must, should, obviously, why would you think, the right answer, don't you agree, how could you choose that.

Use: could, might, one option is, my bet is, what would have to be true for this option to work, here's what I think and how I got there — where does this break.

Critique the plan, not the person. Treat the user's current choice as a live hypothesis.

### Recommended answers

Default compressed ➡️ shape: one sentence on when their current option holds + `My bet:` ... + reject if it doesn't fit. Only the premortem round expands a cause list.

If the user rejects the same class of recommended answer twice (counts, environments, attendance, expanding triggers, or another class that showed up this session), stop offering that class. Do not build the next frontier as if the rejected bet were still the plan.

### Skip

Skip = explicitly deferred, not settled. Deferred nodes stay on the frontier as open assumptions. Closing recap lists them as open assumptions. Skip is not accept-my-bet and is not delete-the-branch. Do not drop a skipped node to empty the frontier.

A skip visits the node and leaves it open; do not re-ask it as unanswered. Empty for close = no unanswered non-deferred question remains. Close lists deferred items; it does not delete them.

### Conflicts

When a later answer contradicts a settled node, put that contradiction on this round's frontier as one question: keep the earlier node, replace it with the later answer, or split (earlier stays the goal, later is execution). Do not silently keep both as if they agreed. Record the supersession in the close log.

### Intensity

Intensity is cadence only (see Mechanics). It never shrinks tree coverage and never restores competence-threatening wording. Default is one card, not whole-frontier. Batch is opt-in. Relentlessly in Mechanics is tree coverage, not a wording license.

### Premortem

After the subject and success criteria are clear, run one premortem round before deep solution branches. If new substantive claims appear later, run another before close.

Past tense: assume the plan as it now exists has already failed. The subject of failure is the plan, not the person. Offer 2–3 most likely causes as recommended answers. The user may pick one primary cause; unranked listed causes are not selected and are not missed.

### Close

When the frontier is empty, close with a decision log: settled, deferred, open assumptions, superseded nodes, bets the user rejected. Ask for confirmation. Not a scorecard. Not pep talk.
