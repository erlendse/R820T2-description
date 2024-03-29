# IF Calibrate
Requires: Cali-clock, cali-trigger
Gives: cal-code

To verify? mixer LO is divided down by a given ratio and filters are adjusted to get a given drop in signal level.
Final filter bandwidth may be dependent of tuned frequency! Try to force different cal-codes.

# Image reject:
Image reject is done via a quadrature mixer and polyphase filter

Connect ring-osc to mixer input (via tracking filter), and try to cancel out the image by tuning so the ring-osc is in the image frequency. 
Driver uses a complex pattern of many levels and frequencies, not fully figured out.


# IF filter plotting:
Activate ring-osc, mixer src=ring osc, set a single frequency
step(1 kHz or less) the LO while obsering ADC (pdet3)

# Quick tune:
The PLL autoselects one of two VCO cores, and a tuning band on the selected core.

The core & band selections can be mapped out in advance if quick tuning is desired (and charge pump current increased)

# Tuner AGC:
LNA(wideband) & MIXER (narrowband) have a detector gain setting, + lower and upper thresholds for detector voltage before gain steps up or down.

![block diagram](r820t-diagram.png)

The gain steps are clocked by a selectiable clock

The VGA amplifier have control via external voltage (or register setting)

See also:
https://github.com/wizardyesterday/RtlSdrDiags/tree/master/doc/agcResearch
