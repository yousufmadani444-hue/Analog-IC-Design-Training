# Five Days Hands-on Training Program 

## Session 1

### MOSFET Regions of Operation

The session began with a discussion of the regions of operation of a MOSFET, focusing on the voltage conditions required for cutoff, triode, and saturation regions. The relationship between the gate-to-source voltage (VGS), drain-to-source voltage (VDS), and threshold voltage (VTH) was analyzed to understand how a MOSFET transitions from acting as a voltage-dependent resistor to behaving as a current source.
For a MOSFET to operate in the saturation region, the following conditions must be satisfied:
VGS > VTH  
VDS ≥ VOV, where VOV = VGS − VTH  
Under these conditions, the channel pinches off near the drain and the drain current becomes primarily controlled by the gate-to-source voltage.  
The drain current of a MOSFET operating in the saturation region can be expressed as:

ID = (1/2) μn Cox (W/L) (VGS − VTH)² (1 + λVDS)

In an ideal long-channel device, the drain current is independent of VDS once saturation is achieved. However, practical MOSFETs exhibit channel-length modulation, where an increase in VDS causes the effective channel length to reduce due to movement of the pinch-off point toward the source.

The term (1 + λVDS) accounts for this non-ideal behavior, introducing a finite output resistance and causing the drain current to increase slightly with VDS even in saturation.



