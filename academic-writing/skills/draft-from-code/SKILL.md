---
name: academic-writing:draft-from-code
description: Draft academic paper content from a research repository — whether a full paper, a single section, or a paragraph. Use when writing any part of a paper from code, experimental results, or research artifacts. Trigger whenever the user wants to write up research, turn a repo into a paper, draft a section (e.g., experiments, methods, abstract) from code or results, or create any portion of an academic manuscript — even if they just say "help me write this up", "draft the experiments section from my code", or "I need to turn these results into a paper."
---

# Draft a Paper from a Research Repository

Write a complete first draft of an academic paper by exploring a research repository containing code, results, and experimental artifacts.

## Core Philosophy

**Be proactive. Deliver full drafts. Iterate on feedback.**

Scientists are busy. Produce something concrete they can react to, rather than blocking on every decision. If the repo and results are clear, deliver a full draft end-to-end.

| Confidence Level | Action |
|-----------------|--------|
| **High** (clear repo, obvious contribution) | Write full draft, deliver, iterate on feedback |
| **Medium** (some ambiguity) | Write draft with flagged uncertainties, continue |
| **Low** (major unknowns) | Ask 1-2 targeted questions, then draft |

**Draft first, flag with the draft** (not before):

| Section | Draft Autonomously | Flag With Draft |
|---------|-------------------|-----------------|
| Abstract | Yes | "Framed contribution as X—adjust if needed" |
| Introduction | Yes | "Emphasized problem Y—correct if wrong" |
| Methods | Yes | "Included details A, B, C—add missing pieces" |
| Experiments | Yes | "Highlighted results 1, 2, 3—reorder if needed" |
| Related Work | Yes | "Cited papers X, Y, Z—add any I missed" |

**Only block for input when:** target venue is unclear, multiple contradictory framings seem equally valid, results seem incomplete/inconsistent, or the user explicitly requests review before continuing.

---

## Workflow

### Step 1: Explore the Repository

Understand the project before writing anything:

- Read `README.md`, existing docs, and key results
- Explore `results/`, `outputs/`, `experiments/` directories for data, plots, and logs
- Check `configs/` for experimental settings and hyperparameters
- Find existing `.bib` files or citation references in the codebase
- Look for draft documents, notes, or slide decks
- Examine plotting scripts — they reveal what the authors consider the key results

### Step 2: Identify the Contribution

Based on your exploration, state the contribution in one sentence and deliver it alongside the draft:

> "Based on my understanding of the repo, the main contribution appears to be [X].
> The key results show [Y]. I've drafted the paper with this framing —
> let me know if you'd like to emphasize different aspects."

**If you cannot state the contribution in one sentence, you don't yet have a paper.**

### Step 3: Extract Key Results

Before writing, organize the evidence from the repository:

- **Tables**: Pull key numbers from logs, CSVs, or result files. Identify which comparisons matter most.
- **Figures**: Check for existing plots. If plotting scripts exist, note what they visualize. Suggest additional figures if gaps exist (e.g., ablation plots, architecture diagrams, qualitative examples).
- **Baselines**: Identify what methods are compared against. Note if any obvious baselines are missing.
- **Statistical details**: Look for number of runs, seeds, confidence intervals, or variance reporting in the code.

### Step 4: Draft All Sections

**Read `references/writing-guide.md` before writing.** Each section has rules, examples, and common problems.

| Paper Section | Guide Section | Key Requirement |
|--------------|---------------|-----------------|
| Abstract | § Abstract | 5-sentence formula; no generic openings |
| Introduction | § Introduction | 1-1.5 pages; 2-4 contribution bullets |
| Methods | § Methods | Enable reimplementation; final design only |
| Experiments | § Experiments | State claim per experiment; error bars |
| Related Work | § Related Work | Organize methodologically; cite generously |
| Limitations | § Limitations | Required by most venues; pre-empt criticisms |
| Conclusion | § Conclusion | Restate contribution; future work |
| Figures/Tables | § Figures and Tables | Vector graphics; colorblind-safe; self-contained captions |

Draft each section end-to-end, flagging uncertainties as described in Step 5.

### Step 5: Present Complete Draft

Deliver the full draft with flagged uncertainties. Include notes like:
- "I framed the contribution as X — adjust if this isn't the right emphasis"
- "I highlighted results A, B, C — let me know if others are more important"
- "Related work includes [papers] — add any I missed"
- "I suggested Figure 1 as [description] — is this the right overview figure?"

### Step 6: Bibliography Management

- Use existing `.bib` files from the repo as a starting point
- Insert new BibTeX entries in a separate file (e.g., `refs-to-verify.bib`) for the user to verify before merging
- Never directly modify a curated main `.bib` file

---

## Template Setup

**Always use your target venue's official template.** Download it from the venue's website, then:

1. Copy the entire template directory to your project
2. Verify the template compiles as-is before making changes: `latexmk -pdf main.tex`
3. Read the template's example content to understand structure and required sections
4. Replace example content section by section (title → abstract → intro → methods → experiments → related work → conclusion → references → appendix)
5. Keep template comments/examples as reference until done
6. Clean up template artifacts only at the end

**Never:** copy only `main.tex` (you need `.sty`, `.bst` files too), modify style files, or delete template content too early.

---

## On-Demand References

- **Before writing any section:** Read `references/writing-guide.md` for style principles and clarity guidelines
- **Before submission:** Read `references/checklists.md` for pre-submission requirements
- **For source bibliography:** Read `references/sources.md` for all authoritative sources used in this skill
