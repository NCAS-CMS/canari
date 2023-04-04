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
* Set -> file -> jinja2 -> ENSEMBLE_NUM as instructed in your email
* In suite.rc file - adapt TRANSFER_DIR= to point to your JASMIN Transfer cache directory.
* Double check that -> modify_netcdf_metadata -> model metadata -> all agrees with the spreadsheet. You shouldn’t have to do anything though.
* Run the suite for 3 months and let me know when you’ve done that.

## Running the suite

* `rose suite-run -- --hold-point=19500101T0000Z`. This will submt the suite and only run the first cycle; holding subsequent cycles highlighted in pink.
* Right click on the jdma task in the cylc GUI and select hold.
* Contact Reinhard when the first cycle coupled task has completed
* Assuming all the tasks have completed succcesfully and you've got the go ahead to continue the run release the suite by right clicking on each of the held (pink) lines and select "Release".

## Troubleshooting

## FAQ
* Why is the storm_analysis/tidy_pt_files tasks still waiting in the previous cycle?
* Monitor has failed what should I do?

## CANARI HIST2 Production Suites

* [Ensemble Member 1 - u-cv575](u-cv575)
* [Ensemble Member 2 - u-cv625](u-cv625)
* [Ensemble Member 3 - u-cv608](u-cv608)
* [Ensemble Member 4 - u-cv830](u-cv830)
* [Ensemble Member 5 - u-cv827](u-cv827)
* 
* 

