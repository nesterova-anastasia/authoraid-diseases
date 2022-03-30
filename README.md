# authoraid-diseases
Automation of extraction citations with references and drugs and biomarkers by disease names 

The retrieved references covers: 
-	Terminology
-	Epidemiology / Demographics
-	Clinical presentation / Diagnosis 
-	Etiology / Pathology (genetics, biomarkers, pathways) 
-	Treatment / Follow-Up; 
-	Case studies.

To retrieve information (list of citations with references) from Elsevier Text Mining (https://demo.elseviertextmining.com/) with queries presented here, you need to know the disease name(s) and have a personal key to access the product API. 

Step 1.
Find and replace “YOUR-API-KEY” with actual ETM API key on “list queries” sheet in ETMinput.xlsx Excel file.

Step 2.
Paste list of disease names to “list queries” sheet in “ETMinput.xlsx” Excel file and apply formulas that construct API queries on the entire sheet.

Step 3.
In “ETMinput.xlsx” Excel file, copy content of “list queries” sheet and paste to “API” sheet as values as instructed in the file.

Step 4.
Make sure Python 3 with “openpyxl” library are installed, and files “ETMinput.xlsx” and “etm.py” are located in the same folder. To install “openpyxl” library, execute the following command in the command line:
python -m pip install openpyxl

Step 5.
In command line, execute “etm.py” as follows:
python etm.py YOUR-API-KEY

How to modify queries:

Number of queries can be modified also but need the adjustment in code
Queries can be modified according to https://demo.elseviertextmining.com/help/HTML/index.html?advanced_search_scope_operators.htm
Example of complex query:
•	rel(subj(protein) AND verb(associate) AND obj(hemophilia AND female)) - finds all relations where any protein associated with hemophilia in females. 
Examples for additional commands are:
/exa - flag for exact term searching
/noexa - flag to turn off exact term searching
