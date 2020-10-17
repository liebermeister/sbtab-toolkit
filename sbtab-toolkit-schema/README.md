Schema files for the SBtab toolkit
==================================

ObjTables schema file for SBtab subformat "sbtab-toolkit"

Original SBtab schema
* SBtab_schema.objtables.tsv                  Original schema file "SBtab.tsv" (from www.objtables.org)
* ecoli_noor_2016_ecm_pre_sbtab.objtables.tsv Example data file

SBtab toolkit schema
* sbtab-toolkit_schema.objtables.tsv              ObjTables schema file for sbtab-toolkit
* ecoli_noor_2016_ecm_sbtab-toolkit.objtables.tsv Example data file
* ecoli_noor_2016_ecm_concatenate_sbtab-toolkit.objtables.tsv Example data file

SBtab toolkit schema with adapted table type QuantityMatrixECM (for ECM results)
sbtab-toolkit_schema_ECM.objtables.tsv         ObjTables schema file for sbtab-toolkit
output_noor_2016_StateRuns.objtables.tsv       Example ECM output file (manually converted to ObjTables)

In the last example file, table attributes in quantity tables have been removed (or moved to tables columns, for 'Unit') to allow concatenation of these tables by ObjTables
