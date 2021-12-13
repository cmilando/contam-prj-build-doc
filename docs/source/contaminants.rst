Indoor contaminants
============================================

PM2.5
--------------------
* Add contaminants, source and sink objects
* Use the CTM file for ambient
* Every room has a PM sink (first order deposition)
* Every room has ambient sink, on top of the stack
* Kitchen has a PM source, which has Cooking_sch
* Living room has ETS source, which has ETS schedule (Smoker 2pr hr 7d)
* Make different species for ambient and from different apartments, and for different sources

* Makes sense to make everything on one floor with all sources, then copy up, then delete
* Make supersink elements for this

NO2
-------------------------
* Sources
* Cooking sch
* 56 ug/s
* Sinks
* 0.87/hr deposition rate

Infectious virus
----------------------------
* Need to be doing this as well
* Sources
* breathing
* Sinks
* Deposition
* RH reaction?

Contaminants:  The “molecular weight” doesn’t make a lot of sense for bacteria or spores, where you usually want to get a count.  Molecular weight is only used by the calculation to convert between volume and mass units – the program allows you to specify volume units but works in mass units.  What you can do is specify a count in mass units (for example, specify that one colony forming unit is equal to one mg/kg), and then conduct your simulation.  Your results will then be in terms of the unit you want.  The program will still require a molecular weight, buy you can specify any number since it isn’t used.  Also, I recommend a “trace” contaminant simulation for most purposes.  Non-trace contaminants (for example, water vapor) are present in such large quantities that they change the density of air.
