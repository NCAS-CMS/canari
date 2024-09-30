# Data issues





| File | Field | Comment / Issue | Action |
| ---   | ---  | ---             | ---    |
| \*\_1hr_pt__\*    | m01s01i235  | field is the hrly mean, but is erroneously written to the hrly instantanous file  |          |
| all files of the form   \*\_mon_XXhrs__\*   |   | the metadata is incorrect, it should include  `cell_methods, time: point within days time: mean over days...` The code to fix this is in `modify _netcdf_metadata` (see `def fix_time_offset_metadata(nc):`) but was not called because of an oversight with the naming of the time coordinate |  fix in cf-store?       |
