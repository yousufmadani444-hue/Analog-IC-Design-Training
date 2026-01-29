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

When VDS is reduced below the overdrive voltage (VOV = VGS − VTH), the MOSFET operates in the triode region. In this region, a continuous channel exists between source and drain, and the drain current depends on both VGS and VDS.

The drain current in the triode region is given by:

ID = (1/2) μn Cox (W/L) [ 2(VGS − VTH) VDS − VDS² ]

As VDS is further reduced such that VDS ≪ 2(VGS − VTH), the quadratic term becomes negligible. Under this deep triode condition, the MOSFET behaves as a voltage-controlled resistor, and the drain current simplifies to:

ID ≈ μn Cox (W/L) (VGS − VTH) VDS

The corresponding on-resistance is:

Ron = 1 / [ μn Cox (W/L) (VGS − VTH) ]

### Mixed Signal IC Design

A mixed signal refers to a system where continuous analog signals and discrete digital signals coexist and interact. Such systems require both analog processing and digital control or computation. Mixed-signal ICs integrate analog and digital circuits on a single chip, allowing continuous real-world signals to be sensed, processed, and controlled using digital logic.  

In a mixed-signal IC, certain analog blocks form the foundation for reliable system operation. Among these, the Low Dropout Regulator (LDO), Phase-Locked Loop (PLL), and Bandgap Reference (BGR) are considered the most critical components. The BGR provides a stable reference voltage or current that is largely independent of process, voltage, and temperature variations. LDOs use this reference to generate clean and regulated supply voltages for different on-chip blocks, while PLLs rely on stable references and low-noise supplies to generate accurate and low-jitter clock signals.  

Despite integrating both analog and digital circuitry on a single chip, mixed-signal ICs face several fundamental challenges. The supply voltage can vary due to battery conditions, load changes, and temperature fluctuations, while digital switching activity injects noise into sensitive analog blocks. Additionally, transistor characteristics vary with temperature, and manufacturing process variations cause shifts in key device parameters. These combined effects make it difficult to achieve stable and predictable circuit behavior without dedicated reference, regulation, and timing circuits.

### Bandgap Reference (BGR)

A Bandgap Reference (BGR) is a fundamental analog building block used to generate a stable reference voltage or current that is largely independent of temperature, supply voltage, and process variations. This reference forms the backbone for biasing circuits, LDOs, ADCs, DACs, and PLLs in mixed-signal integrated circuits.

#### Need for a Temperature-Independent Reference
Transistor parameters such as threshold voltage, carrier mobility, and junction voltages vary significantly with temperature. Simple voltage references based on a single device, such as a diode or transistor junction, exhibit strong temperature dependence and are therefore unsuitable for precision analog systems. To ensure reliable and predictable circuit operation across a wide temperature range, a temperature-independent reference is required.

#### CTAT Voltage
The base–emitter voltage (VBE) of a bipolar junction transistor (BJT) decreases with increasing temperature, exhibiting a negative temperature coefficient (CTAT). At room temperature, VBE typically decreases at a rate of approximately −1.5 mV/°C. This predictable temperature behavior makes VBE a useful CTAT voltage component in reference generation.

#### PTAT Voltage
When two identical BJTs operate at different current densities, the difference between their base–emitter voltages (ΔVBE) is proportional to absolute temperature (PTAT). This voltage can be expressed as VT ln(n), where VT is the thermal voltage and n represents the ratio of current densities or emitter areas. Unlike VBE, this PTAT voltage increases linearly with temperature and is largely independent of absolute device parameters.

#### Generation of Temperature-Independent Reference Voltage
A temperature-independent reference voltage is obtained by combining a CTAT voltage (VBE) with a scaled PTAT voltage (ΔVBE). By properly weighting and summing these two voltages, the negative temperature coefficient of VBE cancels the positive temperature coefficient of the PTAT term. The resulting reference voltage exhibits a near-zero overall temperature coefficient and settles around the silicon bandgap voltage, approximately 1.2 V.

#### Importance of BJTs in Bandgap References
BJTs play a crucial role in bandgap reference circuits due to their well-defined exponential current–voltage relationship and highly predictable temperature behavior. The generation of accurate CTAT and PTAT voltages relies on the physical properties of BJTs, which are superior to MOSFETs for this purpose. As a result, even in CMOS technologies, parasitic or vertical BJTs are commonly used in bandgap reference implementations.  

## Session 2  

### Design and analysis of simple cs amplifier using Cadence Virtuoso  

### Objective

To gain practical hands-on experience with Cadence Virtuoso by creating a custom design library, developing a new cell and its associated views, and implementing a Common Source (CS) amplifier. This exercise aims to build familiarity with the Cadence design environment, standard libraries, and basic analog components, while understanding the complete workflow from library setup to schematic-level circuit design.  

### Design  

<img width="1600" height="900" alt="circuit" src="https://github.com/user-attachments/assets/b66cacb7-7486-4ba0-b39d-5222ba166757" />  

A simple cs circuit is designed by giving a sinusoidal input at the gate terminal with bias voltage.

### Analysis  

We can perform 3 types of analysis on this circuit  
1. DC Analysis
2. AC Analysis
3. Transient Response

#### DC Analysis  

<img width="1600" height="900" alt="dcoppoint" src="https://github.com/user-attachments/assets/62c3d71d-6c2a-403c-a463-6065370f32c6" />  

First we perform the dc analysis. The procedure followed is as follows:  
1. Launch the adel window
2. Select analysis
3. In analysis choose dc
4. Select save dc operating point
5. Click ok
6. Select output option
7. In that select to be plotted
8. In the circuit label the input and the output voltages and select them to plot
9. Run

By following the above steps we will be able to obtain the above dc operating points on the figure.  
Similarly we are able to plot the dc sweep by selecting variable option in dc dialogue box in the adel window, we have done two sweep plots in the dc analysis one is the Rd sweep and another is the Vb sweep.  

Rd sweep  
<img width="1600" height="900" alt="dcsweeprd" src="https://github.com/user-attachments/assets/19315c05-e514-4021-a4a1-fad20c22d3c7" />  

Vb sweep  
<img width="1600" height="900" alt="dcsweepvb" src="https://github.com/user-attachments/assets/f62483c4-1e2b-446f-855d-d60ddd24de46" />  

### Tran Analysis  

<img width="1600" height="900" alt="tran" src="https://github.com/user-attachments/assets/af494d70-7ad8-4970-a0f1-fe1024543848" />  

The above plot is for the transient analysis of the cs amp circuit i.e Vout and Vin plots.  
The steps for the above plot are as follows:  
1. Open the ADE L window.
2. Select Analysis.
3. In that choose tran.
4. In the new dialogue box set stop time to be 5m.
5. Click ok and then Run the simulation.

By following the above steps we were able to obtain the above plot of Vout and Vin.  

### AC Analysis  

<img width="1600" height="900" alt="ac" src="https://github.com/user-attachments/assets/9b4f86c2-1755-45aa-9223-a7b840de1876" />  

It is the freq response plot of the cs amp circuit.  
To Obtain the above plot we followed the following steps:  
1. Open the ADE L window.
2. Select Analysis.
3. Choose AC, a new window opens.
4. In the window set start and stop frequency as 0.1 to 100G and vary the stop frequency accordingly to obtain a detailed plot.
5. Select no of points as 10.
6. Select logorithmic.
7. Click ok and Run the simulation.

By following the above steps we were able to obtain the above plot.  

### Parametric Analysis  

<img width="1600" height="900" alt="paraanalysis" src="https://github.com/user-attachments/assets/90aae3b7-4d61-44e4-b57a-62dfe995ca97" />  

Parametric analysis was carried out by varying circuit parameters such as bias voltage and load resistance to study their effect on output voltage.
















