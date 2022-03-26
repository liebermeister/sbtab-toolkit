# Schema files (SBtab and ObjTables) for the SBtab format "sbtab-toolkit"

Each folder contains an ObjTables schema file and a subfolder with example files following this schema 

Original SBtab schema (from www.objtables.org)
* schema-sbtab.objtables.tsv
* schema-sbtab.sbtab.tsv

SBtab toolkit schema
* schema-sbtab-toolkit.objtables.tsv
* schema-sbtab-toolkit.sbtab.tsv

SBtab toolkit schema with adapted table type QuantityMatrixECM (for current ECM result file format)
* schema-sbtab-toolkit_ECM.objtables.tsv
* schema-sbtab-toolkit_ECM.sbtab.tsv

In the example file, table attributes in quantity tables have been removed (or moved to tables columns, for 'Unit') to allow concatenation of these tables by ObjTables
