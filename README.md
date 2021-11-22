# TK4 and z/OS Assembler Comparison
This looks at backward compatibility between the current HLASM running in z/OS 2.04 and its far-distant predecessor, Assembler F running in a TK4 environment.

GOAL
----

Show how the IBM processor has maintaned backward compatibility for more than half century.

METHOD
------

Attempt to run the exact same code in TK4 and z/OS. Utilize SNAP command to dump storage and investigate differences.

HIGH LEVEL PROCESS
------------------

The program was submitted via the SYSIN (see JCL modules). It is a very simple program, and it originates from the ASSIST teaching manual (Assembler Language with Assist - 1976). Basically, two numbers are added and the result is stored in a storage location named WORD3. To investigate storage, the SNAP command is used. 

MODULES
-------

JCL 
---
TK4_ASMF_SNAP_ASMFT01_JCL.TXT and zOS_2.04_HLASM_SNAP_ASMFT01_JCL.TXT

The jobs submitted to run the program and obtain the storage sump. Slight changes were made, mainly related to job card and output files (immaterial to the goal).

Assemble/Link/Go PROC 
--------------------
TK4_ASMF_ASMFCLG_PROC.TXT and zOS_2.04_HLASM_HLASMCLG_PROC.TXT (IBM provided)

SNAP OUTPUT 
-----------
TK4_ASMF_SNAP_DUMP.txt and zOS_2.04_HLASM_SNAP_DUMP.txt

PROGRAM ASSEMBLE LISTING  
------------------------
TK4_ASMF_SNAP_LIST.txt and zOS_2.04_HLASM_SNAP_LIST.txt

YREGS MACRO
-----------
TK4_ASMF_YREGS_MACRO.TXT and zOS_2.04_HLASM_SNAP_YREGS_MACRO.txt


SUMMARY
-------         
TK4 
---
System/360, Proc:ASMFCLG, Assembler:IFOX00, Language:AssemblerF, Program:ADD2 (via Sysin), Notable:SNAP-WTO-DCB,YREGS 

z/OS 
----
z/OS 2.04, Proc:ASMACLG, Assembler:ASMA90, Language:HLASM R6.0, Program:ADD2 (via Sysin), Notable:SNAP-WTO-DCB,YREGS
