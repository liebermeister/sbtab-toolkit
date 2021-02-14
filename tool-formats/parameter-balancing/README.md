SBtab files used in parameter balancing
=======================================

Files
----------------------------------

Configuration files

* definitions.tsv (= SBtab-parameter-balancing schema file)
* pb_options.tsv
* pb_prior.tsv

(copies from the Parameter Balancing github repository, directory standalone_version/files/default_files)

Example files

* teusink/teusink_data.tsv
* teusink/teusink_modeldata.tsv
* teusink/teusink_result.tsv
  
(copies from the Parameter Balancing github repository, directory standalone_version/files/example_files/teusink)

Tables used in Parameter Balancing
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
!!ParameterBalanced


----------------------
Details on table types
----------------------

### Options file

!!TableID='ConfigurePB' TableType='Config'  
!Option | !Value

### Model file

!!TableID='Compartment'   TableType='Compartment'  
!ID  
!Size

!!TableID='Compound'      TableType='Compound'   
!ID  
!Name  
!Location  
!Charge  
!IsConstant  
!InitialConcentration  
!hasOnlySubstanceUnits  
!Identifiers:kegg.compound

!!TableID='Reaction'      TableType='Reaction'  
!ID  
!Name  
!ReactionFormula  
!Regulator  
!KineticLaw  
!IsReversible  
!Identifiers:ec-code								

### Prior table file

!!TableID='PriorTable'  TableType='QuantityInfo'  
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

### Input data file

!!TableID='ParameterData'  TableType='Quantity'  
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

### Output data file

!!TableID="ParameterBalanced" TableType="Quantity"  
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
