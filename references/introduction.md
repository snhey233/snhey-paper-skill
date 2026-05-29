---
name: snhey-paper-introduction
description: Write, diagnose, restructure, or polish IEEE-style Introduction sections for power systems, smart grid, energy dispatch, unit commitment, renewable uncertainty, extreme-weather contingency, resilience, distributionally robust optimization, stochastic/robust optimization, prediction-then-optimization, and transmission-distribution coordination papers. Use when the user asks for introduction writing, Introduction写作, 引言写作, IEEE引言, 电力系统论文引言, DRO引言, 调度论文引言, or wants a reusable Introduction writing skill distilled from IEEE power-system papers.
---

# SNHEY Paper Introduction

Use this skill to write or revise IEEE Transactions-style Introduction sections for power-system optimization papers. The target Introduction is not a long background essay. It is a staged argument that moves from system pressure to literature map, from literature map to precise gap, and from gap to the paper's model, algorithm, validation logic, and contributions.

This skill was distilled from 14 unique IEEE Introduction sections in the user's Zotero collection "电网高温日" (15 IEEE records, one duplicate), covering IEEE Transactions on Power Systems, IEEE Transactions on Smart Grid, and IEEE Transactions on Sustainable Energy.

## Core Thesis

An IEEE power-systems Introduction should prove three things before the technical sections begin:

1. The engineering problem is urgent under a concrete system transition.
2. Existing literature has made progress, but a specific modeling/algorithmic/data gap remains.
3. The proposed work closes that gap through a coherent chain: uncertainty representation -> optimization model -> tractable solution -> numerical validation.

The Introduction should make the reader think: "Given this system pressure and this literature gap, the proposed method is the natural next step."

## Canonical Introduction Architecture

Most IEEE Introductions in this corpus follow 7 moves. Keep these moves even if the final section has different paragraph counts.

### Move 1: System Pressure And Application Stakes

Open with a real power-system transformation or reliability pressure.

Common openings in the corpus:

- Renewable penetration is increasing, bringing intermittency, volatility, and forecast-error uncertainty.
- Extreme weather events are becoming more frequent and intense, threatening power-system reliability and resilience.
- Active distribution grids, distributed generation, and energy storage make transmission-distribution coordination more important.
- Urban water systems, storage arbitrage, or other flexible loads are increasingly coupled with grid operation.
- New-energy systems reduce the share of controllable generation, increasing the need for reserves and coordinated scheduling.

Good Move 1 writing:

- Names the system object: unit commitment, energy/reserve dispatch, ITD/TDS scheduling, distribution-network resilience, N-k contingency warning, renewable scenario generation, storage arbitrage.
- Names the stressor: renewable forecast error, small samples, extreme weather, outages, price uncertainty, DDU, distributed predictions.
- Connects the stressor to an operational consequence: cost, reserve need, line overload, security violation, blackout risk, poor coordination, or reduced flexibility.

Avoid:

- "Power systems are important to modern society" unless the paper is about reliability/resilience and the next sentence immediately narrows to extreme-weather risk.
- General climate or carbon-neutrality background that does not lead to the paper's model.

### Move 2: First Literature Layer - Mainstream Problem Formulation

After the opening pressure, introduce the established modeling family for the task.

Typical literature layers:

- UC/dispatch under uncertainty: stochastic programming, robust optimization, DRO, chance-constrained optimization.
- Scenario generation: statistical models, probabilistic forecasting, deep generative models, GANs.
- Resilience planning: hardening, DER allocation, network reconfiguration, contingency modeling.
- ITD/TDS coordination: centralized coordination, distributed optimization, ADMM, decentralized dispatch.
- Prediction-to-decision: forecast-then-optimize, stochastic optimization, decision-focused learning.

Purpose:

- Show the reader that the paper sits inside an established literature.
- Avoid making the proposed work appear disconnected from prior methods.

Write this layer as:

```text
To address [uncertainty/task], existing studies have investigated [method family A], [method family B], and [method family C].
```

Then immediately begin narrowing. Do not write a catalog.

### Move 3: Second Literature Layer - Specific Technical Branch

IEEE Introductions usually zoom into a narrower branch before stating the final gap.

Examples:

- For DRO papers, zoom from stochastic/robust optimization to Wasserstein/moment/conditional/decision-dependent ambiguity sets.
- For chance-constrained dispatch, zoom from security-constrained dispatch to data-driven chance constraints and DR chance constraints.
- For scenario generation, zoom from scenario generation to conditional GANs, temporal encoders, and meteorological conditioning.
- For ITD dispatch, zoom from distributed optimization to synchronous/asynchronous ADMM and subsystem heterogeneity.
- For resilience, zoom from extreme-weather hardening to DDU, limited outage data, and scenario-wise ambiguity.

This move gives the Introduction technical depth. It tells the reader exactly which neighborhood of the literature you are entering.

### Move 4: Gap Crystallization

State the unresolved problem explicitly. This is the hinge of the Introduction.

Common gap types in the corpus:

- **Distributional gap**: Existing ambiguity sets ignore local/global multimodality, conditional dependence, tail behavior, moment-prediction relationships, or distributed predictions.
- **Decision-dependence gap**: Existing uncertainty sets treat uncertainty as exogenous, but scheduling/hardening/boundary decisions change the uncertainty distribution or feasible boundary range.
- **Joint-security gap**: Individual chance constraints cannot guarantee simultaneous satisfaction of security constraints.
- **Scalability gap**: Exact Wasserstein/DRCC/two-stage mixed-integer formulations become nonconvex or computationally heavy as samples, buses, scenarios, or subsystems grow.
- **Prediction-optimization gap**: Forecasting and optimization are trained separately, producing predictions that are statistically accurate but decision-suboptimal.
- **Extreme-weather gap**: Traditional N-k analysis or contingency screening fails to represent simultaneous weather-induced outages, spatio-temporal failure patterns, or sufficient preventive lead time.
- **Flexibility-modeling gap**: Existing UC/dispatch models do not quantify flexible resources, quick-start units, storage, or demand-side flexibility in the right decision stage.

Strong gap writing includes:

- What existing methods assume.
- Why that assumption fails in this paper's setting.
- What operational harm follows.

Weak gap writing:

- "However, few studies have considered this problem."
- "The existing methods are not accurate enough."
- "This problem remains challenging."

Replace weak gap statements with mechanism-level gaps:

```text
However, these methods usually construct ambiguity sets around unconditional forecast-error samples, thereby ignoring the dependence between the forecast value and the error distribution. This may yield overly conservative schedules when the conditional distribution changes across operating states.
```

### Move 5: This Paper's Technical Response

After the gap, state the paper's response in one compact paragraph.

This paragraph should include:

- Main model/framework.
- Uncertainty representation.
- Optimization or decision layer.
- Solution mechanism if central to the novelty.

Use a chain:

```text
To close this gap, this paper proposes [framework] for [task]. The framework constructs [uncertainty/ambiguity/scenario model] using [information], and embeds it into [optimization model]. To solve the resulting [difficulty], [algorithm/reformulation] is developed.
```

For power-system optimization, do not separate "model novelty" from "solution novelty" too much. IEEE readers expect to know whether the model is solvable.

### Move 6: Contributions

Most full IEEE Transactions Introductions include an explicit contribution list. It usually appears after the literature review and before the paper-organization paragraph.

Use 3 contributions by default. Use 2 for letters/short papers; use 4 only when the paper truly has four independent contributions.

The contribution list should not repeat the abstract. Each bullet should be more concrete than the abstract.

Preferred contribution structure:

1. **Modeling contribution**
   - New system model, uncertainty representation, ambiguity set, scenario generation, or coordination formulation.
2. **Theoretical/algorithmic contribution**
   - Reformulation, tractable approximation, decomposition, convergence/guarantee, distributed algorithm, or linearization.
3. **Validation/insight contribution**
   - Case studies, benchmark comparisons, out-of-sample performance, cost-risk tradeoff, scalability, or managerial/planning insight.

Each contribution should contain:

- What is proposed.
- What it captures/solves.
- How it differs from previous work.
- Why it matters operationally.

Avoid contribution bullets that are only nouns:

```text
1) A new DRO model is proposed.
2) A new algorithm is developed.
3) Case studies are conducted.
```

Use richer bullets:

```text
1) A conditional ambiguity set is constructed by exploiting the dependence between renewable forecasts and forecast errors, which reduces the conservatism caused by unconditional Wasserstein ambiguity sets.
```

### Move 7: Paper Organization

End with a short roadmap.

Keep it formulaic and brief:

```text
The remainder of this paper is organized as follows. Section II presents the system model. Section III develops the proposed [method]. Section IV derives the reformulation and solution algorithm. Section V reports case studies. Section VI concludes the paper.
```

Do not overexplain the roadmap. The organization paragraph is functional, not persuasive.

## Paragraph-Level Blueprint

Use this default 6-paragraph Introduction structure for full IEEE papers:

1. **Opening pressure**
   - Start from system transition.
   - Narrow to the exact operational task.
   - End by saying why uncertainty/risk/flexibility/coordination matters.

2. **Broad method literature**
   - Review major approaches.
   - Establish the known solution families.
   - Transition to the branch most relevant to the paper.

3. **Focused literature and limitations**
   - Review the closest technical papers by feature: uncertainty set, algorithm, coordination architecture, scenario generation, or resilience model.
   - State what each branch misses.

4. **Gap and paper response**
   - Crystallize the unresolved issue.
   - State "This paper..." with model and method.

5. **Contributions**
   - Use 3 bullets.
   - Order: modeling -> reformulation/algorithm -> validation/insight.

6. **Organization**
   - Brief section roadmap.

For shorter IEEE letters, compress to 4 paragraphs:

1. Pressure and gap.
2. Proposed method.
3. Key result/contribution.
4. Roadmap or omit roadmap if the venue style allows.

## Literature Review Logic

Do not organize the literature chronologically. Organize it by the logic of your gap.

### DRO/Robust Dispatch Papers

Recommended literature ladder:

1. Stochastic programming handles uncertainty using assumed or sampled distributions.
2. Robust optimization hedges against uncertainty sets but can be conservative.
3. DRO balances data-driven learning and robustness through ambiguity sets.
4. Wasserstein/moment/conditional ambiguity sets improve distributional modeling.
5. Remaining gap: existing sets ignore conditional structure, decision-dependence, multimodality, small-sample bias, distributed predictions, or tractability.

### Chance-Constrained/Security Dispatch Papers

Recommended ladder:

1. Security-constrained dispatch protects the grid under contingencies.
2. Chance constraints model renewable uncertainty probabilistically.
3. Scenario and sample-based methods are data-driven but may lack robustness.
4. DR chance constraints hedge distributional ambiguity.
5. Remaining gap: exact DR chance constraints are nonconvex/heavy, or individual constraints do not ensure joint security.

### Extreme-Weather Resilience Papers

Recommended ladder:

1. Extreme weather increases outage frequency, intensity, and spatial correlation.
2. Resilience studies use hardening, DER placement, reconfiguration, and proactive operation.
3. Contingency models or fragility models estimate component failures.
4. Existing approaches struggle with limited data, simultaneous failures, DDU, tail events, or preventive lead time.
5. Remaining gap: need a model that captures weather-event sequences/decision-dependent contingencies and supports proactive planning.

### Scenario Generation / Predict-Then-Optimize Papers

Recommended ladder:

1. Renewable scenario generation supports day-ahead or short-term operation.
2. Statistical and ML methods generate probabilistic forecasts/scenarios.
3. Conditional deep generative models capture spatial-temporal and meteorological patterns.
4. Forecast-then-optimize may optimize statistical fit rather than decision quality.
5. Remaining gap: need decision-aware, condition-aware, or optimization-aligned generation.

### ITD/TDS Distributed Optimization Papers

Recommended ladder:

1. Active distribution grids require coordination with transmission systems.
2. Centralized coordination faces privacy, scalability, or ownership limitations.
3. Distributed/decentralized algorithms, especially ADMM, enable coordination.
4. Synchronous algorithms suffer from heterogeneity and underused computation.
5. Remaining gap: need asynchronous or fully distributed methods that handle uncertainty and security constraints.

## Contribution Writing Rules

Use this contribution template:

```text
The main contributions of this paper are summarized as follows:
1) [Modeling contribution]. Specifically, [mechanism/detail]. Compared with [prior approach], [difference/benefit].
2) [Reformulation/algorithm contribution]. By exploiting [structure/theory], the proposed model is [recast/decomposed/approximated] as [tractable form], enabling [computational benefit].
3) [Validation/insight contribution]. Case studies on [systems/data] demonstrate [benefit], and reveal [operational insight].
```

Contribution bullets should be parallel but not identical. Each bullet should have a distinct function.

Good verbs:

- propose, develop, formulate, construct, derive, recast, transform, decompose, approximate, linearize, validate, quantify, reveal.

Avoid:

- introduce without saying what is introduced for.
- consider without stating the technical consequence.
- investigate as a contribution unless the paper is primarily empirical.

## Gap-To-Contribution Alignment

Every contribution must answer a gap from the literature review.

Use a mapping table while drafting:

| Literature gap | Contribution response |
| --- | --- |
| Existing ambiguity sets ignore conditional dependence | Construct conditional ambiguity set using forecast/side information |
| DDU not modeled in contingencies | Build decision-dependent ambiguity/scenario sets |
| Exact DRCC is nonconvex | Derive tractable approximation/reformulation |
| Distributed algorithms require synchronization | Develop asynchronous ADMM/decentralized scheme |
| Forecasting separated from optimization | Design decision-focused or predict-then-optimize loss |
| Extreme-weather scenarios lack lead time | Learn spatio-temporal event process from historical sequences |

If a contribution does not map to a gap, revise either the contribution or the literature review.

## Style Patterns From The Corpus

### Opening Sentence Patterns

- "With the increasing penetration of [renewable energy/distributed generation], [uncertainty/flexibility/coordination issue] has posed significant challenges to [operation task]."
- "Extreme weather events have increased the frequency and severity of [outages/contingencies], threatening power-system [reliability/resilience]."
- "The rapid uptake of [distributed generations/active distribution grids] is reshaping [transmission-distribution coordination]."
- "As [flexible load/storage/water systems] become increasingly coupled with power grids, [scheduling/pricing uncertainty] plays a critical role in [operational objective]."

### Literature Transition Patterns

- "To hedge against [uncertainty], existing studies have mainly adopted [method families]."
- "Among these methods, [branch] has attracted increasing attention because [reason]."
- "Recently, [technical approach] has been used to [specific task]."
- "However, most of these studies assume that [limiting assumption]."
- "This assumption may be restrictive in [target setting], where [mechanism]."

### Gap Sentence Patterns

- "Nevertheless, the above methods do not explicitly capture [dependence/decision-dependence/spatio-temporal correlation], which may lead to [operational harm]."
- "Although [method] improves [benefit], its computational burden grows rapidly with [samples/scenarios/subsystems], limiting its application to [large-scale task]."
- "Existing [models] generally treat [uncertainty] as exogenous, while in [task] it is affected by [decision]."
- "Most existing approaches focus on [individual/local/static] constraints and therefore cannot systematically ensure [joint/simultaneous/dynamic] security."

### This-Paper Paragraph Patterns

- "Motivated by these observations, this paper proposes [method] for [task] under [uncertainty]."
- "The key idea is to [technical mechanism], so that [benefit]."
- "Based on [uncertainty representation], we formulate [optimization model]."
- "To make the model computationally tractable, [reformulation/algorithm] is developed."

### Roadmap Patterns

- "The remainder of this paper is organized as follows..."
- Keep the roadmap in one paragraph and under 100 words unless the paper has unusual structure.

## Expected Section Length

Typical IEEE Introduction length in the corpus:

- Short letter: about 2,500-3,000 extracted characters.
- Standard article: about 5,000-10,000 extracted characters.
- Method-heavy article with extensive related work: about 12,000-16,000 extracted characters.

For a new IEEE Transactions paper, aim for:

- 6-10 paragraphs.
- 25-45 citations, depending on maturity of the topic.
- 3 contribution bullets.
- One concise organization paragraph.

## Citation Placement Rules

- Cite the first paragraph only when making factual claims about system trends, outage losses, penetration levels, or industry statistics.
- In broad literature paragraphs, group citations by method family instead of giving one sentence per paper.
- In focused literature paragraphs, discuss fewer papers but explain their technical limitations.
- Do not put citations inside contribution bullets unless you are explicitly contrasting with a named prior method.
- Use recent IEEE TPWRS/TSG/TSTE papers for direct power-system comparisons; use Mathematical Programming/Operations Research papers for foundational DRO theory when needed.

## Revision Checklist

Before finalizing an Introduction, check:

- Does the first paragraph narrow from system pressure to the paper's exact task?
- Does the literature review have layers, or is it just a list?
- Is there a clear hinge paragraph where the final gap is stated?
- Does the gap name a mechanism, not just an absence?
- Does the "This paper" paragraph state model, uncertainty representation, and solution idea?
- Are the contribution bullets specific, parallel, and non-overlapping?
- Does every contribution answer an earlier gap?
- Is the validation contribution more informative than "case studies verify effectiveness"?
- Does the roadmap match the actual section structure?
- Are citations used to support claims rather than decorate sentences?
- Is there a clear difference between the abstract and the Introduction?

## Common Failure Modes

- **Too much macro background**: carbon neutrality, renewable growth, or climate change is discussed for too long before the actual optimization task appears.
- **Flat literature list**: every cited paper is summarized once, but no taxonomy or gap emerges.
- **Gap too late**: the reader reaches the contribution list without knowing what problem remains unsolved.
- **Contribution bullets too generic**: "model, algorithm, case study" with no technical specificity.
- **Uncertainty not decomposed**: the text says "uncertainty" without identifying source, distributional ambiguity, decision dependence, and operational consequence.
- **Algorithm detached from model**: the Introduction names ADMM/C&CG/S-lemma/MILP but does not explain what computational difficulty they solve.
- **Validation undersold**: the Introduction says numerical tests are conducted but does not say what insight they validate.
- **Overclaiming novelty**: "first" or "novel" is used without a precise comparison basis.

## Output Modes

When writing a new Introduction:

1. Ask for the paper's task, uncertainty source, proposed method, closest baselines, and target venue if missing.
2. Draft a structured Introduction with headings removed unless the user asks for an outline.
3. Include contribution bullets and roadmap.
4. Flag placeholders for missing citations or results.

When revising an Introduction:

1. Preserve the user's technical claims.
2. Reorder paragraphs into the canonical architecture.
3. Strengthen the gap by naming assumptions and operational consequences.
4. Rewrite contributions so they map to the gap.
5. Do not invent experimental results, citations, or theoretical guarantees.

When diagnosing an Introduction:

1. Provide a move map: pressure, literature layers, gap, response, contributions, roadmap.
2. Identify missing or weak moves.
3. Suggest concrete paragraph-level edits.
4. If useful, provide revised gap and contribution paragraphs.

