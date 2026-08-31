# MIG Journal Club: causal inference

## Session

- Format: 40-minute presentation followed by 20 minutes of discussion.
- Audience: statisticians, bioinformaticians and wet-lab scientists.
- This is not a comprehensive introduction to causal inference. It is one step in an ongoing effort to demystify what causal inference does, what it assumes and what it cannot establish from data alone.
- The session must work for people who have not read the papers.

## Central thesis

Causal inference does not extract causation from data. It defines a causal contrast, designs an analysis that could approximate that contrast, and makes explicit the assumptions connecting the observed data to the causal claim.

It can provide a precise scientific question, a disciplined design, a conditional estimate and a vocabulary for possible failure. It cannot by itself verify all identifying assumptions, reveal biological mechanism, guarantee generalisation or discover causal truth from patterns alone.

## Brief context: experiments, observational data and real-world data

The canonical way to estimate a causal effect is a randomised controlled experiment: specify the intervention and comparator, randomise units, define time zero and follow outcomes. Randomisation supports comparability of the treatment groups, although an RCT can still have measurement, adherence, selection and generalisability problems.

Many important questions cannot be answered by an RCT because an experiment would be unethical, infeasible, too slow, too expensive or unable to cover the population and follow-up of interest. There is therefore growing interest in causal inference—and, separately, causal discovery—from observational data. In pharmaceutical and regulatory settings, routinely collected data about patient health or healthcare delivery—such as electronic health records, insurance claims and registries—are commonly called **real-world data (RWD)**. **Real-world evidence (RWE)** is the clinical evidence produced by analysing RWD; data and evidence should not be treated as synonyms. The three papers in this session mainly concern estimating intervention effects from observational data, not causal discovery.

## Roles of the three papers

The talk will be organised around an argument rather than as three equal paper summaries.

1. **Dickerman et al., _Avoidable flaws in observational analyses_** is the narrative spine and concrete example. The same observational setting yields a near-null estimate under a target-trial design and a dramatic protective estimate when future treatment duration is used to define exposure.
2. **Lu et al., _Four targets_** supplies the reusable vocabulary: target estimand, target population, target trial and target validity.
3. **Swales, _The troublesome search for evidence_** supplies the broader frame: mechanistic, clinical/observational and numerical/statistical evidence should inform one another rather than compete for exclusive authority.

The papers need not receive equal time. The statin example should receive the most time; Swales should frame the limits and the closing synthesis.

## Recommended narrative

### 1. A result that should make us suspicious (0–4 minutes)

- Open with the claim that long-term statin use reduces cancer risk by roughly 77%.
- Place the flawed estimate (about 0.22–0.23) beside the target-trial estimate (about 1.02).
- Ask how analyses of essentially the same observational setting can produce such different answers.

### 2. What kind of causal inference is this? (4–9 minutes)

- Briefly establish the RCT as the canonical design for estimating intervention effects.
- Explain why observational or real-world data are increasingly used.
- Delimit the session: effects of interventions from observational data, rather than a survey of causal discovery, mediation, instrumental variables, Mendelian randomisation or causal graphical theory.
- Introduce the fundamental problem: a causal effect compares outcomes under alternative interventions, but we cannot observe the same unit in both worlds.
- The missing comparison is replaced by design and assumptions—not by data alone.

### 3. Four targets for formulating the question (9–18 minutes)

Translate the framework into ordinary questions:

- **Target estimand:** What effect, exactly—intervention, comparator, outcome, time horizon and summary measure?
- **Target population:** For whom is the conclusion intended?
- **Target trial:** What randomised experiment would answer the question?
- **Target validity:** Why should the estimate from this study answer that question for that population?

Avoid teaching the full technical glossary. Use one worked question and keep terminology subordinate to the scientific problem.

### 4. Solve the statin puzzle (18–30 minutes)

- Specify the hypothetical statin trial.
- Draw a patient timeline showing eligibility, treatment assignment and start of follow-up.
- Explain immortal time in plain language: to be classified as a user for more than four years, a person must remain alive, cancer-free and observed for those four years.
- Show that aligning eligibility, assignment and follow-up at time zero removes this built-in advantage.
- Contrast the near-null cancer estimates with the strongly protective flawed estimates.
- Use type 2 diabetes as a benchmark: the target-trial analysis agrees with the modest harmful effect seen in trials, whereas the flawed duration-based analysis manufactures a large protective association.
- Main lesson: the statistical model did not rescue the design; defining the experiment changed the answer.

### 5. What target-trial emulation does not fix (30–35 minutes)

- Unmeasured confounding remains possible.
- Treatment and outcomes may be misclassified.
- Positivity may fail.
- Selection and post-treatment filtering can create bias.
- The study sample may not represent the target population.
- Some errors are directly diagnosable, such as misaligned time zero; the absence of unmeasured confounding generally cannot be verified from observed data.

### 6. Evidence cultures and return to cell biology (35–40 minutes)

- Use Swales to resist replacing a mechanistic hierarchy with a statistical hierarchy.
- A carefully designed observational estimate remains one kind of evidence alongside perturbation experiments, biological mechanism and replication.
- Apply the four questions to a familiar example: “Does inhibiting pathway X reduce entry into an inflammatory macrophage state after 48 hours?”
- Ask whether the inferential unit is a cell, culture, donor or patient; whether treatment-induced death affects which cells survive quality control; when time zero occurs; and to which donors or systems the result could generalise.

## Slide design principles

- Aim for approximately 20–22 slides, with one claim per slide. The previous FactorIV deck used 22 rendered slides successfully for the same 40-minute plus 20-minute-discussion format.
- Prefer a problem → assumptions → worked example → limitations → discussion rhythm.
- Use minimal notation. Introduce technical names only after the underlying problem is concrete.
- Recreate the key numerical comparisons and the immortal-time timeline rather than showing dense full-page screenshots.
- Put detailed estimand components, inverse-probability weighting, sequential trial emulation and sensitivity analyses in backup slides if needed.
- Keep citations adjacent to claims and figures.

## Lessons carried forward from the FactorIV journal-club repository

The previous repository establishes a useful local precedent for both pedagogy and implementation:

- Treat the talk as a guided learning experience rather than a compressed paper recital.
- Build intuition before terminology and terminology before technical detail.
- Do not frame the session as “association bad, causation good”; association, prediction and causal inference answer different questions.
- Use a short, audience-facing glossary before relying on terms such as estimand, confounder and time zero.
- Reuse the restrained xaringan visual language: Inter typography, dark-navy section slides, blue headings, teal emphasis, generous margins, two-column panels, small comparison tables and callout boxes.
- Use simple HTML/SVG diagrams for the counterfactual comparison, RCT, target trial and immortal-time timeline. These were clearer in the prior deck than dense imported figures.
- Preserve the “what it is / what it is not” comparison as the closing boundary slide.
- Avoid reproducing the prior deck's densest moments: a multi-part assumptions diagram plus table on one slide, and an uncropped full paper figure with labels too small for the room.
- Keep detailed definitions, weighting methods and additional paper figures in speaker notes or backup slides.

The likely implementation path is to adapt the previous repository's `slides.Rmd` and `slides.css` structure rather than introduce a new presentation framework. Its browser-robust HTML/Unicode notation is preferable to relying on MathJax for simple expressions.

## Closing message

**Causal inference can give us:**

- a precisely formulated scientific question;
- a design intended to answer it;
- an estimate conditional on assumptions; and
- a vocabulary for explaining how the estimate could fail.

**It cannot give us by itself:**

- verification of every identifying assumption;
- biological mechanism;
- automatic generalisation; or
- causal truth discovered from associations alone.

## Discussion prompts

1. What would the target trial be for an analysis we routinely perform?
2. In single-cell experiments, when is the cell the wrong experimental unit?
3. What combination of statistical, experimental and mechanistic evidence would change our minds?

## Next step

Prepare a numbered 20–22-slide storyboard with approximate speaking time and a single headline claim for each slide. After approval, adapt the FactorIV xaringan source and CSS, render early, and visually check every slide for overflow and readability.
