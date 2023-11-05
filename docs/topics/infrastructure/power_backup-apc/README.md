Sourced: https://www.reddit.com/r/homelab/comments/14o22ep/what_ups_are_you_using/

Pure sine wave is what you want. Preferably a double conversion or "online" UPS. Line interactive is also acceptable for most use.

Double conversion completely isolates input and creates a clean output. These handle 9 types of power problems. These are pure sine wave.

Line interactive has step up and step down capability to deal with high and low utility, but the output is a cleaned up input. These cover 5 types of power issues. These are usually pure sine wave.

Standby UPS, normally what you get with the cheap $40 300va Walmart specials is the worst of the bunch. These still have some use and cover 3 power problems. These are rarely pure sine wave.

Ideally you should load a UPS to 25-50% of it's rating. Need headroom for start currents, high demand periods, etc.


Q: 
Do you have a list of the 9 problems you mention? Would be interested to read.

A: 
Power failure, power sag, power surge, under voltage, over voltage, line noise, frequency variation, switching transient and harmonic distortion.

If you browse Eaton UPSs, every model starts with a 3, 5 or 9. This immediately identifies the UPS architecture used.

They're listed in order, so a line interactive can handle the first 5 issues and a standby can do the first 3.

Anything it can't handle is either passed through to the load or sends the UPS to battery mode.

9 power failure
Sourced:
https://www.eaton.com/us/en-us/products/backup-power-ups-surge-it-power-distribution/backup-power-ups/9-common-power-problems.html