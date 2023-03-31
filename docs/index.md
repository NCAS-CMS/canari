# CANARI

## Prerequiste setup

Before running your first CANARI production run, you need to ensure you have the following setup:

* Machine Accounts:  PUMA, ARCHER2, JASMIN, MOSRS
* Request access to CANARI GWS on JASMIN.  Jasmin accounts portal.  Request access to ET CANARI workspace - email MJP?
* Ensure you are setup to run the UM -  https://ncas-cms.github.io/um-training/getting-setup-selfstudy.html
* Setup GridFTP - https://cms.ncas.ac.uk/unified-model/pptransfer/
* Setup JDMA environment and connection from PUMA to sci* nodes - https://cms.ncas.ac.uk/unified-model/jdma
* Setup JASMIN transfer cache - https://help.jasmin.ac.uk/article/4536-install-jasmin-xfc-client

## Setting up the CANARI suite

* Take a copy of suite u-cv575.
* Adapt -> suite-info -> title
* Adapt -> suite conf ->  Project Accounting
* Set Total Run Length to 3 months in suite conf -> Run Initialisation & Cycling
* Set -> file -> jinja2 -> ENSEMBLE_NUM to 4/5 for Jeff/Dan
* In suite.rc file - adapt TRANSFER_DIR=
* Double check that -> modify_netcdf_metadata -> model metadata -> all agrees with the spreadsheet. You shouldn’t have to do anything though.
* Run the suite for 3 months and let me know when you’ve done that.

## Running the suite


## CANARI Production Suites

* [u-cv575](u-cv575.md)
* [u-cv625](u-cv625.md)
* [u-cv608](u-cv608.md)
* [u-cv???](u-cv???.md)
* [u-cv827](u-cv827.md)
* 
* 

