# Neural Operator Learning for PDE-Based Workload Dynamics in Space–Air–Ground Computing Systems

This repository contains the code, notebooks, figures, and report source for a course project on neural operator learning for PDE-based workload prediction.

## Project overview

In this project, I model workload evolution in a space–air–ground computing system as a diffusion–reaction partial differential equation (PDE). The goal is to learn the solution operator of this PDE so that future workload fields can be predicted without repeatedly running a numerical solver.

I explored several model families:

- MLP as a simple baseline
- DeepONet as an initial operator-learning approach
- Fourier Neural Operator (FNO) as the main model
- Physics-informed FNO with an added PDE residual loss

## Main findings

- FNO is much better suited than vanilla DeepONet for this regular-grid, diffusion-dominated PDE problem.
- On clean simulated data, FNO achieves highly accurate one-step prediction and stable multi-step rollout.
- FNO also shows meaningful generalization under parameter/source shifts and zero-shot transfer from 32×32 to 64×64 grids.
- Physics-informed loss provides only marginal gains on clean data, but gives clearer improvements under limited and noisy supervision.

## Repository structure

```text
neural-operator-workload-pde/
├── README.md
├── requirements.txt
├── notebooks/
│   ├── fno_physics_noisydata.ipynb
│   └── deeponet_baseline.ipynb
├── report/
│   ├── final_report.pdf
│   └── figures/
