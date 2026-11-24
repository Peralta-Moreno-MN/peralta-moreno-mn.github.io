---
layout: page
title: The CADD Toolbox
permalink: /tutorials/cadd-toolbox/
provisional: true
# background_image: /assets/img/covers/tutorials.jpg
---

<p class="gallery-breadcrumb"><a href="{{ '/tutorials/' | relative_url }}">&larr; Tutorials</a></p>

Computer-aided drug design (CADD) is not one method, but a whole toolbox. Which tool you pick
depends on what you know: the structure of your target, a set of active molecules, or nothing
but a question.

This page is a map of the methods used today, with what each one is good for and what to watch
out for. It will grow with links to the tutorials as I write them.

## Structure-based methods

Used when you have a 3D structure of the target (from X-ray crystallography, cryo-EM, NMR or a
predicted model).

- **Molecular docking.** Places a molecule into a binding site and scores how well it fits.
  Fast and ideal for screening large libraries, but scoring functions are approximate, so treat
  the ranking as a filter, not as a prediction of affinity.
- **Virtual screening.** Docking applied to libraries of thousands to billions of compounds, to
  select a few candidates worth testing in the lab.
- **Molecular dynamics (MD).** Simulates how a protein and its ligand move over time. It shows
  flexibility, water molecules, cryptic pockets and whether a pose is actually stable.
- **Binding free energy calculations.** MM/PBSA and MM/GBSA are fast and approximate; alchemical
  methods such as FEP and thermodynamic integration are much more accurate and much more
  expensive. The right choice depends on how many compounds you need to rank.
- **Enhanced sampling.** Metadynamics, umbrella sampling and similar methods reach events that
  plain MD would never see in a reasonable time, such as a ligand unbinding.
- **Structure-based pharmacophores.** Turn the key interactions of a binding site into a 3D
  query to search for molecules that match it.
- **Fragment-based design.** Start from very small molecules that bind weakly, then grow or link
  them into a potent compound.
- **Covalent docking.** For inhibitors that form a bond with the target, usually with a specific
  residue such as a cysteine.

## Ligand-based methods

Used when you don't have a structure, but you do know molecules that work.

- **QSAR.** Builds a model relating molecular descriptors to activity, to predict new compounds.
- **Similarity searching and fingerprints.** Looks for molecules similar to a known active one,
  on the principle that similar structures often have similar activity.
- **Ligand-based pharmacophores.** Extracts the common features of several active molecules and
  searches for new ones sharing them.
- **Shape-based screening.** Compares the 3D shape and electrostatics rather than the 2D formula,
  which helps find new chemical scaffolds.

## Quantum chemistry

- **DFT and ab initio methods.** For reaction mechanisms, covalent inhibition, metal-containing
  sites and accurate interaction energies, where force fields are not enough.
- **QM/MM.** Treats the active site quantum-mechanically and the rest of the protein classically:
  the standard approach for enzymatic reactions.

## AI and machine learning

- **Structure prediction.** AlphaFold and related tools give a model when there is no experimental
  structure. Always check the confidence scores, especially for flexible loops and side chains.
- **Scoring and affinity prediction.** Models trained to score poses or predict binding affinity.
- **Generative models.** Propose new molecules with the properties you ask for, instead of
  searching an existing library.
- **Protein design.** Tools such as RFdiffusion and ProteinMPNN design proteins that do not exist
  in nature, a field recognised with the 2024 Nobel Prize in Chemistry.

## Properties and filters

Potency is not enough: a drug also has to reach its target and be safe.

- **ADMET prediction.** Absorption, distribution, metabolism, excretion and toxicity.
- **Drug-likeness rules.** Lipinski's rule of five and similar guides. Useful filters, not laws.
- **Physicochemical properties.** Solubility, logP, pKa and permeability, which decide whether a
  good binder can ever become a medicine.

## A practical note

No method is right on its own. Docking proposes, MD checks, free energy ranks, and the lab
decides. The real skill in CADD is choosing the cheapest method that can still answer your
question, and knowing what each one can and cannot tell you.

*Tutorials on these methods are on the way. If there's one you'd like first, [let me know]({{ '/contact/' | relative_url }}).*
