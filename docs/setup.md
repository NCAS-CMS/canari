# Setting up to run an ensemble member

* Prequisites
* Starting the run

## Prerequiste setup

Before running your first CANARI production run, you need to ensure you have the following setup:

* Machine Accounts:  PUMA, ARCHER2, JASMIN, MOSRS
* Request access to CANARI GWS on JASMIN.  Jasmin accounts portal.  Request access to ET CANARI workspace - email MJP?
* Ensure you are setup to run the UM -  [UM Training Getting Setup](https://ncas-cms.github.io/um-training/getting-setup-selfstudy.html)
* Setup GridFTP - [https://cms.ncas.ac.uk/unified-model/pptransfer/](https://cms.ncas.ac.uk/unified-model/pptransfer/)
* Setup JDMA environment and connection from PUMA to sci* nodes - [JDMA Setup](https://cms.ncas.ac.uk/unified-model/jdma)
* Setup JASMIN transfer cache - [https://help.jasmin.ac.uk/article/4536-install-jasmin-xfc-client](https://help.jasmin.ac.uk/article/4536-install-jasmin-xfc-client)

## Setting up the CANARI suite

* Take a copy of suite u-cv575.
* Adapt -> suite-info -> title
* Adapt -> suite conf ->  Project Accounting
* Set -> file -> jinja2 -> ENSEMBLE_NUM as instructed in your email
* In suite.rc file - adapt TRANSFER_DIR= to point to your JASMIN Transfer cache directory.
* Double check that -> modify_netcdf_metadata -> model metadata -> all agrees with the spreadsheet. You shouldn’t have to do anything though.
* Run the suite for 3 months and let me know when you’ve done that.

## Running the suite

* `rose suite-run`. This will submt the suite and only run the first cycle; holding subsequent cycles highlighted in pink.
* Right click on the jdma task in the cylc GUI and select hold.
* Contact Reinhard when the first cycle coupled task has completed
* Assuming all the tasks have completed succcesfully and you've got the go ahead to continue the run release the suite by right clicking on each of the held (pink) lines and select "Release".

## Documenting the running suite

* Create a new page on the CANARI github site.
