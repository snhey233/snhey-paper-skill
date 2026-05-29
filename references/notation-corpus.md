# IEEE Notation Corpus Extraction From "电网高温日"

This file records the extraction used to build `snhey-paper-notation`. It paraphrases notation and nomenclature design patterns and does not reproduce full copyrighted symbol tables.

## Corpus Summary

- IEEE records found: 15
- Unique IEEE papers: 14
- Duplicate record: `XSUEUNX5` and `W88TVEVZ` are the same 2019 IEEE TPWRS Wasserstein unit commitment article.
- Most optimization papers include an upfront `NOMENCLATURE` block.
- Some method or ML-oriented papers define symbols inline in the problem/method sections rather than through a full symbol table.

## Cross-Paper Notation Pattern

The common ordering is:

1. Functions/operators when needed.
2. Indices and sets.
3. Parameters/constants.
4. Uncertain quantities/random variables.
5. Decision variables.
6. Algorithmic/auxiliary variables.

The most consistent papers group symbols by mathematical role and physical object, not by order of appearance only.

## 1. S7G5GGB7

- Title: Bayesian Nonparametric Two-Stage Distributionally Robust Unit Commitment Optimization
- Venue: IEEE Transactions on Power Systems, 2024
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Sets and indices: generators, wind farms, loads, batteries, transmission lines, time.
  - Parameters: startup/shutdown cost, ramping cost, load shedding cost, wind curtailment cost, adjustment cost, start/shutdown time, output limits, ramp limits, battery efficiency/capacity, carbon-capture parameters, emission quota.
  - Variables: commitment/startup/shutdown, adjustment capacity, charge/discharge status, battery plans, recourse generation, carbon capture power.
- Lesson:
  - For a rich UC model, a front nomenclature table is essential because multiple subsystems are modeled together.

## 2. 664PKLSZ

- Title: Two-Stage DRO Dispatch for Power Systems With Uncertain Small-Sample Wind and Photovoltaic Data
- Venue: IEEE Transactions on Smart Grid, 2026
- Notation style: mostly inline definitions in modeling sections.
- Main symbol needs:
  - wind/PV output data;
  - prediction errors;
  - CGAN generator/discriminator variables;
  - Wasserstein ambiguity set;
  - first-stage and second-stage dispatch costs;
  - hard and soft constraints.
- Lesson:
  - When a paper combines deep learning and optimization, notation should separate ML symbols from dispatch optimization symbols.

## 3. XSUEUNX5

- Title: Wasserstein Metric Based Distributionally Robust Approximate Framework for Unit Commitment
- Venue: IEEE Transactions on Power Systems, 2019
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Sets: thermal generators, wind farms, ambiguity set, standardized ambiguity set, set of probability measures.
  - Parameters: load demand, generator output limits, wind forecast output, costs and reserve prices.
  - Deterministic variables: thermal unit base output, reserve capacity, commitment variables.
  - Uncertainty quantities: wind power uncertainty/random variables.
- Lesson:
  - DRO notation should explicitly distinguish ambiguity set, uncertainty set, random variables, and deterministic decisions.

## 4. 4SBSUXML

- Title: Distributionally Robust Unit Commitment With Flexible Generation Resources
- Venue: IEEE Transactions on Power Systems, 2022
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Indices and sets: time periods, buses, units/transmission lines, piecewise approximation, renewable resources, loads, regular/flexible/all generation resources.
  - Parameters and variables are organized for regular and flexible resources.
- Lesson:
  - Use set partitions such as regular vs flexible resources to make the modeling novelty visible in notation.

## 5. BYNZT364 / H3CU3HE8

- Title: A Two-Step Approach to Wasserstein DR Chance- and Security-Constrained Dispatch
- Venue: IEEE Transactions on Power Systems, 2024
- Notation style: no large front nomenclature detected; symbols are defined around problem statement and compact form.
- Main symbol needs:
  - generation and reserve decisions;
  - renewable uncertainty deviation;
  - contingency set;
  - chance-constraint indices;
  - Wasserstein ambiguity set;
  - compact vectors/matrices for robust reformulation.
- Lesson:
  - For theory-heavy compact reformulation papers, inline definitions must carefully map compact symbols back to physical dispatch objects.

## 6. 7K66NLW5

- Title: Conditional Style-Based GANs for Renewable Scenario Generation
- Venue: IEEE Transactions on Power Systems, 2023
- Notation style: inline notation in problem formulation and model architecture.
- Main symbol needs:
  - day/sample index;
  - time step;
  - actual renewable profile;
  - forecast profile;
  - meteorological condition;
  - latent vectors;
  - generator/discriminator/encoder;
  - generated scenarios.
- Lesson:
  - Scenario-generation notation should separate data profiles, conditions, latent variables, and generated outputs.

## 7. ZFIN98H8

- Title: Decision-Centric Uncertainty Sets for Storage Arbitrage
- Venue: IEEE Transactions on Power Systems, 2025
- Notation style: compact inline definitions in formulation.
- Main symbol needs:
  - market price;
  - charging/discharging power;
  - net operating power;
  - stored energy;
  - charge/discharge efficiency;
  - energy bounds;
  - uncertainty-set parameters.
- Lesson:
  - IEEE letters may not need a full nomenclature table, but storage dynamics require clean definitions immediately after equations.

## 8. 7F6UKVYW

- Title: A DRO Resilience Enhancement Strategy for Distribution Networks Considering Decision-Dependent Contingencies
- Venue: IEEE Transactions on Smart Grid, 2024
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Indices: hardening measures, nodes/lines, time periods, hurricane tracks, geographical zones.
  - Sets: hardening measures, track scenarios, time periods, distribution lines, nodes, substations, zones, switches, poles, conductor wires.
  - Parameters: demand priority, line capacity, DER output, voltage bounds, restoration coefficients.
  - Variables: hardening decisions, DER allocation, reconfiguration, load restoration, contingency variables.
- Lesson:
  - Extreme-weather resilience notation must combine power-network, geography, weather, and infrastructure-failure symbols.

## 9. 8W35SDHD

- Title: End-to-End Stochastic Predict-Then-Optimize for Cost-Efficient Water-Energy Resource Scheduling
- Venue: IEEE Transactions on Smart Grid, 2025
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Indices: reservoirs, pumps, filtering tanks, distribution network nodes, time steps.
  - Sets: all pumps, distribution pumps, pumps by station, filtering tanks, nodes, time.
  - Parameters: reference flow rates, water-level change, deviation margins, evaporation, predicted electricity price, time lag, head-loss coefficients, demand.
  - Variables: pump schedules, flows, tank/reservoir levels, energy consumption.
- Lesson:
  - Cross-domain grid-coupled papers need notation for the non-power system, but still follow IEEE grouping discipline.

## 10. 6IB9A59U

- Title: Distributionally Robust Joint Chance-Constrained Dispatch for ITD Systems
- Venue: IEEE Transactions on Smart Grid, 2022
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Functions: indicator function, expectation, probability measure.
  - Sets: parent/children nodes, controllable units in DS, distribution lines/nodes/renewables, DS set, boundary nodes, transmission generators/lines/nodes/renewables.
  - Parameters: risk parameters, renewable forecasts, reserve capacities, network limits.
  - Variables: local dispatch decisions, coupling variables, ADMM variables.
- Lesson:
  - Distributed ITD papers should distinguish TS and DS symbols using superscripts or subsystem-indexed sets.

## 11. 2B6B5829

- Title: Distributed DRO Scheduling for Coordinated Transmission and Distribution Systems Considering DDU
- Venue: IEEE Transactions on Power Systems, 2026
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Indices and sets.
  - Parameters and constants.
  - Decision variables.
  - Special emphasis on TDS power-source operating costs, boundary variables, tie-line constraints, DDU/DIU-related symbols.
- Lesson:
  - DDU coordination papers need notation that clearly separates boundary variables from internal source/load uncertainties.

## 12. QJ7ZUXA6

- Title: Distributionally Robust Energy and Reserve Dispatch With Distributed Predictions
- Venue: IEEE Transactions on Power Systems, 2025
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Indices and sets: time, generating units, renewable sources, nodes, branches, dual vertices/outer-layer iterations, inner-layer iterations, uncertainty set.
  - Parameters: prediction values, moment parameters, reserve/generation/network limits.
  - Decision variables: base outputs, reserves, predictive decisions, recourse decisions.
  - Algorithmic variables: dual vertices and iteration indices.
- Lesson:
  - When algorithmic iteration symbols appear in the nomenclature, separate them from physical indices and define them explicitly.

## 13. 9AW7JDDQ

- Title: Approximately Adaptive DRO for Energy and Reserve Dispatch
- Venue: IEEE Transactions on Sustainable Energy, 2025
- Notation style: upfront `NOMENCLATURE`
- Main groups:
  - Indices and sets: generators, wind farms, demanders, branches, time, distribution constraints, segmented uncertainty subsets, second-stage dual vertices, slack/non-slack generators.
  - Parameters and variables for energy/reserve dispatch.
  - Approximation-specific notation: segment index, dual vertices, piecewise policy/value-function terms.
- Lesson:
  - Approximation papers should include symbols for both the original dispatch model and the approximation machinery.

## 14. YVQRC6TL

- Title: Early Warning of Extreme Weather-Induced N-k Contingencies
- Venue: IEEE Transactions on Power Systems, 2026
- Notation style: mostly inline definitions in preliminary knowledge and model sections.
- Main symbol needs:
  - event time;
  - spatial location;
  - mark/component;
  - event history;
  - weather/environmental variables;
  - fragility function;
  - diffusion/noising variables;
  - generated failure-event sequence;
  - N-k contingency scenarios.
- Lesson:
  - Event-learning papers should define stochastic-process symbols close to the preliminary theory instead of forcing all symbols into a power-system nomenclature table.

## Practical Synthesis Table

| Paper type | Best notation organization | Highest conflict risk |
| --- | --- | --- |
| UC/dispatch | sets -> parameters -> uncertainty -> decisions | `P` for power/probability, `u` for unit status/uncertainty |
| Wasserstein DRO | uncertainty support -> distribution -> ambiguity set -> samples | random variable vs distribution vs ambiguity set |
| Flexible-resource UC | regular/flexible/all resource sets | `G` partitions and second-stage binaries |
| ITD/TDS coordination | transmission symbols, distribution symbols, boundary symbols | same index for DS, scenario, and iteration |
| Resilience/EWE | network objects, weather objects, hardening/restoration variables | line, zone, track, scenario overload |
| Scenario generation | sample/profile/condition/latent/output | actual vs forecast vs generated profiles |
| Storage arbitrage | price, charge/discharge, energy dynamics | price symbol vs dual variable |
| Water-energy scheduling | water-system objects plus energy price/pump decisions | non-power hydraulic symbols undefined to power readers |
| Early warning | event process, fragility, weather, generated contingencies | time/location/mark symbols mixed with power-system indices |

