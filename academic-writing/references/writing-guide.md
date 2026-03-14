# Academic Paper Writing Philosophy & Best Practices

This is the single source of truth for writing advice across all academic-writing skills. Skill files defer here for rules, examples, and diagnostics.

Severity tags: `[CRITICAL]` = causes desk rejection or major reviewer complaints. `[IMPORTANT]` = affects perceived quality. `[NICE]` = polish.

---

## Contents

### Part I: Paper Architecture

- [The Narrative Principle](#the-narrative-principle)
- [Time Allocation](#time-allocation)
- [Abstract](#abstract)
- [Introduction](#introduction)
- [Methods](#methods)
- [Experiments](#experiments)
- [Related Work](#related-work)
- [Limitations](#limitations)
- [Conclusion](#conclusion)
- [Figures and Tables](#figures-and-tables)

### Part II: Cross-Cutting Writing Principles

- [Sentence-Level Clarity](#sentence-level-clarity)
- [Micro-Level Writing Tips](#micro-level-writing-tips)
- [Word Choice and Precision](#word-choice-and-precision)
    - [Calibrated Hedging](#calibrated-hedging)
    - [Reporting Quantitative Results](#reporting-quantitative-results)
- [Mathematical Writing](#mathematical-writing)

### Part III: Quality Assurance

- [Grammar & Formatting Checklist](#grammar--formatting-checklist)
- [Pre-Submission Checklist](#pre-submission-checklist)
- [Citation Workflow](#citation-workflow)

---

## Part I: Paper Architecture

---

### The Narrative Principle

"A paper is a short, rigorous, evidence-based technical story with a takeaway readers care about."

The narrative rests on three pillars that must be crystal clear by the end of your introduction:

**The "What"**: One to three specific novel claims fitting within a cohesive theme. Vague contributions like "we study X" fail immediately—reviewers need precise, falsifiable claims.

**The "Why"**: Rigorous empirical evidence that convincingly supports those claims, including strong baselines honestly tuned and experiments that distinguish between competing hypotheses rather than merely showing "decent results."

**The "So What"**: Why readers should care, connecting your contribution to problems the community recognizes as important.

A paper is not a random collection of experiments you report on. The paper sells a single thing that was not obvious or present before. The entire paper is organized around this core contribution with surgical precision. This applies whether you're presenting a new architecture, a theoretical result, or improved understanding of existing methods.

**Practical Implication**: If you cannot state your contribution in one sentence, you don't yet have a paper. Everything else—experiments, related work, discussion—exists only to support that core claim.

---

### Time Allocation

Spend approximately **the same amount of time** on each of:

1. The abstract
2. The introduction
3. The figures
4. Everything else combined

This isn't hyperbole—most reviewers form preliminary judgments before reaching your methods section. Readers encounter your paper in a predictable pattern: **title → abstract → introduction → figures → maybe the rest.**

Studies of reviewer behavior show:

- Abstract is read 100% of the time
- Introduction is skimmed by 90%+ of reviewers
- Figures are examined before methods by most reviewers
- Full methods are read only if interest is established

**Implication**: Front-load your paper's value. Don't bury the contribution.

---

### Abstract

#### 5-Sentence Formula

1. **What you achieved**: "We introduce...", "We prove...", "We demonstrate..."
2. **Why this is hard and important**
3. **How you do it** (with specialist keywords for discoverability)
4. **What evidence you have**
5. **Your most remarkable number/result**

#### Example

```
We prove that gradient descent on overparameterized neural networks
converges to global minima at a linear rate. [What]
This resolves a fundamental question about why deep learning works
despite non-convex optimization landscapes. [Why hard/important]
Our proof relies on showing that the Neural Tangent Kernel remains
approximately constant during training, reducing the problem to
kernel regression. [How with keywords]
We validate our theory on CIFAR-10 and ImageNet, showing that
predicted convergence rates match experiments within 5%. [Evidence]
This is the first polynomial-time convergence guarantee for
networks with practical depth and width. [Remarkable result]
```

#### What to Avoid

If the first sentence can be prepended to any paper in the field, delete it.

**Delete these openings**:

- "Large language models have achieved remarkable success..."
- "Deep learning has revolutionized..."
- "In recent years, neural networks have..."

**Start with your specific contribution instead.**

#### Common Problems

| Severity      | Symptom                                      | Fix                                                                           |
| ------------- | -------------------------------------------- | ----------------------------------------------------------------------------- |
| `[CRITICAL]`  | Abstract could be prepended to any ML paper  | Delete generic first sentence; start with "We introduce/prove/demonstrate..." |
| `[IMPORTANT]` | Opening uses "In recent years..." or similar | Replace with what you achieved                                                |

---

### Introduction

#### Structure

- **1-1.5 pages maximum** (in two-column format)
- **Methods should start by page 2-3**
- Must include **2-4 bullet contribution list** (max 1-2 lines each)

#### Template

```markdown
1. Opening Hook (2-3 sentences)
   - State the problem your paper addresses
   - Why it matters RIGHT NOW

2. Background/Challenge (1 paragraph)
   - What makes this problem hard?
   - What have others tried? Why is it insufficient?

3. Your Approach (1 paragraph)
   - What do you do differently?
   - Key insight that enables your contribution

4. Contribution Bullets (2-4 items)
   - Be specific and falsifiable
   - Each bullet: 1-2 lines maximum

5. Results Preview (2-3 sentences)
   - Most impressive numbers
   - Scope of evaluation

6. Paper Organization (optional, 1-2 sentences)
   - "Section 2 presents... Section 3 describes..."
```

#### Contribution Bullets: Good vs Bad

**Good:**

- We prove that X converges in O(n log n) time under assumption Y
- We introduce Z, a 3-layer architecture that reduces memory by 40%
- We demonstrate that A outperforms B by 15% on benchmark C

**Bad:**

- We study the problem of X (not a contribution)
- We provide extensive experiments (too vague)
- We make several contributions to the field (says nothing)

#### Common Problems

| Severity      | Symptom                            | Fix                                                                                                  |
| ------------- | ---------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `[CRITICAL]`  | Introduction too long (>1.5 pages) | Move background to Related Work; front-load contribution bullets within first page; cut content that doesn't directly motivate the contribution |
| `[CRITICAL]`  | Missing contribution bullets       | Add 2-4 specific, falsifiable claims                                                                 |
| `[IMPORTANT]` | Methods buried (after page 3)      | Front-load contribution, cut intro                                                                   |

---

### Methods

The goal is to enable reimplementation from the description alone.

#### Requirements

- **Conceptual outline or pseudocode** for the algorithm
- **All hyperparameters** listed explicitly
- **Architectural details** sufficient for reproduction (layer sizes, activation functions, etc.)
- **Final design only** — present the design you used; ablations belong in Experiments

#### Common Problems

| Severity      | Symptom                                            | Fix                                                                     |
| ------------- | -------------------------------------------------- | ----------------------------------------------------------------------- |
| `[CRITICAL]`  | A reader couldn't reimplement from the description | Add pseudocode, list all hyperparameters, specify architectural details |
| `[IMPORTANT]` | Ablation studies mixed into Methods                | Move ablations to Experiments; keep Methods focused on final design     |

---

### Experiments

For each experiment, explicitly state what claim it supports and how it connects to the main contribution.

#### Requirements

- **Claim-driven structure**: Before each experiment, state "This experiment tests whether [specific claim]..." After results: "The results in Table X show that [interpretation], confirming [claim]."
- **Error bars** with methodology (standard deviation vs standard error)
- **Number of runs and seeds** reported
- **Hyperparameter search ranges** documented
- **Compute infrastructure** (GPU type, total hours)
- **Seed-setting methods** specified

#### Results Rhetoric

How you present numbers matters as much as the numbers themselves:

- **Lead with the key numeric finding, then interpret.** Don't bury the number after a long setup.
    - **Weak**: "After applying our method to the dataset and comparing with baselines, we found that accuracy was 92.1%"
    - **Strong**: "Our method achieves 92.1% accuracy, a 4.8% improvement over the strongest baseline (Table 2). This confirms that..."
- **Use consistent directional language** throughout the paper: "within X% of," "X% below," "+X% over"
- **For comparative tables**: always include the baseline value alongside improvements, so readers don't have to cross-reference
- **Avoid false universals**: use "most," "5 of 6," or "across all three datasets" instead of unqualified "all"

#### Claim Substantiation

Every claim needs proportional evidence:

- **Surprising results require explicit hypotheses** with "could be explained by" + citation
    - Example: "AL occasionally matches full-data performance. This could be explained by noise in the full dataset, where AL selectively filters low-quality samples \citep{...}."
- **Ground general claims with citations**: "an observation consistent with prior work \citep{...}"
- Claims without supporting evidence or citations read as speculation — either substantiate or remove

#### Common Problems

| Severity      | Symptom                                          | Fix                                                                                                  |
| ------------- | ------------------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| `[CRITICAL]`  | Tables and figures without clear takeaways       | Add a sentence before each experiment stating what it tests, and after results stating the interpretation |
| `[CRITICAL]`  | Single-run results with no error bars            | Add error bars (specify std dev or std error); report number of runs and seeds; add statistical tests if comparing methods |
| `[IMPORTANT]` | Experiments without explicit claims              | State what each experiment tests                                                                     |
| `[IMPORTANT]` | Surprising results stated without explanation    | Add explicit hypothesis with "could be explained by" + citation                                      |
| `[IMPORTANT]` | Vague quantitative language ("roughly," "about") | Use exact values and ranges; include both metric and absolute context                                |

---

### Related Work

Organize methodologically, not paper-by-paper.

**Good:** "One line of work uses X's assumption [refs] whereas we use Y's assumption because..."

**Bad:** "A et al. introduced X while B et al. introduced Y."

Cite generously—reviewers likely authored relevant papers.

#### Common Problems

| Severity      | Symptom                                                    | Fix                                                                                                  |
| ------------- | ---------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `[CRITICAL]`  | Paper-by-paper listing ("A et al. did X. B et al. did Y.") | Reorganize methodologically: "One line of work addresses X using approach A [refs], while another uses approach B [refs]. Our work differs in..." |
| `[IMPORTANT]` | Missing relevant citations                                 | Reviewers authored papers—cite generously                                                            |
| `[NICE]`      | Inconsistent citation format                               | Use BibLaTeX with consistent keys                                                                    |

---

### Limitations

All major conferences require a limitations section. Counter-intuitively, honesty helps:

- Reviewers are instructed not to penalize honest limitation acknowledgment
- Pre-empt criticisms by identifying weaknesses first
- Explain why limitations don't undermine core claims

#### Structure

Organize limitations in decreasing order of scope:

1. **Scope limitations**: What the method does not cover (e.g., "We evaluate only on English-language data")
2. **Methodological limitations**: Assumptions, simplifications, or design choices that constrain generality (e.g., "Our approach assumes access to paired training data")
3. **Evaluation limitations**: Gaps in experimental coverage (e.g., "We do not evaluate on datasets larger than 10M examples due to compute constraints")

#### Good vs Bad Limitation Writing

**Bad**: "Our method has some limitations."

**Good**: "Our evaluation is limited to English-language benchmarks. While the architecture is language-agnostic, cross-lingual transfer performance remains untested. Additionally, our method requires O(n²) memory, making it impractical for sequences longer than 8K tokens without the approximation described in Appendix B."

The good example is specific, honest, and explains scope without undermining core claims.

#### Common Problems

| Severity      | Symptom                                              | Fix                                                                                        |
| ------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| `[CRITICAL]`  | Limitations section is missing entirely              | Add one — all major venues require it; desk rejection risk                                 |
| `[IMPORTANT]` | Limitations section is just one sentence             | Address scope, methodology, and evaluation gaps separately                                 |
| `[IMPORTANT]` | Limitations are vague ("our method has limitations") | Be specific: state what the limitation is, why it exists, and what it means for the claims |
| `[NICE]`      | Limitations are overly apologetic                    | State facts neutrally; don't undermine your own contribution                               |

---

### Conclusion

Restate contribution, summarize evidence, point to future work. Keep it concise — this is not the place for new claims or results.

#### Structure

1. **Contribution restatement**: Remind the reader what you did and why it matters (1-2 sentences)
2. **Key evidence summary**: Highlight the most compelling results that support your claims (1-2 sentences)
3. **Broader implications**: Connect your work to the larger research landscape (1 sentence)
4. **Future work**: Point to concrete next steps or open questions (1-2 sentences)

#### What NOT to Put in Conclusions

- **No new claims**: Every claim must appear in the body first
- **No new results**: If a number matters, it belongs in Experiments
- **No apologies**: Don't end the paper by undermining your own work ("unfortunately, we could not...")
- **No excessive speculation**: Future work should be grounded, not a wish list

#### Common Problems

| Severity      | Symptom                                              | Fix                                                                   |
| ------------- | ---------------------------------------------------- | --------------------------------------------------------------------- |
| `[IMPORTANT]` | Conclusion introduces claims not in the paper body   | Move new claims to the appropriate section; conclusion only restates  |
| `[IMPORTANT]` | Conclusion is just a copy of the abstract            | Rewrite to emphasize evidence and implications, not just re-summarize |
| `[NICE]`      | Future work is too vague ("we plan to explore more") | Name specific directions: datasets, methods, or open questions        |
| `[NICE]`      | Conclusion is more than half a page                  | Cut to 1 paragraph (2-column) or 2 short paragraphs (single-column)   |

---

### Figures and Tables

#### Cross-Referencing Rule

`[IMPORTANT]` Every algorithm, figure, and table must be **introduced by text before it appears** and **referenced at least once** in the body. Never let a float appear without the reader knowing why it's there.

#### Figure Design Principles

1. `[CRITICAL]` **Figure 1 is crucial**: Often the first thing readers examine after abstract
2. `[CRITICAL]` **Self-contained captions**: Reader should understand figure without main text
3. `[IMPORTANT]` **No title inside figure**: The caption serves this function
4. `[IMPORTANT]` **Vector graphics**: PDF/EPS for plots, PNG (600 DPI) only for photographs

#### Table Formatting

- Use `booktabs` package
- Bold best values
- Include direction symbols (↑ higher better, ↓ lower better)
- Right-align numbers
- Consistent decimal precision

#### Accessibility

8% of men have color vision deficiency. Your figures must work for them.

- Use colorblind-safe palettes: Okabe-Ito or Paul Tol
- Avoid red-green combinations
- Verify figures work in grayscale
- Use different line styles (solid, dashed, dotted) in addition to colors

#### Tools

```python
# SciencePlots: Publication-ready styles
import matplotlib.pyplot as plt
plt.style.use(['science', 'ieee'])

# Or for Nature-style
plt.style.use(['science', 'nature'])
```

#### Common Problems

| Severity      | Symptom                                  | Fix                          |
| ------------- | ---------------------------------------- | ---------------------------- |
| `[CRITICAL]`  | Captions require main text to understand | Make captions self-contained |
| `[IMPORTANT]` | Raster graphics for plots                | Use vector (PDF/EPS)         |
| `[IMPORTANT]` | Red-green color scheme                   | Use colorblind-safe palette  |
| `[NICE]`      | Title inside figure                      | Put title in caption         |

---

## Part II: Cross-Cutting Writing Principles

---

### Sentence-Level Clarity

Readers have structural expectations about where information appears in prose. Violating these expectations forces readers to spend energy on structure rather than content.

> "If the reader is to grasp what the writer means, the writer must understand what the reader needs."

#### The 7 Principles of Reader Expectations

**Principle 1: Subject-Verb Proximity**

Keep grammatical subject and verb close together. Anything intervening reads as interruption of lesser importance.

**Weak**: "The model, which was trained on 100M tokens and fine-tuned on domain-specific data using LoRA with rank 16, achieves state-of-the-art results"

**Strong**: "The model achieves state-of-the-art results after training on 100M tokens and fine-tuning with LoRA (rank 16)"

**Principle 2: Stress Position (Save the Best for Last)**

Readers naturally emphasize the **last words of a sentence**. Place your most important information there.

**Weak**: "Accuracy improves by 15% when using attention"
**Strong**: "When using attention, accuracy improves by **15%**"

**Principle 3: Topic Position (First Things First)**

The beginning of a sentence establishes perspective. Put the "whose story" element first—readers expect the sentence to be about whoever shows up first.

**Weak**: "A novel attention mechanism that computes alignment scores is introduced"
**Strong**: "To address the alignment problem, we introduce a novel attention mechanism"

**Principle 4: Old Information Before New**

Put familiar information (old) in the topic position for backward linkage; put new information in the stress position for emphasis.

**Weak**: "Sparse attention was introduced by Child et al. The quadratic complexity of standard attention motivates this work."
**Strong**: "Standard attention has quadratic complexity. To address this, Child et al. introduced sparse attention."

**Principle 5: One Unit, One Function**

Each unit of discourse (sentence, paragraph, section) should serve a single function. If you have two points, use two units.

**Principle 6: Articulate Action in the Verb**

Express the action of each sentence in its verb, not in nominalized nouns.

**Weak**: "We performed an analysis of the results" (nominalization)
**Strong**: "We analyzed the results" (action in verb)

**Principle 7: Context Before New Information**

Provide context before asking the reader to consider anything new. This applies at all levels—sentence, paragraph, section.

**Weak**: "Equation 3 shows that convergence is guaranteed when the learning rate satisfies..."
**Strong**: "For convergence to be guaranteed, the learning rate must satisfy the condition in Equation 3..."

#### Summary Table

| Principle              | Rule                           | Mnemonic                   |
| ---------------------- | ------------------------------ | -------------------------- |
| Subject-Verb Proximity | Keep subject and verb close    | "Don't interrupt yourself" |
| Stress Position        | Emphasis at sentence end       | "Save the best for last"   |
| Topic Position         | Context at sentence start      | "First things first"       |
| Old Before New         | Familiar → unfamiliar          | "Build on known ground"    |
| One Unit, One Function | Each paragraph = one point     | "One idea per container"   |
| Action in Verb         | Use verbs, not nominalizations | "Verbs do, nouns sit"      |
| Context Before New     | Explain before presenting      | "Set the stage first"      |

---

### Micro-Level Writing Tips

Small changes that accumulate into significantly clearer prose.

When starting a sentence do not use "Fig.". Use "Figure". Similar for "Table"

#### Pronoun Management

**Minimize pronouns** ("this," "it," "these," "that"). When pronouns are necessary, use them as adjectives with a noun:

**Weak**: "This shows that the model converges."
**Strong**: "This result shows that the model converges."

**Weak**: "It improves performance."
**Strong**: "This modification improves performance."

#### Verb Placement

**Position verbs early** in sentences for better parsing:

**Weak**: "The gradient, after being computed and normalized, updates the weights."
**Strong**: "The gradient updates the weights after being computed and normalized."

#### Apostrophe Unfolding

Transform possessive constructions for clarity:

**Original**: "X's Y" → **Unfolded**: "The Y of X"

**Before**: "The model's accuracy on the test set"
**After**: "The accuracy of the model on the test set"

This isn't always better, but when sentences feel awkward, try unfolding.

#### Words to Eliminate

Delete these filler words and phrases in almost all cases:

- "actually"
- "a bit"
- "fortunately" / "unfortunately"
- "very" / "really"
- "quite"
- "basically"
- "essentially"
- "It is worth noting that" → just state it
- "In order to" → "To"
- Excessive connectives ("however," "moreover," "furthermore" when not needed)

#### Sentence Construction Rules

1. **One idea per sentence** - If struggling to express an idea in one sentence, it needs two
2. **No repeated sounds** - Avoid similar-sounding words in the same sentence
3. **Every sentence adds information** - Delete sentences that merely restate
4. **Active voice always** - Specify the actor ("We find..." not "It is found...")
5. **Expand contractions** - "don't" → "do not" for formality

#### Paragraph Architecture

- **First sentence**: State the point clearly
- **Middle sentences**: Support with evidence
- **Last sentence**: Reinforce or transition

Don't bury key information in the middle of paragraphs.

---

### Word Choice and Precision

#### Calibrated Hedging

Hedge precisely based on evidence strength — neither over-hedge nor under-hedge:

- Use **"can"** for direct observations supported by your data: "The model can recover 95% of lesions at this threshold."
- Use **"could"** for post-hoc explanatory reasoning or hypotheses: "This could be explained by the fact that..."
- Avoid **stacked hedges**: "might possibly suggest" → pick one hedge word
- Avoid **empty hedges**: "theoretically," "arguably" — either provide the theory/argument or drop the qualifier
- Delete **vacuous intensifiers that signal insecurity**: "provides *very* tight approximation" → "provides tight approximation"
- When claiming non-obvious or surprising results, provide an **explicit hypothesis**: "This could be explained by X \citep{...}."

#### Avoid Vacuous Intensifiers

Delete: very, extremely, highly, significantly (unless statistical). These words signal insecurity, not strength.

#### Precision Over Brevity

Replace vague terms with specific ones.

| Vague        | Specific                                       |
| ------------ | ---------------------------------------------- |
| performance  | accuracy, latency, throughput                  |
| improves     | increases accuracy by X%, reduces latency by Y |
| large        | 1B parameters, 100M tokens                     |
| fast         | 3x faster, 50ms latency                        |
| good results | 92% accuracy, 0.85 F1                          |

#### Consistent Terminology

Referring to the same concept with different terms creates confusion.

**Choose one and stick with it**:

- "model" vs "network" vs "architecture"
- "training" vs "learning" vs "optimization"
- "sample" vs "example" vs "instance"

**Abbreviation discipline:**

- Define abbreviations on first occurrence in each major section, then use the abbreviation consistently thereafter
- Once a term is established (e.g., "Active Learning (AL)"), never paraphrase it as a synonym — always use the defined form

#### Reporting Quantitative Results

When describing numeric findings, precision builds credibility:

- **Prefer exact values and ranges** over "roughly," "about," "approximately" — use "1--3%", "6--12%" instead
- **Include both metric values AND absolute context**: "FROC of 0.853, falling 6% below the full-data baseline (0.910)"
- **Standard comparison format**: `[Method] achieves [Metric] [Value], [+/-X%] over [Baseline]`
    - Example: "Our method achieves 92.1% accuracy, +4.8% over the previous best (87.3%)"

#### Vocabulary Signaling

**Avoid words signaling incremental work**:

- Never: "combine," "modify," "expand," "extend"
- Instead: "develop," "propose," "introduce"

**Why**: "We combine X and Y" sounds like you stapled two existing ideas together. "We develop a method that leverages X for Y" sounds like genuine contribution.

---

### Mathematical Writing

#### Principles

1. **State all assumptions formally** before theorems
2. **Provide intuitive explanations** alongside proofs
3. **Use consistent notation** throughout the paper
4. **Define symbols at first use**

#### Notation Conventions

```latex
% Scalars: lowercase italic
$x$, $y$, $\alpha$, $\beta$

% Vectors: lowercase bold
$\mathbf{x}$, $\mathbf{v}$

% Matrices: uppercase bold
$\mathbf{W}$, $\mathbf{X}$

% Sets: uppercase calligraphic
$\mathcal{X}$, $\mathcal{D}$

% Functions: roman for named functions
$\mathrm{softmax}$, $\mathrm{ReLU}$
```

---

## Part III: Quality Assurance

---

### Grammar & Formatting Checklist

#### Text

- [ ] Spelling and grammar (run spellcheck)
- [ ] Consistent tense (past for completed work, present for claims)
- [ ] No dangling modifiers or ambiguous pronoun references
- [ ] Consistent use of Oxford comma (or consistent omission)
- [ ] Proper hyphenation of compound modifiers ("well-known method" but "the method is well known")
- [ ] Em-dashes reserved for genuine paired parenthetical asides only; prefer commas, colons, or parentheses otherwise
- [ ] "i.e." and "e.g." set off by commas for inline definitions/examples

#### LaTeX

- [ ] Consistent math mode (`$x$` everywhere, not sometimes italic text)
- [ ] Proper escaping of special characters (`\%`, `\_`, `\&`)
- [ ] Non-breaking spaces before references: `Figure~\ref{fig:x}`, `Table~\ref{tab:y}`
- [ ] Consistent use of `\emph{}` vs `\textit{}` vs `\textbf{}`
- [ ] No overfull/underfull hbox warnings (check compilation log)

#### LaTeX Conventions

- [ ] Use `\citet{}` for narrative citations ("Smith et al. (2023) show...") and `\citep{}` for parenthetical citations ("...as shown previously \citep{smith2023}")
- [ ] Non-breaking tilde `~` before all `\cite{}`, `\ref{}`, and `\eqref{}` commands (e.g., `results~\citep{x}`, `Section~\ref{sec:y}`, `Equation~\eqref{eq:z}`)
- [ ] Use `\paragraph{}` for inline headings when sections get dense, instead of adding more `\subsubsection{}` levels
- [ ] Consistent `\label{}` naming conventions: `fig:` for figures, `tab:` for tables, `sec:` for sections, `eq:` for equations (e.g., `\label{fig:overview}`, `\label{tab:results}`)
- [ ] Use `\usepackage{microtype}` in preamble for improved character spacing and typography
- [ ] If the template or existing tex uses `\cite{}` rather than `\citet{}`/`\citep{}`, stay consistent with the existing convention
- [ ] Use `\looseness=-1` on paragraphs that overflow by 1-2 words to fit page limits (place before the paragraph's blank line)

#### References

- [ ] All `\cite{}` keys resolve (no undefined references)
- [ ] No dangling references (cited but not in `.bib`, or in `.bib` but never cited)
- [ ] All figure/table cross-references resolve (`\ref{}` matches `\label{}`)
- [ ] Consistent citation format (e.g., "Smith et al. (2023)" vs "(Smith et al., 2023)")

#### Figures & Tables

- [ ] All figures referenced in text
- [ ] Captions are self-contained (understandable without reading main text)
- [ ] Consistent number formatting (decimal places, thousands separators)
- [ ] Direction indicators on metrics (↑ higher better, ↓ lower better)
- [ ] Best values bolded consistently

---

### Pre-Submission Checklist

Before submitting, verify:

**Narrative**:

- [ ] Can state contribution in one sentence
- [ ] Three pillars (What/Why/So What) clear in intro
- [ ] Every experiment supports a specific claim

**Structure**:

- [ ] Abstract follows 5-sentence formula
- [ ] Introduction ≤1.5 pages
- [ ] Methods start by page 2-3
- [ ] 2-4 contribution bullets included
- [ ] Limitations section present

**Writing**:

- [ ] Consistent terminology throughout
- [ ] No generic opening sentences
- [ ] Hedging removed unless necessary
- [ ] All figures have self-contained captions

**Technical**:

- [ ] Error bars included with methodology
- [ ] Compute resources documented
- [ ] Code/data availability stated

**Readability Self-Check**:

- [ ] Explicit signposting present ("In this section, we show X" / "Having established Y, we now...")
- [ ] Each paragraph makes exactly one point
- [ ] No disconnected sections — clear logical flow throughout

---

### Citation Workflow

When adding new references during drafting or revision:

- **Never directly modify the main `.bib` file.** The main bibliography is a curated, verified source of truth.
- **Insert new BibTeX entries in a separate file** (e.g., `citation-to-verify.bib`) for review before merging into the main `.bib`.
- This prevents accidental corruption of existing entries and creates a clear review checkpoint for co-authors to verify new citations.