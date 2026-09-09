---
title: "Optimizing Initialization in Graph Dynamics: from Ferromagnetism to Opinion Consensus"
# Only the year is verified; January 1 is a sorting key, not a publication date.
date: 2025-01-01
authors: "**Marek Jankola**"
venue: "Master’s thesis, Charles University, Faculty of Mathematics and Physics"
paperurl: https://dspace.cuni.cz/bitstream/handle/20.500.11956/202499/120518985.pdf?sequence=1
pdf: https://dspace.cuni.cz/bitstream/handle/20.500.11956/202499/120518985.pdf?sequence=1
# Title, institution and year: supplied Google Scholar screenshot.
# Original abstract and PDF link supplied by Marek.
---

The analytical study of non-equilibrium properties of dynamical systems is notoriously hard. The backtracking dynamical cavity method (BDCM) is a step forward in understanding such systems by characterizing the properties of attractors on large sparse graphs. In particular, it has allowed us to study majority dynamics, answering questions such as “What is the minimal initial number of +1 nodes needed to end up in a +1 global consensus?”. In this thesis, we solve the BDCM equations iteratively on full instances of random regular and Erdős–Rényi graphs, which gives us lower bounds on the minimal fraction of initial +1 nodes necessary for consensus. Furthermore, we aim to find these initial conditions. To this end, we introduce a novel algorithm that we coin history passing reinforcement (HPR). It is an adaptation of the belief propagation reinforcement algorithm to the BDCM framework. We find that our algorithm outperforms standard Monte Carlo based methods, and comes close to the theoretical limits predicted by BDCM. Notably, we find initial conditions where the final consensus is the original opinion of the minority. While we implement HPR in the setting of majority dynamics on random regular graphs, the algorithm generalizes naturally to broader classes of dynamics and network topologies. Finally, we explore the implications of one-step replica symmetry breaking (1RSB) for the algorithmic performance of HPR. We find that the onset of the dynamical 1RSB phase corresponds to the emergence of an algorithmically hard regime for HPR in this setting.
