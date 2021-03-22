# Estimation of error in the ultrasonic sensor HC-SR504

The datasheet for this sensor is not very complete. It claims a maximum range
of 4m, but the area of the blocks is smaller than what they suggest, and there
is no data for this use case. Based on the [suggestions of the
demonstrator](https://www.vle.cam.ac.uk/mod/hsuforum/discuss.php?d=46792) it is
assumed here that the maximum range is 1m.

Given that the ATMega4809 is able to time pulses in hardware (based on stopping
a counter in hardware on an interrupt), the uncertainty due to accurate time
measurement can be safely ignored. The uncertainty in the sensor itself is 3mm
from the datasheet, and adding a decent helping of random noise and so on, it
is estimated here that the maximum uncertainty is 10mm.
