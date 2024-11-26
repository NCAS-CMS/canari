# HIST2 Production Suites - Known Issues

- I'm looking at the daily zonal mean wind on pressure levels (files /gws/nopw/j04/canari/shared/large-ensemble/priority/HIST2/*/ATM/yearly/*/*_day_z_m01s30i201_?.nc), but I think it applies to the other files in the relevant directories too. This is maybe just Iris being conservative otherwise I wouldn't have even noticed, but the attribute "parent_source_id" is set inconsistently across years for ensemble members 11 and 12:
  - In member 11, it is "" for year 1950 but set to "CMIP6.CMIP.MOHC.HadGEM3-GC31-MM.historical.r3i1p1f3" for all other years.
  - In member 12, it is "" for years 1950-1975, not set at all for 1976, and set to "CMIP6.CMIP.MOHC.HadGEM3-GC31-MM.historical.r3i1p1f3" for years 1977-2014.
  - In all the other members, it is set consistently across all years for each member.

  Maybe this is expected, and can easily be worked around (e.g. iris.util.equalise_attributes(...) or xarray.concat(..., combine_attrs="drop_conflicts") but I wanted people to be aware of it. Having this attribute set consistently would also make it easier to keep the link back to the parent in derived data and so help keep track of which ones might cluster due to being micro perturbations of the same parent.

- NEMO ocean: subbasin.nc and diaptr issues.

# Data issues


| File | Field | Comment / Issue | Action |
| ---   | ---  | ---             | ---    |
| \*\_1hr_pt__\*    | m01s01i235  | field is the hrly mean, but is erroneously written to the hrly instantanous file  |          |
| all files of the form   \*\_mon_XXhrs__\*   |   | the metadata is incorrect, it should include  `cell_methods, time: point within days time: mean over days...` The code to fix this is in `modify _netcdf_metadata` (see `def fix_time_offset_metadata(nc):`) but was not called because of an oversight with the naming of the time coordinate |  fix in cf-store?       |
