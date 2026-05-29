# IEEE Solution Design Corpus Extraction From "电网高温日"

This file records the extraction used to build `snhey-paper-solution-design`. It paraphrases the core problem-solving and proposed-method sections of the IEEE papers. It does not reproduce full copyrighted sections.

## Corpus Summary

- IEEE records found: 15
- Unique IEEE papers: 14
- Duplicate record: `XSUEUNX5` and `W88TVEVZ` are the same 2019 IEEE TPWRS Wasserstein unit commitment article.
- Target section names vary widely: Proposed Model, Solution Methodology, Model Reformulation, Tractable Approximation, Revised Integer L-Shaped Algorithm, Two-Step Method, Proposed Framework, C-StyleGAN2-SE, Constrained Diffusion STPP Model, etc.
- Extraction principle: identify the core "how the paper solves the problem" pipeline, not the exact heading only.

## Cross-Paper Solution Pattern

Across the corpus, solution-design sections usually follow:

1. Restate why the original formulation is difficult.
2. Introduce the key technical idea.
3. Build an uncertainty/scenario/ambiguity/architecture component.
4. Embed it into the optimization or prediction task.
5. Reformulate or approximate the difficult terms.
6. Design an executable algorithm/training procedure.
7. Discuss exactness, convergence, scalability, conservatism, or implementation.

The best sections connect every mathematical tool to a specific obstacle.

## 1. S7G5GGB7

- Title: Bayesian Nonparametric Two-Stage Distributionally Robust Unit Commitment Optimization: From Global Multimodality to Local Trimming-Wasserstein Ambiguity
- Venue: IEEE Transactions on Power Systems, 2024
- Core solution sections: Bayesian nonparametric TSDRO framework; reformulation and solution algorithm
- Solution chain:
  - Starts from a two-stage UC model under wind forecast uncertainty.
  - Introduces a Dirichlet process mixture model to infer mixture components from uncertainty data.
  - Uses the Bayesian mixture structure to capture global-local distributional features.
  - Constructs a mixture ambiguity set from local ambiguity sets.
  - Uses probability trimming and Wasserstein metric to encode both Bayesian inference and empirical data.
  - Embeds the mixture ambiguity set into the TSDRO UC model.
  - Applies duality theory and SAA to reformulate the BN-TSDRO problem as an MILP.
  - Develops a complete algorithm for solving to prescribed precision.
- Writing lesson:
  - The method chain should be written as data structure -> ambiguity construction -> optimization embedding -> deterministic reformulation.

## 2. 664PKLSZ

- Title: Two-Stage Distributionally Robust Optimization Dispatch for Power Systems With Uncertain Small-Sample Wind and Photovoltaic Data
- Venue: IEEE Transactions on Smart Grid, 2026
- Core solution sections: Two-stage DRO framework; mathematical modeling; model transformation and efficient solution
- Solution chain:
  - Defines a three-part framework: small-sample data modeling, DRO dispatch construction, and model transformation.
  - Uses CGAN to augment wind/PV output data under extreme weather.
  - Uses CNN-based prediction to obtain wind/PV forecast errors.
  - Constructs Wasserstein ambiguity sets from forecast-error data.
  - Builds a two-stage DRO model with hard constraints and soft prediction-error constraints.
  - Handles nonlinearity/nonconvexity using duality, relaxation approximation, and Taylor linearization.
  - Transforms the model to MILP-like solvable form.
- Writing lesson:
  - Data augmentation, uncertainty construction, and dispatch optimization should be described as one integrated pipeline.

## 3. XSUEUNX5

- Title: Wasserstein Metric Based Distributionally Robust Approximate Framework for Unit Commitment
- Venue: IEEE Transactions on Power Systems, 2019
- Core solution sections: ambiguity-set construction; robust UC formulation; model reformulation
- Solution chain:
  - Constructs Wasserstein ambiguity set centered on empirical distribution.
  - Builds data-driven uncertainty set from historical wind forecast error samples.
  - Formulates robust UC as DRO with worst-case expected adjustment cost.
  - Identifies computational burden because the robust counterpart size depends on sample size.
  - Derives the distributionally robust counterpart.
  - Proposes WDRA upper approximation to reduce the model size.
  - Provides conditions where the approximation becomes exact.
  - Positions the approximation as solver-friendly for large systems.
- Writing lesson:
  - Approximation writing must name both the computational bottleneck and the exactness/quality condition.

## 4. 4SBSUXML

- Title: Distributionally Robust Unit Commitment With Flexible Generation Resources Considering Renewable Energy Uncertainty
- Venue: IEEE Transactions on Power Systems, 2022
- Core solution sections: improved DRUC formulation; confidence set; abstract formulation; revised integer L-shaped algorithm
- Solution chain:
  - Formulates improved DRUC where regular units are first-stage decisions and flexible generation resources are second-stage mixed-binary recourse.
  - Constructs a confidence set for ambiguous renewable-output distribution.
  - Rewrites the improved DRUC model in abstract form.
  - Explains why traditional separation algorithms do not apply to the mixed-binary second stage.
  - Develops a revised integer L-shaped algorithm.
  - Combines distribution separation, scenario filtering, and lift-and-project/parametric cut techniques.
  - Produces valid cuts for first-stage UC solutions.
- Writing lesson:
  - If the core challenge is recourse integrality, make "why standard algorithms fail" explicit before presenting the revised algorithm.

## 5. BYNZT364 / H3CU3HE8

- Title: A Two-Step Approach to Wasserstein Distributionally Robust Chance- and Security-Constrained Dispatch
- Venue: IEEE Transactions on Power Systems, 2024
- Core solution section: Two-step distributionally robust method for solving CCSCD
- Solution chain:
  - Rewrites the dispatch model in compact form with deterministic constraints and joint chance constraints.
  - Constructs the Wasserstein DR chance-constrained problem.
  - Notes that exact solution is nonconvex and computationally heavy.
  - Step 1 constructs a polyhedral uncertainty set containing sufficient probability mass under every distribution in the ambiguity set.
  - The mass-covering set is constructed by solving lower-dimensional DR problems.
  - Step 2 solves a linear robust optimization problem over the constructed set.
  - Discusses scalability and tunable cost-violation tradeoff.
- Writing lesson:
  - A two-step method should clearly state the input/output of each step and why the first step makes the second step safe or scalable.

## 6. 7K66NLW5

- Title: Conditional Style-Based Generative Adversarial Networks for Renewable Scenario Generation
- Venue: IEEE Transactions on Power Systems, 2023
- Core solution section: Proposed model
- Solution chain:
  - Motivates StyleGAN2 for renewable profiles because it can separate high-level trend characteristics and low-level stochastic variations.
  - Designs conditional renewable time-series GAN with meteorological conditions.
  - Uses generator/discriminator adversarial learning to produce realistic renewable samples.
  - Develops a sequence encoder using the fixed trained generator.
  - The encoder infers day-ahead latent patterns and generates accurate scenarios.
  - The generated scenarios are later evaluated statistically and through scheduling analysis.
- Writing lesson:
  - For ML architecture papers, explain why each architectural component matches a data property of renewable power.

## 7. ZFIN98H8

- Title: Decision-Centric Uncertainty Sets for Storage Arbitrage: Integrating Estimation and Optimization
- Venue: IEEE Transactions on Power Systems, 2025
- Core solution section: Formulation and methodology
- Solution chain:
  - Starts from storage arbitrage model.
  - Defines risk-averse storage arbitrage policy under price uncertainty.
  - Chooses ellipsoidal uncertainty set for tractability and correlation representation.
  - Proposes decision-centric uncertainty set that ties parameter estimation to bidding profitability.
  - Uses decision-centric gradient based on implicit-function reasoning.
  - Calibrates uncertainty-set size with a statistically valid coverage method.
- Writing lesson:
  - Decision-centric solution writing must repeatedly link estimation/calibration choices back to final profit or risk coverage.

## 8. 7F6UKVYW

- Title: A Distributionally Robust Resilience Enhancement Strategy for Distribution Networks Considering Decision-Dependent Contingencies
- Venue: IEEE Transactions on Smart Grid, 2024
- Core solution sections: scenario-wise decision-dependent ambiguity sets; DD-DRRE model; reformulation and solution
- Solution chain:
  - States assumptions for representative extreme-weather events.
  - Constructs scenario-wise decision-dependent ambiguity sets for contingency distributions.
  - Uses fragility analysis to derive decision-dependent failure probability functions.
  - Handles hurricane intensity stochasticity and estimation error.
  - Formulates two-stage tri-level DD-DRRE model with hardening, DER allocation, and network reconfiguration.
  - Explores strong duality and equivalent linearization.
  - Recasts the tri-level model into MILP master problem and scenario-wise subproblems.
  - Solves with customized C&CG.
- Writing lesson:
  - In resilience papers, the solution section often begins with contingency-distribution construction because that is the core method, not merely data preparation.

## 9. 8W35SDHD

- Title: End-to-End Stochastic Predict-Then-Optimize for Cost-Efficient Water-Energy Resource Scheduling
- Venue: IEEE Transactions on Smart Grid, 2025
- Core solution sections: integrated water-energy scheduling model; end-to-end stochastic predict-then-optimize framework
- Solution chain:
  - Builds integrated water-energy scheduling model with energy-side and water-side constraints.
  - Defines electricity price uncertainty and probabilistic forecasting.
  - Embeds price distribution into scheduling optimization through stochastic predict-then-optimize.
  - Aligns predictive distribution with optimality gap rather than point forecast accuracy alone.
  - Derives SPTO+ as differentiable convex upper-bound surrogate.
  - Enables gradient-based end-to-end training.
- Writing lesson:
  - Predict-then-optimize writing should explicitly trace prediction output -> optimization input -> decision loss -> training feedback.

## 10. 6IB9A59U

- Title: Distributionally Robust Joint Chance-Constrained Dispatch for Integrated Transmission-Distribution Systems via Distributed Optimization
- Venue: IEEE Transactions on Smart Grid, 2022
- Core solution sections: tractable approximation; distributed optimization algorithm
- Solution chain:
  - Starts from separable ITD models and DRJCC dispatch.
  - Uses Wasserstein metric ambiguity sets for unknown renewable forecast-error distributions.
  - Reformulates worst-case objective terms.
  - Uses Bonferroni and CVaR approximation for joint chance constraints.
  - Produces tractable conic formulations.
  - Summarizes the model as a standard distributed optimization problem.
  - Designs asynchronous ADMM so subsystems can update with partial neighbor information.
- Writing lesson:
  - Distributed solution sections should connect mathematical separability to physical communication requirements.

## 11. 2B6B5829

- Title: Distributed Distributionally Robust Scheduling for Coordinated Transmission and Distribution Systems Considering Decision-Dependent Uncertainties
- Venue: IEEE Transactions on Power Systems, 2026
- Core solution sections: DRO scheduling model considering DDU and DIU; distributed solution
- Solution chain:
  - Analyzes DDU in boundary coupling variables between transmission and distribution systems.
  - Distinguishes boundary-variable DDU from traditional decision-independent source/load uncertainty.
  - Builds decision-dependent probability distribution set.
  - Formulates two-stage DRO scheduling model containing both DDU and DIU.
  - Combines improved ADMM with adaptive C&CG.
  - Uses distributed solution to exploit natural decoupling between TDS.
- Writing lesson:
  - DDU method sections need a mechanism-analysis subsection before the actual DRO formulation.

## 12. QJ7ZUXA6

- Title: Distributionally Robust Energy and Reserve Dispatch With Distributed Predictions of Renewable Energy
- Venue: IEEE Transactions on Power Systems, 2025
- Core solution sections: energy/reserve dispatch with DDU; solution methodology
- Solution chain:
  - Defines two-stage energy/reserve dispatch with here-and-now and wait-and-see variables.
  - Incorporates distributed predictions from system operator and renewable energy sources.
  - Captures relationships among expectation, variance, covariance, and predictive decisions.
  - Builds a less conservative moment-based ambiguity set.
  - Normalizes uncertain variables to handle decision-dependent uncertainty.
  - Uses dual-vertex relaxation for second-stage recourse value function.
  - Applies duality theory and S-lemma for tractable transformation.
  - Develops two-layer iterative algorithm with acceleration strategies.
  - Discusses convergence and optimality.
- Writing lesson:
  - Layered algorithms need an explicit explanation of what each layer updates and why.

## 13. 9AW7JDDQ

- Title: Approximately Adaptive Distributionally Robust Optimization for Energy and Reserve Dispatch
- Venue: IEEE Transactions on Sustainable Energy, 2025
- Core solution sections: distributionally robust energy/reserve dispatch; piecewise linear policy approximation; piecewise value-function approximation
- Solution chain:
  - Defines strict adaptive DRO energy/reserve dispatch as baseline.
  - Constructs wind-power ambiguity set using moment information.
  - Uses equal-probability principle to segment the ambiguity set.
  - Proposes piecewise linear policy-based AADRO to approximate recourse decisions.
  - Reformulates resulting DRO constraints via duality and S-lemma.
  - Handles bilinear terms using alternating optimization.
  - Proposes piecewise value function-based AADRO to approximate quadratic recourse with piecewise linear value functions.
  - Uses dual vertex generation for the value-function formulation.
- Writing lesson:
  - Approximation sections must keep two questions visible: what is approximated and how the approximation is solved.

## 14. YVQRC6TL

- Title: Early Warning of Extreme Weather-Induced N-k Contingencies Leveraging Spatio-Temporal Analysis of Historical Event Sequences
- Venue: IEEE Transactions on Power Systems, 2026
- Core solution section: Constrained diffusion STPP model
- Solution chain:
  - Defines overall CDSTPP architecture.
  - Uses context encoder to encode failure-event history and geographic information of transmission lines.
  - Designs marked spatio-temporal constrained diffusion model for future failure event generation.
  - Incorporates spatial, temporal, meteorological, and network constraints.
  - Uses a two-stage training strategy.
  - Generates high-risk N-k contingency scenarios from predicted failure distributions.
- Writing lesson:
  - Event-learning solution sections should be written as context encoding -> constrained distribution modeling -> scenario/event generation -> operational use.

## Practical Synthesis Table

| Paper type | Core method object | Main obstacle | Typical solution writing |
| --- | --- | --- | --- |
| Wasserstein DRO UC/dispatch | ambiguity set + robust counterpart | sample-size-dependent or nonconvex model | define ambiguity -> dual reformulation -> approximation/MILP |
| DR chance/security dispatch | DRCC approximation | exact joint chance constraints are hard | compact form -> mass-covering set -> robust linear problem |
| Flexible-resource DRUC | integer recourse algorithm | mixed-binary second stage | abstract model -> revised integer L-shaped -> cuts |
| DDU scheduling | decision-dependent distribution set | uncertainty depends on decisions | analyze DDU -> normalize/construct set -> reformulate -> distributed algorithm |
| ITD/TDS distributed dispatch | separable model + ADMM | coupling and subsystem heterogeneity | local models -> coupling -> asynchronous updates |
| Scenario generation | conditional generator/encoder | spatial-temporal and conditional scenario realism | architecture rationale -> generator -> encoder -> scenarios |
| Predict-then-optimize | differentiable decision loss | prediction separated from optimization | forecast distribution -> optimizer -> regret/surrogate -> training |
| Resilience under EWE | fragility/ambiguity + tri-level model | DDU and limited outage data | fragility -> ambiguity set -> tri-level model -> MILP/C&CG |
| Extreme-weather early warning | constrained diffusion STPP | simultaneous spatio-temporal failures | context encoder -> constrained diffusion -> N-k scenario generation |

