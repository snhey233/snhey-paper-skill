# snhey-paper-skill

`snhey-paper-skill` is a Codex skill for writing IEEE-style power systems and smart grid papers. It was distilled from the IEEE papers in the user's Zotero collection on power-grid operation under extreme weather, renewable uncertainty, distributionally robust optimization, dispatch, resilience, and related topics.

The skill is designed for Chinese-speaking academic writing workflows, but the generated paper text and guidance target English IEEE-style manuscripts.

## What It Covers

This bundled skill contains six writing modules:

- **Abstract**: problem pressure, methodological contribution, tractability, and validation.
- **Introduction**: literature layering, gap construction, contribution bullets, and paper organization.
- **Notation**: IEEE-style nomenclature, indices, sets, parameters, decision variables, random variables, and ambiguity-set symbols.
- **Problem Description**: system model, decision stages, uncertainty, objective function, and constraint groups.
- **Solution Design**: proposed method, reformulation, algorithm design, approximation, and methodology writing.
- **Case Study**: test systems, baselines, out-of-sample tests, sensitivity analysis, scalability, and result interpretation.

Each module has a detailed reference file under `references/`, plus a corpus-extraction file that records the writing logic extracted from the IEEE paper set.

## Repository Structure

```text
snhey-paper-skill/
├── SKILL.md
└── references/
    ├── abstract.md
    ├── abstract-corpus.md
    ├── introduction.md
    ├── introduction-corpus.md
    ├── notation.md
    ├── notation-corpus.md
    ├── problem-description.md
    ├── problem-description-corpus.md
    ├── solution-design.md
    ├── solution-design-corpus.md
    ├── case-study.md
    └── case-study-corpus.md
```

## Installation

Copy this folder into your Codex skills directory:

```bash
~/.codex/skills/snhey-paper-skill
```

On Windows Codex Desktop, the directory may be:

```text
C:\Users\Administrator\.codex\skills\snhey-paper-skill
```

Restart or refresh Codex after installation so the skill list reloads.

## Usage Examples

Ask Codex things like:

- `用 snhey-paper-skill 帮我写 IEEE 摘要`
- `帮我诊断这段 introduction 的 gap 是否清楚`
- `帮我构建这个 DRO 调度模型的符号表`
- `帮我写 problem formulation 的文字说明`
- `帮我重构 solution methodology`
- `帮我设计 case study 的实验结构`

The top-level `SKILL.md` routes the task to the correct module and only loads detailed references when needed.

## Intended Paper Types

This skill is especially suitable for papers about:

- unit commitment and economic dispatch;
- energy and reserve dispatch;
- renewable uncertainty and forecast errors;
- stochastic, robust, and distributionally robust optimization;
- Wasserstein ambiguity sets and chance constraints;
- decision-dependent uncertainty;
- transmission-distribution coordination;
- resilience enhancement under extreme weather;
- N-k contingency early warning;
- renewable scenario generation;
- prediction-then-optimization;
- IEEE TPWRS, TSG, TSTE-style manuscripts.

## Notes

The skill provides writing structure, rhetorical logic, and section-level guidance. It does not invent experimental results, citations, theoretical guarantees, or numerical values. Unknown technical details should be left as placeholders until supplied by the author.
