===============================================================================================================
DATABASE CONTINUOUS INTEGRATION / CONTINUOUS DELIVERY USAGE:
===============================================================================================================

The following folders structure is used to deploy database changes for postgres CI/CD:

|-- Code:
| |-- Functions:	In this folder you can add scripts with changes related to the functions:
| |					- Function creation scripts
| |					- Function alter scripts
| |					- Function drop scripts
| |
| |-- Procedures:	In this folder you can add scripts with changes related to the store procedures:
|					- Store Procedure creation scripts
|					- Store Procedure alter scripts
|					- Store Procedure drop scripts
|
|-- Data:
| |-- Environments:	In this folder you can add scripts with the settings per environment e.g.:
| |					- Connection Strings
| |					- Services Urls
| |					- Api Urls
| |					- Users
| |					- Permissions
| |					The scripts should start with the environment prefix + "-" (parameter "-e" or "--environment" used in the tool)
| |
| |-- Fixes:		In this folder you can add scripts with changes in the data e.g.:
| |					- Insert records scripts
| |					- Update records scripts
| |					- Delete records scripts
| |					- Truncate table scripts
| |					- Data fixes in general
| |
| |-- Settings:		In this folder you can add scripts with changes in the data related to the settings e.g.:
|					- App Settings
|					- Modules
|					- Roles
|					- Menus
|					If there are different settings values per environment, put them in the "Environments" folder
|
|-- Schema
  |-- Sequences:	In this folder you can add scripts with changes related to the sequences:
  |					- Sequence creation scripts
  |					- Sequence drop scripts
  |
  |-- Synonyms:		In this folder you can add scripts with changes related to the synonyms:
  |					- Synonym creation scripts
  |					- Synonym drop scripts
  |
  |-- Tables:		In this folder you can add scripts with changes related to the tables and columns:
  |					- Table creation scripts (keys, constraints, indexes)
  |					- Table alter scripts (keys, constraints, indexes)
  |					- Table drop scripts (keys, constraints, indexes)
  |
  |-- Types:		In this folder you can add scripts with changes related to the types:
  |					- View creation scripts
  |					- View alter scripts
  |					- View drop scripts
  |
  |-- Views:		In this folder you can add scripts with changes related to the views:
					- View creation scripts
					- View alter scripts
					- View drop scripts

===============================================================================================================

The scripts execution by folder is in the following logic order:

01. Schema/Sequences
02. Schema/Tables
03. Schema/Types
04. Schema/Views
05. Schema/Synonyms
06. Code/Functions
07. Code/Procedures
08. Data/Settings
09. Data/Fixes
10. Data/Environments

===============================================================================================================
