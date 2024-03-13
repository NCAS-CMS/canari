# CANARI Large Ensemble

The page contains information for users and developers of the CANARI Large Ensemble.
Basic properties and the experiment design of this Large Ensemble are described [here](https://canari.ac.uk/resources_new/tools).

## Accessing the output

### Priority and derived output on JASMIN CANARI group workspace

A subset of the complete output is retrieved from the JASMIN Elastic Tape to this location:
`/gws/nopw/j04/canari/shared/large-ensemble/priority`.
The available priority variables are listed [here](/metadata/20240303-canari-le-priority-variables.xlsx); the spreadsheet contains:
  - the priority UMatmos variables, 
  - priority NEMO variables ("Priority 1" monthly and 2D daily only), and
  - priority CICE variables (all CICE output is included in the priority output).

**Note:** an unfortunate change in the names of four variables occurred during the HIST2 runs. The spreadsheet referenced above details the variable naming for the currently extracted ensemble members and indicates where the names switch. Variable naming is consistent within an ensmeble member.


Alongside the `priority` directory, derived diagnostics are shared by the CANARI community, and you are encouraged to share your own in an appropriate location, e.g., adding to `/gws/nopw/j04/canari/shared/large-ensemble/derived`. Management of this shared space is very light-touch, and **different users can write** to it, so please make sure you either keep a private copy of your data for small datasets, or that you can easily reproduce these derived diagnostics should the need arise.

### Full output on the JASMIN Elastic Tape

Variables not contained in the priority output can be retrieved from the JASMIN Elastic Tape. In order to do this, you need to
  - know how to read from the ET, using the so-called JDMA tool. This is explained [here](https://help.jasmin.ac.uk/category/196-long-term-archive-storage).
  - know the ET batches corresponding to the ensemble members your are looking for. These are detailed [below](#canari-hist2-production-suites) for the historical ("HIST2") simulations.

### Ancillary files

Commonly used ancillary files, such as for the land fraction and orography, are available at `/gws/nopw/j04/canari/shared/large-ensemble/ancil`.

## CANARI SSP3-7.0 Production Suites

### Ensemble Members In Progress

|     |    |
| --- | ---|
| [01 - u-de](ssp370/1-de) | [02 - u-de436](ssp370/2-de436) |


## CANARI HIST2 Production Suites

[Known issues affecting more than suite suite](hist2-known-issues)

### Completed Ensemble Members
* [01 - u-cv575](hist2/1-cv575)
* [02 - u-cv625](hist2/2-cv625)
* [03 - u-cw345](hist2/3-cw345)
* [04 - u-cw356](hist2/4-cw356)
* [05 - u-cv827](hist2/5-cv827)
* [06 - u-cv976](hist2/6-cv976)
* [07 - u-cz547](hist2/7-cz547)
* [09 - u-cw342](hist2/9-cw342)
* [10 - u-cw343](hist2/10-cw343)
* [11 - u-cy375](hist2/11-cy375)
* [12 - u-cy376](hist2/12-cy376)
* [13 - u-cy537](hist2/13-cy537)
* [14 - u-cy811](hist2/14-cy811)
* [16 - u-cy873](hist2/16-cy873)
* [17 - u-cy877](hist2/17-cy877)
* [18 - u-cy879](hist2/18-cy879)
* [20 - u-cy881](hist2/20-cy881)
* [21 - u-da179](hist2/21-da179)
* [22 - u-da190](hist2/22-da190)
* [24 - u-da192](hist2/24-da192)
* [28 - u-db303](hist2/28-db303)
* [30 - u-db305](hist2/30-db305)
* [31 - u-cz475](hist2/31-cz475)
* [32 - u-cz568](hist2/32-cz568)
* [33 - u-cz647](hist2/33-cz647)
* [34 - u-cz648](hist2/34-cz648)
* [35 - u-cz649](hist2/35-cz649)
  
### Ensemble Members In Progress

* [08 - u-cy436](hist2/8-cy436)
* [15 - u-cy866](hist2/15-cy866)
* [19 - u-cy880](hist2/19-cy880)
* [23 - u-da191](hist2/23-da191)
* [25 - u-da193](hist2/25-da193)
* [26 - u-db291](hist2/26-db291)
* [27 - u-db301](hist2/27-db301)
* [29 - u-db304](hist2/29-db304)
* [36 - u-dd436](hist2/36-dd436)
* [37 - u-dd438](hist2/37-dd438)
* [38 - u-dd439](hist2/38-dd439)
* [39 - u-dd441](hist2/39-dd441)
* [40 - u-dd442](hist2/40-dd442)

####  Abandoned Suites:
* [03 - u-cv608](hist2/3-cv608)
* [04 - u-cv830](hist2/4-cv830)
* [07 - u-cw083](hist2/7-cw083)
* [08 - u-cw085](hist2/8-cw085)

## CANARI HIST1 Production Suites

* [u-cu600](u-cu600)
* u-cv592
* [u-cv247](HIST1-RI36-u-cv247-runlog.md)
* [u-cv281](u-cv281)
* [u-cw263](u-cw263)
* [u-cw264](u-cw264)

## Documents related to suite running

* [Setting up to run a CANARI production suite](setup)
* [Setting up to run a CANARI SSP3-7.0 productions suite](setup-ssp3)
* [CANARI suite description](suite-description)
* [ARCHER2 OS Upgrade - Suite Restart Instructions](archer2-os-upgrade)
* [Troubleshooting](troubleshooting)
* [Frequently Asked Questions](faq)
