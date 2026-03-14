---
name: academic-writing:peer-review
description: Simulate peer review of a paper. Use when you want to anticipate reviewer concerns, identify weaknesses, or get a simulated review with scores before submission. Trigger whenever the user asks to review a paper, check for weaknesses, simulate what reviewers would say, do a pre-submission check, stress-test a draft, or get feedback on a manuscript — even informally like "what would reviewers think of this" or "is this ready to submit."
---

# Simulate Peer Review

Produce a structured simulated review that anticipates real reviewer concerns, identifies weaknesses, and provides actionable improvement suggestions.

**Before reviewing, read `references/reviewer-guidelines.md` for reviewer evaluation criteria and guidelines.**

---

## Review Modes

Choose the appropriate review mode based on what the user needs:

### Pre-Submission Review (Default)
**Goal:** Help strengthen the paper before submission. Balanced, constructive, identifies fixable weaknesses.

Use when the user says things like "review my paper," "is this ready to submit," "what should I improve."

### Adversarial Stress-Test
**Goal:** Simulate the harshest plausible reviewer. Find every weakness, question every assumption, demand more evidence.

Use when the user explicitly wants to stress-test (e.g., "what's the worst a reviewer could say," "tear this apart," "find every weakness").

The review format is the same for both modes — the difference is in how aggressively you probe for weaknesses and how high you set the bar.

---

## Review Workflow

### Step 1: Read the Full Paper

Read the paper end-to-end before forming judgments. Note first impressions but reserve scoring until after careful analysis.

### Step 2: Score on 4 Dimensions

| Dimension | What to Evaluate |
|-----------|-----------------|
| **Quality** | Technical soundness, well-supported claims, correct methodology, reproducibility |
| **Clarity** | Clear writing, logical flow, reproducible by experts in the field |
| **Significance** | Community impact, advances understanding, practical or theoretical importance |
| **Originality** | New insights, methods, or perspectives (doesn't require entirely new method) |

### Step 3: Identify Weaknesses

Systematically check for:

| Weakness Type | What to Look For |
|---------------|-----------------|
| **Overclaiming** | Claims not supported by evidence; gap between abstract/intro claims and actual results |
| **Weak baselines** | Missing obvious comparisons; outdated baselines; unfair comparison setup |
| **Unclear contributions** | Can't identify what's novel; contribution buried or vague |
| **Missing ablations** | No analysis of which components matter; can't tell what drives performance |
| **Reproducibility concerns** | Missing hyperparameters, code, dataset details, or compute information |
| **Writing clarity** | Hard to follow; inconsistent terminology; missing signposting |
| **Insufficient evaluation** | Too few datasets; no error bars; no statistical significance testing |
| **Missing limitations** | No discussion of when the method fails or its scope |

### Step 4: Think Adversarially

Even in pre-submission mode, consider what a skeptical reviewer would challenge:
- What's the weakest experiment?
- Which claim has the least evidence?
- What would a domain expert find unconvincing?
- Is there a simpler explanation for the results?
- Could the improvements be due to hyperparameter tuning rather than the method?
- Are there obvious related works that aren't cited or compared against?

### Step 5: Calibrate Your Assessment

Simulated reviews are only useful if they're calibrated to real reviewer behavior. Common pitfalls:

| Pitfall | Why It's Bad | Correction |
|---------|-------------|------------|
| Too generous | Authors submit overconfident, get blindsided | Be honest about weaknesses — that's the point of simulation |
| Too harsh | Authors lose confidence in good work | Distinguish major weaknesses (would change recommendation) from minor issues (should fix but not deal-breakers) |
| Focusing on minor issues | Misses the forest for the trees | Lead with the 2-3 things that would most influence a real reviewer's score |
| Ignoring the positive | Real reviews acknowledge strengths | Always identify genuine strengths — this helps authors know what's working |

**Rule of thumb:** If you can't identify at least 2 genuine strengths, either the paper has fundamental problems or you haven't read it carefully enough.

### Step 6: Produce Structured Review Output

```
## Summary of Contributions
[1-2 sentences: what the paper claims to contribute, as the reviewer understands it]

## Strengths
- [Strength 1]
- [Strength 2]
- [Strength 3]
(2-4 bullet points, specific and evidence-based)

## Weaknesses
- [Weakness 1 — severity: major/minor]
- [Weakness 2 — severity: major/minor]
- [Weakness 3 — severity: major/minor]
(2-4 bullet points, ranked by severity, with specific suggestions for how to address each)

## Questions for Authors
- [Question 1]
- [Question 2]
(Questions whose answers could change the assessment)

## Overall Assessment
Score: [X/10]
Confidence: [X/5] (1 = not confident, 5 = very confident)

Justification: [2-3 sentences explaining the score]

## Actionable Suggestions
- [Specific improvement 1]
- [Specific improvement 2]
(Concrete steps to address weaknesses before submission)
```

---

## Scoring Guidance

Use a 1-10 scale unless the user specifies a different scale:

| Score | Label | Meaning |
|-------|-------|---------|
| 9-10 | Strong Accept | Exceptional work; among the best you'd expect at a top venue |
| 7-8 | Accept | Solid contribution with minor issues; would strengthen the venue |
| 5-6 | Borderline | Has merit but significant weaknesses; could go either way |
| 3-4 | Below threshold | Fundamental issues with claims, methodology, or evaluation |
| 1-2 | Strong Reject | Critical flaws, known results, or ethical concerns |

**Confidence scale:**

| Score | Meaning |
|-------|---------|
| 5 | Very confident — deep expertise in this exact area |
| 4 | Confident — familiar with the field and related work |
| 3 | Somewhat confident — know the area but not the specific subfield |
| 2 | Low confidence — outside main expertise |
| 1 | Guessing — very unfamiliar with the topic |

---

## Common Reviewer Concerns Checklist

Use this as a quick scan before writing the review:

### Technical & Scientific Merit
- [ ] **Technical soundness:** Is the paper technically sound with correct methodology and well-supported claims?
- [ ] **Originality:** Does the paper describe original work, clearly differentiated from prior work?
- [ ] **Baselines:** Are comparisons fair and up-to-date?
- [ ] **Statistical rigor:** Error bars, multiple runs, significance tests?
- [ ] **Reproducibility:** Could someone reimplement from the paper alone?

### Relevance & Significance
- [ ] **Audience interest:** Is the work of interest to the target venue's audience?
- [ ] **Significance:** Would the community benefit from this work?
- [ ] **Conciseness:** Does the paper contain material that might well be omitted?

### Writing & Presentation
- [ ] **Abstract:** Is the abstract an adequate digest of the work reported?
- [ ] **Introduction:** Does the introduction give sufficient background of the work?
- [ ] **Summary & conclusions:** Are the summary and conclusions adequate?
- [ ] **Clarity of contribution:** Do the authors explain clearly what they have done?
- [ ] **Motivation:** Do the authors explain clearly why what they did was worth doing?
- [ ] **Presentation order:** Is the order of presentation satisfactory and logical?
- [ ] **Language quality:** Is the English satisfactory throughout?
- [ ] **References:** Does the paper make adequate references to related and prior work?
- [ ] **Figures:** If there are color figures included, are they helpful and necessary?

### Broader Concerns
- [ ] **Limitations:** Are failure modes and scope clearly stated?
- [ ] **Ethics:** Any potential negative societal impact discussed?

---

## On-Demand References

- **For detailed reviewer evaluation criteria:** Read `references/reviewer-guidelines.md` for evaluation guidelines and common concerns
