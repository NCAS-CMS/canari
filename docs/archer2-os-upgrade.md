# ARCHER2 OS Upgrade Suite Update & Restart Instructions

Following the ARCHER2 OS Upgrade in June 2023 make the changes below before restarting suites.

1. Copy in an updated `make_iodef_xml.py` python script from  `/home/ros/roses/u-cn134/app/xml/bin/make_iodef_xml.py` to your suite
  
2. In panel *postproc->NEMO->Restart Files*
  * add **01-01** to `rebuild_restart_timestamps`
  * add **01-01** to `archive_restart_timestamps`

3. In panel *postproc->CICE->Restart Files*
  * add **01-01** to `archive_restart_timestamps`

4. Copy in an updated `archer2.rc` file from `/home/ros/roses/u-cn134/site/archer2.rc`
  
5. In `suite.rc`, change TRANSFER_DIR to `/work/xfc/vol7/user_cache/canari` \
  (vol7 is now dedicated to CANARI   -- NB make sure your pptransfer and jdma tasks are in sync first)

6. In `rose-suite.conf` set `CONFIG_MODULE_NAME='GC3-PrgEnv/v3'`
  
7. Copy in updated `storm_processing.py` script from  `/home/ros/roses/u-cn134/app/storm_analysis/bin/storm_processing.py`
  
8. Commit your changes

9. Make a note of the last cycle that completed before the ARCHER2 upgrade.  Record this on your suite log page:  e.g. [u-cv976](https://ncas-cms.github.io/canari/u-cv976)
  
10. Let CMS know when you have completed 1-9; we'll do a sanity check

11. After CMS have sanity checked:
  * Setup your puma->jamsin connection
  * Follow the *"How to Restart Suites"* section at: [https://cms.ncas.ac.uk//archer2/os-upgrade/#how-to-restart-suites](https://cms.ncas.ac.uk//archer2/os-upgrade/#how-to-restart-suites)
