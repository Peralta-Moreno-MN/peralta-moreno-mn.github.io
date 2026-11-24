---
layout: page
title: The fdMD framework
permalink: /research/fdmd/
provisional: true
# background_image: /assets/img/covers/research.jpg
---

<p class="gallery-breadcrumb"><a href="{{ '/research/' | relative_url }}">&larr; Research</a></p>

Before you can turn a small molecule into a drug, you need to answer two questions: **where**
does it bind to its target, and **how** does it sit there? Get those wrong, and everything built
on top of them is wrong too.

**Fragment dissolved Molecular Dynamics (fdMD)** answers them with a simple but powerful idea:
instead of asking a computer to guess one pose in one pocket, let many copies of the molecule
explore the whole protein at once, and see where they choose to stay.

## How it works

In an fdMD simulation, the target protein is solvated in water together with **many copies of
the same fragment**, which are then free to move. The copies explore the whole surface and
compete for it, so a single simulation yields as many ligand–receptor trajectories as there are
copies in the box. One technical detail makes this possible: a repulsive Lennard-Jones term is
added to the central atom of the fragments, which stops them from clumping together, one of the
classic problems of multiple-copy simulations.

This has two advantages over docking a single molecule into a single pocket:

- **It doesn't need to know the binding site in advance.** Pockets emerge from the simulation,
  including cryptic ones that only open up when the protein moves.
- **The protein is flexible and the solvent is there**, so what you see is closer to what
  actually happens in solution.

## From fdMD to fdGaMD

Molecular dynamics is limited by time: some motions are simply too slow to see within a
reasonable simulation. Fragments can get trapped in a local minimum, find a spurious site, or
reach the right pocket but in the wrong orientation.

The work published in *JCIM* introduces **Gaussian accelerated molecular dynamics (GaMD)** into
the framework, giving **fdGaMD**. GaMD adds an adaptive boost to the potential energy, smoothing
the energy landscape so the system crosses barriers that conventional dynamics would rarely
cross, without biasing it along a predefined coordinate.

The protocol is semiautomatic and runs at least **four independent replicates of 400 ns** each.
The global simulation is then stripped into individual ligand–receptor trajectories, and each
candidate site is characterised with a set of descriptors: **residence time, interaction energy,
binding free energy (MM-GBSA), solvent accessible surface area and number of hydrogen bonds**.
With those, the candidate sites are ranked.

It was validated on **12 protein–fragment complexes with known crystal structures**.

## What came out of it

- **fdGaMD reproduces the experimental binding mode**, not just the binding site. That was the
  main goal: going from "it binds here" to "it binds here, like this".
- **It speeds up binding site detection** and makes the choice between candidates clearer,
  because the descriptors separate the favourable site from the rest.
- **Weak fragments tend to be discarded** by the boost. Counterintuitively, that is useful: in a
  screening campaign it automatically focuses attention on the fragments that interact most
  strongly.
- **Enhanced sampling is not a substitute for simulation time.** One of the most interesting
  findings: capturing the native binding mode needs both *enough replicates*, so the right
  orientation is sampled, and *enough time*, so the protein can adapt to the ligand (induced
  fit). In a difficult case, the ligand reached the crystallographic site but stayed in a
  prebinding pose until it was given longer. Protocols based on many very short simulations will
  struggle with complex systems.
- **A promising route to cryptic and allosteric pockets**, precisely because the protein is
  explored so thoroughly.

An honest open question, stated in the paper: unbinding events are observed for weak fragments,
but not for ligands that have settled correctly into the experimental site. Selectively
accelerating the protein–ligand interaction is one possible direction for future development.

## Code

[**fdMD-hub**](https://github.com/Peralta-Moreno-MN/fdMD-hub) brings the original method and its
extensions together in one repository, under a BSD 3-Clause license:

- **`fdMD/`** — the original approach, from
  [DrugDesignUBUJA](https://github.com/DrugDesignUBUJA/fdMD), with its original attribution
  (copyright © 2019 Jaime Rubio Martínez).
- **`fdGaMD/`** — the Gaussian accelerated version published in *JCIM*, also available at
  [DrugDesignUBUJA/fdGaMD](https://github.com/DrugDesignUBUJA/fdGaMD).
- **`fdGaMD-ML/`** — work in progress: **machine learning to prioritise candidate sites**. A
  Random Forest classifier, trained on a benchmark of 12 ligand–protein systems and 102 candidate
  sites (14 native, 88 alternatives) and validated by leaving one whole system out at a time,
  ranks the candidates of each system instead of relying on reading every descriptor by hand. It
  is an exploratory study on a small, imbalanced dataset, and it can only rank the sites the
  simulation found: it supports the structural analysis, it does not replace it.

Simulations are run with AMBER and AmberTools.

## Publication

**Peralta-Moreno, M. N.**; Granadino-Roldán, J. M.; Santos Tomas, M.; Rubio-Martinez, J.\*
Boosting Drug Discovery: Expanding the Applicability of Fragment Dissolved Molecular Dynamics to
Accelerate Binding Mode Elucidation. *Journal of Chemical Information and Modeling* **2025**,
65 (23), 12879–12893. [doi:10.1021/acs.jcim.5c02122](https://doi.org/10.1021/acs.jcim.5c02122)
(open access)
