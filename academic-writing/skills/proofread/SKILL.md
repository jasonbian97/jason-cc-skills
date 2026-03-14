---
name: academic-writing:proofread
description: Proofread paper for style, clarity, and grammar. Use when polishing a draft for language quality, fixing typos, improving sentence structure, ensuring consistent terminology, or preparing a manuscript for submission. Trigger whenever the user asks to proofread, polish, copy-edit, check grammar, improve writing quality, or do a final pass on any academic paper, LaTeX document, or manuscript section — even if they just say "can you clean this up" or "check my writing."
---

# Proofread Paper for Style and Clarity

Polish a draft for language quality, applying proven scientific writing principles to improve readability and professionalism.

**Before proofreading, read `references/writing-guide.md` for detailed style rules and examples.**

---

## Multi-Pass Proofreading Workflow

Effective proofreading requires multiple focused passes. Trying to catch everything at once causes you to miss things. Work through these passes in order:

### Pass 1: Structure and Flow

Read the paper end-to-end without editing. Focus on:
- Does each section accomplish its purpose?
- Do paragraphs flow logically? Does each paragraph make exactly one point?
- Are transitions between sections smooth?
- Is the narrative arc clear (problem → approach → evidence → conclusion)?

Flag structural issues but don't fix them yet — fixing structure changes text, making later passes on the original version wasted effort.

### Pass 2: Sentence-Level Clarity

Apply the 7 reader-expectation principles from `references/writing-guide.md` (§ Sentence-Level Clarity):
- Subject-verb proximity (don't interrupt yourself)
- Stress position (important information at sentence end)
- Topic position (context at sentence start)
- Old information before new
- One idea per sentence/paragraph
- Action in the verb (not nominalized nouns)
- Context before new information

Also check:
- Pronoun clarity ("this" → "this result", "it" → "the model")
- Verb placement (verbs early in sentences)
- Filler word elimination ("actually", "basically", "very", "In order to" → "To")
- Active voice throughout

### Pass 3: Word Choice and Precision

- **Terminology consistency**: Same concept = same word throughout (don't alternate between "model"/"network"/"architecture" for the same thing)
- **Abbreviation discipline**: Define on first use, then use consistently — never paraphrase back to a synonym
- **Calibrated hedging**: "can" for observations, "could" for hypotheses, no stacked hedges
- **Precision over vagueness**: Replace "good results" → "92% accuracy", "large dataset" → "1.2M examples"
- **Vocabulary signaling**: Avoid "combine," "modify," "extend" → use "develop," "propose," "introduce"

### Pass 4: Grammar and Formatting

Work through the checklist below item by item.

### Pass 5: LaTeX-Specific Review

Check compilation output and LaTeX conventions (see checklist below).

---

## Grammar & Formatting Checklist

### Text
- [ ] Spelling and grammar (run spellcheck)
- [ ] Consistent tense (past for completed work, present for claims)
- [ ] No dangling modifiers or ambiguous pronoun references
- [ ] Consistent use of Oxford comma (or consistent omission)
- [ ] Proper hyphenation of compound modifiers ("well-known method" but "the method is well known")
- [ ] Em-dashes reserved for genuine paired parenthetical asides only
- [ ] "i.e." and "e.g." set off by commas

### LaTeX
- [ ] Consistent math mode (`$x$` everywhere, not sometimes italic text)
- [ ] Proper escaping of special characters (`\%`, `\_`, `\&`)
- [ ] Non-breaking spaces before references: `Figure~\ref{fig:x}`, `Table~\ref{tab:y}`, `Section~\ref{sec:z}`
- [ ] Non-breaking tilde before `\cite{}`, `\ref{}`, `\eqref{}`
- [ ] Consistent use of `\emph{}` vs `\textit{}` vs `\textbf{}`
- [ ] "Figure" (not "Fig.") at the start of a sentence; likewise for "Table", "Section", "Equation"
- [ ] `\citet{}` for narrative citations, `\citep{}` for parenthetical (if the template supports natbib; otherwise stay consistent with existing convention)
- [ ] Consistent `\label{}` prefixes: `fig:`, `tab:`, `sec:`, `eq:`
- [ ] `\usepackage{microtype}` in preamble for improved typography
- [ ] No overfull/underfull hbox warnings (check compilation log)

### References
- [ ] All `\cite{}` keys resolve (no undefined references)
- [ ] No dangling references (cited but not in `.bib`, or in `.bib` but never cited)
- [ ] All figure/table cross-references resolve (`\ref{}` matches `\label{}`)
- [ ] Consistent citation format throughout

### Figures & Tables
- [ ] All figures and tables referenced in text before they appear
- [ ] Captions are self-contained (understandable without reading main text)
- [ ] Consistent number formatting (decimal places, thousands separators)
- [ ] Direction indicators on metrics (↑ higher better, ↓ lower better)
- [ ] Best values bolded consistently
- [ ] No title inside figure (the caption serves this function)

---

## Page-Fitting Techniques

When the draft exceeds the page limit:

| Technique | How | Impact |
|-----------|-----|--------|
| `\looseness=-1` | Place before a paragraph's blank line | Squeezes paragraph by ~1 line |
| Move content to appendix | Move proofs, extra ablations, implementation details | Can save 0.5-2 pages |
| Condense related work | Convert to shorter paragraph form | Saves 0.25-0.5 pages |
| Tighten figure placement | Use `[t]` or `[h]` float specifiers; adjust `\textfloatsep` | Reduces whitespace |
| Reduce figure size | `\includegraphics[width=0.45\linewidth]` | Fits more per page |
| Combine small tables | Merge related tables side by side | Eliminates float overhead |
| Use `\paragraph{}` | Replace `\subsubsection{}` with inline headings | Saves vertical space |

**Do not** modify margins, font sizes, or spacing commands in the style file — this violates venue formatting rules and risks desk rejection.

---

## On-Demand References

- **For detailed style rules and examples:** Read `references/writing-guide.md`
