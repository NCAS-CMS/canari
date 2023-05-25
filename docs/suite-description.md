# Suite Description
## One-time suite tasks
### fcm_make2_um
### fcm_make2_ocean
### fcm_make2_drivers
### fcm_make2_pp
### install_ancil
### xml
### recon
## Cycling suite tasks
### xml-fix
Sets the path for output of atmosphere and ocean data in the xml files. Model ouput is directed the suite cycle directory. 

runs on: ARCHER login node

frequency: each cycle

depends on: completion of previous coupled task
### coupled
Runs the coupled atmosphere-ocean model

runs on: ARCHER compute nodes

frequency: each cycle

depends on: xml-fix for current cycle, previous coupled task
### postproc
Manipulates CICE files to create daily/monthly means, rebuilds NEMO files (ocean and icebergs)

runs on: ARCHER seral nodes

frequency: each cycle

depends on: success of postproc in the previous cycle and all create_frames in the current cycle

### create_frames\<region\>
### modify_netcdf_metada
Adds metadata to atmosphere, ocean, and cice netcdf files

runs on: ARCHER serial nodes in batch

frequency: each cycle

depends on: success of postproc for current cycle and modify_netcdf_metadata in the previous cycle
### storm_analysis
### pptransfer
### monitor
### jdma
Requests a jdma data transfer to tape. The transfer is effected by the jdma in an asynchronous autonomous process. Success of the jdma task inidicates only that the request has been successful.

runs on: a JASMIN sci machine 

frequency: each cycle

depends on: success of the monitor task
### tidy_pt_files
### install_ozone_stream
### retrieve_ozone
### redistribute_ozone
### housekeeping
