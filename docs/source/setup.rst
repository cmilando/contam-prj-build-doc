Initial setup
=====

Project options
----------------

* View > Project options > Sketchpad Dimensions
* Scaling factor = 0.5 ft resolution (walls need to be aligned in floors above/below, no 1 cell gaps, min 2 cell)
* Pseudo-geometry on
* # of levels = # of floors + 1 for level above roof
* Level > Edit Level Data (or F8) 
* Set the height of each level: zones are 9ft, basement is 8 ft attic is 4ft, roof is 4ft
* Click Replace and the arrow to update the level height
* Make area big enough to leave enough border all the way around; calculate this before drawing the zones 
* Basement has to have negative elevation
* Roof or Wall height to height of buildings
* Terrain coefficient and velocity profile exponents- select values relevant to surrounding land area you want to simulate (see table screenshot)
* Have to unclick conditioned zones to make them not appear conditioned later and also in the conditioned volume
* Data > Day Schedules > Dimensionless (Or Week schedules)
* Library - Browse (insert screenshot) 
* Load Closed schedule [confirm what this exact name should be] 

Drawing zones
------------------
* Draw boxes, Select Draw Box in the icons menu (the black square) to begin sketching 
* Set origin by selecting point for the origin before selecting (View > Set Origin)
* Round to the nearest 0.5 ft resolution
* Right click in a designated zone and select "Zone" to define the zone
* Zone names from the pre-defined list (e.g., L_kitchen, bathroom, den, bedroom1)
* ZONE NAMES NEED TO BE UNIQUE!!!!! And systematic
* Zone icons in similar positions
* Arrange building in the north-south orientation 
* Hover over zone icon to ensure height and volume are defined

Zoning (roofs, walls, shafts, phantoms):  
When establishing zones, remember that they are assumed to have uniform concentration throughout. _
For some modeling problems, several rooms can be grouped together as a single zone, _ 
while for others much more detail is needed.  For example, if a contaminant were _ 
released in a closet, then the closet would need to be modeled as its own zone.  _
Otherwise, the level of detail of closets is usually not needed.  _ 
Often each room will be treated as a separate zone, but occasionally it is _ 
desirable to sub-divide rooms.  My preference is to use the stair and shaft _ 
models provided (based on fire research) for stair and elevator shafts.  _
However, because the floor to floor leakage for these models is large, _
the results in most cases often won’t be significantly different than _
if another large leakage path were used.  One many people forget is to _
put a roof on the building and give it leakage.  If this isn’t done, rooms _
on the top floor will have a perfectly airtight roof.  _
To add a roof, you specify a top level, and specify the smallest level height the program will allow.  Instead of defining a zone on this level, you place the “ambient” icon there.  

Wind pressure profiles
----------------
* Load wind profiles for external flow paths (ext door, wall_ext, and wdop) – Look at the NIST libraries for this: Data > WindPressureProfiles

Weather 
-------------------------------
Weather:  You may encounter cases where it is desirable to investigate weather effects.  For example, if you are trying to size a depressurization (or pressurization) fan to maintain a space at a negative (positive) pressure, you would want to verify that the pressure difference can be maintained when stack and wind effects are present.  Working with temperatures is easy.  Wind is considerably more difficult, but is important since it can significantly affect results.  I recommend setting the local terrain constant and velocity profile exponent for wind based either on information supplied in the CONTAM help file or in material published regarding the LBNL model (see ASHRAE Fundamentals).  To do this, look at the site and match it to the closest qualitative description.  When in doubt, use the more obstructed condition, since I have found these descriptions to somewhat over-estimate leakage.  

After you specify wind, you still won’t see any effects on your model until you follow another step.  You have to tell each leakage path whether it is on the windward or leeward side of the building, and how to calculate the incident wind pressure.  If you open up the dialog box for “airflow path properties”, you will see a tab for “wind pressure”.  The default is “none”, which means that regardless of the specified wind velocity, there is no pressure on the wall.  The “constant” model allows you to directly specify the pressure, which you might do if you had measurement data.  In almost any case where you are modeling wind, you will want to choose “variable”.  The wind speed modifier is calculated using the data you entered on the “weather” menu, and usually is the same for all paths, so it won’t need to be modified.  The wind pressure profile can be specified based on generic profiles published by ASHRAE.  See page 25.8 of the 1997 ASHRAE Fundamentals Handbook for this formulation and the assumptions on which it is based.  Once these items are defined, you should see wind effects.  Note:  since this is time consuming, you’ll want to put these profiles in before you copy floors for tall buildings.
