# glr-2024e-bms

Our Battery Management System, using STM32 NUCLEO-G474RE, ADBMS6830, ADBMS2950 and ADBMS6822.

Needed requirements for BMS, based on FSG rules:
* Monitoring when LV system is enabled
* Monitoring when charging
  * Balancing to be implemented in software
* Measure voltage of all cells
  * Open sdc if critical voltage by manufacturer for 500ms
  	* Notice accuracy, noise and sample rate
  * Check of wire break for voltage measure
  * One wire must be individually disconnectable for inspection
* Measure current of tractive system
  * Open sdc if critical current for 500ms
  	* Notice accuracy, noise and sample rate
* Measure temperature of 30% of cells
  * Open sdc if critical temperature by manufacturer for 1s
  	* Notice accuracy, noise and sample rate
  * Check of wire break for temperature measure
  * 60°C max temperature
  * One wire must be individually disconnectable for inspection
* Independent cell measure by event
* At all times it must be possible to read and view all values in a overview (laptop / maybe steering display?)


States:
LV off -> bms off
LV on -> bms monitoring
LV on and charging possible -> bms balancing & monitoring
Charging impossible when LV off


Needed requirements for charging:
* even more
