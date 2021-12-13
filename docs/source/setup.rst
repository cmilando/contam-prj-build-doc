Initial setup
=====

Project options
----------------

* View > Project options
* Scaling factor = 0.5 ft resolution (walls need to be aligned in floors above/below, no 1 cell gaps, min 2 cell)
* Pseudo-geometry on
* # of levels = # of floors + 1 for level above roof
* Set the height of each level: zones are 9ft, basement is 8 ft attic is 4ft, roof is 4ft
* Make area big enough to leave enough border all the way around
* Basement has to have negative elevation
* Roof or Wall height to height of buildings
* Terrain coefficient and exponents
* Have to unclick conditioned zones to make them not appear conditioned later and also in the conditioned volume
* Load Closed schedule

Drawing zones
------------------
* Draw boxes, set origin
* Round to the nearest 0.5 ft resolution
* Zone names from the pre-defined list (e.g., L_kitchen, bathroom, den, bedroom1)
* ZONE NAMES NEED TO BE UNIQUE!!!!! And systematic
* Zone icons in similar positions
* Arrange building in the north-south orientation 


Wind pressure profiles
----------------
* Load wind profiles for external flow paths (ext door, wall_ext, and wdop) – Look at the NIST libraries for this: Data > WindPressureProfiles
