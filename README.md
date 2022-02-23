# R-HistoTrac-IHIW-Families
R code for IHIW families project identification from HistoTrac

Version 4.0 code changes:
1.	Code to extract the tables from HistoTrac was revised. The error-correcting code is now used once at the beginning, and all of the table extractions use the error-correcting code. This makes the code cleaner, and makes it easier to extract all of the tables. 
2.	Note that the code requires the computer to have a connection to your HistoTrac server with a connection named “HistoTrac.” Please see Powerpoint file, which contains instructions on how to create a connection to the HistoTrac server on a Windows computer.

Version 3.0 code changes:
1.	Tables extracted from HistoTrac SQL server are saved as RDS files, which preserves data structure. Saving as csv.gz files remains as an option.
2.	Tables are loaded back into R by reading the RDS files, and code ensures all blank values are recorded as “NA.” 
3.	The code to find families consisting of the patient and 2 children was returning families with 3 children. The code was revised to correct this. Theoretically, the code for finding families with a patient and 2 parents could also return a family of 3 parents (even though this is unlikely), so that code was revised as well.
4.	The previous version of the code resulted in families where one member was named “PT,” which is not helpful for uploading to the IHIW. Code was written to rename all family members as either parent or child.
5.	Code was written to copy the typing from the first allele to the second allele when the second allele is blank. This ensures homozygous loci will show up as 2 alleles with the same type.
6.	Code was written to filter out families consisting of 1 parent and multiple HLA identical children.

Version 2.0 code changes:
1.	Improved, error-correcting code for extracting difficult tables from the SQL server of HistoTrac.
2.	Output file is more user-friendly, including typing of all family members.



