# Setting up to run an SSP3-7.0 Ensemble Member

These instructions assume that you have previously run a HIST2 CANARI suite and thus have all your accounts setup correctly.

## Setting up the CANARI suite

* Checkout the suite you've been assigned.  (`rosie checkout u-c????`)
* In the rose edit GUI:
  * Under *"Project Accounting"* (or in the `rose-suite.conf` file), set your ARCHER2 username.
  * Under *"jinja2"* check that `ENSEMBLE_NUM` and `HIST2_SUITE` match the Ensemble Number and HIST2 Parent suite id in the spreadsheet.
  * Under *"modify_netcdf_metadata -> model metadata"* check all settings agree with the spreadsheet. Pay particular attention to the `parent_source_id` and `parent_variant_id`. You shouldn’t have to do anything.

## Running the suite

* Run the suite with `rose suite-run`.
* Right click on the `jdma` task in the cylc GUI and select hold.
* Once the second cycle (19500401T0000Z) appears in the cylc GUI right click on it and select hold.
* When the first cycle `coupled` and `modify_netcdf_metadata` tasks have finished contact Reinhard to check all is ok.
* Assuming all the tasks have completed succcesfully and you've got the go ahead to continue the run. Release the suite by running `cylc release <suiteid>`.
 
## Documenting the running suite

* Create a new page on the CANARI github site under the SSP3-7.0 section.
* Remember to document any "out of the ordinary" events. (E.g. perturbations, having to re-run cycles, etc)
