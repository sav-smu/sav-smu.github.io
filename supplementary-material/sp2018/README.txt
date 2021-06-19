==============
SWaT Simulator
==============

This is our software for simulating the Secure Water Treatment testbed (SWaT) system located at the Singapore University of Technology and Design, under iTrust.

The software should contain three blocks from the top level: (1) the PLC logic; (2) the HMI, or the SCADA module; and (3) the plant model.

The SWaT system has 6 PLCs, each connected to the HMI with a star structure. The plant is also divided into 6 phases, and communicate exclusively with a PLC in both ways.

The main function of this software is swat.py: you can run it by typing:

	python swat.py
	
in a terminal.

The structure of this software is as follows:

1. The IO.py file instantiates the input output classes for communication between PLC and plant.
2. The SCADA.py file instantiates the input output classes for communication between PLC and HMI.
3. The plc/ directory contains 6 PLC classes files.
4. The HMI/ directory contains HMI classes to support SCADA.py.
5. The controlblocks/ directory contains PLC subfunction classes to support building the PLC classes.
6. The io_plc/ directory contains classes to support IO.py.
7. The logicblock/ directory contains useful functions like Timers and Alarms used in PLC class.
8. The plant_ode/ directory contains the plant model. You can change initial configurations manually here.

The simulation period is 5ms, same as the SWaT system.

================
Pre-requirements
================

python version 2.7
scipy
numpy

=======
Contact
=======

Please contact CHEN Yuqi (yuqi_chen@mymail.sutd.edu.sg) with any questions regarding this software.

=============
Release Notes
=============

Dated Jan 16th, 2016, in this version, we play with some test plants, and check our results with Eunsuk's trajectory prediction model. --PF

Dated Jan 22nd, 2016. 
Spotted that the scaling function SCL and w_li scales the level reading incorrectly, which result in HMI.LIT101.AL to be 0, which results in PLC.Mid_MV101_AutoInp to be 0. Commented out the HMI.PLANT.Ready for PLCs 2-6

Dated Jan 25th, 2016
Fixed scaling problem completely.
Fixed unit problem.
Raise exception SETD intake 1 and 1, need to fix.
Tank 101 and Tank 301 functioning.

Dated Jan 26th, 2016
We need to check SETD logic block, which one has higher priority, the set input or the unset input?
Changed condition for tank 301 to accumulate water in plant.py and worked as charm.

Dated Feb 1st, 2016
Located HMI.MV201.Status != 2
Controlblock/AIN commented out the "#self.Hty =  Mid_Inst_Hty and (Mid_Raw  >  Mid_L_Raw) and (Mid_Raw < Mid_H_Raw) " , this sentence generates unhealthy and inturn make permissive for P101 not good, it's because preset value issue in function block for scaling, need to check with code in SWaT lab, now it's commented out and temporarily good.
Simulation with all tank level init to be 200 mm, for 2 hours, tank 101 be 1000, tank 301 be 980 and all stable.

Dated Feb 3rd, 2016
Interesting qustion! Due the lack of case statement in python, we used to adopt if-elif-else structure. But it's proved that this structure causes problems when too many elifs or blank lines. Now new class and function is added in logicblock/. Now we can use case sturcture like in PLC3
PLC3 for the P301 and P302, corrected problem of AutoInp
HMI.P3.TMP_High is one of the kind, I'm putting the value to 0, maybe it comes from user.

Dated Feb 4th, 2016
if-elif-else clause caused us another problem in plant_ode/. Now it's solved, temporarily comment out PLC5, some unmentioned HMI attributes.
*******************************************************************************************************************************
Good news! The whole system is now functioning, still need to fix PLC5 but the bugs should be same as that in PLC3 and other.
Now the system is able to run LIT101,LIT301,LIT401,LIT602, only left LIT601
*******************************************************************************************************************************

Dated Feb 15th, 2016
Changed PLC5 to case structure. Added at the end of case structure break clause. Need to test how it works
SUCCESS!!
All 5 tank levels are changing as expected during the simulation.


Dated Jan 1st, 2017
Added the logic related to the critical values.
