# Ultrasonic HC-SR504
The datasheet for this sensor is not very complete. It claims a maximum range
of 4m, but the area of the blocks is smaller than what they suggest, and there
is no data for this use case. Based on the [suggestions of the
demonstrator](https://www.vle.cam.ac.uk/mod/hsuforum/discuss.php?d=46792) it is
assumed here that the maximum range is 1.5m.

The clock speed of the ATMega4809 ADC is 16MHz, so a reasonable estimate of the
speed at which we can read IO might be 10$\mu$s. So our uncertainty from
digital IO might be (340m/s)\*10us = 3.4mm. Adding the 3mm resolution specified
on the datasheet, and a decent helping of random noise and so on, I have
estimated here a maximum uncertainty of +/- 10mm, dropping a bit with distance
to the block.
