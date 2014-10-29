How to build documents and images
=================================

Find out tool versions
----------------------

Axialis IconWorkshop:

* Select Help => About Axialis IconWorkshop
* Version 6.70

ComponentOne Doc-To-Help:

* Select Help => About ComponentOne Doc-To-Help...
* ComponentOne Doc-To-Help Enterprise 2006.3
* Version 2006.3.0.313

Microsoft Word

* Select Help => About Microsoft Office Word
* 2003 SP3

Microsoft PowerPoint

* Select Help => About Microsoft Office Powerpoint
* 2003 SP3

Microsoft PhotoDraw:

* Select Help => About Microsoft PhotoDraw...
* Version 1.0

Edit text files
---------------

Text files used in Distance include:

* %BASE%\Interface\Help - rtf files for built-in help, information and text
  - This includes Authors.rtf and Sponsors.rtf
* %BASE%Extras\External Documentation\ReadMe
  - This includes the ReadMe for each release

Edit text files with WordPad, not Microsoft Word - Word adds extra characters that can mess up the formatting of the files.

To edit a file in WordPad:

* Right-click file name
* Select Open With => WordPad

Edit Distance icon
------------------

* Open icon, ico, file in Axialis IconWorkshop:
  - Browse to %BASE%Extras\Graphics\Icons\
  - Double-click DistanceProject2.ico file

Copy Distance icon for use in Visual Basic and release
------------------------------------------------------

Copy file:

<p/>

    copy %BASE%Extras\Graphics\Icons\DistanceProject2.ico %BASE%\Interface\Main\Graphics - Misc and General\DistanceProject.ico

Edit splash screen
------------------

* Open Microsoft Image Composer, mix, file, in Microsoft PhotoDraw:
  - Browse to %BASE%Extras\Graphics\Splash\
  - Double-click D62release.mix
* Create new file:
  - Select File => Save As...
  - Browse to %BASE%Extras\Graphics\Splash\
  - Enter file name: DXYZ.mix where X is the major release number, Y the minor release number and Z is either release or beta
  - Click Save
* Update version number:
  - Click 'version 6.2' in image
  - Edit text in box on right-hand side e.g. 'version X.Y'
* Update release number:
  - Click 'release 1' in image
  - Edit text in box on right-hand side e.g. 'release Z' or 'BETA Z'
* Save mix file:
  - Select File => Save
* Save mix file as a jpg:
  - Select File => Save As...
  - Select Save as type: JPEG File Interchange Format
  - Browse to %BASE%Extras\Graphics\Splash\
  - Click Save

TODO
----

* Naming convention for .mix and .jpg 
  - DXYZ
  - X = major version number - 6, 7, ...
  - Y = minor version number - 1, 2, ...
  - Z = release or beta
  - What about if there was a 6.3 release 2? or 6.4 beta 3?

Copy splash screen for use in Visual Basic and release
------------------------------------------------------

Copy file:

<p/>

    copy %BASE%Extras\Graphics\Splash\Dxyz.jpg %BASE%\Interface\Help\DistanceLogo.jpg

Update user guide version number
--------------------------------

* Open Doc-To-Help, d2h, file, in ComponentOne Doc-To-Help:
  - Browse to %BASE%Extras\External Documentation\Documents\
  - Double-click distance.d2h
* Update Distance version number:
  - In properties on left-hand side, click Help Targets
  - Click Name: distance Manual
  - For Property: Title, update Value: Distance 6.2 Release 1

Build HTML Help
---------------

* Open Doc-To-Help, d2h, file, in ComponentOne Doc-To-Help:
  - Browse to %BASE%Extras\External Documentation\Documents\
  - Double-click distance.d2h
* Build HTML Help:
  - In menu-bar drop-down build targets list, select distance HTML Help
  - Select Build => Make Target OR Press F5
  - To rebuild everything, select Build => Rebuild Target

Copy HTML Help for use in Visual Basic and release
--------------------------------------------------

* Copy compiled HTML help:

<p/>

    copy %BASE%Extras\External Documentation\Documents\HTMLHelp\distance.chm %BASE%\Utilities\Help\

* Copy Visual Basic macro file for use in Visual Basic components:
  - This contains a list of constants giving shortcuts to the help pages and is used to provide context-sensitive help.

<p/>

    copy %BASE%Extras\External Documentation\Documents\HTMLHelp\distance.bas %BASE%\Utilities\Help\

TODO
----

* "If you're going to be releasing a new version of Distance, it's also worth coping the distance.bas VB macro file into the \Utilities\Help directory. Ater you've done this, you'll need to replace all the Const in this with Public Const, and then recompile all the VB code. You only need to do all this if you've created any new pages of help, etc."
  - distance.bas already has Public Const e.g.

<p/>

    Public Const IDH_workingwithdatafiltersandmodeldefinitions = 356 ' &H164

  - What VB do I compile? _All_ the projects? 

Build HTML Help from command prompt
-----------------------------------

* Start command prompt:
  - Select Start => All Programs => Accessories => Command Prompt
* Change into HTML Help directory:

<p/>

    chdir %BASE%Extras\External Documentation\Documents

* Build HTML help:[.chm/.bas]



<p/>

    "C:\Program Files\ComponentOne\DocToHelp\C1D2HBatch.exe" -build distance.d2h "distance HTML Help"

Update title slide with splash screen
-------------------------------------

* Start Microsoft PowerPoint:
  - Browse to %BASE%Extras\External Documentation\Images\TitlePage\
  - Double-click TitlePage.ppt
* Insert splash screen:
  - Select Insert => Picture => From File...
  - Browse to %BASE%Extras\Graphics\Splash\
  - Double-click DXYZ.jpg where X is the major release number, Y the minor release number and Z is either release or beta
  - Replace current splash screen image in slide with newly-inserted one
* Save title slide:
  - Click CTRL-S

Build title page image
----------------------

* Start Microsoft PowerPoint:
  - Browse to %BASE%Extras\External Documentation\Images\TitlePage\
  - Double-click TitlePage.ppt
* Save as Windows Metafile, wmf:
  - Select File => Save As...
  - Select Save as type: Windows Metafile (*.wmf)
  - Browse to %BASE%Extras\External Documentation\Images\TitlePage\
  - Click Save
  - If asked 'Do you want to export every slide in the presentation or only the current slide?' click Current Slide Only

Build user guide
----------------

* Open Doc-To-Help, d2h, file, in ComponentOne Doc-To-Help:
  - Browse to %BASE%Extras\External Documentation\Documents\
  - Double-click distance.d2h
* Build Microsoft Word document:
  - In menu-bar drop-down build targets list, select distance Manual
  - Select Build => Make Target OR Press F5
  - To rebuild everything, select Build => Rebuild Target

Build user guide from command prompt
------------------------------------

* Start command prompt:
  - Select Start => All Programs => Accessories => Command Prompt
* Change into HTML Help directory:

<p/>

    chdir %BASE%Extras\External Documentation\Documents

* Build HTML help:

<p/>

    "C:\Program Files\ComponentOne\DocToHelp\C1D2HBatch.exe" -build distance.d2h "distance Manual"

Add title page image to user guide
----------------------------------

* Start Microsoft Word:
  - Browse to %BASE%Extras\External Documentation\Documents\Manual\
  - Double-click distance-master.doc
* Insert title page image:
  - Select Insert => Picture => From File...
  - Browse to %BASE%Extras\External Documentation\Images\TitlePage\
  - Double-click TitlePage.wmf
* Resize image so it is the same width as the black-bordered place-holder on the front-page
* Select the image and press CTRL-X (cut)
* Select the place-holder and press CTRL-V (paste)
* Save the document
  - Click CTRL-S

Build user guide PDF
--------------------

* Start Microsoft Word:
  - Browse to %BASE%Extras\External Documentation\Documents\Manual\
  - Double-click distance-master.doc
* Check conversion settings:
  - Select Adobe PDF => Change Conversion Settings
  - Check Conversion Settings: Standard
  - Click OK
* Create PDF:
  - Select Adobe PDF => Convert to PDF
  - Browse to %BASE%Extras\External Documentation\Documents\Manual\
  - Click Save
  - If asked 'Do you want PDFMaker to turn off tagging for this document?',
click No
  - This can take a long time!
* Check:
  - Browse to %BASE%Extras\External Documentation\Documents\Manual\
  - Double-click document-master.pdf
  - If the images do not look OK then try again with a higher-quality conversion setting

Build user guide PDF from command prompt
----------------------------------------

This assumes that:

* Adobe PDF is the default printer
* Adobe PDF will not prompt for a file name or display the PDF. To configure this:
  - Select Start => Printers and Faxes
  - Right-click Adobe PDF => Preferences
  - Click  Printing Preferences...
  - Select Adobe PDF Output Folder: My Documents\*.pdf
  - Uncheck View Adobe PDF results
  - Click OK

* Start command prompt:
  - Select Start => All Programs => Accessories => Command Prompt
* Change into Manual directory:

<p/>

    chdir %BASE%Extras\External Documentation\Documents\Manual

* Run:

<p/>

    start /WAIT "" "C:\Program Files (x86)\Microsoft Office\Office11\winword.exe" distance-master.doc /q /n /mFilePrintDefault /mFileSave /mFileExit 

* Copy PDF:

<p/>

    copy "%userprofile%\My Documents" %BASE%Extras\External Documentation\Documents\distance-master.pdf

**Note that using this means cross-references are not hyperlinked.**

Copy user guide PDF for use in Visual Basic and release
-------------------------------------------------------

* Copy file:

<p/>

    copy %BASE%Extras\External Documentation\Documents\distance-master.pdf %BASE%\Utilities\Help\distance.pdf
