# Guide to Parameters in the CPD

This page gives an explanation for the parameters included in CPD entries. The CPD currently contains density functional theory-computed surface adsorption energies. The parameters reflect this application.

For a more visually pleasing representation of the same info, go to the CPD Quick Guide at https://cpd.chemcatbio.org/parameter-guide

## Bulk Properties

The properties of the bulk material from which a surface slab or cluster model has been generated for the adsorption energy calculation.

### Bulk Formula

The chemical formula of the bulk material.

String

Required

### Lattice Constants, &#8491; (x3)

The lattice constants, in angstroms, give the edge dimensions of the unit cell in the bulk crystal structure for the material. Depending on the symmetry of the unit cell (<a href="https://dictionary.iucr.org/Laue_class" target="_blank">Laue class</a>), 1–3 may be reported.

Numeric

### Primary Class

Metadata describing primary characteristics of the bulk material, such as "transition metal".

String

### Secondary Class

Metadata describing secondary characteristics of the bulk material, such as "bulk alloy".

String

### Space Group

The [space group](https://en.wikipedia.org/wiki/Space_group) describes the three-dimensional symmetry of the bulk crystal structure.

String

### Stretched?

Some calculations introduce a bulk lattice deformation. This field indicates whether the lattice was stretched relative to its relaxed (optimized) lattice parameters.

Boolean

Required

### Compressed?

Some calculations introduce a bulk lattice deformation. This field indicates whether the lattice was compressed relative to its relaxed (optimized) lattice parameters.

Boolean

Required

## Surface/Particle Properties

The properties of the surface slab or cluster model generated for the adsorption energy calculation.

### Facet

Which crystalline facet was used to form the surface slab model? Using <a href="https://en.wikipedia.org/wiki/Miller_index" target="_blank">Miller index</a> notation.

String

### Surface Termination

For many multicomponent materials, after defining a particular facet (cut angle), there are multiple possible surface terminations depending on the precise cut point along the Miller index direction. This field describes the outermost atoms terminating the surface slab or nanoparticle cluster. For example, for a Pt-Pd alloy material, Pt, Pd, or mixed Pt-Pd terminations are possible.

String

### Surface Composition

Chemical composition of the surface layer.

String

### Sub-Surface Composition

Chemical composition of the sub-surface layer, i.e., the layer between the surface and the bulk.

String

### Cell Symmetry

This field describes the relation of the surface slab to a single unit cell, in both size and relative shape. For example, 1x1 indicates a single instance of the unit cell in the periodically repeated directions (typically x and y), whereas 2x2 would indicate four total unit cells in the slab. Other, non-primitive unit cells apply the naming conventions used to describe overlayers in surface science.

String

### Nanoparticle Size

For nanoparticle calculations only, how many atoms comprise the nanoparticle cluster? (excluding adsorbate atoms)

Numeric

## Methods

Describes the specific <a href="https://en.wikipedia.org/wiki/Density_functional_theory" target="_blank">density-functional theory</a> methods used to calculate the adsorption energy.

### Software

Commercial software package or custom code used for the calculation.

String

Required

### Potential

<a href="https://en.wikipedia.org/wiki/Density_functional_theory#Pseudo-potentials" target="_blank">Pseudopotential</a> used to approximate potentials felt by valence electrons as a result of interactions with the nucleus and core electrons, without explicit calculation of core electron states.

String

### Basis Set

<a href="https://en.wikipedia.org/wiki/Basis_set_(chemistry)" target="_blank">Basis set</a> used to expand the valence electron wave functions.

String

Required

### Exchange Correlation (XC) Functional

<a href="https://en.wikipedia.org/wiki/Density_functional_theory#Approximations_(exchange%E2%80%93correlation_functionals)" target="_blank">Exchange-correlation functional</a> used to approximate the exchange-correlation energy.

String

Required

### Fixed Substrate?<

Was the slab or nanocluster model completely fixed during adsorbate optimization (TRUE), or was any portion of the model allowed to relax (FALSE)?

Boolean

### Spin Polarized?

Were spin-polarized calculations performed? In spin polarized calculations the up and down spins in each electron pair are not restricted. This method is commonly used for materials and species with a non-zero magnetic moment.

Boolean

### Zero Point Energy (ZPE) Corrected?

Were the calculated energies corrected using the <a href="https://en.wikipedia.org/wiki/Zero-point_energy" target="_blank">zero-point energy</a>?

Boolean

## Adsorbate and Reference Species: Overview

An adsorption energy is always calculated as the energy of a surface-adsorbed molecule relative to the sum of the energy of a) the "empty" surface and b) an isolated gas-phase molecular reference. The gas-phase reference may be the same molecule as the adsorbate but simply isolated in space, or it may be a different set of molecules having the same overall formula as the adsorbate. It can even be composed of one or more molecules minus another, such as H2 on a Pt surface being referenced to Pt and H2O – 0.5 O2.

## Adsorbate

### Adsorbate Species

The molecular species adsorbed on the surface. The Adsorbate/Reference Species section below provides more details on the info included for each species.

Species Record

Required

### Adsorption Site

Metadata describing the surface site of adsorption and/or binding configuration. Note that this field is not standardized. Users should consult the linked reference for site and configuration naming conventions.

String

### Coverage Fraction

Surface coverage of the adsorbate species (in units of monolayer, ML), typically defined as number of adsorbates/number of surface sites. Represented as a fraction string. What consititutes a surface site for this data value is defined in the Coverage Fraction Unit.

String

### Coverage Fraction – Numeric

A numeric (decimal) value for the coverage fraction, calculated automatically from the Coverage Fraction string.

Numeric

### Coverage Fraction Unit

Defines what constitutes a surface site (e.g., for a Pt(111) site, the coverage fraction would be per Pt).

String

## Gas-Phase Reference Set

The reference set is composed of one or more pairs of a species, from the adsorbate/reference species table below, and the coefficient for that species in the balanced adsorption reaction (e.g., 1 for H2O and -0.5 for O2 in </span> <b>Pt + H2O – 0.5 O2 &#8594; Pt–H2</b>)

### Reference Species

The gas-phase reference species. Each database entry must have at least one. The Adsorbate/Reference Species section below provides more details on the info included for each species.

Species Record

1+ Required

### Coefficient

The stoichiometric coefficient for the reference species in the balanced adsorption energy equation. The coefficient is multiplied by the calculated gas-phase energy of the reference species when computing the adsorption energy.

Numeric

1+ Required

## Adsorbate/Reference Species

Details on the chemical structure of adsorbate/reference species.

### Structural Formula

The <a href="https://en.wikipedia.org/wiki/Structural_formula#Condensed_formulas" target="_blank">condensed structural formula</a> of the species (e.g., CH3OH for methanol).

String

Required

### SMILES

Chemical structure of the species represented using the <a href="https://en.wikipedia.org/wiki/Simplified_molecular-input_line-entry_system" target="_blank">Simplified molecular-input line-entry system</a> (SMILES). SMILES strings in the CPD are canonicalized using the <a href="http://opensmiles.org/" target="_blank">OpenSMILES</a> implementation in <a href="https://github.com/openbabel" target="_blank">OpenBabel</a> to prevent inclusion of multiple entries of the same structure.

String

Required

### Molecular Formula

<a href="https://en.wikipedia.org/wiki/Chemical_formula#Molecular_formula" target="_blank">Molecular formula</a> for the species using <a href="https://en.wikipedia.org/wiki/Chemical_formula#Hill_system" target="_blank">Hill notation</a> (e.g., ethylene's molecular formula is C2H4).

String

Required

### Connectivity SMILES

A version of the SMILES that contains only connectivity information, replacing all multiple bonds with single bonds and adding explicit hydrogen counts, where needed, to preserve connectivity and structural formula. Because the bonding of the adsorbate species is often indeterminate, species having the same Connectivity SMILES are treated as identical in the CPD.

String

Required

### Name

The chemical name for the species (common or IUPAC).

String

## Adsorption Energy

Computed adsorption energy data.

### Adsorption Energy, eV

Calculated adsorption energy in electron volts (eV), denoting the strength of interaction between the adsorbate and substrate. This is the key output of the calculation.

Numeric

Required

### Most Stable Configuration?

Of the adsorption sites and configurations studied in the paper for this surface and adsorbate, was this the adsorption site/configuration found to have the lowest energy (i.e., energetically preferred)?

Boolean

Required

## Source Metadata

Information on the source of the record.

### DOI

Digital object identifer (DOI) for the peer-reviewed publication that the data is reported in.

String

Required

### Uploaded By

Name, email, and institutional affiliation for the user who uploaded the data point.

String

Required

### Notes

Additional details, if any, that did not fit into other fields.

String
