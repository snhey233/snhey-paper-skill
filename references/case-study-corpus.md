# IEEE Case Study Corpus Extraction From "电网高温日"

This file records the extraction used to build `snhey-paper-case-study`. It paraphrases the numerical/case-study logic of IEEE papers and does not reproduce full copyrighted sections.

## Corpus Summary

- IEEE records found: 15
- Unique IEEE papers: 14
- Duplicate record: `XSUEUNX5` and `W88TVEVZ` are the same 2019 IEEE TPWRS Wasserstein unit commitment article.
- Target section names include Case Study, Case Studies, Numerical Simulation, Numerical Results, Results, Results and Discussion, Experiments and Results Discussion, and Illustrative Case Studies.

## Cross-Paper Case Study Pattern

Across the corpus, case studies usually include:

1. Validation purpose.
2. Test system/data description.
3. Solver/hardware/implementation settings.
4. Baseline or compared method definitions.
5. Main performance comparison.
6. Out-of-sample or robustness test.
7. Sensitivity/parameter analysis.
8. Scalability or computation-time analysis.
9. Operational insight.

The strongest case studies map experiments directly to the paper's contributions.

## 1. S7G5GGB7

- Title: Bayesian Nonparametric Two-Stage Distributionally Robust Unit Commitment Optimization: From Global Multimodality to Local Trimming-Wasserstein Ambiguity
- Venue: IEEE Transactions on Power Systems, 2024
- Target section: `V. Case Study`
- Test systems:
  - Six-bus system.
  - IEEE 118-bus system.
  - South Carolina 500-bus system for scalability and affine dispatch policy validation.
- Validation dimensions:
  - effectiveness;
  - scalability;
  - in-sample and out-of-sample performance;
  - comparison with state-of-the-art methods;
  - affine dispatch policy effectiveness.
- Baselines:
  - adaptive robust optimization;
  - DRO variants such as mixture-DRO or state-of-the-art methods;
  - other competing uncertainty-handling methods.
- Writing logic:
  - Opens by stating validation goals and systems.
  - Defines compared methods before results.
  - Uses small system for detailed interpretation.
  - Uses IEEE 118-bus and 500-bus systems for scalability.
  - Reports out-of-sample performance to prove generalization and reduced conservatism.
- Reusable lesson:
  - Use a small system to explain mechanism and larger systems to support scalability.

## 2. 664PKLSZ

- Title: Two-Stage Distributionally Robust Optimization Dispatch for Power Systems With Uncertain Small-Sample Wind and Photovoltaic Data
- Venue: IEEE Transactions on Smart Grid, 2026
- Target section: `V. Results and Discussion`
- Test systems:
  - Improved IEEE 24-node system.
  - IEEE 118-node system case analysis.
- Data/settings:
  - thermal units, cascaded hydropower, wind farms, and PV station;
  - CPLEX solver;
  - sample sizes and confidence levels varied.
- Validation dimensions:
  - cost under different sample sizes;
  - cost under different confidence levels;
  - dispatch results;
  - model-solving efficiency;
  - larger-system applicability.
- Writing logic:
  - Starts with data description and simulation setup.
  - Studies relationship between sample capacity, confidence level, and system cost.
  - Shows dispatch curves/results.
  - Extends from 24-node to 118-node case.
- Reusable lesson:
  - For small-sample DRO, case study should vary sample size and confidence level because these parameters define the uncertainty claim.

## 3. XSUEUNX5

- Title: Wasserstein Metric Based Distributionally Robust Approximate Framework for Unit Commitment
- Venue: IEEE Transactions on Power Systems, 2019
- Target section: `V. Numerical Simulation`
- Test systems:
  - Modified IEEE 118-bus system.
  - Real 703-bus system.
- Data/settings:
  - thermal generators and wind farms;
  - unit data from public test data;
  - wind data from TenneT;
  - Monte Carlo simulation.
- Validation dimensions:
  - optimal objective value vs simulated cost;
  - sample-size influence;
  - comparison with robust optimization and stochastic optimization;
  - computational time reduction;
  - economy-conservatism balance.
- Writing logic:
  - Describes test systems and data before figures.
  - Uses Monte Carlo simulation to evaluate out-of-sample/simulated cost.
  - Uses both medium and real large systems to show performance and scalability.
- Reusable lesson:
  - Wasserstein approximate frameworks need both objective-quality and computation-time evidence.

## 4. 4SBSUXML

- Title: Distributionally Robust Unit Commitment With Flexible Generation Resources Considering Renewable Energy Uncertainty
- Venue: IEEE Transactions on Power Systems, 2022
- Target section: `IV. Case Study`
- Test systems:
  - 6-bus system.
  - Modified IEEE 118-bus system.
- Data/settings:
  - 6-bus system with regular thermal units, one quick-start unit, and one wind farm;
  - CAISO wind forecast-error data;
  - CPLEX;
  - LP and MBLP solved on specified CPU/RAM.
- Validation dimensions:
  - flexibility benefit;
  - comparison to traditional DRUC;
  - out-of-sample cost/risk using Monte Carlo samples;
  - algorithm convergence;
  - cut effectiveness;
  - large-system validation.
- Writing logic:
  - Begins with system and computational setting.
  - Uses small system to isolate flexible-resource benefits.
  - Uses Monte Carlo samples for out-of-sample evaluation.
  - Uses larger system to show practicality.
- Reusable lesson:
  - When modeling a new resource type, design an experiment that isolates the value of that modeling change.

## 5. BYNZT364 / H3CU3HE8

- Title: A Two-Step Approach to Wasserstein Distributionally Robust Chance- and Security-Constrained Dispatch
- Venue: IEEE Transactions on Power Systems, 2024
- Target section: `IV. Numerical Results`
- Test system:
  - Modified IEEE RTS 24-bus reference case.
- Data/settings:
  - 12 conventional generation units;
  - six wind generation units;
  - 2500 MW demand across 17 locations;
  - 45 contingencies including line and generator contingencies, with excluded disconnected case;
  - partitioned wind generators in some cases.
- Validation dimensions:
  - dispatch under renewable uncertainty and contingencies;
  - cost and violation-frequency tradeoff;
  - effect of method parameters;
  - scalability with samples/constraints.
- Writing logic:
  - Carefully describes modified RTS setup and contingency set.
  - Evaluates whether constraints are satisfied with high probability.
  - Frames results around cost vs violation frequency rather than cost alone.
- Reusable lesson:
  - Chance/security-constrained papers must report both economic cost and security/violation performance.

## 6. 7K66NLW5

- Title: Conditional Style-Based Generative Adversarial Networks for Renewable Scenario Generation
- Venue: IEEE Transactions on Power Systems, 2023
- Target section: `IV. Results`
- Datasets:
  - ELIA offshore wind/PV data in Belgium.
  - NREL data: wind farms in Washington State and PV plants in California.
- Validation dimensions:
  - wind and PV scenario generation;
  - statistical metrics;
  - comparison with three state-of-the-art scenario generation methods;
  - power-system scheduling analysis;
  - generalization to expanded datasets;
  - time efficiency.
- Writing logic:
  - Starts with data description and parameter settings.
  - Separates statistical scenario-quality analysis from downstream scheduling analysis.
  - Uses multiple data sources to show generality.
  - Evaluates both region aggregation level and distributed power station level.
- Reusable lesson:
  - Scenario generation case studies must prove both statistical realism and operational usefulness.

## 7. ZFIN98H8

- Title: Decision-Centric Uncertainty Sets for Storage Arbitrage: Integrating Estimation and Optimization
- Venue: IEEE Transactions on Power Systems, 2025
- Target section: `III. Case Study`
- Data/settings:
  - Simulated percentage forecast error samples from normal distribution;
  - inter-temporal correlation;
  - 500 samples for parameter estimation;
  - 4500 samples for actual performance evaluation;
  - Python 3.10 and CVXPY.
- Baselines:
  - stochastic optimization;
  - robust optimization;
  - distributionally robust optimization;
  - proposed decision-centric uncertainty set robust optimization.
- Validation dimensions:
  - storage arbitrage profit;
  - risk coverage;
  - sensitivity to uncertainty-set parameters;
  - comparison of decision-centric and traditional uncertainty sets.
- Writing logic:
  - Clearly defines sample split for estimation and evaluation.
  - Uses baseline methods that represent SO/RO/DRO families.
  - Reports both profitability and coverage/risk.
- Reusable lesson:
  - Decision-centric methods should be validated on decision quality and risk coverage, not estimation error alone.

## 8. 7F6UKVYW

- Title: A Distributionally Robust Resilience Enhancement Strategy for Distribution Networks Considering Decision-Dependent Contingencies
- Venue: IEEE Transactions on Smart Grid, 2024
- Target sections:
  - `V. Worst-Case Distributions and Evaluation Methods`
  - `VI. Case Studies`
- Test system:
  - IEEE 33-node distribution system.
- Validation dimensions:
  - worst-case contingency distributions;
  - stress tests under uncertainty;
  - resilience enhancement strategies;
  - weighted load shedding / uninterrupted load;
  - comparison of three cases;
  - budget and robustness-level sensitivity;
  - value of ambiguity and distributional information.
- Writing logic:
  - Introduces evaluation methods before case studies.
  - Uses stress testing to evaluate strategies under uncertain contingencies.
  - Studies hardening decisions and their consequences during hurricane periods.
  - Uses budget/risk preference analysis to provide planner guidance.
- Reusable lesson:
  - Resilience papers should include both operational performance curves and planning-value analysis.

## 9. 8W35SDHD

- Title: End-to-End Stochastic Predict-Then-Optimize for Cost-Efficient Water-Energy Resource Scheduling
- Venue: IEEE Transactions on Smart Grid, 2025
- Target section: `V. Experiments and Results Discussion`
- Test setting:
  - Real-world urban water supply district;
  - pump parameters for stations;
  - Windows computer with CPU, RAM, and GPU specified;
  - Pyomo and Gurobi.
- Validation dimensions:
  - effectiveness of SPTO;
  - forecasting model accuracy;
  - optimization model solution;
  - cost reduction;
  - decision regret / optimality gap;
  - baseline comparison.
- Writing logic:
  - Starts with experimental and implementation settings.
  - States three experiment goals: SPTO effectiveness, forecasting quality, optimization correctness.
  - Connects forecasting results to scheduling outcomes.
- Reusable lesson:
  - Predict-then-optimize experiments should evaluate forecasting and optimization jointly but keep their metrics distinct.

## 10. 6IB9A59U

- Title: Distributionally Robust Joint Chance-Constrained Dispatch for Integrated Transmission-Distribution Systems via Distributed Optimization
- Venue: IEEE Transactions on Smart Grid, 2022
- Target section: `V. Numerical Results`
- Test systems:
  - T39D3: modified IEEE 39-bus transmission system connected with one modified IEEE 33-bus distribution system.
  - T118D7: modified IEEE 118-bus transmission system connected with seven modified IEEE benchmark distribution systems.
- Data/settings:
  - risk parameters set to 5%;
  - wind output data from southeastern Australia;
  - Wasserstein 1-norm to reduce model to quadratic program;
  - MATLAB implementation;
  - asynchronous ADMM initialization details.
- Validation dimensions:
  - effectiveness of DRJCC model;
  - Wasserstein radius and out-of-sample performance;
  - cost and risk;
  - convergence residuals;
  - scalability from T39D3 to T118D7.
- Writing logic:
  - Uses two benchmark scales.
  - Reports out-of-sample cost as function of Wasserstein radius and sample size.
  - Shows primal/dual residuals to validate distributed algorithm convergence.
- Reusable lesson:
  - Distributed DRO case studies need both uncertainty-performance plots and algorithm-convergence plots.

## 11. 2B6B5829

- Title: Distributed Distributionally Robust Scheduling for Coordinated Transmission and Distribution Systems Considering Decision-Dependent Uncertainties
- Venue: IEEE Transactions on Power Systems, 2026
- Target section: `V. Case Studies`
- Test systems:
  - T30D33: IEEE 30-bus transmission system with two IEEE 33-bus distribution systems.
  - T118D33: IEEE 118-bus transmission system with five IEEE 33-bus distribution systems.
- Data/settings:
  - wind farm and PV station in transmission system;
  - WGUs, PGU, ESSs, and gas turbine in distribution systems;
  - load and renewable forecast profiles.
- Validation dimensions:
  - effectiveness of coordinated scheduling model;
  - necessity of considering DDU;
  - cost/risk comparison under different modes;
  - larger-system validation;
  - distributed algorithm performance.
- Writing logic:
  - Starts with simulation settings and topology.
  - Defines multiple modes to isolate DDU and coordination effects.
  - Uses economic results to show value of the proposed model.
- Reusable lesson:
  - For DDU coordination papers, compared modes should isolate decision-dependence, coordination, and robustness.

## 12. QJ7ZUXA6

- Title: Distributionally Robust Energy and Reserve Dispatch With Distributed Predictions of Renewable Energy
- Venue: IEEE Transactions on Power Systems, 2025
- Target sections:
  - `IV. Illustrative Case Studies`
  - `V. Case Studies in Larger-Scale Systems and Discussions`
- Test systems:
  - IEEE 39-bus system.
  - Larger-scale systems in later section.
- Data/settings:
  - 8 units and 4 wind farms;
  - 6-hour dispatch cycle;
  - 15-minute resolution and 24 periods;
  - YALMIP and MOSEK;
  - specified CPU/RAM.
- Validation dimensions:
  - comparison with decision-independent uncertainty model;
  - out-of-sample performance;
  - prediction price;
  - system regulatory capability;
  - acceleration strategy;
  - inner-layer convexification;
  - larger-scale discussions.
- Writing logic:
  - Starts with illustrative case to validate DDU model and solution method.
  - Separates model-value experiments from algorithm-value experiments.
  - Uses out-of-sample tests to assess statistical performance.
  - Uses larger systems to discuss scalability and conditions under which predictions are valuable.
- Reusable lesson:
  - When both model and algorithm are novel, design separate experiment subsections for each.

## 13. 9AW7JDDQ

- Title: Approximately Adaptive Distributionally Robust Optimization for Energy and Reserve Dispatch
- Venue: IEEE Transactions on Sustainable Energy, 2025
- Target sections:
  - `V. Illustrative Simulation in Small-Scale System`
  - `VI. Simulation in Large-Scale Systems`
- Test systems:
  - IEEE 39-node system.
  - Larger-scale systems later.
- Data/settings:
  - 8 generators and 4 wind farms;
  - 6-hour horizon from 6 PM to midnight;
  - 15-minute resolution;
  - segment number settings;
  - CPU/RAM specified.
- Validation dimensions:
  - approximation accuracy against strict ADRO;
  - approximation error of recourse cost;
  - comparison of piecewise linear policy and piecewise value function;
  - out-of-sample performance;
  - segment-number sensitivity;
  - large-scale simulation.
- Writing logic:
  - Uses small system to compare against strict ADRO where tractable.
  - Uses large system when strict ADRO is impractical.
  - Studies segment settings because segmentation is the core approximation mechanism.
- Reusable lesson:
  - Approximation papers should validate both approximation accuracy on small systems and scalability on large systems.

## 14. YVQRC6TL

- Title: Early Warning of Extreme Weather-Induced N-k Contingencies Leveraging Spatio-Temporal Analysis of Historical Event Sequences
- Venue: IEEE Transactions on Power Systems, 2026
- Target section: `VI. Case Study`
- Test system/data:
  - ENTSO-E Transmission System.
  - Real-world weather-induced failure data used to fit fragility functions.
  - Synthesized event sequences as ground truth.
  - Data from 1990-2019 for training and 2020-2023 for testing.
- Validation dimensions:
  - failure-event generation;
  - spatio-temporal-mark dependency extraction;
  - CDSTPP performance evaluation;
  - comparison with baseline event models;
  - high-risk N-k contingency early warning;
  - operational risk support.
- Writing logic:
  - Starts by describing how event data/ground truth are generated.
  - Separates model prediction performance from contingency early-warning capability.
  - Uses train/test split over historical years.
  - Evaluates temporal, spatial, and mark prediction dimensions.
- Reusable lesson:
  - Early-warning case studies should show both event-model accuracy and usefulness for generating actionable high-risk contingencies.

## Practical Synthesis Table

| Paper type | Must-have case-study evidence | Typical baselines/variants |
| --- | --- | --- |
| DRO UC/dispatch | cost, robustness, out-of-sample, sample/radius sensitivity, computation time | SO, RO, DRO, ADRO, proposed variants |
| DR chance/security dispatch | cost and violation probability/security satisfaction | scenario approach, robust/chance baselines, parameter variants |
| Flexible-resource UC | flexibility benefit, out-of-sample cost, algorithm convergence | traditional DRUC, no-flexibility variant |
| Scenario generation | statistical scenario quality and downstream scheduling value | GAN/statistical scenario generators |
| Predict-then-optimize | forecast quality plus decision regret/cost | forecast-then-optimize, stochastic baseline |
| ITD/TDS distributed dispatch | cost/risk plus convergence/scalability | centralized/synchronous/DIU/no-DDU modes |
| Resilience under EWE | load restoration/risk under worst-case events plus budget sensitivity | stochastic, robust, no-ambiguity, no-DDU strategies |
| Approximate adaptive DRO | approximation error plus large-scale solvability | strict ADRO, linear policy, piecewise variants |
| Early-warning event model | temporal/spatial/mark metrics plus N-k scenario utility | point-process/diffusion/baseline event models |

