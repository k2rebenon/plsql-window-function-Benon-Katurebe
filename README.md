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
Provide screenshots of both the creation and deletion processes.


Task 3: Oracle Enterprise Manager  

Configure Oracle Enterprise Manager (OEM).  
Provide a screenshot of the OEM dashboard showing the username clearly after completing Tasks 1 and 2.



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




Screenshot:

Task 2: Create and Delete a PDB

PDB Creation:
Created a second PDB using:CREATE PLUGGABLE DATABASE er_to_delete_pdb_2024101
ADMIN USER eric_plsqlauca_2024101 IDENTIFIED BY simplepassword
FILE_NAME_CONVERT = ('/pdbseed/', '/er_to_delete_pdb_2024101/');


Opened the PDB:ALTER PLUGGABLE DATABASE er_to_delete_pdb_2024101 OPEN;


Verified the creation:SELECT pdb_name, status FROM dba_pdbs;


Screenshot of the creation is saved as task2_pdb_creation.png in the screenshots folder.


PDB Deletion:
Deleted the PDB using:DROP PLUGGABLE DATABASE er_to_delete_pdb_2024101 INCLUDING DATAFILES;


Verified the deletion:SELECT pdb_name, status FROM dba_pdbs;


Screenshot of the deletion is saved as task2_pdb_deletion.png in the screenshots folder.



Task 3: Oracle Enterprise Manager

OEM Configuration:
Accessed Oracle Enterprise Manager by navigating to the OEM URL (e.g., https://<hostname>:5500/em).
Logged in using the SYSTEM user credentials.
Configured OEM to monitor the Container Database (CDB) and the newly created PDB (er_pdb_2024101).
Verified that the PDBs and user details were visible in the OEM dashboard.


Screenshot: A screenshot of the OEM dashboard, clearly showing the username (eric_plsqlauca_2024101), is saved as task3_oem_dashboard.png in the screenshots folder.

Issues Encountered and Resolutions

Issue 1: Permission error while creating the PDB.  
Resolution: Ensured the session was connected as SYS with SYSDBA privileges using sqlplus / as sysdba.


Issue 2: OEM URL was inaccessible initially.  
Resolution: Verified that the OEM service was running using emctl status dbconsole and started it with emctl start dbconsole if necessary.


Issue 3: PDB creation failed due to incorrect FILE_NAME_CONVERT path.  
Resolution: Corrected the file path to match the Oracle database directory structure.



Screenshots
All required screenshots are stored in the screenshots folder:

task1_pdb_creation.png: Shows the creation of er_pdb_2024101.
task2_pdb_creation.png: Shows the creation of er_to_delete_pdb_2024101.
task2_pdb_deletion.png: Shows the deletion of er_to_delete_pdb_2024101.
task3_oem_dashboard.png: Shows the OEM dashboard with the username visible.

Submission

This repository is public and contains all required files and screenshots.
The repository link will be shared via email before the deadline: 11:59 PM on the same day of the class next week.

Grading
The assignment is graded out of 5 points:

Task 1: 2 points
Task 2: 2 points
Task 3: 1 point

