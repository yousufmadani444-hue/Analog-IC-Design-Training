# Session 1  
In day 1 we had designed a cs amp using a resistor. In Day 2 we started of with replacing the resistor with a diode connected pmos and analysied the circuit.  

## Circuit 2  

A cs amp with diode connected pmos as the load.  

### Design  

<img width="521" height="646" alt="mos_circuit" src="https://github.com/user-attachments/assets/0eca338e-739e-4f94-a83c-7592aea0309e" />  

The circuit 2 was designed as above by replacing the resistor with a diode connected pmos load.  

### Analysis  

DC Analysis  

<img width="521" height="646" alt="mos_circuit" src="https://github.com/user-attachments/assets/bef80220-64f2-4ae0-b893-920a1754b696" />  

The above image shows the dc operating points of the circuit with current 2uamp flowing in the circuit.  

Transient Analysis  

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/f5af50d8-05f3-4909-b58d-251e8e1d3992" />  

 AC Analysis  

 <img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/dec2a328-cce8-44fa-89c3-125eface7690" />  

 From the above analysis of the Circuit 2 we understand that the bandwidth as increased in comparision with the previous circuit of day 1 but the gain is still less so we move on to the another ciruit with load as pmos not diode connected.  

 ## Circuit 3  

 A CS amp with pmos as the load. 

### Design  

<img width="1277" height="716" alt="image" src="https://github.com/user-attachments/assets/8cd39cb2-b92a-4701-88c9-d0a02880e836" />  

When the analysis for the above circuit was done the Gain obtained was quite larger than the gain of the previous circuit.  

## Circuit 4  

A MOS differential amplifier was implemented using NMOS input transistors with a PMOS current mirror active load. A constant tail current source biases the differential pair, enabling differential input operation.  

### Design  

<img width="416" height="209" alt="image" src="https://github.com/user-attachments/assets/1d8b7d88-9c38-4e10-8e60-2ec44765bda6" />  

### Analysis  

Dc Analysis  

<img width="416" height="209" alt="image" src="https://github.com/user-attachments/assets/1d8b7d88-9c38-4e10-8e60-2ec44765bda6" />  

Transient Analysis  

<img width="716" height="287" alt="image" src="https://github.com/user-attachments/assets/a260ba0e-d856-4216-82f8-10e63d1ffaa2" />  

Using the above circuit replace the input and the output voltage sources with ports to create a symbol of the above differential amplifier and store the symbol in our created library.  

<img width="599" height="302" alt="image" src="https://github.com/user-attachments/assets/a6bbde43-d53c-476a-92b7-8912e0b305ce" />  

After replacing the sources by the ports we create the symbol for the whole differential pair and add to our library and then open a new cell view to use the created symbol. After obtaing the symbol we ready to use the differential pair which avoids the burden of building the whole circuit.  


<img width="530" height="278" alt="image" src="https://github.com/user-attachments/assets/bab31fcb-7981-44a5-a146-beb182dce8c1" />

We then connect the voltage sources and then as required and analyse the differentila pair.  

<img width="509" height="246" alt="image" src="https://github.com/user-attachments/assets/e3f5018c-b6a4-42dc-a094-15af84c38f3b" />  

In Day 2 we learnt about:  
1. Variation of gain for various configuration of the circuits by varying the load of the amplifier.
2. Designed and implemented the differential mos.
3. Created a symbol for the differential mos.







 

  








