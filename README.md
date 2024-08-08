## Diagnostic Tools

This repository contains a selection of the Python scipts and functions I've developed for processing data from primarily a PicoScope oscilliscope and DiaSys (an engine interface software)

### Incylinder Pressure Comparator

This script processes a 2 channel recording of a pressure measurement from within the cylinder of a natural gas spark ignition engine taken during a dry crank. 
    
The scipt converts the recording from the time domain to the angle (Crankangle) domain and attempts to highlight any potential issues with lack of compression, air charge mass loss and valve timing. 

The script is able to process and phase multiple recordings together so that direct comparisons can be quickly made between different cylinders and the same cylinder over time. 