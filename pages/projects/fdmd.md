---
layout: page
title: The fdMD framework
permalink: /research/fdmd/
provisional: true
# background_image: /assets/img/covers/research.jpg
---

<p class="gallery-breadcrumb"><a href="{{ '/research/' | relative_url }}">&larr; Research</a></p>

Before you can design a drug, you need to answer two questions: **where** does a molecule bind
to its target, and **how** does it sit there? Get those wrong, and everything built on top of
them is wrong too.

**Fragment dissolved Molecular Dynamics (fdMD)** answers both with a simple but powerful idea:
instead of asking a computer to guess one pose in one pocket, let many copies of the molecule
explore the whole protein at once, and see where they choose to stay.

## How it works

In an fdMD simulation, **many copies of the same ligand or fragment are dissolved around the
target protein** and left to move freely in a molecular dynamics simulation. The copies compete
for the protein surface, and over time they gather in the places that really can accommodate
them.

This competitive, multi-copy setup has two advantages over docking a single molecule into a
single pocket:

- **It doesn't need to know the binding site in advance.** Pockets emerge from the simulation,
  including ones that are only visible when the protein moves.
- **The protein is flexible and the solvent is there**, so what you see is closer to what
  actually happens in solution.

## The framework

[**fdMD-hub**](https://github.com/Peralta-Moreno-MN/fdMD-hub) brings the original method and its
extensions together in one place:

### fdMD — the original approach

The foundation: fragment dissolved molecular dynamics for locating binding sites. The original
implementation comes from the [DrugDesignUBUJA](https://github.com/DrugDesignUBUJA) group and is
kept with its original attribution and BSD 3-Clause license.

### fdGaMD — adding enhanced sampling

Molecular dynamics is limited by time: some events are simply too slow to see. **fdGaMD**
combines fdMD with **Gaussian accelerated molecular dynamics (GaMD)**, which smooths the energy
landscape so the system explores far more in the same simulation time. The result is better
sampling, for both binding site detection and binding mode elucidation.

### fdGaMD-ML — letting the data help decide

A simulation usually proposes **several** candidate sites, each described by a set of
descriptors. When the profiles look similar, choosing between them by hand becomes slow and
subjective.

This part of the project uses **supervised machine learning** to prioritise candidates. A Random
Forest classifier, trained on a benchmark of **12 ligand–protein systems and 102 candidate sites**
(14 corresponding to the experimental site, 88 alternatives), ranks the candidates of each system
by how likely they are to be the native one.

It is validated with **leave-one-group-out cross-validation**, holding out one whole system at a
time, so no site from a test system is ever seen during training. The metric that matters is how
often the top-ranked candidate is the right one.

Two honest caveats, which are part of the method: the benchmark is small and imbalanced, and the
classifier can only rank the sites the simulation found. It is there to **support** the
structural analysis, not to replace it.

## Why it matters

Fragment-based drug discovery starts from very small molecules that bind weakly, and weak binders
are exactly the hardest case for traditional methods. Being able to locate their site and resolve
their binding mode reliably is what makes it possible to grow them into something useful.

<!-- ✏️ Add here, if you want: which targets you have applied it to, and what came out of it. -->

## Publication

**Peralta-Moreno, M. N.**; Granadino-Roldán, J. M.; Santos Tomas, M.; Rubio-Martinez, J.
Boosting Drug Discovery: Expanding the Applicability of Fragment Dissolved Molecular Dynamics to
Accelerate Binding Mode Elucidation. *Journal of Chemical Information and Modeling* **2025**,
65 (23), 12879–12893. [doi:10.1021/acs.jcim.5c02122](https://doi.org/10.1021/acs.jcim.5c02122)

## Code

[**fdMD-hub** on GitHub](https://github.com/Peralta-Moreno-MN/fdMD-hub) — BSD 3-Clause License.
The repository is being assembled and documented progressively, and each method has its own
directory with its documentation, requirements and citation instructions.

The original fdMD implementation is copyright © 2019 Jaime Rubio Martínez.
