Amy Musser process guide
==================================


Process: These are the general steps I always follow when I build a model.  These help you avoid the common pitfalls.

1.)	Specify geometry, zones, and leakage only.  Perform the following tests:
a.	Blower door test:  Set all interior doors in the building to “open” and put a large pressurization fan in an exterior wall.  Pressurize the building and use the flow rate of the fan and pressure difference across the exterior wall that it induces to calculate the leakage area per area of exterior wall for the building.  Compare this to your input value and make sure they’re close.  This will verify that you specified the proper amount of leakage on all the walls and is especially important when you specify some paths individually.
b.	Stack effects:  Take out the blower door fan, specify a very cold outdoor temperature and run a simulation.  Check the location of the neutral pressure level.  For a building with uniform leakage, it should be at about mid-height.  It will usually be a bit higher if you have roof leakage but no floor leakage.  However, if you find the neutral pressure level is very high or very low, it could indicate large unintended leaks – look for these somewhere near the neutral pressure level.
2.)	Do this only if modeling wind.  Specify wind and wind pressure profiles.  Perform the following test:
a.	Run a simulation with no stack effect, no mechanical system, and a high wind.  You should see flow through each exterior path.  This allows you to quickly identify paths you may have missed.
b.	Verify that you have inflow on the windward side, and outflow on the leeward side, and most likely a smaller outflow on the sides and roof (depends on the pressure profile you use).  This helps you verify that the pressure profile is correctly input and that you have oriented the building and wind properly.
3.)	Input the air handling system(s):  
a.	Run a simulation and check the OA, RA, and XA volumes to verify that the outside air is properly defined.
b.	Also verify that the pressure difference across walls is realistic.  For example, a 50 Pa pressure difference would not occur in a real building, and probably points to problems with either the system or leakage input.  You may need to adjust the model.  
4.)	Input contaminants:
a.	Once you’ve verified that the system is working properly, the contaminants can go in and should distribute as you expect.  Verify.
5.)	Modeling:  I often model ranges of some variables.  Some thoughts:
a.	Leakage:  You might try a range of values to verify that your conclusions aren’t too leakage-dependent.  If they are and you don’t have leakage test data, then you’ll need to report a results range.
b.	System pressure balance:  If a building has multiple air handling systems, their design flow rates may imply perfect balance between the systems.  However, the balance will never be perfect.  This can drive contaminants into shafts and distribute them through the building.  It can be helpful to pressurize or depressurize a floor slightly with respect to others (by specifying slightly imbalanced system flows) to see how big this effect is.
c.	Weather effects:  particularly if you are trying to maintain a pressure differential somewhere in your system, you’ll want to verify that it can accomodate the expected range of outdoor conditions.
