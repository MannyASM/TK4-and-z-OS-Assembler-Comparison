# TK4 and z/OS Assembler Comparison
This looks at backward compatibility between the current HLASM running in z/OS 2.04 and its far-distant predecessor, Assembler F running in the amazing TK4 emulator environment.

GOAL - Show how the IBM processor has maintaned backward compatibility for more than half century.

METHOD -Attempt to run the exact same code in TK4 and z/OS. Utilize SNAP command to dump storage and investigate differences.

HIGH LEVEL PROCESS - The program was submitted via the SYSIN card within the JCL. Most of the program comes directly from the original ASSIST teaching manual (Assembler Language with Assist - 1976). Two numbers are added and the result is stored in a storage location named WORD3. To investigate storage, the SNAP command is used. 

MODULES

JCL - the jobs submitted to run the program and obtain the storage sump. Slight changes were made, mainly related to job card and output files (immaterial to the goal).
  TK4_ASMF_SNAP_ASMFT01_JCL.TXT
  zOS_2.04_HLASM_SNAP_ASMFT01_JCL.TXT

Assemble/Link/Go PROC - as provided by vendor. 
  TK4_ASMF_ASMFCLG_PROC.TXT
  zOS_2.04_HLASM_SNAP_HLASMCLG_PROC.TXT (IBM provided)

SNAP OUTPUT
  TK4_ASMF_SNAP_DUMP.txt
  zOS_2.04_HLASM_SNAP_DUMP.txt

PROGRAM ASSEMBLE LISTING
  TK4_ASMF_SNAP_LIST.txt
  zOS_2.04_HLASM_SNAP_LIST.txt

YREGS MACRO
  TK4_ASMF_YREGS_MACRO.TXT
  zOS_2.04_HLASM_SNAP_YREGS_MACRO.txt

CONCLUSION
              TK4				        z/OS
            --------------      -------------------
OS            System/360			  z/OS 2.04  
Proc			    ASMFCLG			      ASMACLG	
Assembler 	  IFOX00 - ASM F	  ASMA90 - HLASM R6.0
Language		  Assembler F			  HLASM	
Program		    ADD2 (Sysin)			same
Notable			  SNAP				      same
			        WTO macro			    same
			        DCB				        same
			        YREGS macro			  same
 SNAP Output  2 storage areas   same




