---
name: snhey-paper-case-study
description: Write, diagnose, restructure, or polish IEEE-style case study, numerical simulation, numerical results, experiments, results and discussion, validation, benchmark comparison, sensitivity analysis, out-of-sample testing, ablation study, scalability study, and computational performance sections for power systems, smart grid, energy dispatch, unit commitment, renewable uncertainty, extreme-weather contingency, resilience, transmission-distribution coordination, stochastic/robust/distributionally robust optimization, scenario generation, prediction-then-optimization, and early-warning papers. Use when the user asks for case study写作, 算例分析, 仿真分析, 结果分析, numerical results, simulation results, experiments, case studies, sensitivity analysis, out-of-sample, baseline comparison, or IEEE算例部分.
---

# SNHEY Paper Case Study

Use this skill to write or revise the case study / numerical results / experiments section of an IEEE-style power-system paper. This section proves that the proposed method works, explains when and why it works, and translates numerical results into operational insight.

This skill was distilled from 14 unique IEEE papers in the user's Zotero collection "电网高温日". The corpus covers IEEE TPWRS, TSG, and TSTE papers on UC, dispatch, DRO, chance constraints, decision-dependent uncertainty, distributed optimization, resilience, scenario generation, storage arbitrage, water-energy scheduling, and extreme-weather early warning.

## Core Thesis

An IEEE case study section should not merely say "the proposed method is effective." It should answer:

1. **Where was it tested?** Test systems, datasets, time horizon, hardware, solvers.
2. **Against what was it tested?** Baselines, ablations, competing methods, benchmark models.
3. **What dimensions were tested?** Economy, robustness, conservatism, risk, feasibility, scalability, prediction quality, computational time.
4. **What do the results prove?** Each table/figure should support one claim.
5. **Why does the result happen?** Explain the mechanism, not just the number.

The strongest case studies in this corpus follow:

```text
Experimental setup -> baseline design -> main comparison -> robustness/out-of-sample -> sensitivity/ablation -> scalability/computation -> operational insight
```

## Difference From Other Sections

- Problem description defines the model.
- Solution design explains how the model is solved.
- Case study verifies the model and solution under credible data, systems, and baselines.

Do not rederive formulas in the case study. Refer back to equations and methods only to explain experimental settings or results.

## Canonical Case Study Architecture

Use the following moves for most IEEE papers.

### Move 1: Validation Purpose

Open the section by stating what will be verified.

Good forms:

```text
This section validates the effectiveness, robustness, and scalability of the proposed method using [systems/datasets].
```

```text
The numerical studies are designed to answer three questions: whether [model] improves [metric], whether [method] maintains [risk/security] out of sample, and whether [algorithm] scales to [large system].
```

If the paper has multiple experiments, name the validation dimensions up front:

- effectiveness;
- economy;
- robustness;
- conservatism;
- out-of-sample performance;
- scalability;
- algorithmic efficiency;
- forecasting/scenario quality;
- operational feasibility;
- value of each model component.

### Move 2: Test System And Data Description

Describe the physical system, data source, and uncertainty samples before showing results.

Include:

- test system: IEEE 6-bus, 24-bus RTS, 30-bus, 33-node, 39-bus, 118-bus, 500-bus, 703-bus, ENTSO-E, real water district, real renewable datasets.
- system composition: generators, wind farms, PV stations, ESSs, distribution systems, tie lines, pumps, reservoirs, lines, contingencies.
- data source: CAISO, ELIA, NREL, TenneT, southeastern Australia wind data, real weather-induced failure data, reanalysis data, synthetic samples.
- time horizon and resolution: 6 hours, 15-min intervals, day-ahead, intraday, yearly historical samples.
- implementation: solver, platform, CPU/GPU/RAM, programming environment.

Do not bury system setup in captions. IEEE readers expect a concise paragraph or subsection.

### Move 3: Baselines And Compared Methods

Define baselines before results. Every comparison label in a table or figure should be interpretable.

Common baselines from the corpus:

- SO: stochastic optimization.
- RO: robust optimization.
- DRO: distributionally robust optimization.
- ARO/ADRO: adaptive robust/distributionally robust optimization.
- Traditional DRUC or standard UC.
- Decision-independent uncertainty model.
- Individual chance constraints vs joint chance constraints.
- Synchronous ADMM vs asynchronous ADMM.
- Existing scenario generation methods.
- Forecast-then-optimize vs predict-then-optimize.
- Proposed method without key module.
- Proposed method with different segment numbers, ambiguity radii, sample sizes, confidence levels, budgets, or robustness levels.

Good baseline description:

```text
The proposed method is compared with [baseline 1], [baseline 2], and [baseline 3]. [Baseline 1] ignores distributional ambiguity, [baseline 2] uses a conventional ambiguity set, and [baseline 3] removes the proposed decision-dependent mechanism.
```

Avoid:

- unexplained method acronyms;
- baselines that are unfairly weak;
- comparing only against the method's own variants unless no external baseline is relevant.

### Move 4: Main Performance Comparison

This is the central evidence table/figure.

Typical metrics:

- total operating cost;
- first-stage cost and second-stage/recourse cost;
- reserve cost;
- startup/shutdown cost;
- adjustment cost;
- load shedding;
- renewable curtailment;
- expected unserved load;
- weighted load shedding;
- profitability;
- decision regret;
- risk coverage;
- violation frequency;
- line overload risk;
- empirical out-of-sample cost;
- scenario quality metrics;
- negative log-likelihood or prediction error;
- computation time;
- iteration count;
- convergence residuals.

Write results as claim + evidence + explanation:

```text
The proposed method achieves the lowest out-of-sample cost among the compared methods. This is because [mechanism], which allows [model] to [less conservative / better hedge / use predictions].
```

Do not simply list table values. Explain why the values support the paper's contribution.

### Move 5: Out-Of-Sample / Robustness Evaluation

For stochastic/robust/DRO papers, this is often essential.

Out-of-sample tests answer whether decisions remain good under unseen distributions or Monte Carlo samples.

Include:

- how test samples are generated;
- how many samples/distributions are used;
- whether results are averaged over repeated trials;
- what metrics are evaluated;
- how risk or violation is measured;
- how ambiguity radius/confidence level/sample size affects performance.

Common wording:

```text
To assess out-of-sample performance, [N] test samples are generated from [distribution/data source]. The decisions obtained by each method are evaluated under the same test set.
```

For DRO papers, always explain the economy-robustness-conservatism tradeoff.

### Move 6: Sensitivity Analysis

Use sensitivity analysis to show that conclusions are not parameter accidents.

Common sensitivity parameters:

- sample size;
- Wasserstein radius;
- confidence level;
- risk parameter;
- robustness level;
- hardening budget;
- ambiguity-set radius;
- number of segments;
- training data size;
- forecast error variance;
- renewable penetration;
- system regulatory capability;
- uncertainty-set coverage;
- correlation level.

Good sensitivity writing:

```text
As the ambiguity radius increases, the schedule becomes more conservative, leading to higher prescheduling cost but lower violation frequency. This tradeoff helps operators select a radius according to risk preference.
```

Do not present sensitivity plots without decision implications.

### Move 7: Ablation / Component Value

If the method has multiple modules, test the value of each module.

Examples:

- with/without decision-dependent uncertainty;
- with/without flexible resource modeling;
- with/without distributed predictions;
- with/without acceleration strategy;
- with/without lift-and-project cuts;
- different segment numbers in piecewise approximation;
- different generator/encoder architectures;
- forecast-only vs decision-focused loss;
- ambiguity only vs ambiguity + distributional information.

Write ablation as:

```text
Removing [module] causes [metric] to deteriorate, indicating that [module] is responsible for [mechanism].
```

### Move 8: Algorithmic Efficiency And Scalability

Optimization-heavy IEEE papers must show that the proposed method can be solved.

Report:

- solver and platform;
- average/max computation time;
- iteration counts;
- convergence residuals;
- small vs large test systems;
- scalability with buses, samples, scenarios, subsystems, renewable sources, or data size;
- effect of acceleration strategies.

Good computational claim:

```text
Although the proposed model includes [complex feature], the reformulation and acceleration strategy keep the solution time within [range], demonstrating practical scalability for [system scale].
```

Do not claim scalability from a single small test case.

### Move 9: Operational Insight

End major result blocks with what the operator/planner learns.

Examples:

- Flexible resources reduce cost by moving commitment decisions to recourse.
- Conditional or decision-dependent ambiguity sets reduce unnecessary conservatism.
- Larger robustness levels improve risk control but increase investment or operating cost.
- Distributed prediction improves dispatch when renewable-source forecasts contain useful local information.
- Early warning gives time to prepare for high-risk N-k contingencies.
- Hardening budget should be allocated to lines with high failure probability and load impact, not merely high exposure.

This is what makes the case study more than a numerical appendix.

## Common Case Study Structures By Paper Type

### DRO UC / Dispatch

Recommended structure:

1. Test system and data.
2. Compared methods: SO/RO/DRO/proposed.
3. Main cost comparison.
4. Out-of-sample performance.
5. Sensitivity to sample size/radius/confidence level.
6. Computation time and scalability.

Required narrative:

- Explain economy vs conservatism.
- Explain why out-of-sample performance matters.
- Report both cost and risk/violation when possible.

### DR Chance/Security-Constrained Dispatch

Recommended structure:

1. Modified RTS/IEEE system setup.
2. Renewable and contingency data.
3. Risk/chance parameter setup.
4. Cost vs violation-frequency comparison.
5. Effect of uncertainty-set size or DR parameter.
6. Scalability as samples/constraints grow.

Required narrative:

- A lower cost is not enough; the method must also control violation probability.

### Flexible-Resource UC

Recommended structure:

1. Small system illustrating mechanism.
2. Large IEEE system validating scalability.
3. Flexibility benefit analysis.
4. Out-of-sample cost/risk comparison.
5. Algorithm convergence and cut effectiveness.

Required narrative:

- Show that flexible resources matter because they improve second-stage adaptation, not merely because more capacity is available.

### Scenario Generation

Recommended structure:

1. Dataset description and parameter settings.
2. Statistical scenario-quality metrics.
3. Visual or distributional comparison.
4. Benchmark comparison.
5. Downstream power-system scheduling analysis.
6. Generalization or data-scale analysis.

Required narrative:

- Statistical realism and operational value are both required. A scenario generator that looks good statistically but performs poorly in scheduling is not enough.

### Predict-Then-Optimize

Recommended structure:

1. Experimental settings and real-world system.
2. Forecasting model evaluation.
3. Optimization/scheduling performance.
4. Decision regret or optimality gap comparison.
5. Baseline comparison with forecast-then-optimize.
6. Discussion of where decision-focused learning helps.

Required narrative:

- Emphasize alignment between forecast distribution and downstream scheduling cost.

### ITD/TDS Distributed Optimization

Recommended structure:

1. Small and large coordinated systems.
2. Subsystem configuration and coupling.
3. Compared coordination modes or algorithms.
4. Cost/risk/security comparison.
5. Out-of-sample or uncertainty-radius analysis.
6. Convergence residuals and communication/iteration time.

Required narrative:

- Show both model value and distributed algorithm value.

### Resilience Under Extreme Weather

Recommended structure:

1. Test distribution network and weather scenario.
2. Hardening/DER/reconfiguration settings.
3. Compared resilience strategies.
4. Load restoration / weighted load shedding / expected uninterrupted load.
5. Worst-case distribution or stress test.
6. Budget and robustness sensitivity.
7. Planner insight.

Required narrative:

- Results should connect investment decisions to service restoration under uncertain contingencies.

### Extreme-Weather Early Warning

Recommended structure:

1. Event data generation or real data setup.
2. Train/test split.
3. Baseline event models.
4. Forecasting metrics for temporal, spatial, and mark prediction.
5. High-risk N-k scenario generation.
6. Operational early-warning demonstration.

Required narrative:

- Show both prediction accuracy and usefulness for proactive contingency preparation.

## Result-Writing Templates

### Main Comparison Paragraph

```text
Table [X] compares [metric] obtained by [methods]. The proposed method achieves [result], outperforming [baselines] by [amount or qualitative comparison]. This improvement is mainly attributed to [mechanism], which enables [less conservative/more adaptive/more risk-aware] decisions under [uncertainty]. In contrast, [baseline] [limitation], leading to [observed drawback].
```

### Out-Of-Sample Paragraph

```text
To evaluate robustness under unseen uncertainty, [N] out-of-sample scenarios are generated from [data/distribution]. The decisions from all methods are fixed and tested on the same scenarios. As shown in [figure/table], the proposed method maintains [lower cost/lower violation/higher reliability], indicating that [uncertainty representation] improves generalization beyond the training samples.
```

### Sensitivity Paragraph

```text
Fig. [X] shows the impact of [parameter] on [metric]. Increasing [parameter] leads to [trend], reflecting the tradeoff between [economy] and [robustness/risk]. This result suggests that [operator/planner] can tune [parameter] according to [risk preference/budget/data availability].
```

### Scalability Paragraph

```text
The scalability of the proposed algorithm is examined on [larger system]. Although the problem size increases from [small] to [large], the solution time remains [acceptable/trend], mainly because [reformulation/decomposition/acceleration] reduces [bottleneck]. This confirms that the method is applicable to [target scale].
```

### Ablation Paragraph

```text
The value of [module] is assessed by comparing the full model with a variant that removes [module]. The variant yields [worse metric], demonstrating that [module] is essential for [mechanism]. Therefore, the performance gain is not only due to [other factor], but also to [specific proposed idea].
```

## Tables And Figures

Use each table/figure for one clear claim.

Common table types:

- system parameters;
- compared methods;
- cost breakdown;
- out-of-sample performance;
- violation probability/risk;
- computation time;
- sensitivity summary;
- approximation error;
- scheduling results;
- resilience investment decisions;
- forecasting/scenario metrics.

Common figure types:

- test system topology;
- dispatch curves;
- cost vs sample size;
- cost/risk vs ambiguity radius;
- out-of-sample boxplot;
- convergence residuals;
- scenario trajectories;
- forecast vs actual;
- load restoration curves;
- failure probability maps;
- N-k scenario visualization.

Every figure/table should be introduced before it appears and interpreted after it appears.

## IEEE Style Rules

- Use "case study", "numerical simulation", "numerical results", or "experiments" according to venue style; do not mix titles randomly.
- State solver and hardware once in experimental settings.
- Define every baseline acronym before tables.
- Mention whether costs are expected, worst-case, empirical, in-sample, or out-of-sample.
- Use percentages only when the denominator/baseline is clear.
- For DRO, avoid claiming "better" from in-sample objective alone; include out-of-sample or risk evidence.
- For scenario generation, include both statistical metrics and downstream scheduling metrics.
- For distributed algorithms, include convergence or communication evidence.
- For resilience, include service or risk metrics, not only investment cost.
- Do not overinterpret tiny numerical differences.

## Diagnostic Checklist

Before finalizing a case study section, check:

- Does the first paragraph state what the experiments are designed to verify?
- Are test systems, datasets, time horizon, and uncertainty samples clear?
- Are baselines fair and defined?
- Are metrics aligned with the paper's claimed contributions?
- Is there at least one main comparison table/figure?
- Is out-of-sample performance tested for DRO/stochastic/robust methods?
- Is sensitivity analysis included for key parameters?
- Is algorithmic efficiency shown if the method is computationally complex?
- Is scalability tested beyond a toy system if scalability is claimed?
- Are result paragraphs written as claim + evidence + mechanism?
- Does every table/figure support a specific claim?
- Are practical operator/planner insights extracted from the numbers?

## Common Failure Modes

- **Only one test case**: claims broad effectiveness from one small system.
- **No baseline definition**: tables contain acronyms that readers cannot interpret.
- **Cost-only proof**: lower cost is reported without risk, feasibility, or violation evidence.
- **No out-of-sample test**: DRO or data-driven methods are validated only on training samples.
- **Sensitivity missing**: key parameters such as Wasserstein radius, confidence level, risk tolerance, budget, or sample size are never varied.
- **Figures without interpretation**: the text says "Fig. X shows..." but does not explain the trend.
- **Overclaiming scalability**: computation time is reported only for a small test system.
- **No mechanism explanation**: the paper reports proposed method is better but does not say why.
- **Unfair comparison**: baseline lacks the same data, solver, or constraints.
- **Disconnected experiments**: experiments do not map back to contributions.

## Output Modes

When writing a new case study section:

1. Ask for test system, data, baselines, metrics, solver, and available results if missing.
2. Draft the section structure before writing result prose.
3. Use placeholders for unknown numerical values rather than inventing results.
4. Map each experiment to one contribution.
5. Include result interpretation paragraphs for every table/figure.

When revising a case study section:

1. Preserve the user's numerical results.
2. Reorder experiments into setup -> main comparison -> robustness -> sensitivity -> scalability -> insights.
3. Strengthen baseline definitions and metric explanations.
4. Add mechanism-based interpretation.
5. Flag missing experiments when claims are unsupported.

When diagnosing a case study section:

1. Produce an experiment map.
2. Identify which contribution each experiment validates.
3. List missing baselines, metrics, sensitivity tests, or out-of-sample checks.
4. Suggest exact result paragraphs or figure/table captions.

