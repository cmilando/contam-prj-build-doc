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

