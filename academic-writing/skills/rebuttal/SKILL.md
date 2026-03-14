---
name: academic-writing:rebuttal
description: Write rebuttals to reviewer feedback. Use when responding to peer reviews, preparing author responses, or addressing reviewer concerns for conference or journal resubmission. Trigger whenever the user mentions reviewer comments, rebuttal, author response, camera-ready revisions, or needs help crafting responses to referee reports — even informally like "help me respond to these reviews" or "the reviewers said X."
---

# Write Rebuttals to Reviewer Feedback

Craft effective point-by-point responses to peer reviews that address concerns, strengthen the paper, and maximize acceptance probability.

## Workflow

### Step 1: Read All Reviews Holistically

Before responding to any individual point:
- Read ALL reviewer comments end-to-end
- Identify common themes across reviewers (if multiple reviewers flag the same issue, it's critical)
- Note the overall sentiment and scoring pattern
- Understand what each reviewer values most

### Step 2: Categorize Each Concern

For every point raised by every reviewer, classify it:

| Category | Description | Response Strategy |
|----------|-------------|-------------------|
| **Factual error in review** | Reviewer misunderstood the paper | Politely clarify with evidence from the paper |
| **Legitimate weakness** | Valid criticism of the work | Acknowledge, explain mitigation or why it doesn't undermine core claims |
| **Request for experiments** | Additional analysis requested | Provide new results if feasible, or explain why infeasible within rebuttal period |
| **Writing clarity** | Unclear presentation | Acknowledge and describe specific revisions |
| **Significance/novelty concern** | Questions importance of work | Reframe contribution, provide additional context |
| **Out of scope** | Requests beyond paper's stated goals | Respectfully redirect to stated scope |

### Step 3: Prioritize Responses

Rank concerns by impact on the final decision:

1. **Must address:** Issues that could sink the paper (weak baselines, overclaiming, missing comparisons)
2. **Should address:** Issues that affect score (clarity, additional experiments)
3. **Nice to address:** Minor points (typos, formatting, phrasing suggestions)

Focus effort on (1). Reviewers notice when critical concerns are dodged.

### Step 4: Draft the Rebuttal

#### Format

Organize responses **by reviewer**, addressing each point individually:

```
## Response to Reviewer 1

### R1.1: [Paraphrased concern]

**Response:** [Your response]

**Changes made:** [Specific revisions, if any]

### R1.2: [Next concern]
...

## Response to Reviewer 2
...
```

#### Tone

- **Respectful and factual.** Never dismissive, defensive, or condescending.
- **Grateful for constructive feedback.** Even harsh reviews often contain useful insights.
- **Confident but not combative.** Stand by your work without being adversarial.

#### Structure for Each Point

Follow this pattern for every response:

1. **Restate the concern** (shows you understood it)
2. **Provide your response** (evidence, clarification, or acknowledgment)
3. **Describe action taken** (what changed in the revised paper, if anything)

Example:
> **R1.3:** The reviewer notes that baselines are weak and do not include Method X.
>
> **Response:** We agree that comparing against Method X strengthens the evaluation. We have added results for Method X in Table 2 (revised). Our method outperforms Method X by 3.2% on benchmark Y, confirming our original claims.
>
> **Changes:** Added Method X baseline to Table 2 and discussion in Section 4.2.

#### Handling Disagreeing Reviewers

When one reviewer is very positive and another is very negative:

- **Don't play reviewers against each other** ("Reviewer 2 disagrees with you")
- **Do use positive reviewer's language** to frame responses constructively
- **Address the negative reviewer's specific concerns** with evidence — if R1 praised clarity but R3 found it unclear, the confusion is real for R3 and worth fixing
- **Focus on the editor / meta-reviewer**: they see all reviews and look for whether concerns are substantively addressed

### Step 5: Plan Paper Revisions

Based on rebuttal promises, create a revision plan:

- List every change promised in the rebuttal
- Ensure the revised paper actually reflects each promise
- Highlight changes in the revision (blue text or change tracking, per venue policy)
- **Never promise changes you don't deliver** — reviewers will check

---

## Rebuttal Formatting Tips

- **Respect length limits.** Check your venue's word/page limit for rebuttals.
- **Use bold and structure.** Reviewers skim rebuttals — make key points scannable.
- **Lead with impact.** Put your strongest responses first within each reviewer's section.
- **Quantify when possible.** "Improves by 3.2%" beats "improves significantly."
- **Reference specific sections.** "See revised Section 4.2" is actionable; "we clarified this" is not.

---

## Common Rebuttal Mistakes

| Mistake | Why It Hurts | Better Approach |
|---------|-------------|-----------------|
| Dismissing concerns | Signals arrogance | Acknowledge, then explain |
| Vague promises | "We will add experiments" | Specify what, where, and provide preliminary results |
| Arguing with reviewer's taste | Alienates the reviewer | Reframe objectively with evidence |
| Ignoring a concern | Reviewer assumes you can't address it | Address everything, even briefly |
| Overlong responses | Buries important points | Be concise, lead with key information |
| Changing the paper's claims | Suggests original claims were wrong | Clarify scope rather than retreating |

---

## On-Demand References

- **Before writing rebuttals:** Read `references/reviewer-guidelines.md` to understand how reviewers evaluate papers — this helps you target responses to what matters most for scoring decisions
