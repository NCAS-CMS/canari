# Setting up to run an ensemble member

* Prequisites
* Starting the run

## Prerequiste setup

Before running your first CANARI production run, you need to ensure you have the following setup:

* Machine Accounts: PUMA, ARCHER2, JASMIN, MOSRS
* Request access to CANARI GWS on JASMIN via the [Jasmin accounts portal](https://accounts.jasmin.ac.uk/).  Request access to ET CANARI workspace - contact Grenville 
* Ensure you are setup to run the UM -  [UM Training Getting Setup](https://ncas-cms.github.io/um-training/getting-setup-selfstudy.html)
* Setup GridFTP - [Archer2 to Jasmin GridFTP setup](gridftp)
* Setup JDMA environment and connection from PUMA to sci* nodes - [JDMA setup](jdma)
* Setup JASMIN transfer cache - [XFC setup](xfc)

## Setting up the CANARI suite

* Checkout the suite you've been assigned.  (`rosie checkout u-c????`)
* In suite.rc file - check that `TRANSFER_DIR` is either set to `/work/xfc/vol7/user_cache/canari` or `/work/xfc/vol9/user_cache/canari`
* In the rose edit GUI, under "Project Accounting" (or in the `rose-suite.conf` file), set your ARCHER2 username.
* Double check that settings in  *modify_netcdf_metadata -> model metadata* all agrees with the spreadsheet. You shouldn’t have to do anything though.
* Run the suite for 3 months see below.

## Running the suite

* `rose suite-run`. This will submt the suite and only run the first cycle; holding subsequent cycles highlighted in pink.
* Right click on the jdma task in the cylc GUI and select hold.
* Contact Reinhard when the first cycle coupled task has completed
* Assuming all the tasks have completed succcesfully and you've got the go ahead to continue the run. Release the suite by running `cylc release <suiteid>`
 
## Documenting the running suite

* Create a new page on the CANARI github site.
