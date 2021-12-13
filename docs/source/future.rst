The future of CONTAM prj work
=================================

Eventually, the CONTAM input file will be a JSON file. _ 
At that point, a number of scripts to check things will be possible.

Setup
-------------------
* Relative elevations (some should be 0 and some should not be)
* Schedules
* Everything external should have a wind pressure profile, on each level and the roof elements
* Dimensions for windows (height and width are correct)
* Wall_external multipliers should be consistent and should total the area for the wall they are on
* Even number of wdop and window_ elements
* Exh in kitchen and bathrooms, correctly set up
* No setting of schedules for AHS
* Wind_ elements have 0 multipliuer
* Windows are all called windows with no typos (perhaps a CONTAM linter or something)
* Do all AHS have filters?
* No flow paths bigger than the surface they are on (doors, floor leaks)

CTM
-------------------
* Each room has a sink for each ctm
* Kitchens have a source

IDF
-------------------
* Windows etc are ok and not out of bounds
* Check that fan = 0 depending on the scenario
* Basement has preprocessing steps
