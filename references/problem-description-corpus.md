# IEEE Problem Description Corpus Extraction From "电网高温日"

This file records the extraction used to build `snhey-paper-problem-description`. It paraphrases the problem-description/model-formulation logic and does not reproduce full copyrighted sections.

## Corpus Summary

- IEEE records found: 15
- Unique IEEE papers: 14
- Duplicate record: `XSUEUNX5` and `W88TVEVZ` are the same 2019 IEEE TPWRS Wasserstein unit commitment article.
- Target section names vary: Problem Formulation, Model Formulation, Problem Statement, Formulation and Methodology, Preliminary Knowledge, Mathematical Modelling, Energy and Reserve Dispatch, and Coordinated Optimization Scheduling Model.
- Extraction principle: classify by rhetorical function rather than by exact heading.

## Cross-Paper Problem Description Pattern

Across the corpus, problem-description sections usually perform these functions:

1. State the modeled system and operational task.
2. Define planning timeline and decision stages.
3. Introduce sets, indices, parameters, variables, and uncertain quantities.
4. Describe how uncertainty enters system operation.
5. State objective function and its cost/risk components.
6. Group constraints by engineering meaning.
7. Provide a compact formulation or prepare the next methodology section.

The strongest sections do not dump equations. They alternate between engineering interpretation and mathematical expression.

## 1. S7G5GGB7

- Title: Bayesian Nonparametric Two-Stage Distributionally Robust Unit Commitment Optimization: From Global Multimodality to Local Trimming-Wasserstein Ambiguity
- Venue: IEEE Transactions on Power Systems, 2024
- Target section: `II. Model Formulation`
- Problem-description logic:
  - Presents a two-stage UC model with energy storage and carbon capture.
  - Identifies wind farms as renewable sources and wind forecast error as the uncertainty.
  - Separates first-stage decisions: unit on/off, startup/shutdown, adjustment capacity, battery charge/discharge status, charging/discharging plans.
  - Separates second-stage adaptive decisions: thermal generation dispatch and carbon capture facility dispatch after wind uncertainty realization.
  - Represents wind realization as forecast plus forecast error.
  - Uses affine dispatch policies to adapt generation and carbon capture decisions to aggregate wind forecast error.
  - Builds the physical UC formulation before introducing the later BN-TSDRO framework.
- Reusable lesson:
  - For complex two-stage UC, begin by narrating stage decisions and uncertainty realization before introducing ambiguity sets or solution methods.

## 2. 664PKLSZ

- Title: Two-Stage Distributionally Robust Optimization Dispatch for Power Systems With Uncertain Small-Sample Wind and Photovoltaic Data
- Venue: IEEE Transactions on Smart Grid, 2026
- Target sections: `II. Two-Stage DRO Framework for Extreme Weather Conditions`; `III. Mathematical Modelling`
- Problem-description logic:
  - Frames the study in three parts: small-sample data modeling, two-stage DRO construction, and transformation/solution.
  - Describes the two-stage model:
    - First stage includes startup, shutdown, reserve, and operating costs of generators.
    - Second stage minimizes expected compensation cost for wind/PV forecast errors using thermal units.
    - Stages are coupled by affine constraints and proportionality factors.
  - Mathematical modeling section then builds wind/PV output models and data-augmentation logic.
  - Nonlinearities are acknowledged before later transformation.
- Reusable lesson:
  - When data augmentation and DRO both matter, first define the workflow architecture, then define the physical/uncertain output model.

## 3. XSUEUNX5

- Title: Wasserstein Metric Based Distributionally Robust Approximate Framework for Unit Commitment
- Venue: IEEE Transactions on Power Systems, 2019
- Target sections: `II. Construction of Ambiguity Set and Uncertainty Set`; `III. Formulation of the Robust Unit Commitment Model`
- Problem-description logic:
  - Defines Wasserstein ambiguity set and a data-driven uncertainty set before the UC robust formulation.
  - States the proposed model as a data-driven DRO framework.
  - Decision vector includes unit commitment, thermal generation, reserve capacity, and adjustment factor.
  - Random variable represents wind uncertainty following an unknown distribution in the ambiguity set.
  - Objective combines deterministic scheduling cost and worst-case expected recourse/adjustment cost.
  - First presents a basic formulation, then develops tractable approximation in later parts.
- Reusable lesson:
  - For Wasserstein DRO papers, the problem description may need an ambiguity-set construction section before the full optimization model.

## 4. 4SBSUXML

- Title: Distributionally Robust Unit Commitment With Flexible Generation Resources Considering Renewable Energy Uncertainty
- Venue: IEEE Transactions on Power Systems, 2022
- Target section: `II. Problem Formulation`
- Problem-description logic:
  - Formulates improved DRUC based on a two-stage DRO framework.
  - First-stage decisions: UC decisions for regular units.
  - Second-stage decisions: UC decisions for flexible generation resources and economic dispatch decisions for all units.
  - Contrasts the formulation with traditional two-stage stochastic programming: renewable distribution is ambiguous and lies in a confidence set built from historical data.
  - Objective minimizes worst-case expected total cost.
  - Includes confidence set construction.
  - Ends with an abstract compact formulation for algorithmic development.
- Reusable lesson:
  - If the novelty is decision-stage placement, explicitly contrast which decisions are first-stage versus second-stage and why.

## 5. BYNZT364 / H3CU3HE8

- Title: A Two-Step Approach to Wasserstein Distributionally Robust Chance- and Security-Constrained Dispatch
- Venue: IEEE Transactions on Power Systems, 2024
- Target section: `II. Problem Statement`
- Problem-description logic:
  - Models dispatch with renewables and contingencies as a two-stage decision process.
  - First stage: generator set points and reserve capacities.
  - Two reserve categories are distinguished:
    - reserves for imbalances caused by renewable uncertainty;
    - reserves for contingencies/failures.
  - Event between stages: realization of renewable generation and network contingency.
  - Second stage: corrective decisions after the event.
  - Formulates chance/security constraints and prepares a distributionally robust version.
  - States assumptions about timing and contingency realization.
- Reusable lesson:
  - For security-constrained dispatch, problem description must carefully distinguish uncertainty reserves from contingency reserves.

## 6. 7K66NLW5

- Title: Conditional Style-Based Generative Adversarial Networks for Renewable Scenario Generation
- Venue: IEEE Transactions on Power Systems, 2023
- Target section: `II. Problem Formulation`
- Problem-description logic:
  - Defines scenario generation as learning how impact factors drive stochastic renewable power characteristics.
  - Treats each day as a sample containing actual renewable profile and point forecast profile.
  - Defines daily actual profile, forecast profile, and historical sample window.
  - Uses forecasting perspective rather than optimization decision stages.
  - Establishes the input/output structure for the later conditional StyleGAN and sequence encoder.
  - Links generated scenarios to possible realizations of renewable power.
- Reusable lesson:
  - For ML scenario generation, problem description should define samples, profiles, conditions, and target generated trajectories before model architecture.

## 7. ZFIN98H8

- Title: Decision-Centric Uncertainty Sets for Storage Arbitrage: Integrating Estimation and Optimization
- Venue: IEEE Transactions on Power Systems, 2025
- Target section: `II. Formulation and Methodology`, subsection `Energy Storage Arbitrage Model`
- Problem-description logic:
  - Models a storage operator participating in the day-ahead electricity market as a price-taker.
  - Decision variables include charging power, discharging power, net operating power, and stored energy.
  - Objective expresses electricity-market arbitrage cost/profit.
  - Constraints define charging/discharging limits, storage energy dynamics, energy bounds, and terminal condition.
  - Notes simultaneous charging and discharging is naturally avoided because of losses.
  - Later subsections introduce risk-averse policy and decision-centric uncertainty sets.
- Reusable lesson:
  - For compact IEEE letters, the problem description can be short, but every storage variable and dynamic constraint must be interpretable.

## 8. 7F6UKVYW

- Title: A Distributionally Robust Resilience Enhancement Strategy for Distribution Networks Considering Decision-Dependent Contingencies
- Venue: IEEE Transactions on Smart Grid, 2024
- Target sections: `II. Scenario-Wise Decision-Dependent Ambiguity Sets for Contingencies`; `III. DD-DRRE Model`
- Problem-description logic:
  - Begins with assumptions to focus the problem.
  - Constructs scenario-wise decision-dependent ambiguity sets for contingency distributions.
  - Models extreme-weather scenarios and maps dynamic propagation/intensity information into ambiguity sets.
  - Defines decision-dependent failure probability functions through fragility analysis.
  - Explains three fragility-estimation challenges: decision-dependence, stochastic hurricane intensity, and estimation errors.
  - Later formulates a two-stage tri-level resilience enhancement model with hardening, DER allocation, and reconfiguration outputs.
- Reusable lesson:
  - For resilience under extreme weather, uncertainty-set construction is part of problem description because it defines what the contingency distribution means.

## 9. 8W35SDHD

- Title: End-to-End Stochastic Predict-Then-Optimize for Cost-Efficient Water-Energy Resource Scheduling
- Venue: IEEE Transactions on Smart Grid, 2025
- Target sections: `II. Problem Formulation`; `III. Integrated Water-Energy Scheduling Model`
- Problem-description logic:
  - States the coupled peak-demand problem between water systems and power grids.
  - Describes the real urban water district: service area, residents, nodes, pipes, pumping stations, reservoirs, and treatment tanks.
  - Identifies electricity costs for water pumps as a major operational component.
  - Then separates model into energy-side and water-side components.
  - Energy-side describes electricity consumption/cost response.
  - Water-side describes hydraulic and operational constraints.
  - Sets up the later stochastic predict-then-optimize framework.
- Reusable lesson:
  - For cross-domain grid-coupled systems, problem description must first convince readers what the physical subsystem is and how it loads the grid.

## 10. 6IB9A59U

- Title: Distributionally Robust Joint Chance-Constrained Dispatch for Integrated Transmission-Distribution Systems via Distributed Optimization
- Venue: IEEE Transactions on Smart Grid, 2022
- Target sections: `I.D Preliminaries`; `II. Separable Formulation of ITD Systems`
- Problem-description logic:
  - Uses preliminaries to define DRO concepts and ambiguity-set logic before system formulation.
  - Then formulates ITD systems in a separable way.
  - Describes decentralized operation structure for ITD systems.
  - Separates transmission-system and distribution-system local models.
  - Defines coupling through boundary variables and local communications.
  - Establishes a form suitable for asynchronous ADMM and joint chance-constrained DRO.
- Reusable lesson:
  - For distributed ITD papers, problem description must make separability and coupling visible before discussing the distributed algorithm.

## 11. 2B6B5829

- Title: Distributed Distributionally Robust Scheduling for Coordinated Transmission and Distribution Systems Considering Decision-Dependent Uncertainties
- Venue: IEEE Transactions on Power Systems, 2026
- Target section: `II. Coordinated Optimization Scheduling Model for Transmission and Distribution`
- Problem-description logic:
  - Models transmission and distribution systems connected through transformers/tie lines.
  - States the goal: minimize total operating cost of TDS including loss costs.
  - Defines boundary variables and power-flow constraints of tie lines.
  - Develops transmission-system scheduling model and distribution-system scheduling model separately.
  - Builds a local coupling model as the coordination bridge.
  - Prepares the next section's DRO model considering DDU and DIU.
- Reusable lesson:
  - For TDS coordination, start from physical coupling, then give subsystem models, then define local coupling constraints.

## 12. QJ7ZUXA6

- Title: Distributionally Robust Energy and Reserve Dispatch With Distributed Predictions of Renewable Energy
- Venue: IEEE Transactions on Power Systems, 2025
- Target section: `II. Energy and Reserve Dispatch With Decision-Dependent Uncertainty`
- Problem-description logic:
  - Formulates energy and reserve dispatch as a two-stage optimization problem.
  - First stage: look-ahead prescheduling and here-and-now decisions, including base outputs and reserves.
  - Second stage: wait-and-see regulation after renewable fluctuations are observed.
  - Introduces improved prediction using information from system operator and renewable energy sources.
  - Shows how prediction affects expectation, variance, covariance, and uncertainty.
  - Upgrades dispatch with decision-dependent uncertainty.
  - Prepares solution section by making DDU explicit.
- Reusable lesson:
  - For predictive DDU dispatch, problem description must show how prediction decisions change the uncertainty representation.

## 13. 9AW7JDDQ

- Title: Approximately Adaptive Distributionally Robust Optimization for Energy and Reserve Dispatch
- Venue: IEEE Transactions on Sustainable Energy, 2025
- Target section: `II. Distributionally Robust Energy and Reserve Dispatch`
- Problem-description logic:
  - Aligns the proposed energy/reserve dispatch with intraday dispatch and reserve-market frameworks.
  - Defines a classical two-stage dispatch problem with wind uncertainty.
  - First stage: predetermines reserves and base outputs of generators/wind farms.
  - Second stage: regulates real-time outputs within reserves according to available wind power.
  - Formulates a robust/DRO cost constraint and wind ambiguity set.
  - Uses this formulation as the baseline for later piecewise linear policy and value-function approximations.
- Reusable lesson:
  - For approximate adaptive DRO, the original strict/adaptive problem must be clearly defined before approximation is introduced.

## 14. YVQRC6TL

- Title: Early Warning of Extreme Weather-Induced N-k Contingencies Leveraging Spatio-Temporal Analysis of Historical Event Sequences
- Venue: IEEE Transactions on Power Systems, 2026
- Target section: `II. Preliminary Knowledge`
- Problem-description logic:
  - Does not start with an optimization formulation; instead defines preliminary stochastic tools.
  - Introduces marked spatio-temporal point process as the representation of outage events with temporal, spatial, and mark attributes.
  - Defines fragility function as the mapping from external weather stress intensity to component failure probability.
  - Lists environmental variables for different weather hazards such as lightning, wind, icing, and wildfire.
  - These definitions set up the later constrained diffusion STPP model and high-risk N-k scenario generation.
- Reusable lesson:
  - For event-learning early-warning papers, preliminary knowledge is the problem description: it defines event objects, marks, weather covariates, and failure probability before the model.

## Practical Synthesis Table

| Paper type | Problem-description center | Must define clearly |
| --- | --- | --- |
| Two-stage UC/dispatch | Stage sequence and recourse | first-stage decisions, uncertainty realization, second-stage decisions, cost components |
| Wasserstein/DRO | Random variable and ambiguity | samples, empirical distribution, ambiguity set, worst-case expectation |
| DR chance/security dispatch | Event timing and reserves | renewable realization, contingency realization, reserve categories, chance/security constraints |
| Flexible-resource UC | Stage placement of binary decisions | regular-unit UC, flexible-unit UC, second-stage mixed-binary recourse |
| Scenario generation | Data sample and target trajectory | actual profile, forecast profile, condition variables, generated scenarios |
| Storage arbitrage | Device dynamics and market role | price-taker assumption, charge/discharge variables, energy balance, profit/cost |
| Resilience under EWE | Failure probability and decisions | hardening, DER allocation, fragility curves, weather scenarios, contingency ambiguity |
| Water-energy scheduling | Coupled physical subsystem | pumps, reservoirs, treatment tanks, energy cost, hydraulic constraints |
| ITD/TDS coordination | Subsystem separability and coupling | transmission model, distribution model, boundary variables, tie-line constraints |
| Extreme-weather early warning | Event process and fragility | time/location/mark, weather variables, failure probability, N-k scenario generation |

