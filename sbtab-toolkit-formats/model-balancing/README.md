SBtab files used in model balancing
=======================================

Files
----------------------------------

Options files
* options.tsv

Example file
* demo_single_input_file_MODEL_AND_DATA.tsv

Example state data file and result file
* state_data.tsv 
* metabolic_states.tsv 

Format used in Model Balancing
----------------------------------

Options file:  
!!ConfigureModelBalancing

Model and data file:  
!!Reaction  
!!Compound  
!!Parameter  
!!Flux  
!!MetaboliteConcentration  
!!EnzymeConcentration

Note that the model and data file in this example contains only one metabolic state!

State data and result file:  
!!MetabolicFlux
!!MetaboliteConcentration
!!EnzymeConcentration

Note that the state data and result files in this example contain several metabolic states!

----------------------
Details on table types
----------------------

### In options file

!!ConfigureModelBalancing TableID='ConfigureModelBalancing' TableType='Config'
!Option  
!Value

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

### In result file (note that data are in uncontrolled columns!)

!!MetabolicFlux TableID='MetabolicFlux' TableType='QuantityMatrix'
!QuantityType
!Reaction
Sample1_Mean
Sample1_Std
..

!!MetaboliteConcentration TableID='MetaboliteConcentration' TableType='QuantityMatrix'
!QuantityType
!Compound
Sample1_Mean
Sample1_Std
..

!!EnzymeConcentration TableID='EnzymeConcentration' TableType='QuantityMatrix'
!QuantityType
!Reaction
Sample1_Mean
Sample1_Std
..
