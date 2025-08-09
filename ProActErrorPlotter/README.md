# Function

These programs take feedback data from Woodward ProAct throttle actuators, either via DiaSys or directly off the CAN network, manipulates it and plots the calculated error. 

# Hardware

I am using a PEAK CAN FD Interface. The program has been written with this soley in mind. 

# Collecting & Exporting from DiaSys

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


## Exporting a Saved DiaSys Recording

In the DiaSys Avilable functions menu -
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
Sampling time - Set "!Sampling time:" to 100ms. 
Click Save As
Select the Save as type: filetype as "Microsoft Text Driver". 
I find it works best if I save to the main dictionary in a USB drive. 
Ensure you define the filetype as .csv when typing in the filename. 
Click Save
Click Ok


 
