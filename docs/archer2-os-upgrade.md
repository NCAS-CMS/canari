# ARCHER2 OS Upgrade Suite Update & Restart Instructions

Following the ARCHER2 OS Upgrade in June 2023 make the changes below before restarting suites.

* Copy in an updated `make_iodef_xml.py` python script from  `/home/ros/roses/u-cn134/app/xml/bin/make_iodef_xml.py` to your suite
  
* In *postproc->NEMO->Restart Files*
  * add 01-01 to  rebuild_restart_timestamps
  * add 01-01 to  archive_restart_timestamps

* In *postproc->CICE->Restart Files*
  *add 01-01 to  archive_restart_timestamps

* Copy in an updated `archer2.rc` file from `/home/ros/roses/u-cn134/site/archer2.rc`
  
* In `suite.rc`, change TRANSFER_DIR to `/work/xfc/vol7/user_cache/canari`
(vol7 is now dedicated to CANARI   -- NB make sure your pptransfer and jdma tasks are in sync first)

* In `rose-suite.conf` set `CONFIG_MODULE_NAME='GC3-PrgEnv/v3'`
  
* Copy in updated `storm_processing.py` script from  `/home/ros/roses/u-cn134/app/storm_analysis/bin/storm_processing.py`
  
* Commit your changes

* Make a note of the last cycle that completed before the ARCHER2 upgrade.  Record this on your suite log page:  e.g. 
  
* Let CMS know when you have completed 1-6; we'll do a sanity check

* After CMS have sanity checked:
  * Setup your puma->jamsin connection
  * Follow the How to restart suites section from https://cms.ncas.ac.uk//archer2/os-upgrade/
