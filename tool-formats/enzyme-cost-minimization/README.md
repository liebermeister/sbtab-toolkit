SBtab files used in Enzyme Cost Minimization
============================================

The files are copies from the [enzyme-cost-minimization](https://github.com/liebermeister/enzyme-cost-minimization) github repository. The two directories contain alternative SBtab implementations of the same E. coli central metabolism model from *Noor et al. (2016)* (reference below). : 

Directory ecoli_noor_2016:
Files constructed by W. Liebermeister

Directory equilibrator-example:
Files constructed by E. Noor

## References
1. E. Noor, A. Flamholz, A. Bar-Even, D. Davidi, R. Milo, W. Liebermeister (2016), [*The Protein Cost of Metabolic Fluxes: Prediction from Enzymatic Rate Laws and Cost Minimization*](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006010), PLOS Comp. Biol., [DOI: 10.1371/journal.pcbi.1005167](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5094713/)

--------------------------
Current format used in ECM
--------------------------

Typically in model file (e.g. 'FILENAME_ModelData')

!!ConfigureECM
!!Reaction
!!Compound
!!Thermodynamics
!!Parameter
!!Flux
!!GibbsEnergyOfReaction
!!ConcentrationConstraint
!!EnzymeCostWeight

TO do's:
* !!ConcentrationConstraint TableType='' (should be renamed into !!MetaboliteRange)

* (note that tables with incomplete / inconsistent data should be called !!ThermodynamicsData and !!ParameterData)
* (also note that !!Parameter / !!ParameterData should be renamed into !!Kinetics / !!KineticsData, and !!Parameter / !!ParameterData should be used for combined thermodynamic+kinetic data tables)

Typically in experimental data file  (e.g. 'FILENAME_ValidationData')
* !!ConcentrationData (should be renamed into !!MetaboliteData)
* !!EnzymeData

