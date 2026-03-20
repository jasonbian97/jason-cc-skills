# Paper Submission Checklists

This reference documents the essential checklist requirements for submitting academic papers. Most major venues now require paper checklists — missing them can result in desk rejection. Always check your target venue's specific requirements in addition to these universal checks.

---

## Contents

- [Pre-Submission Checklist](#pre-submission-checklist)
- [Reproducibility Checklist](#reproducibility-checklist)
- [Ethics & Broader Impact Checklist](#ethics--broader-impact-checklist)
- [Final Checks](#final-checks)

---

## Pre-Submission Checklist

### Paper Content

- [ ] Abstract within word limit (typically 250-300 words; check venue)
- [ ] Main content within page limit
- [ ] Abstract and introduction claims match actual results (no overclaiming)
- [ ] Contributions are specific and falsifiable
- [ ] References complete and verified
- [ ] Limitations section included (required by most venues; missing this risks desk rejection)
- [ ] All figures/tables have self-contained captions
- [ ] Every figure and table referenced in text before it appears

### Claims Alignment

- [ ] Abstract claims match theoretical and experimental results
- [ ] Introduction doesn't overclaim beyond what the evidence supports
- [ ] Every claim in the paper has proportional evidence

### Formatting

- [ ] Correct template used (venue + year specific)
- [ ] Margins and font sizes unmodified
- [ ] Double-blind requirements met (if applicable)
- [ ] No author names, acknowledgments, or identifiable repository URLs (during review)
- [ ] Prior work cited in third person (during review)
- [ ] Section headings use consistent title case throughout
- [ ] Page numbers present for review submission (or absent for camera-ready, per venue)

### Technical

- [ ] All claims supported by evidence
- [ ] Error bars or confidence intervals included
- [ ] Number of runs and seeds reported
- [ ] Baselines appropriate and up-to-date
- [ ] Hyperparameters documented
- [ ] Compute resources stated (GPU type, training time)
- [ ] Statistical significance testing where methods are compared

### Theory & Proofs (if applicable)

- [ ] All assumptions stated formally before theorems
- [ ] Complete proofs provided (main text or appendix)
- [ ] Proof sketches in main text for intuition

---

## Reproducibility Checklist

### Code & Data

- [ ] Code availability stated (or justification for not releasing)
- [ ] Data availability stated (or justification)
- [ ] Exact commands to reproduce main results
- [ ] Environment specifications (requirements.txt, conda env, Docker)
- [ ] Dataset licenses cited and respected

### Experimental Details

- [ ] Train/validation/test split details
- [ ] All hyperparameters listed
- [ ] Hyperparameter search ranges documented
- [ ] Selection method explained (grid search, random, Bayesian, etc.)
- [ ] Seed-setting methods specified

### Statistical Reporting

- [ ] Error bars on all results (specify standard deviation vs standard error)
- [ ] Number of runs stated
- [ ] Significance tests if comparing methods
- [ ] Calculation method documented

---

## Ethics & Broader Impact Checklist

### Broader Impact

- [ ] Potential positive impacts considered
- [ ] Potential negative applications discussed
- [ ] Fairness considerations addressed (if applicable)
- [ ] Privacy implications noted (if applicable)
- [ ] Mitigation strategies described

### Data & Models

- [ ] Licenses of existing assets respected (cite creators, license names, URLs)
- [ ] New datasets/models documented (datasheets or model cards)
- [ ] Safeguards for high-risk models (controlled release, usage guidelines)

### Human Subjects (if applicable)

- [ ] IRB approval obtained
- [ ] Participant instructions documented
- [ ] Compensation details provided (minimum wage compliance)
- [ ] Risk assessment completed

### LLM Use Disclosure

Many venues now require disclosure if LLMs played a significant role in research ideation or writing. Check your target venue's policy. Writing/editing assistance typically doesn't require disclosure, but using LLMs as core methodology components usually does.

---

## Final Checks

- [ ] PDF compiles without errors
- [ ] All figures render correctly
- [ ] All citations resolve (no undefined references)
- [ ] No overfull/underfull hbox warnings
- [ ] Supplementary material organized
- [ ] Venue-specific checklist completed (check your target venue's website for their specific paper checklist requirements)
