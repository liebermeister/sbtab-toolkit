SBtab files used in parameter balancing
=======================================

Files
----------------------------------

Example file
* demo_single_input_file_MODEL_AND_DATA.tsv

Format used in Parameter Balancing
----------------------------------

Model and data file:

!!Reaction  
!!Compound  
!!Parameter  
!!Flux  
!!MetaboliteConcentration  
!!EnzymeConcentration

----------------------
Details on table types
----------------------

### In model and data file 








!!Reaction TableID='Reaction' TableType='Reaction'  
!ID  
!ReactionFormula  
!Name  
!Identifiers:kegg.reaction  
!IsReversible

!!Compound TableID='Compound' TableType='Compound'  
!ID  
!Name  
!Identifiers:kegg.compound  
!IsConstant

!!Parameter TableID='Parameter' TableType='Quantity'   
!QuantityType  
!Reaction  
!Compound  
!Mode  
!Unit  
!Compound:Identifiers:kegg.reaction  
!Compound:Identifiers:kegg.compound

!!Flux TableID='Flux' TableType='Quantity'  
!QuantityType  
!Reaction  
!Reaction:Identifiers:kegg.reaction  
!Mean  
!Std

!!MetaboliteConcentration TableID='MetaboliteConcentration' TableType='Quantity'  
!QuantityType  
!Compound  
!Compound:Identifiers:kegg.compound  
!Mean  
!Std

!!EnzymeConcentration TableID='EnzymeConcentration' TableType='Quantity'  
!QuantityType  
!Reaction  
!Reaction:Identifiers:kegg.reaction  
!Mean  
!Std