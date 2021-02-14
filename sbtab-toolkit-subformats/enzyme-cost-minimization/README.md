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

Typically in model file  (e.g. 'FILENAME_ModelData')

!!TableID='ConfigureECM'            TableType='Config'  
!!TableID='Reaction'                TableType='Reaction'  
!!TableID='Compound'                TableType='Compound'  
!!TableID='Thermodynamics'          TableType='Quantity'  
!!TableID='Parameter'               TableType='Quantity'  
!!TableID='Flux'                    TableType='Quantity'  
!!TableID='GibbsEnergyOfReaction'   TableType='Quantity'  
!!TableID='ConcentrationConstraint' TableType='Quantity'  
!!TableID='EnzymeCostWeight'        TableType='Quantity'  

TO do's:
* !!ConcentrationConstraint TableType='' (should be renamed into !!MetaboliteRange)

* (note that tables with incomplete / inconsistent data should be called !!ThermodynamicsData and !!ParameterData)
* (also note that !!Parameter / !!ParameterData should be renamed into !!Kinetics / !!KineticsData, and !!Parameter / !!ParameterData should be used for combined thermodynamic+kinetic data tables)

Typically in experimental data file  (e.g. 'FILENAME_ValidationData')
* !!ConcentrationData (should be renamed into !!MetaboliteData)
* !!EnzymeData


-------------------------------------
Details on table types (ECM)
-------------------------------------

TableID='Config' TableType='Config'  
!Option  
!Value  
!Comment                  

TableID='Reaction' TableType='Reaction'  
!ID  
!ReactionFormula  
!Identifiers:kegg.reaction  
!IsReversible  
!Gene  
!NameForPlots

TableID='Compound' TableType='Compound'  
!ID  
!Name  
!Identifiers:kegg.compound  
!IsConstant  
!NameForPlots  

TableID='Thermodynamics' TableType='Quantity' StandardConcentration='M'  
!QuantityType  
!Reaction  
!Compound  
!Value  
!Unit

TableID='Parameter' TableType='Quantity'  
!QuantityType  
!Reaction  
!Compound  
!Value  
!Unit  
!Reaction:Identifiers:kegg.reaction  
!Compound:Identifiers:kegg.compound  
!ID

TableID='Layout' TableType='Position'  
!Element  
!PositionX  
!PositionY					

TableID='Flux' TableType='Quantity' Unit='mM/s'  
!QuantityType  
!Reaction  
!Reaction:Identifiers:kegg.reaction  
!Value

TableID='GibbsEnergyOfReaction' TableType='Quantity' Unit='kJ/mol'  
!QuantityType  
!Reaction  
!Reaction:Identifiers:kegg.reaction  
!Value  
!OriginalValue  
!ReactionFormula

TableID='ConcentrationConstraint' TableType='Quantity' Unit='mM'  
!QuantityType  
!Compound  
!Compound:Identifiers:kegg.compound  
!Concentration:Min  
!Concentration:Max

TableID='EnzymeCostWeight' TableType='Quantity' Unit='ArbitraryUnits'  
!QuantityType  
!Reaction  
!Reaction:Identifiers:kegg.reaction  
!Value

TableID='ConcentrationData' TableType='Quantity' Unit='mM'  
!QuantityType  
!Compound  
!Compound:Identifiers:kegg.compound  
!Value

TableID='EnzymeData' TableType='Quantity' Unit='mM'  
!QuantityType  
!Reaction  
!Reaction:Identifiers:kegg.reaction  
!Value
