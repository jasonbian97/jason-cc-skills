---
name: academic-writing:revise
description: Revise paper sections based on co-author feedback or TODO comments. Use when iterating on an existing draft, addressing co-author suggestions, or processing inline TODO comments in LaTeX source. Trigger whenever the user has feedback to incorporate, TODOs to resolve, sections to rewrite, or needs to adapt a paper for a different venue — even informally like "my advisor says this section needs work" or "can you fix these TODOs."
---

# Revise Paper Sections

Process co-author feedback, resolve inline TODO comments, and improve specific sections of an existing draft.

## Processing Feedback

### Co-Author Feedback

When feedback comes via email, chat, or comments:

1. **Map feedback to sections.** Each piece of feedback should target a specific part of the paper.
2. **Distinguish types:**
   - Content changes (new claims, different framing, added/removed experiments)
   - Structural changes (reorder sections, move content between sections)
   - Writing changes (rephrase, clarify, shorten)
3. **Confirm ambiguous feedback.** If a comment could mean multiple things, ask before revising.
4. **Make changes, then report.** Summarize what was changed and where.

### TODO Comment Workflow

For `% TODO:` comments in LaTeX source:

1. **Scan** the entire LaTeX source for all `% TODO:` comments
2. **List** all TODOs with file location, line number, and content
3. **Prioritize**: Content TODOs (missing results, wrong claims) before structural TODOs (reorder, expand) before cosmetic TODOs (rephrase, format)
4. **Process** each TODO: make the requested change
5. **Remove** the `% TODO:` comment after addressing it
6. **Report** a summary of all changes made

Example:
```latex
% Before:
We achieve state-of-the-art results on X. % TODO: add specific numbers

% After:
We achieve state-of-the-art results on X, improving accuracy from 87.3\% to 92.1\% (Table~\ref{tab:main}).
```

---

## Section-Specific Revision

For diagnosis and fixes of common section problems (generic abstract, long intro, reproducibility gaps, missing claims, etc.), consult `references/writing-guide.md` — each paper section includes a Common Problems table with symptoms and fixes.

---

## Revision vs. Rewrite

| Signal | Action |
|--------|--------|
| Feedback targets specific sentences/paragraphs | **Revise in-place** — edit the existing text |
| Feedback says "this section doesn't work" | **Restructure** — outline new structure, then rewrite |
| Multiple reviewers confused by same section | **Rewrite from scratch** — the framing is wrong, not just the words |
| Feedback is "needs more X" | **Expand** — add content while preserving existing structure |
| Feedback is "too long / too detailed" | **Condense** — cut ruthlessly, move details to appendix |

When rewriting a section:
1. Save the old version (comment out or keep in a separate file)
2. Outline the new structure before writing
3. Draft the new version
4. Compare against old version to ensure no content was accidentally dropped

---

## Track Changes

By default, make edits directly without track-change markup. Only use track changes when the user explicitly asks for them (e.g., "mark changes in blue," "use latexdiff," "highlight what you changed").

When requested, make changes visible:

| Method | When to Use |
|--------|-------------|
| Blue text (`\textcolor{blue}{...}`) | Quick, works everywhere, good for rebuttals |
| `\changed{}` custom macro | Define once in preamble, toggle on/off for camera-ready |
| `latexdiff old.tex new.tex` | Automated diff between two versions; generates marked-up PDF |
| Comments (`% CHANGED:`) | Lightweight, for co-author review within source |

**Tip:** Define a toggle macro so you can easily switch between marked-up and clean versions:

```latex
\newcommand{\changed}[1]{\textcolor{blue}{#1}}  % For review
% \newcommand{\changed}[1]{#1}                   % For camera-ready
```

---

## Format Conversion (Resubmission)

When resubmitting to a different venue:

1. **Start fresh** with the target venue's template (never merge preambles)
2. **Copy content only** (between `\section{}` commands), not LaTeX preamble
3. **Adjust for page limits** — cut or expand as needed
4. **Update venue-specific requirements** (checklists, impact statements, disclosures)
5. **Add new related work** published since last submission

---

## On-Demand References

- **Before revising any section:** Read `references/writing-guide.md` for style and clarity principles
