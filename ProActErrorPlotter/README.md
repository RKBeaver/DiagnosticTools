## Function

These scripts take feedback data from Woodward ProAct throttle actuators, either via DiaSys or directly off the CAN network, manipulates it and then plots the calculated error. 

## Hardware

I am using a PEAK CAN FD Interface. The program has been written with this solely in mind. 

## Collecting & Exporting Data via DiaSys

The ProActs report onto the CAN their desired and actual positions every 100ms. 

DiaSys connects to the ECU which relays messages from the "internal" CAN bus. 

Therefore you want to try and keep the sample period for any DiaSys recording below 100ms. 

Inevitably there will be some data lost as the ProAct broadcast time and ECU-DiaSys sample time will come in and out of phase. 

Ensure that the following ID's are recorded

```
1__1_4550_003_A___Desired_Valve_Position

1__1_4550_002_A___Actual_Valve_Position

1__1_4550_103_B___Desired_Valve_Position

1__1_4550_102_B___Actual_Valve_Position
```


### Exporting a Saved DiaSys Recording

In the DiaSys Available functions menu -

Export measuring data. 

Select the desired saved recording.

Select the following available sensors - 
```
1__1_4550_003_A___Desired_Valve_Position

1__1_4550_002_A___Actual_Valve_Position

1__1_4550_103_B___Desired_Valve_Position

1__1_4550_102_B___Actual_Valve_Position
```

Export to Uniplot - Set to Off.

Sampling time - Set "Sampling time:" to 100ms. 

Click Save As

Select the Save as type: filetype as "Microsoft Text Driver". 

I find it works best if I save to the main directory of a USB memory stick. 

Ensure you define the filetype as .csv when typing in the filename. 

Click Save

Click Ok

Copy the exported CSV file into the CSVInputFiles folder within the ProAct Error - DiaSys folder. 

## Collecting Data via CAN

MTU CAN network operates at 250Kbit/s. To clarify this is not the same CAN network you connect to when using DiaSys. You want to connect to the inner network between the ECU, ProActs, TecJet, AKC, Ignition etc. 
The proprietary CAN network in the Cummins QSK60 operates at 500Kbits/s. 

Its important that when you connect to either network that your interface is set to passive (listen only/no transmission). The scripts are set to do this automatically for Peak interfaces

Select the relevant script depending on the engine you're connected to. The MTU script will automatically adjust for reading from a single throttle V8 variant and the twin throttle V12 - V20 variants. 

Upon running the script you will be prompted for a filename as well as a desired recording duration in mins. Once inputted the script will just run until that duration has been fulfilled. 
The program outputs a percentage status update. 


## Plotting the Collected Data

Both plotting scripts are designed to be easily operated. 

When ran both will prompt you to select the file to be processed and give you the option of defining the title. 

Both scripts will output into their respective OutputPlots folder as a PDF. 

I have found that the formatting that works as a PDF does not render correctly within the Jupyter instance within VScode. 

