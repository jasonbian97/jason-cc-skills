# Reviewer Guidelines & Evaluation Criteria

This reference documents how reviewers evaluate academic papers in engineering and computer science, helping authors anticipate and address reviewer concerns.

---

## Contents

- [Universal Evaluation Dimensions](#universal-evaluation-dimensions)
- [What Makes Reviews Strong](#what-makes-reviews-strong)
- [Common Reviewer Concerns](#common-reviewer-concerns)
- [How to Address Reviewer Feedback](#how-to-address-reviewer-feedback)

---

## Universal Evaluation Dimensions

Reviewers at engineering and CS venues typically assess papers across four core dimensions:

### 1. Quality (Technical Soundness)

**What reviewers ask:**
- Are claims well-supported by theoretical analysis or experimental results?
- Are the proofs correct? Are the experiments properly controlled?
- Are baselines appropriate and fairly compared?
- Is the methodology sound?

**How to ensure high quality:**
- Include complete proofs (main paper or appendix with sketches)
- Use appropriate baselines (not strawmen)
- Report variance/error bars with methodology
- Document hyperparameter selection process

### 2. Clarity (Writing & Organization)

**What reviewers ask:**
- Is the paper clearly written and well organized?
- Can an expert in the field reproduce the results?
- Is notation consistent? Are terms defined?
- Is the paper self-contained?

**How to ensure clarity:**
- Use consistent terminology throughout
- Define all notation at first use
- Include reproducibility details (appendix acceptable)
- Have non-authors read before submission

### 3. Significance (Impact & Importance)

**What reviewers ask:**
- Are the results impactful for the community?
- Will others build upon this work?
- Does it address an important problem?
- What is the potential for real-world impact?

**How to demonstrate significance:**
- Clearly articulate the problem's importance
- Connect to broader research themes
- Discuss potential applications
- Compare to existing approaches meaningfully

### 4. Originality (Novelty & Contribution)

**What reviewers ask:**
- Does this provide new insights?
- How does it differ from prior work?
- Is the contribution non-trivial?

**Key insight:** Originality does not necessarily require introducing an entirely new method. Papers that provide novel insights from evaluating existing approaches or shed light on why methods succeed can also be highly original.

---

## What Makes Reviews Strong

### Following Daniel Dennett's Rules

Good reviewers follow these principles:

1. **Re-express the position fairly** — Show you understand the paper
2. **List agreements** — Acknowledge what works well
3. **List what you learned** — Credit the contribution
4. **Only then critique** — After establishing understanding

### Review Structure Best Practices

**Strong Review Structure:**
```
Summary (1 paragraph):
- What the paper does
- Main contribution claimed

Strengths (3-5 bullets):
- Specific positive aspects
- Why these matter

Weaknesses (3-5 bullets):
- Specific concerns
- Why these matter
- Suggestions for addressing

Questions (2-4 items):
- Clarifications needed
- Things that would change assessment

Minor Issues (optional):
- Typos, unclear sentences
- Formatting issues

Overall Assessment:
- Clear recommendation with reasoning
```

---

## Common Reviewer Concerns

### Technical Concerns

| Concern | How to Pre-empt |
|---------|-----------------|
| "Baselines too weak" | Use state-of-the-art baselines, cite recent work |
| "Missing ablations" | Include systematic ablation study |
| "No error bars" | Report std dev/error, multiple runs |
| "Hyperparameters not tuned" | Document tuning process, search ranges |
| "Claims not supported" | Ensure every claim has evidence |

### Novelty Concerns

| Concern | How to Pre-empt |
|---------|-----------------|
| "Incremental contribution" | Clearly articulate what's new vs prior work |
| "Similar to [paper X]" | Explicitly compare to X in Related Work |
| "Straightforward extension" | Highlight non-obvious aspects |

### Clarity Concerns

| Concern | How to Pre-empt |
|---------|-----------------|
| "Hard to follow" | Use clear structure, signposting |
| "Notation inconsistent" | Review all notation, create notation table |
| "Missing details" | Include reproducibility appendix |
| "Figures unclear" | Self-contained captions, proper sizing |

### Significance Concerns

| Concern | How to Pre-empt |
|---------|-----------------|
| "Limited impact" | Discuss broader implications |
| "Narrow evaluation" | Evaluate on multiple benchmarks |
| "Only works in restricted setting" | Acknowledge scope, explain why still valuable |

---

## How to Address Reviewer Feedback

### Rebuttal Best Practices

**Do:**
- Thank reviewers for their time
- Address each concern specifically
- Provide evidence (new experiments if possible)
- Be concise — reviewers are busy
- Acknowledge valid criticisms

**Don't:**
- Be defensive or dismissive
- Make promises you can't keep
- Ignore difficult criticisms
- Write excessively long rebuttals
- Argue about subjective assessments

### When to Accept Criticism

Some reviewer feedback should simply be accepted:
- Valid technical errors
- Missing important related work
- Unclear explanations
- Missing experimental details

Acknowledge these gracefully: "The reviewer is correct that... We will revise to..."

### When to Push Back

You can respectfully disagree when:
- Reviewer misunderstood the paper
- Requested experiments are out of scope
- Criticism is factually incorrect

Frame disagreements constructively: "We appreciate this perspective. However, [explanation]..."

---

## Pre-Submission Self-Review

Before submitting, ask yourself:

**Quality:**
- [ ] Would I trust these results if I saw them?
- [ ] Are all claims supported by evidence?
- [ ] Are baselines fair and recent?

**Clarity:**
- [ ] Can someone reproduce this from the paper?
- [ ] Is the writing clear to non-experts in this subfield?
- [ ] Are all terms and notation defined?

**Significance:**
- [ ] Why should the community care about this?
- [ ] What can people do with this work?
- [ ] Is the problem important?

**Originality:**
- [ ] What specifically is new here?
- [ ] How does this differ from closest related work?
- [ ] Is the contribution non-trivial?
