Tests
====================

Blower door test
----------------------------
* Change wall_ext, wall_int, wall_inter-apt, floor, and roof to 10 cm2/m2
* Close all openings
* Run blower door test at PA = 4
* Copy into spreadsheet and change calculated surface area to match that of current building
* You should get back 9.999 cm2/m2
* If not, likely errors are:
* The wall area or height isn’t correct for wall_ext
* Gable is open, window is open, door is open
* Missing a floor or roof leak
* One element isn’t 10 cm2/m2

Steady state airflow
----------------------------
* Provides a general view of interzone airflows including SAHS supply and return
* Stack effect test:
* Set ambient to 0 degC (indoor = 20 C)
* Turn all AHS schedules to Off
* Run SS simulation and check envelope flows exhibit stack flow pattern
* Should be no flows through closed windows or doors

Transient
-----------------------------
* Run at least 2 weeks
* Allows the use of RESTART file in coupled simulations
* Runs a building check to test definition of PRJ
* Provides other checks

Reset prior to running
------------------------------
* Transient
* Contaminants to transient
* Reset flow elements to correct leakage
* Adjust the start and end dates
* Turn ahs back on
* Adjust the output and calculation timesteps (every 5 min)
* Use the RESTART file
