# TUDelft-IMAP-IGS

**Preference-Based Optimisation — IMAP Inter-Generational Solver (IGS) Framework**

---

## About

The open-source **Preferendus** software package for preference-based optimisation — used for all IMAP demonstrators in the ODESYS book — is publicly available via the GitHub repository: https://github.com/TUDelft-Odesys.

The results of the first demonstrator presented in the associated paper (the floating wind farm) are described in Chapter 8.5 of the ODESYS book and can also be accessed through the same GitHub repository. Furthermore, an extended stochastic variant of this design–decision example is available at: https://github.com/Boskalis-python/ODYCON.

A contemporary and further extended implementation of the **Preferendus** framework, incorporating multiple **Inter-Generational Solver (IGS)** instantiations such as IGS-GA-I, IGS-GA-II, IGS-BRKGA, and IGS-SI, is available here at: https://github.com/TUDelft-IMAP-IGS.

In particular, the **IGS-BRKGA** instantiation is used for the second demonstrator (dynamic vessel allocation — AlloDyn). The corresponding results are subject to confidentiality constraints and are available upon reasonable request.

---

## Repositories

### [`IGS-GA-I`](https://github.com/TUDelft-IMAP-IGS/IGS-GA-I)
The original IGS-GA algorithm — the foundational **Inter-Generational Solver** using a Genetic Algorithm backbone. This is Kareem's user-friendly implementation, equivalent to Harold's original version linked to all ODESYS book examples. It integrates IMAP preference aggregation directly into standard GA survival selection.

### [`IGS-GA-II`](https://github.com/TUDelft-IMAP-IGS/IGS-GA-II)
An improvement on IGS-GA-I, built on the **NSGA-II** genetic loop (crossover, mutation, mating) but replacing non-dominated sorting and crowding distance with **IMAP affine aggregation** survival. Designed for benchmarking against reference test suites (e.g. DAS-CMOP). Supports multi-stakeholder preference models, constraint handling via the Constraint Dominance Principle (CDP), tournament and truncation selection, and an optional cross-generation archive to stabilise IMAP Z-score normalisation.

### [`IGS-BRKGA`](https://github.com/TUDelft-IMAP-IGS/IGS-BRKGA)
A **Biased Random-Key Genetic Algorithm (BRKGA)** instantiation of the IMAP-IGS framework, developed for combinatorial and constraint-heavy scheduling problems. Used as the solver for the AlloDyn dynamic vessel allocation demonstrator (Boskalis). Results from this demonstrator are subject to confidentiality and available upon reasonable request.

### [`IGS-SI`](https://github.com/TUDelft-IMAP-IGS/IGS-SI)
A **Swarm Intelligence (SI)** instantiation of the IMAP-IGS framework, targeting graph-based and routing optimisation problems. Implements the Preferendus method via Ant Colony Optimisation (ACO), with the same preference-aggregation interface as the GA-based solvers. Applicable to directed graph problems such as route planning and Markov-chain modelling.

---

## Framework Overview

All IGS solvers share the same **IMAP (Integrative Maximisation of Aggregated Preferences)** preference-aggregation kernel:

1. Raw objective values are converted into preference scores (0–100) via stakeholder-defined preference functions.
2. Scores are Z-score-normalised across the current candidate pool.
3. A weighted sum P\* is computed over all criteria and stakeholders.
4. P\* is min-max-scaled to [0, 100] to produce the final ranking.

Because normalisation is pool-relative, IMAP scores are generation-specific — this is a deliberate design property that drives diversity-preserving selection.

For full terminology and formal definitions, see [`TUDelft-IMAP-IGS_overview.pdf`](./TUDelft-IMAP-IGS_overview.pdf) included in this repository.

---

## References

- Wolfert, A.R.M. (Rogier) et al. (2023). *Open Design Systems (ODESYS)*. TU Delft.  
  Repository: https://github.com/TUDelft-Odesys

- Woflert, A.R.M. (Rogier) (2026). *Unique Preference Aggregation in Design and Decision Making*. TU Delft.
  https://doi.org/10.48550/arXiv.2601.19759

- Teuber et al. (2025). *ODYCON — Stochastic design-decision extension.*  
  Repository: https://github.com/Boskalis-python/ODYCON

---

## License

This project is licensed under the **MIT License** — see the [`LICENSE`](./LICENSE) file for details.

Copyright (c) 2026 TUDelft-IMAP-IGS Contributors
