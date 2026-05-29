---
name: snhey-paper-solution-design
description: Write, diagnose, restructure, or polish the core solution design, proposed method, methodology, model reformulation, algorithm design, tractable approximation, framework design, and problem-solving sections of IEEE-style power systems papers. Use for power systems, smart grid, energy dispatch, unit commitment, renewable uncertainty, extreme-weather contingency, resilience, transmission-distribution coordination, stochastic/robust/distributionally robust optimization, Wasserstein DRO, chance constraints, ADMM, C&CG, S-lemma, MILP/conic reformulation, GAN/scenario generation, point-process early warning, and prediction-then-optimization. Trigger on 方案设计, 问题解决, 核心方法, 方法设计, solution design, methodology, proposed method, model reformulation, algorithm section, solution algorithm, tractable approximation, or IEEE方法部分.
---

# SNHEY Paper Solution Design

Use this skill to write or revise the core "how we solve the problem" section of an IEEE-style power-system paper. This section may be titled **Proposed Method**, **Solution Methodology**, **Model Reformulation**, **Tractable Approximation**, **Algorithm Design**, **Two-Step Method**, **Proposed Framework**, **Revised Integer L-Shaped Algorithm**, **C-StyleGAN2-SE**, **Constrained Diffusion STPP Model**, or similar.

This skill was distilled from 14 unique IEEE papers in the user's Zotero collection "电网高温日". It covers optimization-heavy and ML-heavy core methods: Wasserstein DRO, two-stage DRO, DR chance constraints, decision-dependent uncertainty, asynchronous ADMM, C&CG, S-lemma, MILP/conic reformulation, piecewise adaptive DRO, GAN scenario generation, decision-centric uncertainty sets, stochastic predict-then-optimize, resilience enhancement, and extreme-weather early warning.

## Core Thesis

The solution-design section must convince the reader of four things:

1. **Necessity**: why the original problem cannot be solved directly or why a naive method is insufficient.
2. **Mechanism**: what technical object is introduced to overcome the difficulty.
3. **Transformation**: how the technical object changes the original problem into a tractable, trainable, decomposable, or implementable form.
4. **Executable procedure**: how the reader would actually run the method.

In this corpus, strong solution sections are not just derivations. They are staged engineering arguments:

```text
Original difficulty -> key idea -> mathematical construction -> tractable reformulation/algorithm -> implementation details -> guarantee/discussion
```

## Difference From Other Sections

- Abstract: says what the solution is and what it achieves.
- Introduction: justifies why the solution is needed.
- Problem description: defines the original system/model/problem.
- Solution design: explains how the proposed method solves or transforms the original problem.
- Case study: proves the solution works empirically.

Do not repeat the full problem formulation unless a compact restatement is needed for reformulation.

## Canonical Solution-Design Architecture

Use the following moves. Full IEEE papers often use all moves; letters or ML papers may compress them.

### Move 1: Bridge From Original Problem To Technical Difficulty

Open by restating the exact obstacle created by the problem formulation.

Common obstacles in the corpus:

- Wasserstein DRO counterpart depends on many samples and becomes computationally heavy.
- Two-stage DRO with mixed-binary recourse cannot be handled by standard separation algorithms.
- DR chance-constrained dispatch is nonconvex and hard to solve exactly.
- Decision-dependent uncertainty makes the ambiguity set or uncertainty set depend on dispatch decisions.
- Joint chance constraints and worst-case expectations are not directly tractable.
- Forecasting/scenario generation must be aligned with downstream scheduling, not only statistical accuracy.
- Extreme-weather event sequences require spatio-temporal and network-constrained generation.

Good opening forms:

```text
The model in Section II is difficult to solve directly because [specific mathematical obstacle]. This section develops [method] to obtain a tractable formulation.
```

```text
To address the decision-dependent ambiguity in [problem], we first [normalization/construction], and then [dual transformation/decomposition].
```

Avoid vague openings:

- "In this section, we introduce the proposed method."
- "The solution process is as follows."

### Move 2: State The Key Idea Before Derivation

Before formulas, give the reader a one-paragraph overview.

This paragraph should answer:

- What is the core idea?
- Which part of the problem does it attack?
- What is the output of the section?

Examples of key ideas from the corpus:

- Use Bayesian nonparametric mixture modeling to decompose a complex distribution, then build local trimming-Wasserstein ambiguity sets.
- Use CGAN/CNN to augment small-sample renewable data, then construct a Wasserstein ambiguity set for forecast errors.
- Construct an uncertainty set with enough probability mass under all Wasserstein-near distributions, then solve a robust linear problem.
- Replace strict adaptive DRO recourse with piecewise linear policies or piecewise value functions.
- Use Bonferroni and CVaR approximations to turn DR joint chance constraints into a conic form.
- Use asynchronous ADMM to exploit ITD star topology and subsystem heterogeneity.
- Encode event history and geographic information, then use constrained diffusion to generate future failure events.

### Move 3: Decompose The Solution Into Modules

IEEE solution sections are usually modular. Use subsections that match the technical pipeline, not arbitrary math fragments.

Common module orders:

#### DRO / Optimization Pipeline

1. Ambiguity/uncertainty-set construction.
2. Compact reformulation.
3. Dual transformation or approximation.
4. Tractable deterministic equivalent.
5. Decomposition or iterative algorithm.
6. Convergence/optimality/complexity discussion.

#### DDU Pipeline

1. Analyze how decisions affect uncertainty.
2. Normalize or decouple decision-dependent variables.
3. Build decision-dependent uncertainty/ambiguity set.
4. Reformulate using duality/S-lemma/vertices.
5. Solve with layered/decomposed algorithm.

#### Chance/Security Pipeline

1. Compact chance-constrained form.
2. Distributionally robust version.
3. Inner/outer or safe approximation.
4. Robust counterpart or conic/MILP reformulation.
5. Scalable algorithm or two-step method.

#### Distributed Optimization Pipeline

1. Separable subsystem formulation.
2. Local objective and constraints.
3. Coupling variables and consensus conditions.
4. Local subproblem updates.
5. Communication protocol.
6. Convergence or stopping criterion.

#### ML / Scenario / Early-Warning Pipeline

1. Data representation and input-output definition.
2. Architecture overview.
3. Component modules.
4. Loss/training objective.
5. Scenario/event generation procedure.
6. Downstream scheduling/risk-support interface.

### Move 4: Explain Each Module With Purpose-Formula-Effect

For every technical module, write in this pattern:

1. **Purpose**: what difficulty or requirement this module addresses.
2. **Formula/construction**: the mathematical or algorithmic object.
3. **Effect**: what becomes tractable, expressive, less conservative, or implementable.

Example:

```text
To eliminate the dependence of the ambiguity set on the original scale of uncertain variables, the uncertain variables are first normalized. This normalization converts the decision-dependent support into a standard form, which enables the subsequent dual transformation.
```

Do not let the section become equation-only. Every important equation should have a sentence before it and a sentence after it.

### Move 5: Tractable Reformulation

For optimization papers, this is often the heart of the solution section.

When writing reformulation, always state:

- original difficult term: worst-case expectation, chance constraint, bilinear term, max-min problem, tri-level model, recourse value function.
- mathematical tool: strong duality, S-lemma, CVaR, Bonferroni, SAA, big-M, dual vertices, linearization, conic reformulation, semidefinite constraints.
- resulting form: MILP, MISOCP, conic program, linear robust optimization, master/subproblem decomposition, tractable deterministic equivalent.
- assumptions or approximation status: exact reformulation, safe approximation, upper approximation, relaxation, inner/outer approximation.

Precise status matters. Do not call an approximation exact unless the paper proves exactness under stated conditions.

Useful phrases:

- "The following proposition shows that..."
- "By applying strong duality, the worst-case expectation can be equivalently reformulated as..."
- "The nonconvex term is handled by..."
- "This yields a tractable [MILP/conic/semidefinite] formulation."
- "The approximation is conservative because..."
- "The exactness condition is..."

### Move 6: Algorithm Design

After reformulation, provide an executable procedure.

Good algorithm writing includes:

- Inputs: samples, forecasts, network data, ambiguity radius, risk level, convergence tolerance.
- Initialization: candidate solution, ambiguity set, master problem, scenario set, dual vertices, model weights.
- Iteration loop:
  - solve master or training step;
  - solve subproblem/separation problem/adversarial problem;
  - generate cut/scenario/dual vertex/gradient;
  - update solution/model;
  - check convergence.
- Outputs: dispatch decisions, schedules, uncertainty set, generated scenarios, failure forecasts, resilience plan.

Algorithm prose should explain why each step exists.

Avoid:

- dumping pseudocode with no narrative;
- naming C&CG/ADMM/Taylor/S-lemma without explaining the role;
- hiding stopping criteria.

### Move 7: Guarantees, Complexity, And Practical Discussion

IEEE papers often include a short discussion after the method:

- convergence of iterative algorithm;
- optimality or approximation quality;
- scalability;
- finite convergence;
- communication requirements;
- conservatism;
- out-of-sample reliability;
- computational burden;
- implementation details.

This discussion is especially important when the method is approximate, distributed, or data-driven.

Example:

```text
The outer-layer dual-vertex generation progressively tightens the relaxation of the recourse value function, while the inner-layer convexification improves tractability of the nonlinear master problem.
```

## Corpus-Derived Solution Patterns

### Bayesian Nonparametric TSDRO UC

Solution chain:

1. Use Dirichlet process mixture model to infer mixture components from uncertainty data.
2. Extract global-local distributional structure.
3. Construct mixture ambiguity set as weighted local ambiguity sets.
4. Use trimming-Wasserstein logic to reduce conservatism.
5. Embed the ambiguity set into two-stage DRO UC.
6. Use duality and SAA to reformulate as MILP.
7. Provide a complete solution algorithm.

Writing lesson:

- When the uncertainty model is the novelty, make the "data -> distribution structure -> ambiguity set -> optimization model" chain explicit.

### Small-Sample Wind/PV Two-Stage DRO

Solution chain:

1. Establish a three-part framework: data augmentation, two-stage DRO construction, model transformation/solution.
2. Use CGAN to augment small-sample wind/PV output data.
3. Use CNN/prediction module to obtain forecast errors.
4. Construct Wasserstein ambiguity set from forecast-error data.
5. Build two-stage DRO with hard and soft constraints.
6. Transform nonconvex model using duality, relaxation, and Taylor linearization.

Writing lesson:

- For data-driven optimization, describe data production and optimization construction as one pipeline.

### Wasserstein DRO Approximate UC

Solution chain:

1. Define Wasserstein ambiguity set and data-driven uncertainty set.
2. Formulate UC as a DRO problem with worst-case expected adjustment cost.
3. Identify that the robust counterpart grows with sample size.
4. Derive a distributionally robust counterpart.
5. Propose an upper approximate framework with constant-size constraint structure.
6. State exactness conditions.

Writing lesson:

- Computation-focused papers should show the complexity bottleneck before presenting the approximation.

### Flexible-Resource DRUC

Solution chain:

1. Formulate improved two-stage DRUC with regular-unit first-stage UC and flexible-resource second-stage UC.
2. Construct confidence set for ambiguous renewable distribution.
3. Rewrite the model abstractly.
4. Develop a revised integer L-shaped algorithm.
5. Combine distribution separation, scenario filtering, and parametric/lift-and-project cuts.
6. Show why cuts are valid for first-stage UC structures.

Writing lesson:

- For mixed-binary recourse, the method section should emphasize why standard separation fails and how the revised cut-generation framework fixes it.

### Two-Step DR Chance/Security Dispatch

Solution chain:

1. Rewrite the original dispatch problem in compact chance-constrained form.
2. Construct a Wasserstein distributionally robust version.
3. Step 1: construct a polyhedral uncertainty set containing enough probability mass under all distributions in the ambiguity set.
4. Step 2: solve a linear robust optimization problem over that uncertainty set.
5. Discuss cost-violation tradeoff and scalability.

Writing lesson:

- If the solution is a named multi-step approach, make each step's input, output, and safety role explicit.

### Conditional StyleGAN Scenario Generation

Solution chain:

1. Explain why StyleGAN2 and sequence encoder are appropriate for renewable profiles.
2. Define conditional renewable time-series GAN.
3. Build generator/discriminator and meteorological conditioning.
4. Train the generator adversarially.
5. Freeze the trained generator.
6. Develop sequence encoder to infer latent style from forecasts/conditions and generate day-ahead scenarios.
7. Connect scenarios to statistical and scheduling evaluation.

Writing lesson:

- ML method sections need architecture rationale, not just architecture description.

### Decision-Centric Uncertainty Sets

Solution chain:

1. Start from storage arbitrage model.
2. Define risk-averse policy under price uncertainty.
3. Choose an ellipsoidal uncertainty set for tractability and correlation modeling.
4. Introduce decision-centric uncertainty set tying parameter estimation to bidding profitability.
5. Use decision-centric gradient and size calibration to align uncertainty set with decision quality.

Writing lesson:

- For decision-centric methods, repeatedly connect estimation choices to operational objective, not only statistical fit.

### Resilience Enhancement With Decision-Dependent Contingencies

Solution chain:

1. State assumptions for extreme-weather scenarios.
2. Construct scenario-wise decision-dependent ambiguity sets.
3. Derive decision-dependent failure probability functions using fragility curves.
4. Build two-stage tri-level DD-DRRE model.
5. Recast model into MILP master problem and scenario-wise subproblems.
6. Apply customized C&CG.

Writing lesson:

- For resilience papers, uncertainty modeling and solution design are intertwined; describe fragility/contingency modeling before optimization reformulation.

### Stochastic Predict-Then-Optimize Water-Energy Scheduling

Solution chain:

1. Build integrated water-energy scheduling model with energy side and water side.
2. Define probabilistic forecasting of electricity prices.
3. Embed predictive distribution into scheduling through stochastic predict-then-optimize.
4. Derive a differentiable convex upper-bound surrogate for end-to-end training.
5. Connect prediction loss to decision regret/cost.

Writing lesson:

- For predict-then-optimize, the central writing task is to show how prediction output enters the optimizer and how optimization feedback trains prediction.

### DR Joint Chance-Constrained ITD Dispatch

Solution chain:

1. Build separable ITD formulation.
2. Use Wasserstein ambiguity set for renewable forecast errors.
3. Reformulate worst-case objective and joint chance constraints.
4. Use Bonferroni and CVaR approximation for tractable conic formulation.
5. Express result as distributed optimization.
6. Develop asynchronous ADMM respecting star-topology ITD systems.

Writing lesson:

- Distributed optimization papers must connect mathematical decomposition to physical operator communication.

### TDS DRO Scheduling With DDU/DIU

Solution chain:

1. Analyze DDU in boundary coupling variables.
2. Distinguish DDU from decision-independent source-load uncertainty.
3. Build decision-dependent probability distribution set.
4. Formulate DRO scheduling model containing both DDU and DIU.
5. Combine improved ADMM and adaptive C&CG for distributed solution.

Writing lesson:

- When DDU is central, spend a subsection on mechanism analysis before equations.

### Energy/Reserve Dispatch With Distributed Predictions

Solution chain:

1. Formulate two-stage energy/reserve dispatch.
2. Improve renewable prediction using operator and renewable-source predictions.
3. Build moment-based ambiguity set depending on predictive decisions.
4. Normalize uncertain variables to manage DDU.
5. Use dual vertices, duality, and S-lemma for tractable transformation.
6. Develop two-layer iterative algorithm and acceleration strategies.
7. Discuss convergence/optimality.

Writing lesson:

- When the algorithm is layered, explain outer-loop and inner-loop roles separately.

### Approximately Adaptive DRO

Solution chain:

1. Define strict adaptive DRO dispatch as the target.
2. Propose two approximations:
   - piecewise linear policy;
   - piecewise value function.
3. Segment ambiguity set by equal-probability principle.
4. Reformulate piecewise constraints using duality and S-lemma.
5. Handle dual vertices and bilinear terms through generation/alternating optimization.
6. Discuss which approximation works better under which case.

Writing lesson:

- Approximation papers should clearly state "what is approximated" and "what structure is preserved."

### Extreme-Weather CDSTPP Early Warning

Solution chain:

1. Define overall architecture of constrained diffusion spatio-temporal point process.
2. Use context encoder for failure history and geographic/network information.
3. Use marked spatio-temporal constrained diffusion model for failure-event generation.
4. Incorporate meteorological and network constraints.
5. Use two-stage training.
6. Generate high-risk N-k contingency scenarios from predicted event distributions.

Writing lesson:

- For event-generation methods, describe the architecture as "history/context -> constrained event distribution -> scenario generation -> operation support."

## Writing Templates

### Optimization Reformulation Template

```text
The model in Section [X] is difficult to solve directly because [difficult term/structure]. To address this issue, this section derives a tractable reformulation. First, [uncertainty/ambiguity/recourse] is rewritten as [compact form]. Then, by applying [duality/S-lemma/CVaR/Bonferroni/SAA], [worst-case/chance/nonconvex] constraints are transformed into [MILP/conic/linear/semidefinite] constraints. Finally, the resulting formulation is solved by [algorithm], whose main steps are [master/subproblem/update/stopping].
```

### Algorithm Design Template

```text
The solution procedure is summarized as follows. The algorithm starts from [initialization]. At each iteration, the master problem determines [candidate first-stage decision]. Given this decision, the subproblem identifies [worst-case distribution/scenario/violated constraint/dual vertex]. If [condition] is violated, [cut/scenario/vertex] is added to the master problem; otherwise, the algorithm terminates and returns [solution]. This design exploits [problem structure] and avoids [computational bottleneck].
```

### Data-Driven Optimization Pipeline Template

```text
The proposed framework consists of [number] modules. The first module constructs [data/scenarios/predictions] from [historical samples/meteorological information]. The second module uses these outputs to build [ambiguity set/uncertainty set/probabilistic forecast]. The third module embeds the uncertainty representation into [dispatch/scheduling/UC] and derives [tractable reformulation]. The final module solves the resulting problem and outputs [decisions/scenarios/risk forecasts].
```

### ML/Scenario Method Template

```text
The proposed model maps [inputs/conditions/history] to [scenario/event/output]. Its architecture contains [module 1], [module 2], and [module 3]. [Module 1] extracts [feature/context]. [Module 2] generates [candidate trajectories/events] subject to [constraints/conditions]. [Module 3] calibrates or selects outputs for [downstream task]. The model is trained using [loss/training strategy], enabling [desired property].
```

## Style Rules

- Start each method subsection with purpose, not equations.
- Use "therefore", "to this end", and "based on this" only when a real dependency exists.
- Name the mathematical status of every transformation: exact, equivalent, approximate, relaxed, conservative, safe, upper-bound, or heuristic.
- Explain why a chosen tool is appropriate: S-lemma for quadratic constraints, duality for worst-case expectation, C&CG for robust/separation structure, ADMM for separable coupled systems, GAN for scenario generation, diffusion for event-sequence generation.
- Keep physical meaning alive: after abstract symbols, remind the reader what decision or uncertainty they represent.
- Put long proofs in appendices when possible; keep the main text focused on transformation logic and usable results.
- Use figures for pipelines with three or more modules; use algorithms for iterative procedures; use propositions/theorems for reformulation guarantees.

## Diagnostic Checklist

Before finalizing a solution-design section, check:

- Does the first paragraph state the specific difficulty being solved?
- Is the key idea explained before heavy formulas?
- Are method modules ordered as a pipeline?
- Does each subsection have purpose, construction, and effect?
- Are exact reformulations distinguished from approximations?
- Are all assumptions stated before they are used?
- Does the algorithm specify inputs, initialization, update, stopping criterion, and outputs?
- Is the chosen tool linked to the problem structure?
- Is the physical interpretation preserved after compact notation?
- Is there a guarantee, convergence, complexity, or practical discussion if the method is iterative or approximate?
- Does the section end ready for case studies, with clear outputs and comparison targets?

## Common Failure Modes

- **Equation avalanche**: derivation starts without saying what obstacle is being removed.
- **Tool-name decoration**: duality, S-lemma, ADMM, C&CG, GAN, or diffusion are named but not connected to a specific role.
- **No method pipeline**: subsections are mathematically correct but the reader cannot see the end-to-end procedure.
- **Approximation ambiguity**: the text does not say whether the reformulation is exact, relaxed, or conservative.
- **Algorithm without inputs/outputs**: pseudocode appears but cannot be implemented from the description.
- **Lost engineering meaning**: compact notation hides generators, reserves, contingencies, forecasts, or coupling variables.
- **Disconnected data module**: data augmentation or prediction is described but not linked to the optimization model.
- **No transition to experiments**: the method section does not state what outputs or metrics the case study should evaluate.

## Output Modes

When writing a new solution-design section:

1. Ask for the original problem, main obstacle, proposed technical idea, mathematical tools, algorithm steps, and validation outputs if missing.
2. Draft a section outline with method modules.
3. Write prose around formula placeholders if equations are not supplied.
4. Include algorithm skeleton or proposition statements when useful.
5. Flag missing assumptions or guarantee claims.

When revising a solution-design section:

1. Preserve equations and technical claims.
2. Reorder material into obstacle -> key idea -> construction -> reformulation -> algorithm -> discussion.
3. Add purpose/effect sentences around equations.
4. Clarify approximation status and algorithm flow.
5. Do not invent convergence, exactness, or performance claims.

When diagnosing a solution-design section:

1. Produce a module map.
2. Identify missing bridge sentences, undefined tools, or unclear transformations.
3. Check if every method component answers a problem difficulty.
4. Suggest concrete subsection titles and transition sentences.

