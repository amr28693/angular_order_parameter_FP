# Angular Order Parameter for Drift–Diffusion Dynamics

This repository accompanies the paper:

**“An Angular Order Parameter for Drift–Diffusion Systems from the Fokker–Planck Operator”**  
Anderson M. Rodriguez

It provides a minimal, transparent implementation of a generator-level coordinate
that characterizes the local balance between deterministic drift and stochastic diffusion
in stochastic dynamical systems.

The code is intended to be both inspectable and reusable.


## This repository demonstrates:

- **Generator-level estimation** of drift and diffusion from time series data
- Construction of a **bounded angular order parameter**
  \[
  \theta(t) = \arctan\!\left(\frac{\sigma(t)}{|\mu(t)|}\right)
  \]
  which quantifies the local drift–diffusion balance
- Validation on:
  - a canonical **Ornstein–Uhlenbeck** process (with known analytic generator),
  - a **nonlinear bistable** system,
  - **COVID-NET** weekly hospitalization rates (as a real-world, high-variance example)

The analysis operates at the level of the **Fokker–Planck generator**, not on
trajectory statistics or predictive models.

---

## Note on Inference and Scope: This repository does not:

- introduce a new stochastic model,
- perform forecasting or inference,
- attempt change-point detection,
- optimize predictive accuracy.

The goal is descriptive and geometric: **to provide a coordinate on stochastic dynamics**
that is invariant, bounded, and comparable across systems.

---

## Repository structure

- **Notebook(s)**  
  Contain complete, runnable analyses:
  - OU benchmark and drift recovery
  - Computation of θ(t) from local increments
  - Summary tables and plots
  - COVID-NET demonstration

- **Code cells**  
  Are intentionally explicit and minimally abstracted so that each step can be read,
  audited, or modified without hidden machinery.

---

## Notes on reproducibility and COVID-NET

COVID-NET data are obtained from the CDC’s public surveillance feed
(data.cdc.gov, asset `6jg4-xsqq`).

Because this is a live surveillance dataset, numerical values may change if the
notebook is re-run at a later date due to retrospective data updates.

The results reported in the associated manuscript correspond to COVID-NET data
**through the week ending January 17, 2026**.  
This temporal truncation is documented in the paper.

Some notebooks are retained for **inspection and correspondence with the manuscript**
and are not intended to be re-run verbatim for exact numerical reproduction.

---

## Dependencies

The code uses standard scientific Python tooling:

- `numpy`
- `pandas`
- `matplotlib`
- `requests` (only required for live COVID-NET access)

All analyses were developed and run in a standard Jupyter Notebook environment.

---

## How to use this repo

If you want to:

- **Understand the method:** → read the notebook top to bottom.
- **Reproduce the manuscript logic:** → inspect the “OU benchmark” and θ summary sections.
- **Experiment with new systems:** → replace the input time series and re-run the estimator.
- **Apply the idea elsewhere:** → treat the code as a reference implementation.

## Conceptual takeaway

Even highly noisy systems possess structured dynamics at the level of their stochastic
generators. By working directly at that level, the angular order parameter θ provides a
compact, invariant descriptor of stochastic regime that is independent of scale,
parameterization, or domain.


## License

This repository is released under the MIT License.
You are free to use, modify, and redistribute the code with attribution.
See the `LICENSE` file for full details.

MIT License

Copyright (c) 2026 Anderson M. Rodriguez


