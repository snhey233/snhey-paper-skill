---
name: snhey-paper-abstract
description: Write, diagnose, or revise IEEE-style abstracts for power systems, smart grid, energy dispatch, unit commitment, renewable uncertainty, extreme-weather contingency, distributionally robust optimization, stochastic/robust optimization, prediction-then-optimization, and resilience papers. Use when the user asks for abstract writing, abstract polishing, 摘要写作, IEEE摘要, 电力系统论文摘要, DRO摘要, 调度摘要, or wants a reusable writing skill distilled from IEEE power-system papers.
---

# IEEE Power Systems Abstract Writing

Use this skill to write abstracts that match the rhetorical logic of IEEE Transactions-style power systems papers. The target output is a single dense abstract, usually 150-250 words, with clear problem pressure, a precise methodological contribution, tractability or algorithmic handling, and validation claims.

## Evidence Base

This skill was distilled from 15 IEEE abstracts in the user's Zotero collection "电网高温日" (14 unique papers; one Wasserstein UC paper appears twice). The corpus covers:

- IEEE Transactions on Power Systems
- IEEE Transactions on Smart Grid
- IEEE Transactions on Sustainable Energy
- Topics: unit commitment, energy/reserve dispatch, transmission-distribution coordination, renewable scenario generation, storage arbitrage, extreme-weather N-k contingencies, resilience enhancement, Wasserstein DRO, chance constraints, decision-dependent uncertainty, distributed/decentralized optimization, and prediction-then-optimization.

The abstracts share a stable pattern: they do not merely state "we propose a method"; they turn a specific power-system uncertainty into a modeling gap, then show how the proposed uncertainty representation, optimization model, reformulation/algorithm, and experiments form one chain.

## Canonical Abstract Moves

Write the abstract as 4-8 functional moves. Not every abstract needs every move, but every sentence should serve one move.

1. **System pressure / application setting**
   - State the power-system context that makes the problem important.
   - Typical pressure sources: high renewable penetration, extreme weather, low-probability high-impact events, limited samples, peak-hour grid stress, transmission-distribution coupling, reduced controllable generation, or simultaneous contingencies.
   - Keep it concrete. Avoid generic openings like "Power systems are important."

2. **Specific limitation / research gap**
   - Name the exact weakness of existing approaches.
   - Strong IEEE abstracts often identify two limitations in one opening block.
   - Common gap types:
     - Uncertainty representation is inaccurate or too conservative.
     - Existing stochastic/robust/DRO models ignore conditional information, decision-dependence, spatial-temporal structure, or joint security.
     - Exact formulations are nonconvex, mixed-integer, bilinear, or computationally heavy.
     - Prediction and optimization are separated, causing suboptimal decisions.
     - Existing contingency screening does not capture simultaneous weather-induced failures or gives insufficient warning time.

3. **Main proposal**
   - State the proposed model/framework in one sentence.
   - Include the application object and the methodological identity.
   - Use a form like: "This paper proposes/develops/presents a [method type] for [power-system task] under [uncertainty type]."
   - The proposal sentence should answer: what is new, where it is used, and what uncertainty it handles.

4. **Uncertainty modeling innovation**
   - Explain how the method characterizes uncertainty.
   - Common slots:
     - Wasserstein ambiguity set centered at empirical distribution.
     - Moment-based ambiguity set using expectation, variance, covariance, or predictive decisions.
     - Scenario-wise decision-dependent ambiguity sets.
     - Conditional ambiguity set using forecast value, side information, meteorological conditions, or distributed predictions.
     - Bayesian nonparametric mixture model plus local ambiguity sets.
     - Spatio-temporal point process for historical failure-event sequences.
     - GAN/scenario generator for renewable trajectories.
   - Show why the uncertainty model is better: less conservative, more data-aware, captures dependence, captures local/global distributional features, supports out-of-sample reliability, or handles limited data.

5. **Optimization / reformulation / algorithm**
   - IEEE power-system abstracts often include a tractability sentence.
   - Mention the mathematical challenge first if it is important, then the remedy.
   - Typical remedies: duality theory, S-lemma, sample average approximation, CVaR/Bonferroni approximation, MILP reformulation, conic reformulation, C&CG, ADMM, asynchronous decentralized optimization, integer L-shaped algorithm, lift-and-project cuts, dual vertex generation, Taylor linearization, alternating optimization, difference-of-convex optimization.
   - Do not list tools randomly. Tie each tool to what it resolves.

6. **Validation design**
   - State the test system/data and comparison scope.
   - Preferred evidence types:
     - IEEE test systems, real-world systems, real datasets, large-scale systems.
     - Comparison with stochastic optimization, robust optimization, traditional DRO, benchmark forecasting/scenario models, or state-of-the-art methods.
     - In-sample and out-of-sample performance.
     - Scalability, robustness, operating cost, decision regret, risk coverage, model-solving efficiency, or security satisfaction.

7. **Result / value claim**
   - End with what the proposed method achieves.
   - Good claims are specific but not overloaded.
   - Strong endings include numbers when available, e.g. cost reduction, profitability gain, computational time reduction, out-of-sample improvement, or risk coverage.
   - If no numbers are available, claim the validated dimension: effectiveness, scalability, robustness, reduced conservatism, or support for proactive resilient operation.

## Sentence Budgets

Choose sentence count based on paper type.

- **3 sentences**: IEEE letter or highly focused methodological note.
  - S1 gap; S2 proposal and mechanism; S3 quantified result.
- **4-6 sentences**: compact application-method paper.
  - Context/gap; proposal; method details; algorithm; validation.
- **7-9 sentences**: standard IEEE Transactions abstract.
  - Context; gap; proposal; uncertainty set; model; reformulation; algorithm; validation; result.
- **10-12 sentences**: method-heavy paper with chance constraints, two-step approximations, or distributed algorithms.
  - Use only when each step has a distinct role. Avoid turning the abstract into a mini-method section.

For most full IEEE Transactions papers in this domain, aim for 6-8 sentences.

## Corpus-Derived Move Patterns

Use these patterns as prototypes, not as rigid templates.

- **Bayesian nonparametric UC / local ambiguity**
  - Renewable uncertainty pressure -> need to characterize global-local unknown distribution -> propose data-driven BN two-stage DRO UC -> decompose distribution into local mixture components -> build mixture ambiguity set/local Wasserstein-trimming sets -> reformulate to MILP and algorithm -> validate in/out-of-sample and scalability.

- **Small-sample wind/PV dispatch**
  - Extreme meteorological events and insufficient data -> small-sample uncertainty hard to characterize -> propose two-stage DRO dispatch -> augment/generate data with CGAN -> construct Wasserstein model with hard/soft constraints -> nonconvexity and computational burden -> duality/relaxation/Taylor linearization -> reduce operating cost and improve solving efficiency.

- **Wasserstein UC approximation**
  - Propose Wasserstein DRO framework for wind forecast error in UC -> define Wasserstein ball and worst-case costs -> explain sample size/conservatism relation -> identify WDRC computational burden -> propose upper approximation/exactness condition -> compare with RO/SO and test on large systems.

- **Flexible generation UC**
  - Renewable penetration makes flexible generation important -> propose two-stage DRO UC with adjustable flexible resources -> design algorithm for mixed-binary two-stage model -> show cost reduction through better flexibility quantification.

- **Chance/security constrained dispatch**
  - Security-constrained dispatch with renewables and contingencies -> model uncertainty with joint chance constraints and reserves -> use Wasserstein ambiguity set -> identify nonconvex heavy problem -> adopt two-step approximation -> construct mass-covering polyhedral uncertainty set -> solve linear robust optimization -> demonstrate scalability/robustness.

- **Renewable scenario generation**
  - Day-ahead renewable scenario generation matters for operations -> propose style-based GAN plus sequence encoder -> condition on meteorological information to capture diurnal/seasonal patterns -> validate on wind/PV real datasets -> compare statistical and scheduling performance.

- **Decision-centric uncertainty set**
  - Traditional two-stage uncertainty optimization separates estimation and decisions -> propose decision-centric uncertainty set integrating estimation and optimization -> report profitability improvement while maintaining risk coverage.

- **Resilience with decision-dependent contingencies**
  - Resilience enhancement faces DDU and limited outage data in extreme weather -> develop scenario-wise decision-dependent ambiguity sets -> formulate two-stage tri-level DRO resilience model -> reformulate to MILP master/subproblems with C&CG -> validate out-of-sample and quantify value of ambiguity/distributional information.

- **Predict-then-optimize scheduling**
  - Application system is coupled with the grid -> prediction uncertainty affects scheduling -> propose stochastic predict-then-optimize to align prediction distribution with optimality gap -> derive differentiable surrogate for training -> demonstrate lower cost and decision regret.

- **ITD joint chance dispatch**
  - Distributed ITD dispatch has synchronization and joint-security limitations -> present DR joint chance-constrained model with asynchronous decentralized optimization -> use Wasserstein ambiguity sets for transmission/distribution -> approximate JCC to tractable conic form -> propose asynchronous ADMM -> show scalability.

- **TDS cooperative scheduling with DDU**
  - New energy reduces controllable generation and increases uncertainty -> independent T/D scheduling struggles with balance -> propose two-stage DRO cooperative scheduling -> boundary decisions induce DDU -> build decision-dependent probability distribution set -> combine improved ADMM and adaptive C&CG -> verify necessity of considering DDU.

- **Distributed predictions for energy/reserve dispatch**
  - Use predictions from operator and renewable sources -> build less conservative moment-based ambiguity set tied to predictive decisions -> transform via dual vertices, duality, and S-lemma -> solve with two-layer iterative algorithm and acceleration -> validate efficiency.

- **Approximately adaptive DRO**
  - Propose approximate adaptive DRO paradigms -> approximate recourse decisions/value functions with piecewise structures -> segment ambiguity set by equal probability principle -> reformulate constraints tractably -> solve bilinear/vertex issues -> verify approximation efficiency and adaptability.

- **Extreme-weather N-k early warning**
  - Traditional N-k analysis is insufficient under extreme weather -> existing construction/screening misses simultaneous weather-induced patterns and lacks lead time -> propose early-warning framework using spatio-temporal point process -> generate high-risk N-k scenarios -> augment scarce failure data with reanalysis/fragility modeling -> evaluate on large-scale system -> support proactive resilience decisions.

## Abstract Writing Workflow

Before writing, collect these inputs:

- Power-system task: UC, dispatch, scheduling, resilience planning, contingency warning, scenario generation, storage arbitrage, water-energy scheduling, etc.
- Uncertainty source: wind/PV forecast error, load, electricity price, line outage, extreme weather, boundary variables, distributed predictions, small samples, tail events.
- Existing-method limitation: conservatism, poor out-of-sample performance, ignored dependence, ignored DDU, no joint security, poor scalability, separated prediction/optimization, insufficient lead time.
- Main contribution: model/framework/algorithm/data method.
- Uncertainty representation: Wasserstein, moment-based, conditional, decision-dependent, Bayesian mixture, GAN, point process, ambiguity set, chance constraints.
- Tractability device: reformulation, approximation, decomposition, linearization, distributed algorithm.
- Validation evidence: datasets, test systems, baselines, metrics, quantified results.

Then write in this order:

1. Draft the final value claim first: what should the reader remember?
2. Draft the proposal sentence: "This paper proposes..."
3. Add only the minimum context needed to make the proposal necessary.
4. Add one sentence naming the most important limitation of prior work.
5. Add method-detail sentences in causal order: uncertainty model -> optimization model -> reformulation/algorithm.
6. Add validation sentence with systems/data/baselines.
7. Add result sentence with quantitative or qualitative benefits.
8. Remove any sentence that does not change the reader's understanding of novelty, validity, or value.

## Reusable Abstract Templates

### DRO Dispatch / Unit Commitment

Use when the paper proposes a DRO model for UC, economic dispatch, energy/reserve dispatch, or scheduling.

```text
[System pressure] has posed significant challenges to [operation task] because [uncertainty source] is difficult to characterize with limited/biased data. Existing [method class] often [specific limitation], leading to [conservatism/risk/computational issue]. This paper proposes a [two-stage/distributionally robust/chance-constrained] [UC/dispatch/scheduling] framework for [system/task] under [uncertainty]. The proposed framework constructs [ambiguity set type] by exploiting [data feature/side information/decision dependence], thereby [less conservative/more reliable/better out-of-sample]. To solve the resulting [nonconvex/mixed-integer/bilevel] problem, [duality/S-lemma/C&CG/ADMM/linearization] is used to reformulate/decompose it into [tractable form]. Numerical studies on [test systems/data] show that the proposed method [validated advantage] compared with [baselines].
```

### Extreme Weather / Resilience / Contingency

Use when the paper is about high-impact low-probability events, N-k contingencies, line outages, resilience enhancement, or early warning.

```text
Extreme weather events have increased the risk of [simultaneous outages/cascading failures/security violations] in power systems, making traditional [N-k analysis/resilience planning/dispatch] insufficient. Existing methods often fail to capture [spatio-temporal dependence/decision-dependent contingencies/limited outage data/tail risk], which restricts their applicability to [preventive operation/resilience planning]. This paper proposes a [risk-based/resilience/early-warning] framework for [task] by modeling [failure/event/uncertainty process] with [method]. The proposed model [generates high-risk scenarios/constructs ambiguity sets/coordinates planning and operation] under [constraints/information]. To make the problem tractable, [reformulation/decomposition/algorithm] is developed. Case studies on [system] demonstrate [forecasting accuracy/risk reduction/out-of-sample improvement/proactive decision support].
```

### Prediction-Then-Optimization / Scenario Generation

Use when the contribution links forecasting, scenario generation, or machine learning with optimization.

```text
[Forecast/scenario] information is essential for [short-term operation/scheduling], but prediction models that are separated from downstream decisions can yield suboptimal schedules. This paper develops a [scenario generation/predict-then-optimize/decision-centric] framework that integrates [forecasting model] with [optimization task]. By incorporating [meteorological conditions/side information/optimality gap/decision-centric gradient], the proposed method captures [spatial-temporal dynamics/conditional distribution/decision relevance]. The resulting [training or optimization] problem is handled through [surrogate function/reformulation/algorithm]. Experiments on [real-world datasets/test systems] show improved [statistical quality/scheduling cost/decision regret/risk coverage] over [benchmarks].
```

## IEEE-Style Language Rules

- Prefer precise nouns over broad adjectives: "joint chance-constrained dispatch" is stronger than "advanced dispatch."
- Use "uncertainty" with a modifier: renewable uncertainty, forecast error uncertainty, outage uncertainty, price uncertainty, decision-dependent uncertainty.
- Use "ambiguity set" only when the paper is truly DRO; otherwise use uncertainty set, scenario set, probability distribution, or failure distribution.
- Explain conservatism as a tradeoff, not as a slogan: what information is ignored, and how does your method reduce the conservatism?
- Mention tractability only with a method: "transformed into a MILP", "recast as a conic formulation", "solved by asynchronous ADMM."
- For IEEE power papers, validation should connect to operation: operating cost, reserve cost, security satisfaction, line overload risk, decision regret, out-of-sample performance, scalability, or resilience.
- Avoid first-person overuse. "This paper proposes..." and "The proposed model..." are standard. "We first..." is acceptable for ordered method details.
- Avoid stacking too many acronyms in the first sentence. Define core acronyms when first used.
- Do not overclaim "optimal" unless the model or algorithm actually proves optimality.

## Contribution Sentence Patterns

Use these patterns when drafting or revising.

- "To address these limitations, this paper presents a novel [model] for [task] via [method]."
- "The proposed framework captures [relationship/dependence/ambiguity] by [mechanism], leading to [benefit]."
- "Using [data/information], we construct [ambiguity/uncertainty/scenario set] that [technical role]."
- "To solve the resulting [problem type], [method] is adopted to transform it into [tractable form]."
- "A tailored [algorithm] is developed to exploit [problem structure/system topology/decomposition]."
- "Numerical results on [systems/datasets] demonstrate [effectiveness/scalability/robustness] compared with [benchmarks]."

## Diagnostic Checklist

Before finalizing an abstract, answer yes/no:

- Does the first sentence identify a real power-system pressure rather than generic importance?
- Is the prior-work limitation specific enough to justify the proposed method?
- Can a reader identify the main contribution by sentence 2 or 3?
- Does the abstract explain what information the uncertainty model uses?
- Does it distinguish the uncertainty source from the ambiguity about its distribution?
- If the model is hard, does the abstract state how it becomes tractable?
- Are the validation systems/data and baseline classes visible?
- Does the final sentence state an operational value, not just "effectiveness"?
- Are all acronyms defined at first use?
- Is every method detail connected to a problem it solves?
- Is the abstract dense but readable, without turning into a formula list?

## Common Failure Modes

- **Background-only abstract**: spends half the abstract on renewable challenges and never reaches the method clearly.
- **Method-name pileup**: lists DRO, Wasserstein, ADMM, C&CG, S-lemma, and MILP without explaining why each appears.
- **No gap sentence**: proposes a model but does not say what existing methods miss.
- **No uncertainty mechanism**: says "considering uncertainty" but never states whether uncertainty is handled by scenarios, ambiguity sets, chance constraints, moments, conditions, or forecasts.
- **Validation too vague**: says "case studies verify effectiveness" without systems, baselines, or metrics.
- **Overquantified without meaning**: gives a percentage improvement but not the metric or baseline.
- **Overclaiming robustness**: claims robust operation without out-of-sample, risk, security, or uncertainty evidence.

## Output Modes

When asked to write an abstract:

- Produce one polished abstract first.
- Then optionally provide a short move map if the user is drafting or learning.

When asked to revise an abstract:

- Preserve the user's technical claims.
- Improve move order, specificity, and IEEE-style density.
- Flag missing evidence rather than inventing results.

When asked to teach abstract writing:

- Explain the move structure.
- Show which sentence in the user's draft performs each move.
- Suggest one or two alternative structures based on the paper type.
