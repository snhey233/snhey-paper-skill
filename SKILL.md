---
name: snhey-paper-skill
description: Comprehensive IEEE-style academic paper writing skill distilled from the user's Zotero IEEE power-system paper collection. Use for writing, diagnosing, restructuring, or polishing power systems/smart grid papers, especially abstracts, introductions, notation/nomenclature, problem descriptions, solution design/methodology, case studies, numerical experiments, DRO/robust/stochastic optimization papers, unit commitment, dispatch, transmission-distribution coordination, renewable uncertainty, extreme-weather contingency, resilience, scenario generation, and prediction-then-optimization. Trigger on snhey论文写作, IEEE论文写作, 电力系统论文写作, 摘要, 引言, 符号表, 问题描述, 方案设计, 方法部分, 算例分析, case study, or paper skill.
---

# SNHEY Paper Skill

Use this skill as the main writing assistant for IEEE-style power-system optimization papers. It bundles six detailed writing modules distilled from the user's Zotero collection "电网高温日".

## Module Router

Load only the reference file needed for the user's task:

- **Abstract writing**: read `references/abstract.md`.
  - Use for 摘要, abstract, abstract polishing, IEEE摘要, DRO摘要, 调度摘要.
  - Evidence file: `references/abstract-corpus.md`.

- **Introduction writing**: read `references/introduction.md`.
  - Use for 引言, Introduction, literature gap, contribution bullets, IEEE引言.
  - Evidence file: `references/introduction-corpus.md`.

- **Notation and variable-symbol system**: read `references/notation.md`.
  - Use for 变量符号, 符号表, nomenclature, indices and sets, parameters, decision variables, DRO符号体系.
  - Evidence file: `references/notation-corpus.md`.

- **Problem description / model formulation**: read `references/problem-description.md`.
  - Use for 问题描述, 问题建模, model formulation, system model, mathematical modeling.
  - Evidence file: `references/problem-description-corpus.md`.

- **Solution design / methodology**: read `references/solution-design.md`.
  - Use for 方案设计, 问题解决, 核心方法, methodology, proposed method, reformulation, algorithm design.
  - Evidence file: `references/solution-design-corpus.md`.

- **Case study / numerical results**: read `references/case-study.md`.
  - Use for 算例分析, case study, numerical results, experiments, simulation, out-of-sample, sensitivity analysis.
  - Evidence file: `references/case-study-corpus.md`.

If the user asks for a complete paper section plan, use the modules in this order:

1. `notation.md`
2. `abstract.md`
3. `introduction.md`
4. `problem-description.md`
5. `solution-design.md`
6. `case-study.md`

If the user asks to revise a draft, first identify which paper section it belongs to, then load the matching module. If a draft spans multiple sections, load only the modules needed for those sections.

## Global Writing Logic

The full IEEE-style paper argument should form this chain:

```text
System pressure
-> Literature gap
-> Clean notation
-> Operational problem formulation
-> Technical solution design
-> Numerical validation
-> Abstract summary
```

Each section has a different job:

- **Notation** makes the model readable.
- **Abstract** compresses the full story into problem, method, tractability, and validation.
- **Introduction** proves the research gap and positions the paper.
- **Problem description** translates engineering operation into variables, uncertainty, objective, and constraints.
- **Solution design** explains how the hard problem becomes solvable.
- **Case study** proves effectiveness, robustness, scalability, and operational value.

## Default IEEE Paper Expectations

For this user's power-system/DRO writing tasks, assume the paper should usually show:

- a concrete power-system pressure such as renewable uncertainty, extreme weather, small samples, DDU, risk, or coordination;
- a literature gap stated as a mechanism, not merely "few studies";
- a notation system that separates sets, parameters, uncertainty, decisions, and algorithmic symbols;
- a two-stage or structured problem description with clear first-stage and recourse logic when applicable;
- a solution section that states the original difficulty before introducing duality, S-lemma, ADMM, C&CG, MILP/conic reformulation, GAN, diffusion, or other tools;
- case studies with baselines, out-of-sample/robustness tests, sensitivity analysis, and computation/scalability evidence when claimed.

## Output Discipline

When writing new content:

- Ask for missing technical facts only if they cannot be reasonably left as placeholders.
- Use placeholders for unknown numerical results, datasets, equations, or citations rather than inventing them.
- Preserve the user's technical claims.
- Make every paragraph perform a rhetorical function.
- Prefer IEEE-style precise terms over generic praise: use "out-of-sample performance", "conservatism", "ambiguity set", "recourse decision", "violation frequency", "scalability", and "tractable reformulation" when appropriate.

When diagnosing content:

- Provide a move map.
- Identify missing technical or rhetorical moves.
- Suggest concrete paragraph-level revisions.
- Flag unsupported claims, especially novelty, robustness, scalability, and numerical superiority.

When polishing:

- Improve logic before language.
- Keep terminology consistent with the chosen module.
- Do not turn technical writing into vague marketing prose.

