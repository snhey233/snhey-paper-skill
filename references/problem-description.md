---
name: snhey-paper-problem-description
description: Write, diagnose, restructure, or polish IEEE-style problem description, problem formulation, model formulation, system model, preliminary knowledge, and mathematical modeling sections for power systems, smart grid, energy dispatch, unit commitment, renewable uncertainty, extreme-weather contingency, resilience, transmission-distribution coordination, stochastic/robust/distributionally robust optimization, and prediction-then-optimization papers. Use when the user asks for 问题描述, 问题建模, 模型描述, problem description, problem formulation, model formulation, system model, mathematical modeling, IEEE问题描述, 电力系统模型描述, DRO建模, or 调度模型描述.
---

# SNHEY Paper Problem Description

Use this skill to write or revise the "problem description" part of an IEEE-style power-system optimization paper. Depending on the paper, this section may be titled **Problem Formulation**, **Model Formulation**, **System Model**, **Mathematical Modelling**, **Preliminary Knowledge**, **Energy and Reserve Dispatch**, **Coordinated Scheduling Model**, or **Formulation and Methodology**.

The purpose of this section is not to persuade the reader that the research gap exists. That is the Introduction's job. The problem description must translate the research idea into an operational and mathematical object that the method section can solve.

This skill was distilled from 14 unique IEEE papers in the user's Zotero collection "电网高温日" covering IEEE TPWRS, TSG, and TSTE papers on UC, dispatch, DRO, chance constraints, resilience, scenario generation, ITD/TDS coordination, storage arbitrage, water-energy scheduling, and extreme-weather contingency warning.

## Core Thesis

A good IEEE problem description section should answer five questions in order:

1. **What physical or operational system is being modeled?**
2. **What decisions are made, by whom, and at what time/stage?**
3. **What uncertainty or event is realized, and how does it affect the system?**
4. **What objective and constraints define feasibility and performance?**
5. **What compact mathematical form will the following method solve?**

If the reader cannot reconstruct the system timeline, decision hierarchy, uncertainty source, and constraint groups after this section, the problem description is not doing its job.

## Difference From Introduction And Methodology

- Introduction: explains why the problem matters and what literature gap exists.
- Problem description: defines the concrete system, variables, uncertainty, objective, and constraints.
- Methodology: explains how the proposed model is transformed, approximated, trained, or solved.

Avoid leaking too much algorithmic derivation into the problem description. It is acceptable to state that the formulation is two-stage, tri-level, chance-constrained, DRO, or mixed-integer, but the proof, duality, decomposition, and solution algorithm usually belong in later sections.

## Canonical Architecture

Use this default order unless the existing paper structure strongly suggests otherwise.

### Move 1: Section Scope Statement

Open the section with one or two sentences saying what is modeled.

Good forms:

```text
This section presents a two-stage [UC/dispatch/scheduling] model for [system] under [uncertainty].
```

```text
The proposed model describes the coordinated operation of [subsystems] connected through [coupling variables/tie lines], with [uncertainty] affecting [operation].
```

```text
This section first introduces [preliminary process/model], and then formulates [optimization/problem].
```

The first paragraph should name:

- system: transmission system, distribution network, ITD/TDS, water-energy system, storage operator, renewable scenario generator, contingency event sequence.
- task: UC, dispatch, scheduling, resilience enhancement, scenario generation, early warning, arbitrage.
- uncertainty/event: wind/PV forecast error, renewable output, price, extreme-weather failures, contingencies, boundary-variable DDU, distributed predictions.

### Move 2: Physical System And Timeline

Before equations, describe the operational sequence.

For two-stage optimization:

- First stage: "here-and-now" decisions before uncertainty is realized.
- Second stage: "wait-and-see" recourse decisions after uncertainty/event realization.
- Coupling: affine policy, reserve activation, boundary variables, recourse cost, or scenario-dependent adjustment.

Typical IEEE wording:

```text
The first stage determines [commitment/base output/reserve/hardening/schedule]. After [uncertainty/event] is realized, the second stage adaptively determines [dispatch/reconfiguration/recourse/compensation].
```

For distributed or coordinated systems:

- Identify each operator/subsystem.
- Define exchanged variables.
- State coupling constraints.
- State whether coordination is centralized, decentralized, or distributed.

For event-sequence or early-warning models:

- Define event attributes: time, location, mark/component, weather variables.
- Define observation history and forecasting target.
- Explain how generated scenarios support operation/planning.

### Move 3: Sets, Indices, Parameters, And Variables

IEEE power-system papers often include a nomenclature block before Introduction or before formulation. Whether or not a table is used, the problem description must introduce symbols in a readable order.

Recommended order:

1. Sets and indices.
2. Deterministic parameters.
3. Uncertain variables/random events.
4. First-stage decision variables.
5. Second-stage/recourse decision variables.
6. Auxiliary or binary variables.

Do not introduce variables only through equations. Before major formulas, provide a sentence that states their engineering meaning.

Example logic:

```text
Let x denote the prescheduling decisions, including unit commitment states, base outputs, and reserve capacities. Let y denote the recourse decisions after renewable fluctuations are observed.
```

For papers with many variables, group them by physical object:

- generator variables
- renewable variables
- storage variables
- network variables
- water-system variables
- contingency/weather variables
- coupling variables

### Move 4: Uncertainty Description

This is the most important part for the user's corpus.

Always distinguish:

- **uncertain quantity**: wind power forecast error, PV output, electricity price, line failure, contingency, boundary flow, demand.
- **information available**: historical samples, forecasts, meteorological conditions, distributed predictions, reanalysis data, fragility curves.
- **uncertainty representation**: random variable, scenario, ambiguity set, chance constraint, uncertainty set, point process, fragility function, conditional distribution, decision-dependent distribution.
- **operational effect**: imbalance, reserve need, overload risk, outage, recourse cost, scheduling cost, decision regret.

For DRO papers, explicitly separate:

- the random variable itself;
- its unknown probability distribution;
- the ambiguity set containing possible distributions;
- the worst-case expectation/probability imposed over that ambiguity set.

For DDU papers, explicitly state which decision affects which uncertainty:

```text
The boundary coupling decisions change the feasible range/distribution of boundary variables.
```

```text
Line-hardening decisions alter the failure probability of overhead structures under an extreme-weather scenario.
```

For conditional/predictive uncertainty, state the condition:

```text
The forecast error distribution is conditional on the renewable forecast value and is therefore not identical across operating states.
```

### Move 5: Objective Function Narrative

Before presenting the objective, state what is minimized or maximized and why.

Common objective components:

- generation cost
- startup/shutdown cost
- reserve procurement cost
- recourse/adjustment cost
- load shedding or curtailment penalty
- line hardening and DER allocation cost
- reconfiguration cost
- expected operating cost
- worst-case expected cost
- chance/security violation risk
- storage arbitrage profit or cost
- water pumping electricity cost
- decision regret

Do not list costs without explaining stage assignment.

Good pattern:

```text
The objective minimizes the sum of first-stage scheduling costs and the worst-case expected second-stage recourse cost over all distributions in the ambiguity set.
```

For profit maximization papers, be explicit if the equation is written as minimization of negative profit.

### Move 6: Constraint Group Narrative

IEEE model sections usually state constraints in groups. Each group needs a one-line engineering explanation.

Common groups:

- unit commitment logic: startup/shutdown, minimum up/down time, ramping.
- generator limits: output, reserve, adjustment capacity.
- renewable limits: available power, curtailment, forecast plus error.
- network constraints: DC power flow, line limits, nodal balance.
- storage constraints: charging/discharging power, state-of-energy dynamics, terminal energy.
- water constraints: hydraulic balance, pump/tank/reservoir limits.
- resilience constraints: hardening budget, DER placement, islanding, reconfiguration, load restoration.
- chance/security constraints: probability of violations, N-1 or N-k contingency constraints.
- coupling constraints: tie-line/boundary exchange, TSO-DSO consistency, local coupling model.

Write constraints in the same order as system operation:

1. balance equations;
2. device limits;
3. network/coupling constraints;
4. uncertainty/risk constraints;
5. integrality/logical constraints.

### Move 7: Compact Or Abstract Reformulation

Many IEEE papers end the problem description by rewriting the physical model as a compact form. This prepares the methodology section.

Use compact forms when:

- the next section derives duality/reformulation;
- the model has many constraints;
- the algorithm needs a master/subproblem structure;
- the paper generalizes beyond the specific engineering instance.

Good transition:

```text
For the subsequent reformulation, the above model can be written in the following compact form.
```

The compact form should preserve:

- first-stage variables;
- second-stage variables;
- uncertainty/random variable;
- ambiguity/uncertainty set;
- objective structure;
- major constraint blocks.

Avoid compact forms that hide the engineering meaning before it has been explained.

## Section Templates By Paper Type

### Two-Stage DRO UC / Dispatch

Use for unit commitment, energy/reserve dispatch, and security-constrained dispatch under renewable uncertainty.

```text
This section formulates a two-stage [UC/dispatch] problem under [wind/PV] uncertainty. The first stage determines [commitment/base output/reserve] before renewable forecast errors are observed. After the uncertainty is realized, the second stage adjusts [generation/renewable curtailment/reserve deployment] to maintain power balance and satisfy network/security constraints.

Let [uncertain variable] denote [forecast error/output]. Since its probability distribution is unknown and only [historical samples/forecasts] are available, the distribution is assumed to belong to [ambiguity set]. The objective minimizes [first-stage cost] plus the worst-case expected [recourse cost] over this ambiguity set.

The model includes [constraint groups]. For later reformulation, the model is represented compactly as [two-stage/DRO form].
```

### Distributionally Robust Chance/Security Dispatch

Use when chance constraints and contingencies are central.

```text
The dispatch problem considers [renewable uncertainty] and [generation/line contingencies]. Before uncertainty and contingencies are realized, the operator schedules [generation set points] and procures [reserve types]. After realization, corrective actions are deployed to restore balance and satisfy security constraints.

The uncertain constraint is required to hold with probability at least [level] for all distributions in [ambiguity set]. This leads to a distributionally robust chance-constrained dispatch model. The model captures [N-1/N-k/security] requirements through [reserve/network/contingency] constraints.
```

### Coordinated Transmission-Distribution Scheduling

Use for ITD/TDS coordination.

```text
The transmission system and distribution systems are connected through [tie lines/transformers]. Their coordinated operation is modeled by boundary variables representing [power exchange/voltage/coupling quantity]. The objective minimizes the total operating cost of both systems while enforcing local constraints and coupling consistency.

The transmission subsystem includes [centralized generation/renewables/network constraints], whereas each distribution subsystem includes [DG/ESS/load/local network constraints]. The coupling constraints ensure that boundary variables reported by adjacent subsystems are consistent. If DDU is present, the scheduling decisions affect [boundary uncertainty/distribution], which is explicitly modeled by [decision-dependent set/distribution].
```

### Resilience Enhancement Under Extreme Weather

Use for hardening, DER allocation, reconfiguration, and contingency planning.

```text
This section models resilience enhancement of a distribution network subject to extreme-weather-induced contingencies. Preventive decisions, including [line hardening/DER allocation], are made before the weather event. After contingencies occur, operational decisions such as [reconfiguration/load restoration] are made to mitigate service interruption.

Failure probabilities are represented through [fragility functions/scenario-wise ambiguity sets], where [weather intensity/location/decision] affects component outages. The objective trades off [investment cost] and [worst-case expected outage/restoration cost]. The constraints describe [network operation, radiality, DER limits, hardening budget, load restoration].
```

### Renewable Scenario Generation

Use when the "problem" is a learning/generation task rather than an optimization model.

```text
The scenario generation task aims to produce daily renewable power trajectories that represent possible realizations conditioned on [forecast/meteorological information]. Each daily sample contains [actual profile] and [forecast/condition profile]. Given historical samples, the goal is to learn a conditional generator that maps [latent variables and conditions] to realistic renewable scenarios.

The generated scenarios should preserve [temporal dependence, spatial correlation, diurnal pattern, seasonality] and support downstream [dispatch/scheduling] analysis.
```

### Storage Arbitrage / Decision-Centric Uncertainty

Use for storage bidding/arbitrage.

```text
The storage operator participates in the day-ahead market as a price-taker. The decision variables include charging power, discharging power, net operating power, and stored energy. The storage dynamics link decisions across time, while power and energy limits define feasible operation.

Because market price predictions are uncertain, the arbitrage policy is evaluated under [risk/uncertainty set]. The problem is written as [cost/profit] optimization subject to storage feasibility and risk coverage.
```

### Water-Energy Scheduling / Flexible Loads

Use for grid-coupled water systems or similar flexible loads.

```text
The problem concerns a water supply district whose pumping and treatment facilities consume electricity and therefore interact with grid peak demand. The scheduling model coordinates water production, pumping, reservoir/tank levels, and electricity cost over the planning horizon.

The model includes energy-side constraints for electricity consumption and price response, and water-side constraints for hydraulic balance, demand satisfaction, and facility limits. Prediction uncertainty enters through [electricity price/load] and affects the scheduling cost.
```

### Extreme-Weather N-k Early Warning

Use when Section II is preliminary knowledge rather than an optimization formulation.

```text
Before introducing the proposed early-warning model, define the event process and failure mechanism. A marked spatio-temporal point process represents outage events with time, location, and component marks. Fragility functions map weather stress variables to component failure probabilities.

These definitions establish the target of the learning problem: predicting future weather-induced failures and generating high-risk N-k contingency scenarios from historical event sequences and meteorological information.
```

## Engineering-To-Math Transition Rules

The best problem descriptions alternate between prose and equations:

1. Prose: "What physical relationship is being modeled?"
2. Equation: "How is it written?"
3. Prose: "What does this equation mean?"

Do not present a block of equations without at least one leading sentence and one interpretation sentence.

Example:

```text
The wind power realization is represented as the sum of its forecast and forecast error. This relation links the deterministic forecast used in prescheduling to the random fluctuation observed in real-time operation.
```

Then give the equation.

## Common IEEE Phrases

Use these phrases when appropriate:

- "The first-stage decisions correspond to..."
- "After the uncertainty is realized..."
- "The second-stage decisions are determined adaptively..."
- "The uncertainty arises from..."
- "The objective is to minimize the sum of..."
- "The following constraints enforce..."
- "For notational simplicity..."
- "For the subsequent reformulation..."
- "The above model can be compactly written as..."
- "The ambiguity set contains all probability distributions that..."
- "The coupling constraints ensure consistency between..."
- "The fragility function maps hazard intensity to failure probability..."

## Diagnostic Checklist

Before finalizing the problem description, check:

- Does the opening sentence state the modeled task and uncertainty?
- Is the operational timeline clear?
- Are first-stage and second-stage decisions separated?
- Are uncertain variables distinguished from their unknown distributions?
- If DDU exists, is the decision-to-uncertainty mechanism explicitly named?
- Is every major variable introduced before or immediately after its equation?
- Does the objective narrative explain every cost/risk/profit component?
- Are constraints grouped by engineering role?
- Does the section explain how subsystems are coupled if coordination is involved?
- Does a compact form appear only after the physical model is understandable?
- Does the section stop before becoming an algorithm/proof section?
- Can a reader understand why the next methodology section is needed?

## Common Failure Modes

- **Formula dump**: equations appear before the system timeline and variable meaning.
- **Unclear stage logic**: first-stage and second-stage decisions are mixed without explaining when uncertainty is realized.
- **Ambiguity confusion**: the text treats random variables, samples, distributions, and ambiguity sets as if they are the same object.
- **No engineering interpretation**: constraints are mathematically correct but not tied to generators, lines, reserves, storage, water, or contingencies.
- **Hidden coupling**: TSO/DSO or water/grid coupling variables appear in equations without a prose explanation.
- **DDU underexplained**: the paper says "decision-dependent uncertainty" but never says which decision changes which uncertainty.
- **Objective underexplained**: costs are listed symbolically but not assigned to stages or physical actions.
- **Methodology creep**: duality, S-lemma, ADMM, or C&CG details appear before the reader understands the original problem.

## Output Modes

When writing a new problem description:

1. Ask for system type, planning horizon, decisions, uncertainty, objective components, and major constraints if missing.
2. Draft the section with prose-equation placeholders when formulas are not yet available.
3. Use subheadings such as "System Description", "Uncertainty Model", and "Optimization Formulation" if the target paper allows them.
4. Provide a compact model skeleton at the end if the next section needs reformulation.

When revising an existing problem description:

1. Preserve the user's equations and technical claims.
2. Reorder prose so system -> timeline -> variables -> uncertainty -> objective -> constraints -> compact form.
3. Add interpretation around equations rather than rewriting all math.
4. Flag missing definitions or stage ambiguities.

When diagnosing a problem description:

1. Produce a move map.
2. Identify missing system, timeline, uncertainty, objective, constraint, or compact-form elements.
3. Suggest exact paragraphs or bridge sentences to add.

