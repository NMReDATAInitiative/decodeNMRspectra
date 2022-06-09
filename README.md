# decodeNMRspectra
The goal of this project is to code the NMR parameters (chem. shift, J's, NOE, etc.) present in non-standard NMR spectra.
Code: 
- What nuclei are decoupled (in 1D and the acquisition of 2D spectra)
- What nuclei are (homo)decoupled in the first dimension of 2D spectra.
- What is the relaxation process taking place and duration in relaxation experiments (NOESY, ROESY, etc. off-resonance ROESY, and 1D selective experiments)
- Code the location of signals and how the coupling are expressed in in J-resolve experiments and homodecoupled variants such as g-serf, DIAG spectra, *etc.*

If you have any interest in this project, [raise issues](https://github.com/NMReDATAInitiative/decodeNMRspectra/issues/new) or contact the author. This page will be further developed if interest is expressed.
# Situation

Currently, only a few of NMR spectra are analysable by CASE software:
- 1D <sup>1</sup>H (a 1D spectrum with coupling structure)
- {<sup>1</sup>H}, <sup>13</sup>C (a 1D spectrum without coupling structure)
- COSY (a 2D with cross-peak at the coordinates of pairs of spins that are scalar coupled)
- TOCSY (total scalar couping correlation)
- NOESY/ROESY (2D relaxation experiment)
- HSQC/HMQC (short-range heteronuclear correlations)
- HMBC (long-range heteronuclear correlations)

*Note*: {<sup>1</sup>H} means that <sup>1</sup>H is decoupled.
# Problem

For many other less common NMR experiments, the CASE software is not aware of the information content of the spectrum and misses the information.

## Case: Heteronuclear coupling is ignored

Consider a <sup>31</sup>P-containing compound. If you compare a 1D <sup>1</sup>H spectrum with and without <sup>31</sup>P decoupling, the J(<sup>1</sup>H,<sup>31</sup>P) could be measured automatically.

Consider a <sup>19</sup>F-containing compound. If you compare a {<sup>1</sup>H}, <sup>13</sup>C spectrum with and without {<sup>19</sup>F}, the J(<sup>13</sup>C,<sup>19</sup>F) could be measured automatically.

## Case: homodecoupling is ignored

Intense developments involved the generation of 1D <sup>1</sup>H spectra with no coupling structure (homonuclear decoupling). They are ignore by CASE software.

## Case: High-resolution in 2D spectra is ignore

In some cases, spectra are recorded with high-resolution so that coupling constants can, in principle, be measured. Measuring coupling constants from COSY correlation spectra with inphase and antiphase strutures is currently not possible but would be very useful. Similarly for heteronuclear coupling from modified HMBC experiments.

## Case: RDC from HSQC
1J(C,H) are often measured using pairs of HSQC with different decoupling combinations. But HSQC are considered as being decoupled in F1 and F2. Coding the absence of decoupling would allow the automatic measurement of the coupling of interest.

## Case: J-resolved and related spectra
Numerous methodology developements resulted in 2D map similar to J-resolved spectra. The J-coupling are either expressed vertically, with 45 or -45 degree angle. Coding it would allow automated analysis of these spectra.

# Related

Ontology of pulse sequences : http://openaccess.uoc.edu/webapps/o2/handle/10609/126306 

Reference to automatic identification of NMR pulse sequence : https://www.nfdi4chem.de/index.php/event/fair-nmr-research-data-management-workshop-2/







