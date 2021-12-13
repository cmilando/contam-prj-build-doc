Configuring flow paths
=========================================

Windows
-----------------------------------
* Two types of windows exist: 
* glass windows (multiplier = 0) have prefix “wind” . No wind pressure profile. 2-way flow element with one opening. No schedule.
* Use spreadsheet to get:
* Height (some multiplier of room height)
* Width (some multiplier of room width)
* Flow path is XX relative height
* Icons located in the middle of the wall, position matters for the glass window, not ‘wdop’
* Operable windows (4x4), prefix “wdop”, smaller to simulate cracking the window half open (schedule = closed). This has a wind pressure profile (variable). 2-way flow element with two opening
* Both have Discharge parameter = 0.78

Doors
-----------------------------------
* Two types of doors elements: operable and undercut (elevation = 0)
* NO EXTERNAL DOOR
* Internal door = both elements
* Set schedule to closed
* Position does not matter
* Probably the best for this is door_open3ft, not door_operable

External wall leakage
------------------------------------
* Standard practice is 3 per wall
* You don’t change the element (wall_ext)
* You modify the relative height and area, as per the spreadsheet
* Set a wind pressure profile
* Standard value is 5 cm2/m2

Internal wall leakage
------------------------------------
* Standard practice is 3 per wall
* You don’t change the element 
* You modify the area, as per the wall area
* Position does not matter for calculation, but should be smart so you can easily scan them
* This may differ for inter-apt vs intra-apt
* Standard is 2 cm2/m2 for both

* Door open for an open floor-plan
* You may want to simply create two-way elements the size of the openings and let mixing occur between zones based on differences in air density.Or, create one orifice high and one low => two-way flow can occur.


In the absence of having any actual leakage tests for the building (which is usually the case), I recommend taking external leakage values from Andy Persily’s article “Myths about building envelopes”.  This publication summarizes the results of many known leakage tests, and breaks them down by building use and location.  Notice that Florida buildings are generally leakier, so you may wish to use these values in the south.  Also note that there are significant variations in leakage for similar buildings.  Therefore, you may wish to check your final results with a leakier or tighter building to test its sensitivity to these variables.  If the contaminant transport is primarily mechanically driven, then leakage may not be as important.  However, if it is migrating through walls or into stairwells, leakage could have a large influence.  Be sure to specify the same discharge coefficient and reference pressure drop as is used in the published data.  

Certain elements, such as operable windows (particularly the automatic motorized ones) are very leaky.  If you know these are present, it’s a good idea to specify a somewhat low leakage per area value for the leakage you don’t know and to add to this leakage for the windows in their actual location.  I recommend this for any large leakage path that you have knowledge of.

I usually assume that roofs have similar leakage to exterior walls and that interior walls and floors are leakier by at least a factor of two.


Floor/Roof leakage
----------------------------------
* Goes above each ceiling
* (so if you have basement and lvl1, it goes on lvl 1)
* (for roof, it goes in the blank layer above the roof)
* Roof wind pressure profile for roof_leakages
* Evelation of roof/floor leaks is 0ft
* Stairs have to be the zone area
* You have to modify for the area below. This can be easier with ‘reveal level below’ feature
* Floor= int wal value
* Roof = ext wall value
* If you are adding a roof that is peaked
* then you should include an attic zone on level 4 and add another roof level.
* Roof level would then have attic ventilation as per specs I sent previously: typically, a ridge vent and soffit or eave vents.
* Currently, your “roof” leaks are attic floor leaks which is why I was making these comments.
