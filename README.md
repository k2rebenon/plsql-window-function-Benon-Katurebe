NAME: KATUREBE Benon
ID: 29143
COURSE:PL/SQL 

**Oracle Database Assignment**

This repository contains the submission for the Oracle Database Assignment, which involves creating and managing Pluggable Databases (PDBs) and configuring Oracle Enterprise Manager (OEM). Below is an overview of the tasks, steps performed, and documentation as required.
Overview of Tasks
The assignment consists of three main tasks:

Task 1: Create a New Pluggable Database (PDB)  

Create a PDB named in the format FirstTwoLettersOfFirstName_pdb_StudentID.  
Create a user account with the format FirstName_plsqlauca_StudentID and assign a simple password.  
This account will store all classwork.


Task 2: Create and Delete a PDB  

Create another PDB named in the format FirstTwoLettersOfName_to_delete_pdb_StudentID.  
Delete the PDB after creation.  


Task 3: Oracle Enterprise Manager  

Configure Oracle Enterprise Manager (OEM).  

Steps Performed
Task 1: Create a New Pluggable Database (PDB)

PDB Creation:
Connected to the Oracle Database as a user with administrative privileges.
Executed the following SQL command to create the *PDB:CREATE PLUGGABLE DATABASE er_pdb_2024101
ADMIN USER eric_plsqlauca_2024101 IDENTIFIED BY simplepassword
ROLES = (DBA)
FILE_NAME_CONVERT = ('/pdbseed/', '/er_pdb_2024101/');


Opened the PDB:ALTER PLUGGABLE DATABASE er_pdb_2024101 OPEN;


Verified the PDB creation using:SELECT pdb_name, status FROM dba_pdbs;




Screenshot: Screenshots/create pluggable database.jpg

Task 2: Create and Delete a PDB

PDB Creation and dropping :
Created a second PDB using:CREATE PLUGGABLE DATABASE be_to_delete_pdb_29143
and dropped it.
ADMIN USER benon_plsqlauca_29143 IDENTIFIED BY simplepassword
FILE_NAME_CONVERT = ('/pdbseed/', '/be_to_delete_pdb_29143/');


Opened the PDB:ALTER PLUGGABLE DATABASE er_to_delete_pdb_2024101 OPEN;


Verified the creation:SELECT pdb_name, status FROM dba_pdbs;

Screenshot: Screenshots/drop pluggable.PNG


Task 3: Oracle Enterprise Manager

OEM Configuration:
Accessed Oracle Enterprise Manager by navigating to the OEM URL.
Logged in using the SYSTEM user credentials.
Configured OEM to monitor the Container Database (CDB) and the newly created PDB (be_pdb_29143).
Verified that the PDBs and user details were visible in the OEM dashboard.


Screenshot: Screenshots/Configuration of oem.PNG

All required screenshots are stored in the screenshots folder:

Submission

This repository is public and contains all required files and screenshots.
