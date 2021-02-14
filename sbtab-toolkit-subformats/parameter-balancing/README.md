SBtab files used in parameter balancing
=======================================

The configuration files

* definitions.tsv (= SBtab-parameter-balancing schema file)
* pb_options.tsv
* pb_prior.tsv

are copies from the Parameter Balancing github repository (directory standalone_version/files/default_files)

The model files

* teusink/teusink_data.tsv
* teusink/teusink_modeldata.tsv
* teusink/teusink_result.tsv
  
are copies from the Parameter Balancing github repo (directory standalone_version/files/example_files/teusink)


----------------------------------
Format used in Parameter Balancing
----------------------------------

Typically in modeldata file (includes options and prior)

!!PbConfig     TableID='Config'       TableType='Config'      
!!Compartment  TableID='Compartment'  TableType='Compartment'  
!!Compound     TableID='Compound'     TableType='Compound'    
!!Reaction     TableID='Reaction'     TableType='Reaction'    
!!QuantityInfo TableID='QuantityInfo' TableType='QuantityInfo'

Note: QuantityInfo (contains prior table; should be renamed, also in spec; maybe "QuantityProperties"?)

Typically in experimental data file:  
!!Quantity (should be renamed into "!!ParameterData", and split into "!!ThermodynamicsData" and  "!!KineticsData")

Typically in result file:  
!!QuantityData (should be renamed into "!!Parameter", and split into "!!Thermodynamics" and  "!!Kinetics")


-----------------------------------------------------
Details on table types (Parameter Balancing)
-----------------------------------------------------

### In model file

TableID='PbConfig' TableType='PbConfig'  
!Option  
!Value

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

TableID='QuantityInfo'  TableType='QuantityInfo'  
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

TableID='Quantity'  TableType='Quantity'  
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

TableID="QuantityData" TableType="QuantityData"  
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
