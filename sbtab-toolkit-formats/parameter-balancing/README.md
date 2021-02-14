SBtab files used in parameter balancing
=======================================

Files
----------------------------------

The configuration files

* definitions.tsv (= SBtab-parameter-balancing schema file)
* pb_options.tsv
* pb_prior.tsv

are copies from the Parameter Balancing github repository (directory standalone_version/files/default_files)

The example files

* teusink/teusink_data.tsv
* teusink/teusink_modeldata.tsv
* teusink/teusink_result.tsv
  
are copies from the Parameter Balancing github repo (directory standalone_version/files/example_files/teusink)


Format used in Parameter Balancing
----------------------------------

Options file:  
!!ConfigurePB

Model file:  
!!ConfigurePB  
!!Compartment  
!!Compound  
!!Reaction

Prior table file:  
!!PriorTable

Experimental data file:  
!!ParameterData

Result file:  
!!Parameter


----------------------
Details on table types
----------------------

### In options file

TableID='ConfigurePB' TableType='Config'  
!Option  
!Value

### In model file

TableID='Compartment'   TableType='Compartment'  
!ID  
!Size

TableID='Compound'      TableType='Compound'   
!ID  
!Name  
!Location  
!Charge  
!IsConstant  
!InitialConcentration  
!hasOnlySubstanceUnits  
!Identifiers:kegg.compound

TableID='Reaction'      TableType='Reaction'  
!ID  
!Name  
!ReactionFormula  
!Regulator  
!KineticLaw  
!IsReversible  
!Identifiers:ec-code								

### In prior table file

TableID='PriorTable'  TableType='QuantityInfo'  
!QuantityType  
!Symbol  
!Unit  
!Constant  
!RelatedElement  
!Scaling  
!Dependence  
!PriorMedian  
!PriorStd  
!LowerBound  
!UpperBound  
!ErrorStd  
!SBMLElement  
!Abbreviation  
!MatrixInfo

### In input data file

TableID='ParameterData'  TableType='Quantity'  
!QuantityType  
!Reaction:SBML:reaction:id  
!Compound:SBML:species:id  
!Mean  
!Std  
!Unit  
!Organism  
!Reaction:Identifiers:kegg.reaction  
!Compound:Identifiers:kegg.compound  
!Reference

### In output file

TableID="Parameter" TableType="Quantity"  
!QuantityType  
!SBML:reaction:id  
!SBML:species:id  
!Mode  
!Value  
!Std  
!Unit  
!Provenance  
!Type  
!Source
