Developer Experience Review
===========================

Based on []() by Mike Jackson, The Software Sustainability Institute / EPCC, The University of Edinburgh

**Bold** indicates high priority.

*Italic* indicates medium priority.

Bold/italic items without names are for Laura.



Refactor developer information form, content and hosting
========================================================

 - [ ] *Use wikis or revision control*
 - [ ] Host documentation alongside its related products
 - [ ] **Review and update documentation**

Folder, file and database formats
=================================

 - [ ] **Mention `.dst` file format in user's guide**

Interfaces between Distance for Windows, FORTRAN and R
======================================================

 - [ ] **Pull out Appendix - MCDS Engine Reference into a stand-alone user guide**
 - [ ] *Len* **Update reference on how to run MCDS from another program**
 - [ ] *Len* **Provide standalone R and MCDS examples**


API documentation
=================

 - [ ] Auto-generate API documentation
 - [ ] Provide API documentation as HTML


Dependencies on third-party software
====================================

 - [ ] List origins of tools and external components
 - [ ] Provide external dependencies as a table


Source code and documentation management
========================================

 - [ ] **Put all manually-created artefacts under revision control**
 - [X] Move MCDS code to GitHub
 - [ ] Fix link to `mrds` repository
 - [ ] *Dave*: **Clarify whether SourceForge hosts the canonical FORTRAN code**
 - [ ] *Dave*: **Add an MCDS README**


Coding standards
================

 - [ ] Refer R developers to the CRAN Writing R Extensions guide
 - [ ] Propose a minimal set of coding standards for each language

*Laura to look at guidelines she's written before*

*Laura suggests "how to release on CRAN" guide?*


Testing protocols
=================

**Return to this when talking about testing and releases**

 - [ ] Provide information on how to run Distance for Windows test projects
 - [ ] Provide information on how to write and run VB tests
 - [ ] Implement MCDS tests
 - [ ] Provide information on how to write and run MCDS tests
 - [ ] Generalise `testthat` advice
 - [ ] Update link to `testthat`

*Laura mentioned importance of having a repo for test projects*


Release processes
=================

 - [ ] *Document (major) release processes*


Setting up a development environment
====================================

 - [ ] *Len* **Provide a "clean" virtual machine**


Additional documentation recommendations
========================================

**Implement if easy**

 - [ ] Put Required knowledge in its own section
 - [ ] Add GIS to required knowledge
 - [ ] Add packrat, testthat and RStudio to tools
 - [ ] Update link to Rtools
 - [ ] Pull out Appendix - Inside Distance into a stand-alone document
 - [ ] Combine internal components list and table
 - [ ] Separate external components into types
 - [ ] Remove incomplete or unwritten doc
 - [ ] Add missing image to user's guide
 - [ ] Add link from DistanceDevelopment `README.md`
 - [ ] Link to DistanceDevelopment web-site from package `README.md` files
 - [ ] Make Creating a New Numerical Engine a stand-alone tutorial


Additional general recommendations
==================================

 - [ ] ~~Automate upgrade support~~
 - [X] Host project resources in project, not personal, spaces
 - [ ] **Add copyright and licence statements to each R repository**
