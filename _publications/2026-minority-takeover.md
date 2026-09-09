---
title: "Minority Takeover in Majority Dynamics: Searching for Rare Initializations via the History Passing Algorithm"
date: 2026-06-04
authors: "**Marek Jankola**, Freya Behrens, Cédric Koller, and Lenka Zdeborová"
venue: "Physical Review E"
citation_detail: "113, 064303"
paperurl: https://arxiv.org/abs/2512.16021
arxiv: https://arxiv.org/abs/2512.16021
doi: 10.1103/b8vm-fz49
# The body below is the authors' abstract from arXiv:2512.16021.
# Publications are displayed on the homepage; they do not need separate pages.
---

We investigate how much bias in the initial configuration is required to drive global agreement in synchronous, deterministic majority dynamics on large random *d*-regular graphs. Nodes take values ±1 and update their states at each discrete time step to align with the majority of their neighbors. Using the backtracking dynamical cavity method (BDCM), we estimate the minimal fraction of initial +1 nodes required to achieve a +1 consensus in *p* time steps. Our analysis predicts that for *d* ≥ 4 an initial global minority of +1 nodes is sufficient to quickly steer the entire system toward consensus on +1.

We then investigate whether such initial conditions can be determined explicitly for a given large random regular graph. To this end, we introduce a new algorithm, which we name history-passing reinforcement (HPR), designed to find such initial configurations with a minority of +1 nodes. We find, as a main result, that the HPR algorithm finds initial configurations where the minority takes over the majority for *d*-regular random graphs with *d* ≥ 4.

The HPR algorithm outperforms standard simulated annealing-based methods, but does not reach the lowest densities predicted by the BDCM. Rather, the lowest density achievable by the algorithm is near the onset of a dynamical one-step replica symmetry breaking (d1RSB) phase, which we estimate using a one-step replica symmetry breaking (1RSB) formulation of the BDCM. While we focus on the majority dynamics and random *d*-regular graphs, the algorithm can be extended to other dynamical rules and classes of sparse graphs.
