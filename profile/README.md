# Preferendus-IMAP-IGS

**Preference-Based Optimisation - IMAP Inter-Generational Solver (IGS) Framework**

---

## About

This is the home of **Preferendus** and it's method and solvers - a collection of preference-based optimisation solvers using the IMAP (Integrative Maximisation of Aggregated Preferences) method. The page hosts four repositories, each a distinct IGS instantiation targeting different problem classes: **IGS-GA-I**, **IGS-GA-II**, **IGS-BRKGA**, and **IGS-SI**.

Earlier work, including the original open-source **Preferendus** package and the first IMAP-IGS-GA demonstrators, can be found at [TUDelft-Odesys](https://github.com/TUDelft-Odesys).

---

## Repositories

### [`IGS-GA-I`](https://github.com/TUDelft-IMAP-IGS/IGS-GA-I)
The original IGS-GA algorithm - the foundational **Inter-Generational Solver** using a Genetic Algorithm backbone. This is a user-friendly implementation, equivalent to the original version linked to all ODESYS book examples. It integrates IMAP preference aggregation directly into standard GA survival selection.

### [`IGS-GA-II`](https://github.com/TUDelft-IMAP-IGS/IGS-GA-II)
An improvement on IGS-GA-I, built on the **NSGA-II** genetic loop (crossover, mutation, mating) but replacing non-dominated sorting and crowding distance with **IMAP affine aggregation** survival. Designed for benchmarking against reference test suites (e.g. DAS-CMOP). Supports multi-stakeholder preference models, constraint handling via the Constraint Dominance Principle (CDP), tournament and truncation selection, and an optional cross-generation archive to stabilise IMAP Z-score normalisation.

### [`IGS-BRKGA`](https://github.com/TUDelft-IMAP-IGS/IGS-BRKGA)
A **Biased Random-Key Genetic Algorithm (BRKGA)** instantiation of the IMAP-IGS framework, developed for combinatorial and constraint-heavy problems. Used as the solver for the Heterogeneous Vessel Allocation and Scheduling Problem (HVASP).

### [`IGS-SI`](https://github.com/TUDelft-IMAP-IGS/IGS-SI)
A **Swarm Intelligence (SI)** instantiation of the IMAP-IGS framework, targeting graph-based and routing optimisation problems. Implements the Preferendus method via Ant Colony Optimisation (ACO), with the same preference-aggregation interface as the GA-based solvers. Applicable to directed graph problems such as route planning and Markov-chain modelling.

---

## Framework Overview

A description of all principles of IMAP-IGS, the full terminology and formal definitions can be found at [`TUDelft-IMAP-IGS_overview.pdf`](./TUDelft-IMAP-IGS_overview.pdf).

For an overview of how IMAP design-decision optimisation relates to other optimisation methods MILP and MIP, see [`Optimisation landscape.pdf`](./Optimisation_landscape.pdf) included in this repository. How IMAP relates to the min-max optimisation method can be found in (Wolfert, 2023 - [odesys.nl](https://odesys.nl/))

[![Optimisation landscape](./Optimisation_landscape.jpg)](./Optimisation_landscape.pdf)

---

## References

- Wolfert, A.R.M. (Rogier) et al. (2023). *Open Design Systems (ODESYS)*. IOS Press
  [IOS Press Ebooks - Open Design Systems](https://doi.org/10.3233/RIDS10) (or [https://books.open.tudelft.nl/home/catalog/book/78](https://books.open.tudelft.nl/home/catalog/book/78))

- Woflert, A.R.M. (Rogier) (2026). *Unique Preference Aggregation in Design and Decision Making*. TU Delft.
  https://doi.org/10.48550/arXiv.2601.19759

- Timp, L.J.K. (Lennard), Yorke-Smith, N. (Neil), Wolfert, A.R.M. (Rogier) *Solving Highly Constrained Multi-Objective Decision Problems with Preference-Guided Metaheuristics: The IMAP-IGS Framework*
  To be published.

---

## License

This project is licensed under the **MIT License** - see the [`LICENSE`](./LICENSE) file for details.

Copyright (c) 2026 TUDelft-IMAP-IGS Contributors
