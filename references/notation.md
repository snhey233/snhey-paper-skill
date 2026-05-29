---
name: snhey-paper-notation
description: Build, diagnose, restructure, or polish IEEE-style nomenclature, notation, variable-symbol systems, indices, sets, parameters, decision variables, random variables, uncertainty symbols, and mathematical symbol tables for power systems, smart grid, unit commitment, energy dispatch, transmission-distribution coordination, resilience, extreme-weather contingency, stochastic/robust/distributionally robust optimization, scenario generation, and prediction-then-optimization papers. Use when the user asks for 变量符号, 符号表, nomenclature, notation, symbols, indices and sets, parameters, decision variables, random variables, uncertainty notation, IEEE符号表, 电力系统变量命名, DRO符号体系, or 模型符号构建.
---

# SNHEY Paper Notation

Use this skill to design or revise the variable-symbol system of an IEEE-style power-system paper. The goal is not only to make a pretty nomenclature table. The goal is to make the mathematical model readable, consistent, non-conflicting, and aligned with power-system engineering meaning.

This skill was distilled from 14 unique IEEE papers in the user's Zotero collection "电网高温日". Most papers use an upfront **NOMENCLATURE** block before the Introduction; some define symbols inside formulation sections. The corpus covers UC, dispatch, DRO, chance constraints, DDU, ITD/TDS coordination, resilience, water-energy scheduling, storage arbitrage, scenario generation, and extreme-weather early warning.

## Core Thesis

A strong IEEE notation system should let a reader answer:

1. What are the physical objects? generators, buses, lines, wind farms, loads, storage, pumps, zones, contingencies.
2. What are the sets and indices over those objects?
3. Which quantities are parameters, which are decisions, and which are uncertain/random?
4. What does each subscript/superscript mean?
5. Which symbols belong to the original physical model, and which belong to the solution method?

Bad notation makes a good model look messy. Good notation makes a complex model feel inevitable.

## Canonical IEEE Nomenclature Order

Use this order unless the target journal or existing paper structure requires otherwise:

1. **Functions and operators** if important.
   - Examples: indicator function, expectation, probability measure, norm, distance, CVaR.
2. **Indices and sets**.
3. **Parameters and constants**.
4. **Uncertain quantities / random variables**.
5. **Decision variables**.
6. **Auxiliary variables and algorithmic variables**.
7. **Acronyms** only if not already defined elsewhere.

Many IEEE papers combine indices and sets as **Indices and Sets**, then parameters, then decision variables. DRO-heavy papers often include probability distributions and ambiguity sets early.

## Build Notation From Model Layers

Do not invent symbols one by one while writing equations. Build them by layers.

### Layer 1: Physical Objects

List the physical objects first:

- time periods;
- buses/nodes;
- transmission lines/branches;
- generators/thermal units;
- wind farms and PV stations;
- loads/demand nodes;
- storage/batteries/ESSs;
- distribution systems;
- transmission systems;
- pumps/tanks/reservoirs for water-energy papers;
- weather zones/tracks/scenarios;
- contingencies/failures/events;
- scenarios/samples.

Then assign sets and indices.

Examples:

- `G, g`: set and index of generators.
- `T, t`: set and index of time periods.
- `L, l`: set and index of transmission lines.
- `W, w`: set and index of wind farms.
- `B, b`: set and index of batteries or buses. Avoid using `B` for both in the same paper.
- `K, k`: scenarios, distribution systems, or constraints. Define carefully.

### Layer 2: System Parameters

Group parameters by engineering role:

- cost parameters: startup, shutdown, fuel, reserve, curtailment, shedding, investment.
- capacity parameters: maximum/minimum output, line limits, reserve limits, storage capacity.
- dynamic parameters: ramping limits, minimum up/down time, storage efficiency, water time lag.
- network parameters: admittance, shift factors, branch limits, voltage bounds.
- uncertainty/statistical parameters: forecast value, sample, mean, covariance, radius, confidence level.
- risk parameters: chance tolerance, robustness level, risk-aversion coefficient.

Use a consistent visual convention:

- bars/underlines for upper/lower bounds;
- hats for forecasts/estimates;
- tildes for random variables or realized uncertain values;
- Greek letters for risk, probability, dual variables, and statistical quantities.

### Layer 3: Decisions By Stage

For two-stage or multi-stage optimization, classify decision variables by timing.

- first-stage / here-and-now:
  - unit commitment;
  - startup/shutdown;
  - base generation;
  - reserve procurement;
  - hardening investment;
  - DER allocation;
  - day-ahead schedule.
- second-stage / wait-and-see:
  - real-time dispatch;
  - reserve deployment;
  - load shedding;
  - renewable curtailment;
  - reconfiguration;
  - restoration;
  - recourse variables.

Use notation that reveals stage:

- `x`: compact first-stage decision.
- `y`: compact second-stage/recourse decision.
- `p_{g,t}`: base output.
- `\tilde p_{g,t}`: realized or recourse output.
- `r^+_{g,t}, r^-_{g,t}`: upward/downward reserves.
- `u_{g,t}, v_{g,t}`: commitment/startup/shutdown binary variables, if consistent with local convention.

### Layer 4: Uncertainty

Separate these concepts:

- forecast: known prediction value;
- forecast error: random deviation;
- realization: forecast plus error;
- random variable: abstract uncertain quantity;
- sample: observed historical instance;
- distribution: probability law;
- empirical distribution: sample-based distribution;
- ambiguity set: set of possible distributions;
- uncertainty set: set of possible values.

Recommended conventions:

- `\xi`: forecast error or generic uncertainty.
- `\tilde \xi`: random uncertainty when tilde convention is used.
- `\hat p`: forecasted power.
- `\tilde p`: actual/realized power.
- `P` or `\mathbb{P}`: probability distribution; avoid conflict with active power `P`.
- `\mathcal P`: ambiguity set.
- `\Xi`: uncertainty support/set.
- `\epsilon`: chance-constraint violation tolerance.
- `\rho`, `\theta`, or `\delta`: Wasserstein radius/confidence/risk parameters, but define consistently.

For DDU:

- explicitly mark decision-dependent objects, e.g. `\mathcal P(x)`, `\Xi(x)`, `\mu(x)`, `\Sigma(x)`.
- explain which decision changes the distribution or support.

### Layer 5: Solution-Method Symbols

Separate method symbols from physical-model symbols.

Method symbols include:

- dual variables;
- cut indices;
- iteration counters;
- sample indices;
- ambiguity-set radii;
- segment indices;
- dual vertices;
- ADMM multipliers;
- C&CG scenario sets;
- neural-network latent variables;
- loss functions;
- model parameters/weights.

Do not mix physical indices and algorithmic iteration indices. For example, do not use `k` for both distribution system and iteration unless the context is unmistakable.

## Naming Rules

### Sets And Indices

Use calligraphic or uppercase letters for sets:

- `\mathcal G`: generators.
- `\mathcal T`: time periods.
- `\mathcal L`: lines.
- `\mathcal N`: buses/nodes.
- `\mathcal W`: wind farms or uncertainty samples depending on context.

Use lowercase for indices:

- `g in \mathcal G`
- `t in \mathcal T`
- `l in \mathcal L`
- `i, j` for nodes or line endpoints.

For papers with many object types, prefer mnemonic sets over single-letter ambiguity:

- `\mathcal G^{T}` for transmission generators.
- `\mathcal G^{D}_k` for controllable units in distribution system `k`.
- `\mathcal N^{D}_k` for nodes in distribution system `k`.

### Parameters

Use symbols that suggest meaning:

- `C` for cost.
- `P`, `Q` for active/reactive power.
- `R` for reserve or ramping; define carefully.
- `U`, `V`, `u` for voltage or commitment only with no conflict.
- `E` for storage energy.
- `\eta` for efficiency.
- `\lambda` for price or dual variable; avoid using it for both in one section.
- `\gamma` for priority weight or risk weight.

For upper/lower bounds:

- `\overline P_g`, `\underline P_g`;
- `P_g^{\max}`, `P_g^{\min}`;
- choose one style and keep it throughout.

### Decision Variables

Use lower-case variables for dispatch decisions:

- `p`: active power.
- `q`: reactive power.
- `r`: reserve.
- `e`: storage energy, if not used for error.
- `z`: binary status, switch, or selection variable.

Use binary variables consistently:

- `u`: on/off commitment.
- `v`: startup.
- `w`: shutdown, unless `w` means wind.
- `z`: charge/discharge status, line status, hardening option, or scenario selection; define role clearly.

Avoid using the same symbol for wind and shutdown in a wind-power paper.

### Random Variables And Distributions

Use visual markers:

- `\hat{}` forecast/estimate.
- `\tilde{}` random realization.
- `\bar{}` nominal/average/upper bound only if defined.
- `\underline{}` lower bound.

For samples:

- `\xi^s` or `\xi_i` for sample `s`/`i`.
- `N` or `N_s` for number of samples.
- `\widehat{\mathbb P}_N` for empirical distribution.

For ambiguity:

- `\mathcal P`: ambiguity set.
- `\mathbb P`: an individual probability distribution.
- `\mathcal W(\cdot,\cdot)`: Wasserstein distance, if not conflicting with wind set.

## Recommended Nomenclature Template

Use this structure for a power-system optimization paper:

```text
NOMENCLATURE

Indices and Sets
\mathcal T, t       Set and index of time periods.
\mathcal N, i, j    Set and indices of buses/nodes.
\mathcal L, l       Set and index of transmission lines.
\mathcal G, g       Set and index of thermal generators.
\mathcal R, r       Set and index of renewable units.
\mathcal S, s       Set and index of scenarios/samples.

Parameters
C_g^{SU}, C_g^{SD}  Startup and shutdown costs of generator g.
\overline P_g, \underline P_g  Maximum and minimum output of generator g.
\overline F_l       Capacity limit of line l.
\hat p_{r,t}        Forecasted renewable output of unit r at time t.
\epsilon            Violation probability tolerance.

Uncertain Quantities
\xi_{r,t}           Forecast error of renewable unit r at time t.
\tilde p_{r,t}      Realized renewable output.
\mathbb P           Probability distribution of uncertainty.
\mathcal P          Ambiguity set of probability distributions.
\Xi                 Support/uncertainty set.

Decision Variables
u_{g,t}             Commitment status of generator g at time t.
v_{g,t}             Startup decision of generator g at time t.
p_{g,t}             Base active output of generator g at time t.
r^+_{g,t}, r^-_{g,t} Upward and downward reserve of generator g at time t.
y(\xi)              Recourse decision after uncertainty realization.
```

Adapt the object names to the actual paper.

## Corpus-Derived Patterns

### UC / Dispatch Papers

Common symbol groups:

- sets: generators, wind farms, loads, batteries, transmission lines, time periods.
- parameters: startup/shutdown costs, ramping costs, load shedding costs, curtailment costs, output limits, ramp limits, storage capacity, emission quota.
- variables: commitment, startup/shutdown, base output, reserve, charge/discharge, recourse generation, curtailment, load shedding.
- uncertainty: wind/PV forecast error, random renewable output, ambiguity set.

Writing lesson:

- UC notation must distinguish commitment binaries from continuous dispatch and reserve variables.

### Wasserstein DRO Papers

Common symbol groups:

- `\mathcal P`: ambiguity set.
- empirical distribution and samples.
- uncertainty support.
- random variable and standardized random variable.
- Wasserstein radius.
- worst-case expectation.

Writing lesson:

- Use different typography for active power `P` and probability distribution `\mathbb P`/ambiguity set `\mathcal P`.

### Flexible-Resource UC

Common symbol groups:

- regular generation resources;
- flexible generation resources;
- all generation resources;
- buses, lines, renewable resources, loads;
- piecewise approximation index.

Writing lesson:

- Use superscripts or set partitions to make regular and flexible resources visually distinct, e.g. `\mathcal G^r`, `\mathcal G^f`.

### Resilience / Extreme Weather

Common symbol groups:

- line hardening measures;
- nodes and directed lines;
- time periods;
- hurricane propagation tracks;
- geographical zones;
- distribution lines in each zone;
- switches, poles, conductor wires;
- demand priority weights;
- voltage and DER bounds;
- restoration variables.

Writing lesson:

- Extreme-weather notation must include both power-network objects and weather/geography objects.

### ITD / TDS Coordination

Common symbol groups:

- transmission nodes/lines/generators/renewables;
- distribution systems and their local nodes/lines/resources;
- boundary nodes;
- coupling variables;
- consensus variables;
- ADMM multipliers and residuals.

Writing lesson:

- Use superscripts `T` and `D` or subsystem index `k` consistently. Boundary variables deserve their own symbol group.

### Scenario Generation / ML Papers

Common symbol groups:

- daily sample index;
- time step;
- actual renewable profile;
- forecast profile;
- condition vector;
- latent vector;
- generator/discriminator/encoder;
- generated scenarios.

Writing lesson:

- ML notation should distinguish data samples, conditions, latent variables, and generated outputs.

### Storage / Water-Energy Papers

Storage:

- time periods;
- market prices;
- charge/discharge power;
- net power;
- stored energy;
- efficiency;
- energy bounds.

Water-energy:

- reservoirs, pumps, filtering tanks, distribution nodes, time steps;
- pump flow rates;
- tank levels;
- water demand;
- electricity price;
- time lags;
- hydraulic coefficients.

Writing lesson:

- Cross-domain papers need domain-specific notation, but the grouping should still separate indices, parameters, and decision variables.

## Inline Definition Rules

If the paper does not use a standalone nomenclature table, define symbols inline with discipline.

Use:

```text
where \(p_{g,t}\) denotes the active power output of generator \(g\) at time \(t\), and \(r^+_{g,t}\) and \(r^-_{g,t}\) denote its upward and downward reserve capacities.
```

Rules:

- Define symbols immediately after the equation where they first appear.
- Define grouped variables together.
- Do not define the same symbol differently later.
- If a symbol is used in many equations, add a small notation paragraph before the model.

## Conflict-Prevention Checklist

Before finalizing notation, check:

- Does every symbol have exactly one meaning?
- Are set symbols visually distinct from scalar parameters?
- Are probability distributions distinct from active power?
- Are forecasts, random realizations, and samples visually distinct?
- Are first-stage and second-stage variables distinguishable?
- Are transmission and distribution symbols distinguishable?
- Are physical indices and algorithmic iteration indices distinguishable?
- Are upper/lower bounds consistently marked?
- Are binary variables clearly identified?
- Are all acronyms defined before use?
- Is the same letter reused only when superscripts/subscripts make the distinction obvious?
- Are all symbols in equations either in the nomenclature table or defined inline?

## Common Failure Modes

- **P overload**: `P` is used for active power, probability distribution, and ambiguity set.
- **B overload**: `B` means bus, battery, and branch.
- **k overload**: `k` means scenario, distribution system, constraint, and iteration.
- **tilde misuse**: tilde is used for both forecast and realization.
- **hat misuse**: hat is used for both estimate and upper bound.
- **stage ambiguity**: first-stage and recourse variables look identical.
- **random/distribution confusion**: `\xi`, `P`, samples, and ambiguity set are not separated.
- **method symbols mixed with physical symbols**: dual variables or iteration counters conflict with generator or scenario indices.
- **undefined compact vectors**: `x`, `y`, and `u` appear without mapping back to physical decisions.

## Output Modes

When building notation from scratch:

1. Ask for the model's physical objects, stages, uncertainty sources, and solution method if missing.
2. Build sets/indices first.
3. Build parameters by physical subsystem.
4. Build decision variables by stage.
5. Build uncertainty and ambiguity notation.
6. Build solution-method symbols.
7. Return a clean nomenclature table and naming rationale.

When revising notation:

1. Detect overloaded symbols.
2. Standardize hats, tildes, bounds, and superscripts.
3. Separate physical-model symbols from algorithmic symbols.
4. Preserve existing equations when possible; propose minimal renaming if conflicts are severe.

When diagnosing notation:

1. Produce a symbol audit table: symbol, current meanings, conflict risk, suggested fix.
2. Identify missing symbols used in equations.
3. Suggest a reorganized nomenclature order.

