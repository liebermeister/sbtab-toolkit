# Schema files for the SBtab  format "sbtab-toolkit"

Each folder contains an ObjTables schema file and a subfolder with example files following this schema 

Original SBtab schema (from www.objtables.org)
* sbtab-schema.objtables.tsv

SBtab toolkit schema
* sbtab-toolkit-schema.objtables.tsv

SBtab toolkit schema with adapted table type QuantityMatrixECM (for current ECM result file format)
* sbtab-toolkit-schema_ECM.objtables.tsv

In the example file, table attributes in quantity tables have been removed (or moved to tables columns, for 'Unit') to allow concatenation of these tables by ObjTables
