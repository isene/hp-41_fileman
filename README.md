# hp-41_fileman
## HP-41: File management system

Here are two menu-driven programs for easy file management on the HP-41. While "FILEMAN" handles creation, deletion, clearing and save/get to/from HEPAX memory, "FILE" handles the contents of ASCII files. These programs requires the LIBXM and LIBHPX libraries. The call to the function XMFILE? in the LIBXM requires the [ICEBOX rom](https://github.com/isene/hp-41_icebox), but these calls can safely be deleted from the FILEMAN and FILE programs as these are only included for the added convenience of showing the user what file is currently handled at the start of these programs.

### FILEMAN

The program shows the short form of labels A-E and then a-e as prompts:

**__C:A D G:A D SK__**

**__P CL S:A D FL__**

Label (menu)	|Description
----------------|-----------
LBL A (C:A) |Create ASCII file (name in Alpha)
LBL B (D) |Create Data file (name in Alpha)
LBL C (G:A) |Get/retreive ASCII file from HEPAX memory (name in Alpha)
LBL D (D) |Get/retreive Data file from HEPAX memory (name in Alpha)
LBL E (SK) |Select file (name in Alpha) and set record to 0 (i.e. exequte a SEEKPTA)
LBL a (P) |Purge file (name in Alpha)
LBL b (CL) |Clear file (name in Alpha)
LBL c (S:A) |Save ASCII file to HEPAX memory (name in Alpha)
LBL d (D) |Save Data file to HEPAX memory (name in Alpha)
LBL e (FL) |Run the "FILE" program (see below)

Here is the program listing for the FILEMAN program.

### FILE

The program shows the short form of labels A-E and then a-e as prompts:

**__+. .+ +1 +X ED__**

**__- .+a -1 S ><__**

Label (menu)	|Description
----------------|-----------
LBL A (+.) |Insert record (in Alpha) before current record
LBL B (.+) |Append record (in Alpha) after current record
LBL C (+1) |Jump one record forward
LBL D (+X) |Jump the specified number of records (in X) forward (or backward if X is negative)
LBL E (ED) |Edit current file
LBL a (–) |Delete current record
LBL b (.+a) |Append Alpha to current record
LBL c (-1) |Jump one record backward
LBL d (S) |Sort file alphabetically
LBL e (><) |Trim file (i.e. run FLSZ- from LIBXM)
