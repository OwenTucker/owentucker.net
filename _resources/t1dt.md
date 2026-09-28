---
title: Type-One Digital Twin
short_name: T1DT
order: 2
summary: >-
  Patient-specific simulation of glucose dynamics: models, tools for fitting
  them to real data, and ways to evaluate them.

# ---------------------------------------------------------------------------
# STARTER ENTRIES: well-known public resources, added as examples.
# Check each one and add or remove entries as you like.
# ---------------------------------------------------------------------------
repos:
  - name: ReplayBG
    url: https://github.com/gcappon/replay-bg
    language: MATLAB
    description: >-
      Fits a patient-specific glucose model to recorded data and replays it
      under altered therapy ("what if") scenarios.

works:
  - title: "The UVA/PADOVA Type 1 Diabetes Simulator: New Features"
    url: https://doi.org/10.1177/1932296813514502
    authors: "Chiara Dalla Man, Francesco Micheletto, Dayu Lv, Marc Breton, Boris Kovatchev, Claudio Cobelli"
    venue: "Journal of Diabetes Science and Technology"
    year: 2014
---

High-fidelity mechanistic models such as the
[UVA/Padova simulator](https://doi.org/10.1177/1932296813514502) describe the
complex glucose-insulin dynamics of T1D as a system of differential equations.
Their parameters encode an individual's physiology: how carbohydrate (CHO)
intake and insulin action drive glucose levels. Identifying those parameters
from a person's observed data gives a **digital twin (DT)**, which can be used
for retrospective analysis of treatment decisions.

Building an accurate DT is hard. Hidden states relate nonlinearly to what we
observe, and physiology varies widely between individuals.

### From MCMC to simulation-based inference

Earlier T1D digital twin methods such as
[ReplayBG](https://github.com/gcappon/replay-bg) use Markov chain Monte Carlo
(MCMC) to infer a posterior distribution over patient-specific parameters from
observed glucose and insulin dosing data. The fitted model can then be replayed
under alternative treatments, such as different insulin doses. MCMC is
computationally expensive, though: every new window of observed data needs a
fresh sampling run.

**Simulation-based inference (SBI)** scales better and has shown success in
T1D digital twinning. In **neural posterior estimation (NPE)**, a neural
network is trained on simulated parameter-CGM pairs to learn a conditional
approximation of the posterior. Once trained, it infers a patient's parameters
almost instantly. This removes MCMC's per-window cost while improving digital
twin accuracy on held-out evaluation windows.
