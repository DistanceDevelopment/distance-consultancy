Distance for Windows and FORTRAN
================================

Analysis engines:

* Conventional distance sampling (CDS)
* Multiple covariate distance sampling (MCDS)

* Stand-alone application, `MCDS.exe`
* For full details of usage and input/output file formats, see Appendix - MCDS Engine Reference, user's guide, p307-344

Distance for Windows <=> FORTRAN interface
------------------------------------------

* Create:
  - Command file
  - Input file
* Invokes `MCDS.exe` via `Ec.exe` e.g.:

<p/>

    C:\Programs\DISTAN~1\ec "C:\Programs\DISTAN~1\MCDS.exe 0, C:\Users\mjj\AppData\Local\Temp\dst3C5.tmp \options 2>C:\Users\mjj\AppData\Local\Temp\dst3C4.tmp" 

* Wait for results:
  - Exits with success
  - Shut down with Internal Error message
  - Crash with FORTRAN runtime error - rare

`Ec.exe` 

* Execute command line after parsing and removing Windows NT-compatible redirection symbols
* Used to capture standard output and standard error.
* See [Compaq Visual Fortran Release Notes August 2002](http://h21007.www2.hp.com/portal/download/files/unprot/Fortran/docs/visual/relnotes.htm).
* See [Redirecting Command-Line Output to Files](https://www.xlsoft.com/jp/products/intel/cvf/docs/vf-html_e/pg/pgsredir.htm):
  - 'The EC tool is located on the Visual Fortran CD-ROM in the `x86\Usupport\Misc\Win95 folder`'.

<p/>

    >ec

    EC - Version: X1.11   Built: Mar 13 1997  17:12:09

    Usage is: EC [-sw -sw] "Command line > out_file 2>&1"

    Switches are:
       l      Toggle display of command execution
       c      Toggle use of command shell
       s      Toggle display of result codes of execution
       t      Toggle Windows 95 style processing
       n      Toggle use of new console windows
       y      Toggle display of consoles
       v      Display program version number
       ?      Display this help message

How to capture input files
--------------------------

* Select Tools => Preferences...
* Click Analysis tab
* Check Debug mode (create command files but don't run engine)

If reusing files elsewhere check to ensure that any paths within the files are updated.

How to capture output
---------------------

* Select Tools => Preferences...
* Click Analysis tab
* Check Capture command line output from CDS and MCDS engines in WinNT

How to run stand-alone
----------------------

At command prompt:

    MCDS 0|1 INPUT_COMMAND_FILE

* `0` - run mode
* `1` - import mode - used for Distance Project Import

Example using files in `C:\Users\mjj\Local Documents\DISTANCE\mcds-dst-tmp-files`:

    mcds.exe 0 dstA705.tmp
    2

Input and output files
----------------------

Command file structure:

    Output file
    Log file
    Stats file
    Plot file
    Bootstrap file|`None`
    Bootstrap progress file|`None`
    OPTIONS;
    ...general options
    END;
    DATA;
    ...column names...
    Fields=STR_LABEL, STR_AREA, SMP_LABEL, SMP_EFFORT, DISTANCE, SIZE;
    ...location of TAB-delimited flat data file...
    Infile=C:\Users\mjj\Local Documents\DISTANCE\mcds-dst-tmp-files\dstA6A6.tmp /NoEcho;
    END
    ESTIMATE;
    ...estimation options
    END;


Output files:

* Correspond to command file header values
* Output file
  - `TABPage titleTAB`
  - ...
  - Human-readable only - not for machine processing beyond pagination
* Log file
  - Copy of input commands
  - Error outputs from analysis engine
* Stats file
  - Engine statistics
  - Sets of records, one per line
* Plot file
  - Data to construct high resolution qq and histogram plots in the Distance interface
* Bootstrap file
  - As for Stats but one set of records for each bootstrap
* Bootstrap progress file
  - Empty until bootstrapping starts
  - 3-digit integer between 000...100 - percentage of way through bootstrap

Error and warning messages
--------------------------

Occur in output and log files:

* Warnings
* Errors
* Internal errors

FORTRAN debugging output:

* Dumped onto the command-line / standard output

Exit codes
----------

* `1` - analysis ran OK
* `2` - warnings, see log file for details
* `3` - errors, see log file for details
* `4` - file errors e.g. could not find the specified command file
* `N` - major error

Implementation
--------------

Random numbers:

* Compaq Visual Fortran function `random_number`
* Seeded from clock or a user-defined value
* Bootstrap resampling
* Two congruential generators - see L'Ecuyer 1988 or Visual Fortran manual for more details
