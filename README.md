# Genetic Algorithms for Job Scheduling: Binary vs. Permutation Representations

Comparative analysis of two chromosome representations, **Binary** and **Permutation**, applied to the Job Scheduling Problem (JSP) using Genetic Algorithms. The study evaluates how each encoding impacts solution quality (makespan), convergence behaviour, and scalability across problem dimensions.

> Developed as part of the **Nature-Inspired Artificial Intelligence** course at the University of Coimbra, 2025/2026.

---

## Problem Definition

The JSP consists of allocating a set of **N jobs** to **M machines**, where each job follows a fixed sequence of operations across machines. The objective is to minimise the **makespan**, i.e., the total completion time of all jobs. This is an NP-hard combinatorial optimisation problem, which motivates the use of metaheuristics.

---

## Representations

**Binary:** each job receives a binary priority value (0 or 1). The genotype is decoded into a job permutation by sorting jobs according to their assigned priority. This indirect encoding introduces ties when multiple jobs share the same priority, which limits the search space.

**Permutation:** the genotype directly encodes the job execution order as a permutation of job indices. No decoding step is required since the genotype is the phenotype, preserving the combinatorial structure of the problem.

---

## Methodology

The experimental pipeline is structured in three phases, each isolating individual components of the GA configuration.

**Phase 1: Parameter Calibration.** Grid search over 25 combinations of crossover rate (Pc) and mutation rate (Pm) per representation, with 5 executions per configuration. Includes a follow-up sensitivity analysis on population size (N ∈ [10, 450]).

**Phase 2: Mechanism Analysis.** Combinatorial evaluation of selection methods (Tournament, Roulette-Wheel) and variation operators (One-Point/Uniform Crossover for Binary; Order Crossover, Swap/Scramble Mutation for Permutation), with parameters fixed from Phase 1.

**Phase 3: Scalability Testing.** Nine scenarios varying N ∈ {20, 50, 100} and M ∈ {5, 10, 20} to assess robustness under increasing problem complexity.

All results, statistical analysis, and discussion are available in the [technical report](RelatorioIAIN.pdf).


---

## How to Run

```bash
git clone https://github.com/tomasgferreira06/MIA_IAIN_TP1.git
cd MIA_IAIN_TP1

pip install numpy matplotlib seaborn pandas

jupyter notebook P1-GA-Job-Scheduling-students.ipynb
```

---

## Authors

- **Tomás Ferreira** · 2025168427
- **Eduardo Pereira** · 2021233890
