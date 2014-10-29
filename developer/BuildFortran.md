How to build Fortran components
===============================

Find out tool versions
----------------------

Compaq Visual Fortran:

* Compaq Visual Fortran runs alongside Microsoft Visual C++ under Microsoft Developer Studio
* Select Help => About Developer Studio
* Visual C++ 6.0
* Compaq Visual Fortran Professional Edition 6.6.c

Build MCDS analysis engine
--------------------------

* Open MCDS project in Compaq Visual Fortran:
  - Browse to %BASE%\Analysis Engines\CDS\Engine\Engine\
  - Double-click MCDS.DSW
  - Compaq Visual Fortran runs alongside Microsoft Visual C++ under Microsoft Developer Studio.
* Build MCDS.exe:
  - Select Build => Build MCDS.exe OR Press F7
  - To rebuild everything, select Build => Rebuild All

Copy MCDS.exe for use by other Distance components
--------------------------------------------------

* Copy exe file:

<p/>

    copy %BASE%\Analysis Engines\CDS\Engine\DEBUG\MCDS.exe %BASE%\Analysis Engines\Shared Stuff\NEngineInterfaceUtilities\

Create a MCDS analysis engine NMake file
----------------------------------------

* Open MCDS project in Compaq Visual Fortran:
  - Browse to %BASE%\Analysis Engines\CDS\Engine\Engine\
  - Double-click MCDS.DSW
* Export NMake file
  - Select Project => Export Makefile

Build MCDS analysis engine using NMake file from the command prompt
-------------------------------------------------------------------

* Start command prompt:
  - Select Start => All Programs => Accessories => Command Prompt
* Change into MCDS analysis engine directory:

<p/>

    chdir %BASE%\Analysis Engines\CDS\Engine\Engine\

* Set Visual Fortran environment variables:

<p/>

    "C:\Program Files\Microsoft Visual Studio\DF98\BIN\DFVARS.BAT"

* Build MCDS.exe using NMake:

<p/>

    nmake /f MCDS.MAK cfg="MCDS - Win32 Debug"
