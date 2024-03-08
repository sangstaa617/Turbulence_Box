This code controls the 64 speakers in the turbulence box. 
It uses a LabJack U6 to generate a digital square wave and LJTick DAC to send an analog signal to the speakers. 
The minimum update time is limited by the LJtickDACs and totals ~11.5 ms, meaning the maximum frequency when all the DACs are being used is ~45 Hz
The default amplitude is 5 V which generates ~23 V P2P 25 V is the calculated maximum for the speakers.
The duration of the test is a user input.
The three modes for the code are Random, Linear, and Constant.

  Random: 
    - the frequency is randomly selected with a 50% chance of ~45 Hz, 25% chance of ~22.5 Hz, 12.5% chance of ~15 Hz, and a 12.5% chance of ~11.25 Hz
    - The number of periods a specicific frequency completes is selected from a gaussian distribution based on a given mean, stdev, min, and max
    
  Linear:
    - The frequency is distributed linearly from ~45 Hz to ~11.25 Hz between the 16 DACs
    
  Constant:
    - A constant frequency is selected and sent to all DACs 
