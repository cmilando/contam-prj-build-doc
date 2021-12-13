Air handling systems
=================================

Setup
---------------------------
* Each household has its own AHS
* Each zone that has a supply also needs a return (unless you make it a plenum, see auxillary notes)
* Position of AHS icon doesn’t matter
* Add a MERV filter for both recirculation and Outside Air
* Doesn’t matter what the flows are in CONTAM, EnergyPlus sets these
* Don’t set a schedule!

.. note::

   To make a project with dedicated HVAC (e.g., a window AC or baseboard heating), just remove the filter from the HVAC system.

Exhaust systems
--------------------------
* The kitchen and bathroom have exhaust systems
* These ahs must be named “exh_” for the 3D exporter to work
* No filter
* And just have a return in each of the specific rooms

Air handling system:  In most cases you will want to use a simple air handling system.  This does not allow you to model pressure drops in ductwork sections and fittings.  However, you can (sort of) account for duct leakage using a simple system by estimating the amount of leakage, and inserting a supply or return outlet in the appropriate plenum or space.  

For an AHU, CONTAM uses three criteria to determine the amount of outside air. First, the supply air must be made up of a mix of outside air and return air.  If there isn’t enough return air specified for an AHU (because you may be pressurizing the building), the amount of outside air will be increased to get the desired supply air volume.  Second, if you set a “minimum outside air flow”, the amount of outside air will never fall below this value, regardless of what your schedule says. Personally, I find it easiest to leave this minimum at zero and schedule what I want with my schedule.  However, the minimum can be useful if you are using feedback controls (such as carbon dioxide demand control) and want to set a minimum.  Finally, you must schedule the outside air.  The default schedule (“none”) is an “always on 100%” schedule.  So, if you don’t specify a schedule you’ll get 100% outside air all the time.  

After you have specified the AHU, it’s good to run a simulation and verify the flow rates of OA, RA, and XA (outdoor, return, exhaust) on the lower left hand corner of the screen when you place the cursor on the air handling unit.  
