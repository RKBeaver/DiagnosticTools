### Description

This script processes a 2 channel recording of a pressure measurement from within the cylinder of a natural gas spark ignition engine taken during a dry crank. 
    
The scipt converts the recording from the time domain to the angle (Crankangle) domain and attempts to highlight any potential issues with lack of compression, air charge mass loss and valve timing. 

The script is able to process and phase multiple recordings together so that direct comparisons can be quickly made between different cylinders and the same cylinder over time. 


### Notes

The Matlab file is generated by PicoScope 6 or 7 from a 2 channel recording. 

The PicoScope setting file is included within the git with the standard recording settings I use.  
Depending on cranking speed the time domain might need to be adjusted. 

Channel A = Incylinder Pressure Sensor.   
Channel B = Crankshaft Flywheel Pickup Signal. 

The number of crankteeth is defined in the first section of the script.   
The script will not work with a n+1 tooth arrangement, ie the crankshaft pickup signal must not contain a missing tooth. 

For reference:-
MTU 4000 Series - 182 teeth

I have found that if after taking the recording you apply any filters or carry out any math functions within Picoscope the Matlab file generation can often get corrupted. 

Copy the Matlab file into the Input folder. 