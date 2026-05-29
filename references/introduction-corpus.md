# IEEE Introduction Corpus Extraction From "电网高温日"

This file records the Introduction-section extraction used to build `snhey-paper-introduction`. It does not reproduce full copyrighted Introduction text. Instead, it provides paper-by-paper rhetorical move maps and writing-logic summaries.

## Corpus Summary

- IEEE records found: 15
- Unique IEEE papers: 14
- Duplicate record: `XSUEUNX5` and `W88TVEVZ` are the same 2019 IEEE TPWRS Wasserstein unit commitment article.
- Full-text Introduction sections were available through Zotero indexing for the IEEE PDFs. The `BYNZT364` item had no child attachment, but its same-paper top-level PDF attachment `H3CU3HE8` was readable.

## Cross-Paper Introduction Pattern

The Introductions generally follow this path:

1. System transition or external pressure.
2. Operational task made difficult by uncertainty/risk/coordination.
3. Broad method families.
4. Focused technical branch.
5. Specific literature gap.
6. Proposed model/framework/algorithm.
7. Explicit contribution list.
8. Paper organization.

The main difference from an abstract is that the Introduction spends much more effort on literature taxonomy and gap justification. A good Introduction proves that the proposed contribution is necessary, not merely new.

## 1. S7G5GGB7

- Title: Bayesian Nonparametric Two-Stage Distributionally Robust Unit Commitment Optimization: From Global Multimodality to Local Trimming-Wasserstein Ambiguity
- Venue: IEEE Transactions on Power Systems, 2024
- Introduction length in extracted text: about 9.4k characters
- Main writing logic:
  - Starts from high renewable penetration and the need for data-driven decision-making in power-system operation.
  - Narrows to two-stage UC under uncertainty.
  - Reviews stochastic programming, robust optimization, and DRO as uncertainty-handling families.
  - Focuses on ambiguity-set construction and the limitation of existing DRO methods in capturing heterogeneous global-local distributional features.
  - Identifies conservatism as the consequence of inadequate distribution characterization.
  - Proposes a Bayesian nonparametric two-stage DRO framework.
  - Contribution list:
    - Unifies Bayesian nonparametric analysis with TSDRO for UC.
    - Constructs a mixture ambiguity set through a divide-and-conquer scheme and trimming-Wasserstein logic.
    - Reformulates the BN-TSDRO problem as an MILP using duality and SAA, with an algorithm for prescribed precision.
    - Notes generic recourse applicability beyond the specific UC model.
  - Ends with section organization.
- Reusable lesson:
  - For advanced DRO papers, the Introduction should explain why a standard ambiguity set is not expressive enough before presenting a new ambiguity construction.

## 2. 664PKLSZ

- Title: Two-Stage Distributionally Robust Optimization Dispatch for Power Systems With Uncertain Small-Sample Wind and Photovoltaic Data
- Venue: IEEE Transactions on Smart Grid, 2026
- Introduction length in extracted text: about 4.5k characters
- Main writing logic:
  - Opens with carbon goals, new power systems, and high wind/PV penetration.
  - Connects frequent extreme meteorological phenomena to supply guarantee and dispatch safety.
  - Identifies small-sample wind/PV data as the practical data bottleneck.
  - Reviews data generation and uncertainty modeling approaches.
  - Makes the gap: small-sample uncertainty is hard to characterize and prediction errors remain large.
  - Proposes a two-stage DRO dispatch strategy combining CGAN-based data generation with Wasserstein DRO.
  - Explains computational handling through duality, relaxation, MILP transformation, and Taylor linearization.
  - Validates through numerical examples focused on uncertainty handling, cost reduction, and efficiency.
- Reusable lesson:
  - When the data problem is the main novelty, the Introduction should make the scarcity and reliability of data part of the central argument, not a side note.

## 3. XSUEUNX5

- Title: Wasserstein Metric Based Distributionally Robust Approximate Framework for Unit Commitment
- Venue: IEEE Transactions on Power Systems, 2019
- Introduction length in extracted text: about 7.4k characters
- Main writing logic:
  - Opens with wind penetration and operation risks from forecast errors.
  - Reviews uncertainty optimization for UC: stochastic, robust, and DRO.
  - Explains the appeal of Wasserstein ambiguity: data-driven, less reliant on exact distribution assumptions.
  - Identifies the computational burden of Wasserstein robust counterparts as sample size grows.
  - Proposes WDRA as an approximate tractable framework.
  - Contribution list:
    - Develops a Wasserstein-metric DRO UC model.
    - Proposes a strong-duality-based approximate framework reducing constraints from sample-size-dependent to constant-size.
    - Verifies exactness conditions and shows optimality is not lost in simulations.
    - Demonstrates computational efficiency on IEEE-118 and real 703-bus systems.
- Reusable lesson:
  - A computation-focused Introduction should first sell the modeling family, then show why its exact form blocks practical use.

## 4. 4SBSUXML

- Title: Distributionally Robust Unit Commitment With Flexible Generation Resources Considering Renewable Energy Uncertainty
- Venue: IEEE Transactions on Power Systems, 2022
- Introduction length in extracted text: about 5.7k characters
- Main writing logic:
  - Opens with increasing wind/solar penetration and intermittent renewable output.
  - Introduces flexible generation resources, such as quick-start units, as practical balancing tools.
  - Reviews UC models and flexible-resource modeling.
  - Identifies that conventional DRUC models usually handle continuous recourse, while flexible resources introduce mixed-binary second-stage decisions.
  - Discusses why traditional separation algorithms do not directly apply.
  - Proposes a two-stage DRUC framework with regular and flexible generation resources.
  - Develops a revised integer L-shaped algorithm with lift-and-project cuts.
  - Shows the modeling value of flexible-resource quantification in reducing cost.
- Reusable lesson:
  - When the novelty is a better operational representation, the gap should be framed as "existing models put the wrong decisions in the wrong stage or wrong variable type."

## 5. BYNZT364 / H3CU3HE8

- Title: A Two-Step Approach to Wasserstein Distributionally Robust Chance- and Security-Constrained Dispatch
- Venue: IEEE Transactions on Power Systems, 2024
- Introduction length in extracted text: about 13.0k characters
- Main writing logic:
  - Opens with renewable-driven changes, production uncertainty, and vulnerability under component failures.
  - Narrows to security-constrained dispatch with renewable uncertainty and N-1 security.
  - Reviews stochastic security-constrained dispatch and chance-constrained formulations.
  - Discusses scenario approaches and sample-based chance constraints.
  - Introduces distributionally robust optimization as a response to scarce, corrupted, or non-identically sampled data.
  - Proposes a Wasserstein DR approach for dispatch with N-1 security and renewable chance constraints.
  - Reviews related works in a clearly marked "Related Works" subsection.
  - Develops a two-step scalable approximation: construct an uncertainty set with enough mass, then solve a robust linear problem.
  - Highlights tunable tradeoff between cost and violation frequency.
  - Ends with a concise paper organization paragraph.
- Reusable lesson:
  - For theory-heavy chance-constrained papers, a subsectioned Introduction can work well: motivation first, related works second, then contribution/organization.

## 6. 7K66NLW5

- Title: Conditional Style-Based Generative Adversarial Networks for Renewable Scenario Generation
- Venue: IEEE Transactions on Power Systems, 2023
- Introduction length in extracted text: about 15.9k characters
- Main writing logic:
  - Opens with fossil-fuel depletion, environmental concerns, and renewable deployment.
  - Narrows to renewable intermittency/volatility and short-term operation uncertainty.
  - Establishes day-ahead scenario generation as essential for scheduling and risk-aware operation.
  - Reviews statistical and machine-learning scenario generation approaches.
  - Focuses on limitations in capturing spatial-temporal dynamics, diurnal patterns, seasonality, and controllable scenario styles.
  - Introduces meteorological conditioning and style-based GAN logic.
  - Contribution list:
    - Designs a style-based time-series generative model with meteorological conditions.
    - Develops a deep sequence encoder to infer day-ahead patterns and generate scenarios.
    - Validates on real wind and PV datasets with statistical and scheduling metrics.
  - Ends with organization.
- Reusable lesson:
  - For ML-in-power papers, the Introduction must connect model architecture features to power-system scenario qualities, not only to ML novelty.

## 7. ZFIN98H8

- Title: Decision-Centric Uncertainty Sets for Storage Arbitrage: Integrating Estimation and Optimization
- Venue: IEEE Transactions on Power Systems, 2025
- Introduction length in extracted text: about 2.6k characters
- Main writing logic:
  - Opens with intermittent renewable penetration and storage's role in balancing supply and demand.
  - Narrows to price forecasts for storage arbitrage and profitability.
  - Reviews stochastic optimization, robust optimization, and DRO for risk-averse decisions.
  - Identifies the key limitation: traditional uncertainty optimization separates estimation from decision-making.
  - Proposes decision-centric uncertainty sets integrating estimation and optimization.
  - Emphasizes decision-centric gradient and statistically valid size calibration.
  - Gives a concise numerical value claim in the abstract/letter style.
- Reusable lesson:
  - For IEEE letters, the Introduction can be much shorter but still needs a sharp gap: "estimation and optimization are separated."

## 8. 7F6UKVYW

- Title: A Distributionally Robust Resilience Enhancement Strategy for Distribution Networks Considering Decision-Dependent Contingencies
- Venue: IEEE Transactions on Smart Grid, 2024
- Introduction length in extracted text: about 8.3k characters
- Main writing logic:
  - Opens with climate change and increasing extreme weather events.
  - Uses outage statistics and economic loss to establish resilience stakes.
  - Reviews distribution-network resilience enhancement: hardening, DER allocation, reconfiguration.
  - Introduces EWE-induced contingencies and limited outage information.
  - Identifies two linked obstacles: DDU caused by line-hardening decisions and distributional ambiguity from limited data.
  - Proposes scenario-wise decision-dependent ambiguity sets.
  - Contribution list:
    - Simultaneously models ambiguity and DDU of EWE-induced contingencies.
    - Constructs a two-stage tri-level decision-dependent DRO resilience enhancement model.
    - Recasts the model as an MILP master problem and scenario-wise subproblems using duality/linearization.
    - Quantifies values of ambiguity and distributional information for budgets/risk aversion.
- Reusable lesson:
  - In resilience papers, concrete event/statistical evidence helps justify why uncertainty modeling must change.

## 9. 8W35SDHD

- Title: End-to-End Stochastic Predict-Then-Optimize for Cost-Efficient Water-Energy Resource Scheduling
- Venue: IEEE Transactions on Smart Grid, 2025
- Introduction length in extracted text: about 7.2k characters
- Main writing logic:
  - Opens with peak demand management and flexible uncertain loads.
  - Introduces urban water supply as a large controllable electricity consumer.
  - Connects electricity price uncertainty to water-energy scheduling.
  - Reviews water-energy scheduling and forecasting/optimization approaches.
  - Identifies separation between probabilistic forecasting and downstream scheduling as the key limitation.
  - Proposes stochastic predict-then-optimize (SPTO), embedding predicted distributions into scheduling via decision-focused learning.
  - Contribution list:
    - Builds a whole-process water-energy scheduling model with hydraulic constraints.
    - Introduces learning-based optimization using price distributions rather than point estimates.
    - Derives a differentiable surrogate for regret-based objectives.
    - Demonstrates cost and decision-regret reductions.
- Reusable lesson:
  - For cross-domain grid-coupled scheduling, the Introduction must first justify why the non-power subsystem is a grid-relevant operational resource.

## 10. 6IB9A59U

- Title: Distributionally Robust Joint Chance-Constrained Dispatch for Integrated Transmission-Distribution Systems via Distributed Optimization
- Venue: IEEE Transactions on Smart Grid, 2022
- Introduction length in extracted text: about 15.4k characters
- Main writing logic:
  - Uses subsectioned Introduction: "Motivation and Background" plus related technical development.
  - Opens with active distribution grids and the rise of ITD coordination.
  - Explains why excluding active distribution grids causes conservative or suboptimal operation.
  - Reviews centralized and distributed ITD dispatch.
  - Identifies synchronization as a scalability bottleneck under subsystem heterogeneity.
  - Reviews chance constraints and notes individual chance constraints do not ensure simultaneous security.
  - Proposes DR joint chance-constrained dispatch via asynchronous decentralized optimization.
  - Contribution list:
    - Tailors asynchronous ADMM for star-topology ITD systems and subsystem heterogeneity.
    - Builds Wasserstein-based DRJCC models for transmission and distribution systems.
    - Uses Bonferroni and CVaR approximation for tractable conic formulation.
    - Shows local communication and asynchronous updates.
- Reusable lesson:
  - For distributed optimization papers, the Introduction should explain the system topology and ownership/computation reason for decentralization.

## 11. 2B6B5829

- Title: Distributed Distributionally Robust Scheduling for Coordinated Transmission and Distribution Systems Considering Decision-Dependent Uncertainties
- Venue: IEEE Transactions on Power Systems, 2026
- Introduction length in extracted text: about 10.1k characters
- Main writing logic:
  - Opens with distributed generation/storage increasing operational flexibility and interaction between transmission and distribution systems.
  - Critiques traditional top-down scheduling and independent scheduling.
  - Reviews coordinated TDS scheduling and DRO approaches.
  - Introduces DDU in boundary coupling variables: scheduling decisions affect uncertainty ranges.
  - Identifies the combined modeling and solution gap for DDU in coordinated scheduling.
  - Contribution list:
    - Proposes two-stage DRO day-ahead coordinated scheduling across TDS with multiple tie-line coordination constraints.
    - Addresses both boundary-variable DDU and source/load DIU.
    - Proposes a decision-dependent probability distribution set.
    - Combines improved ADMM and adaptive C&CG for distributed solution.
  - Ends with validation through two case studies.
- Reusable lesson:
  - When the gap involves DDU, the Introduction must explain exactly which decision changes which uncertainty.

## 12. QJ7ZUXA6

- Title: Distributionally Robust Energy and Reserve Dispatch With Distributed Predictions of Renewable Energy
- Venue: IEEE Transactions on Power Systems, 2025
- Introduction length in extracted text: about 8.5k characters
- Main writing logic:
  - Opens with renewable energy becoming a main power supply and requiring reserves for balance.
  - Establishes energy/reserve dispatch as the operational task.
  - Reviews uncertainty management and renewable prediction in dispatch.
  - Introduces distributed predictions from both system operator and renewable sources.
  - Identifies that prior uncertainty models do not fully exploit relationships among prediction, expectation, variance, covariance, and decisions.
  - Uses a comparison table to position the paper against literature.
  - Proposes a less conservative DRO energy/reserve dispatch with predictive decision-dependent uncertainty.
  - Develops dual-vertex relaxation, duality/S-lemma transformation, two-layer iterative solution, and acceleration strategies.
- Reusable lesson:
  - A comparison table can strengthen an Introduction when the gap is subtle and spans several modeling dimensions.

## 13. 9AW7JDDQ

- Title: Approximately Adaptive Distributionally Robust Optimization for Energy and Reserve Dispatch
- Venue: IEEE Transactions on Sustainable Energy, 2025
- Introduction length in extracted text: about 8.9k characters
- Main writing logic:
  - Opens with diversified and clean energy systems and large-scale wind deployment.
  - Connects wind uncertainty to reserve requirements in energy/reserve dispatch.
  - Reviews robust, stochastic, DRO, and adaptive optimization approaches.
  - Identifies strict adaptive DRO as powerful but computationally difficult.
  - Observes problem structure that allows approximation through segmentation.
  - Extends prior segmentation to piecewise linear policy and piecewise value function for nonlinear convex recourse.
  - Contribution list:
    - Proposes two approximately adaptive DRO paradigms.
    - Develops equal-probability segmentation of ambiguity sets.
    - Recasts formulations into tractable semidefinite forms using duality and S-lemma.
    - Handles dual vertices and bilinear terms with appropriate algorithms.
  - Ends with numerical verification of approximation efficiency and adaptability.
- Reusable lesson:
  - Approximation-method papers must justify why exact adaptivity is valuable but impractical, then show why the approximation preserves useful structure.

## 14. YVQRC6TL

- Title: Early Warning of Extreme Weather-Induced N-k Contingencies Leveraging Spatio-Temporal Analysis of Historical Event Sequences
- Venue: IEEE Transactions on Power Systems, 2026
- Introduction length in extracted text: about 4.4k characters
- Main writing logic:
  - Opens with reliability/resilience as critical infrastructure stakes.
  - Narrows to escalating extreme weather and uses a concrete recent typhoon event as motivation.
  - Critiques traditional N-k contingency analysis under weather-induced simultaneous failures.
  - Identifies two limitations: failure-pattern modeling and insufficient preventive lead time from short-term forecasts.
  - Proposes an early-warning framework based on spatio-temporal point-process modeling of historical failure-event sequences.
  - Introduces constrained diffusion spatio-temporal point process to learn failure patterns under spatial, temporal, meteorological, and network constraints.
  - Adds high-risk N-k scenario generation and data augmentation with meteorological reanalysis and fragility modeling.
  - Validates on large-scale ENTSO-E system.
- Reusable lesson:
  - For early-warning papers, the Introduction must distinguish event-sequence learning from ordinary short-term weather forecasting.

## Practical Synthesis

Use the following mapping when drafting new Introductions:

| Paper type | Best opening | Literature focus | Gap hinge | Contribution focus |
| --- | --- | --- | --- | --- |
| DRO UC/dispatch | Renewable uncertainty and reserve/cost risk | SP/RO/DRO, ambiguity sets | Standard ambiguity set is too conservative or not expressive | New ambiguity set + tractable reformulation |
| DR chance/security dispatch | Contingencies plus renewable uncertainty | Security dispatch, chance constraints, DRCC | Exact DRCC is nonconvex/heavy or joint security is missing | Two-step approximation or tractable DRCC |
| Resilience/extreme weather | EWE outage/risk statistics or event example | Resilience planning, hardening, contingency models | Limited data, DDU, simultaneous failures, lead time | Decision-dependent or spatio-temporal risk model |
| Scenario generation | Day-ahead operations need scenarios | Statistical/ML/GAN scenario generation | Poor spatial-temporal/conditional pattern capture | Conditional generative model + scheduling validation |
| Predict-then-optimize | Forecast uncertainty affects downstream decisions | Forecasting, stochastic scheduling, decision-focused learning | Forecasting and optimization are separated | End-to-end or decision-centric framework |
| ITD/TDS distributed scheduling | Active distribution and coupling | Centralized/distributed coordination, ADMM | Synchronization, heterogeneity, boundary DDU | Asynchronous/distributed algorithm + uncertainty model |

