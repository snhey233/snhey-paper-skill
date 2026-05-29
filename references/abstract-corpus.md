# IEEE Abstract Corpus Extraction From "电网高温日"

This file records the sentence-level rhetorical extraction used to build `SKILL.md`. It paraphrases the abstracts by functional move instead of reproducing them as a full-text corpus.

## Corpus Summary

- IEEE items found: 15
- Unique abstracts: 14
- Duplicate: `XSUEUNX5` and `W88TVEVZ` are the same 2019 IEEE TPWRS Wasserstein unit commitment article.
- Common abstract length: 6-9 sentences
- Common move order: application pressure -> gap/limitation -> proposal -> uncertainty representation -> reformulation/algorithm -> validation/result

## 1. S7G5GGB7

- Title: Bayesian Nonparametric Two-Stage Distributionally Robust Unit Commitment Optimization: From Global Multimodality to Local Trimming-Wasserstein Ambiguity
- Venue: IEEE Transactions on Power Systems, 2024
- DOI: 10.1109/TPWRS.2024.3350632
- Sentence count: 8
- Move extraction:
  - S1: Renewable penetration creates operational uncertainty pressure.
  - S2: The key need is to characterize global-local features of unknown uncertainty distributions.
  - S3: Proposes a data-driven Bayesian nonparametric two-stage DRO framework for UC.
  - S4: Uses Bayesian nonparametric mixture modeling to decompose uncertainty into local components.
  - S5: Builds a mixture ambiguity set from local ambiguity sets.
  - S6: Uses probability trimming and Wasserstein metric to encode Bayesian and data information and reduce conservatism.
  - S7: Uses duality and SAA to reformulate the UC problem as MILP and develop an algorithm.
  - S8: Validates effectiveness and scalability on three systems with in-sample and out-of-sample comparisons.

## 2. 664PKLSZ

- Title: Two-Stage Distributionally Robust Optimization Dispatch for Power Systems With Uncertain Small-Sample Wind and Photovoltaic Data
- Venue: IEEE Transactions on Smart Grid, 2026
- DOI: 10.1109/TSG.2025.3621481
- Sentence count: 9
- Move extraction:
  - S1: Extreme meteorological events create dispatch challenges for new-energy power systems.
  - S2-S3: Data are insufficient and small-sample wind/PV uncertainty is hard to characterize.
  - S4: Develops a two-stage DRO dispatch strategy for uncertain small-sample wind/PV data.
  - S5: Uses CGAN-based modeling to increase hourly wind/PV output data.
  - S6: Constructs a Wasserstein two-stage DRO model with hard and soft constraints.
  - S7: States nonconvexity and heavy computational burden.
  - S8: Uses duality, relaxation, and Taylor linearization to transform the problem to MILP.
  - S9: Shows uncertainty handling, lower operating cost, and improved solving efficiency.

## 3. XSUEUNX5

- Title: Wasserstein Metric Based Distributionally Robust Approximate Framework for Unit Commitment
- Venue: IEEE Transactions on Power Systems, 2019
- DOI: 10.1109/TPWRS.2019.2893296
- Sentence count: 8
- Move extraction:
  - S1: Proposes a Wasserstein DRO approximate framework for UC with wind forecast error.
  - S2: Defines the ambiguity set as a Wasserstein ball around empirical distribution.
  - S3: Specifies worst-case operating cost components.
  - S4: Explains the sample-size and conservatism relationship.
  - S5: Identifies computational burden from sample-size-dependent robust counterpart.
  - S6: Proposes an upper approximation and verifies exactness conditions.
  - S7: Compares with robust and stochastic optimization to show economy-conservatism balance.
  - S8: Uses modified IEEE-118 and real 703-bus systems to show computational time reduction.

## 4. 4SBSUXML

- Title: Distributionally Robust Unit Commitment With Flexible Generation Resources Considering Renewable Energy Uncertainty
- Venue: IEEE Transactions on Power Systems, 2022
- DOI: 10.1109/TPWRS.2022.3149506
- Sentence count: 4
- Move extraction:
  - S1: Renewable penetration makes flexible generation resources important for imbalance management.
  - S2: Proposes a two-stage DRO UC framework with regular and flexible resources, allowing second-stage adjustment.
  - S3: Designs a revised integer L-shaped algorithm with lift-and-project cuts for the difficult mixed-binary model.
  - S4: Shows cost reduction through improved flexible-resource quantification.

## 5. W88TVEVZ

- Title: Wasserstein Metric Based Distributionally Robust Approximate Framework for Unit Commitment
- Venue: IEEE Transactions on Power Systems, 2019
- DOI: 10.1109/TPWRS.2019.2893296
- Note: Duplicate of `XSUEUNX5`; same abstract logic.

## 6. BYNZT364

- Title: A Two-Step Approach to Wasserstein Distributionally Robust Chance- and Security-Constrained Dispatch
- Venue: IEEE Transactions on Power Systems, 2024
- DOI: 10.1109/TPWRS.2023.3242468
- Sentence count: 12
- Move extraction:
  - S1: Considers security-constrained dispatch with contingencies and renewable generation.
  - S2: Uses joint chance constraints for renewables and reserves for mismatches.
  - S3-S6: Constructs a Wasserstein ambiguity set and imposes chance constraints for all distributions in it.
  - S7: States exact solution is nonconvex and computationally heavy.
  - S8: Introduces a two-step approximate solution.
  - S9-S10: Constructs a polyhedral uncertainty set containing enough probability mass.
  - S11: Solves a linear robust optimization over that set.
  - S12: Demonstrates scalability and robustness numerically.

## 7. 7K66NLW5

- Title: Conditional Style-Based Generative Adversarial Networks for Renewable Scenario Generation
- Venue: IEEE Transactions on Power Systems, 2023
- DOI: 10.1109/TPWRS.2022.3170992
- Sentence count: 5
- Move extraction:
  - S1: Day-ahead renewable scenario generation is important for short-term operations.
  - S2: Develops a style-based GAN plus sequence encoder for accurate day-ahead renewable scenarios.
  - S3: Uses meteorological conditions to capture diurnal and seasonal patterns.
  - S4: Validates on real wind/PV datasets at aggregation and station levels.
  - S5: Shows superiority through statistical and scheduling analysis versus benchmarks.

## 8. ZFIN98H8

- Title: Decision-Centric Uncertainty Sets for Storage Arbitrage: Integrating Estimation and Optimization
- Venue: IEEE Transactions on Power Systems, 2025
- DOI: 10.1109/TPWRS.2025.3611152
- Sentence count: 3
- Move extraction:
  - S1: Traditional uncertainty optimization separates estimation from decision-making and can be suboptimal.
  - S2: Proposes decision-centric uncertainty sets for risk-averse storage arbitrage, integrating estimation and optimization.
  - S3: Reports profitability improvement over RO and DRO while preserving risk coverage.

## 9. 7F6UKVYW

- Title: A Distributionally Robust Resilience Enhancement Strategy for Distribution Networks Considering Decision-Dependent Contingencies
- Venue: IEEE Transactions on Smart Grid, 2024
- DOI: 10.1109/TSG.2023.3310979
- Sentence count: 6
- Move extraction:
  - S1: Identifies two obstacles for resilience enhancement: DDU from hardening decisions and ambiguity from limited extreme-weather outage data.
  - S2: Develops scenario-wise decision-dependent ambiguity sets.
  - S3: Formulates a two-stage tri-level decision-dependent DRO resilience model.
  - S4: Recasts it as MILP master problem and scenario-wise subproblems for C&CG.
  - S5: Demonstrates improved out-of-sample performance over stochastic and robust counterparts.
  - S6: Quantifies value of ambiguity/distributional information for planners with different budgets and risk aversion.

## 10. 8W35SDHD

- Title: End-to-End Stochastic Predict-Then-Optimize for Cost-Efficient Water-Energy Resource Scheduling
- Venue: IEEE Transactions on Smart Grid, 2025
- DOI: 10.1109/TSG.2025.3601238
- Sentence count: 6
- Move extraction:
  - S1: Urban water systems are temporally coupled with power grids and intensify peak-hour stress.
  - S2: Develops water-energy scheduling with electricity cost prediction uncertainty.
  - S3: Proposes stochastic predict-then-optimize to align prediction distribution with optimality gap.
  - S4: Contrasts with traditional two-stage approaches by adding closed-loop feedback.
  - S5: Derives a differentiable convex upper-bound surrogate for end-to-end training.
  - S6: Shows reduced operational cost and decision regret on real-world systems.

## 11. 6IB9A59U

- Title: Distributionally Robust Joint Chance-Constrained Dispatch for Integrated Transmission-Distribution Systems via Distributed Optimization
- Venue: IEEE Transactions on Smart Grid, 2022
- DOI: 10.1109/TSG.2022.3150412
- Sentence count: 9
- Move extraction:
  - S1: Focuses on DRO dispatch for ITD systems via distributed optimization.
  - S2: Existing synchronized distributed algorithms are hard to scale and underuse resources.
  - S3: Individual chance constraints cannot robustly ensure simultaneous security.
  - S4: Presents a DR joint chance-constrained dispatch model via asynchronous decentralized optimization.
  - S5: Builds Wasserstein data-driven DRJCC models for transmission and distribution systems.
  - S6: Uses Bonferroni and CVaR approximation to obtain a tractable conic formulation.
  - S7: Proposes tailored asynchronous ADMM for star-topology ITD systems.
  - S8: Explains communication and update advantages.
  - S9: Shows effectiveness and scalability numerically.

## 12. 2B6B5829

- Title: Distributed Distributionally Robust Scheduling for Coordinated Transmission and Distribution Systems Considering Decision-Dependent Uncertainties
- Venue: IEEE Transactions on Power Systems, 2026
- DOI: 10.1109/TPWRS.2025.3599546
- Sentence count: 8
- Move extraction:
  - S1: More new energy reduces controllable generation and increases uncertainty.
  - S2: Independent TDS scheduling struggles with balance challenges.
  - S3: Proposes two-stage DRO cooperative scheduling for TDS.
  - S4: Explains boundary coupling variables create DDU during collaboration.
  - S5: Proposes a decision-dependent probability distribution set.
  - S6: Provides a framework for both DDU boundary variables and DIU source-load power.
  - S7: Combines improved ADMM with adaptive C&CG for distributed solution.
  - S8: Uses two case studies to verify advantages and necessity of considering DDU.

## 13. QJ7ZUXA6

- Title: Distributionally Robust Energy and Reserve Dispatch With Distributed Predictions of Renewable Energy
- Venue: IEEE Transactions on Power Systems, 2025
- DOI: 10.1109/TPWRS.2025.3553921
- Sentence count: 7
- Move extraction:
  - S1: Proposes DRO energy/reserve dispatch with distributed renewable predictions.
  - S2: Uses prediction information from operator and renewable sources to improve dispatch.
  - S3: Captures expectation, variance, covariance, and predictive-decision relationships to form a less conservative moment ambiguity set.
  - S4: Uses dual vertices, duality, and S-lemma to transform the model.
  - S5: Develops a two-layer iterative algorithm for dual vertices and nonlinear master problems.
  - S6: Adds acceleration strategies.
  - S7: Validates model and algorithm in three test systems.

## 14. 9AW7JDDQ

- Title: Approximately Adaptive Distributionally Robust Optimization for Energy and Reserve Dispatch
- Venue: IEEE Transactions on Sustainable Energy, 2025
- DOI: 10.1109/TSTE.2025.3532753
- Sentence count: 7
- Move extraction:
  - S1: Proposes two approximately adaptive DRO paradigms for energy/reserve dispatch with wind uncertainty.
  - S2: Defines policy-based and value-function-based approximations.
  - S3: Develops equal-probability segmentation for the wind ambiguity set.
  - S4: Decomposes distributionally robust quadratic cost constraints into piecewise constraints.
  - S5: Recasts two-stage AADROs into tractable semidefinite forms using duality and S-lemma.
  - S6: Handles dual vertex generation and bilinear terms.
  - S7: Verifies approximation efficiency and adaptability numerically.

## 15. YVQRC6TL

- Title: Early Warning of Extreme Weather-Induced N-k Contingencies Leveraging Spatio-Temporal Analysis of Historical Event Sequences
- Venue: IEEE Transactions on Power Systems, 2026
- DOI: 10.1109/TPWRS.2026.3673579
- Sentence count: 9
- Move extraction:
  - S1: Traditional N-k analysis is insufficient for extreme-weather threats to reliability and resilience.
  - S2: Existing contingency construction/screening misses simultaneous weather-induced outages.
  - S3: Reliance on short-term weather forecasts limits preventive lead time.
  - S4: Proposes early-warning framework using spatio-temporal point-process modeling of historical failure sequences.
  - S5: Uses constrained diffusion spatio-temporal point process to learn failure patterns under spatial, temporal, meteorological, and network constraints.
  - S6: Generates high-risk N-k scenarios from predicted failure distributions.
  - S7: Adds data augmentation using meteorological reanalysis and line fragility modeling.
  - S8: Evaluates on large-scale ENTSO-E test system.
  - S9: Demonstrates forecasting and proactive resilience decision support.
