# Intel CKT Training

## Table of contents
* [Day 1 - Fundamentals of VLSI Design and overview of Sand-to-Silicon ]
* [Day 2 - Details of IC Manufacturing Process ]
* [Day 3 - CMOS Fabrication Process in Deep Submicron (DSM) and Ultra Deep Submicron (UDSM) Technology ]
* [Day 4 - Metal Oxide Semiconductor Structure ]



## Day 1
### Topic - Fundamentals of VLSI Design and overview of Sand-to-Silicon
<Details>
 <summary>Theory</summary>
 
### Theory 
**Overview of VLSI Design: Chip to Wafer**
* **Packaged Chip**  
  -Packaging of silicon die with plastic case to protect the die
  
  ![image](https://user-images.githubusercontent.com/122186991/212478650-40506d24-266b-4382-9968-a343234c3cae.png)
  
  * The central part of the chip is called die
  * Evolution of packaged chip 
  
  ![image](https://user-images.githubusercontent.com/122186991/212478776-d4e8e7b9-f636-416c-a0a1-4763cd70c36a.png)

  * Examples types of packaging:
    * System in a package (SIP)
    * Dual in-line package (DIP)
    * Quad-flat no-leads (QFN)
    * Ball grid array (BGA)
 

  * **Die and Wafer** 
    * Size is generally 1mmx1mm or 1mmx2mm
    * Made from a wafer which every single wafer consists of many die
    * Wafer diameter around 12inch ~ 300mm
  
    * **Inside the die:**  
  ![image](https://user-images.githubusercontent.com/121994033/210920544-118c0d99-ec97-4fcf-a49a-5fb883793df9.png)
      * Digital  
        Consists of Gates, Muxes, Decoders, Counters, Resistors, FSMs etc which all are made by standard cells using semi custom VLSI design flow.
      * Analog and RF
        * Consists of Clock: VCO and PLL; Voltage Ref. and Reg.: Bandgap reference, LDO, DC-DC converter; Data: PRBS generator; Amplifiers and Filters;  
          Interfaces: ADC and DAC  
        * All are made using custom VLSI flow  
      * Memory and Memory Controller  
        Consists of Static Random Access Memory (SRAM) and SRAM controller
     * **Moore's Law**
        *Moore's Law states that the number of transistors on a microchip doubles about every two years, though the cost of computers is halved.
        *In 1965, Gordon E. Moore, the co-founder of Intel, made this observation that became known as Moore's Law.
        ![image](https://user-images.githubusercontent.com/122186991/212529460-fea92745-a42b-4ed8-ba44-430f296fc23d.png)
  
  **VLSI Design Methodology**
    * **FPGA Based Design**
      * Faster prototyping and cost-effective
      * A typical FPGA chip consists,
        * Input/output buffers
        * Array of configurable logic blocks (CLBs)
        * Programmable interconnect structures
      * The programming of interconnects is accomplished by programming of RAM
      * Signal routing between the CLBs and the I/O blocks made by configurable switching matrice
    * **ASIC Design**
      * **Standard cell based design**
        * most prevalent full-custom design styles and requires development of a full-custom mask set.
        * commonly used logic cells are developed, characterized, and stored in a standard-cell library.
        * constant height for all cells in a same technology
        * can have several version for different fan-out driving capability

      * **Full custom design**
        * done without any library by designers
        * layouts, orientation, placement of transistor done by designers
        * developement cost is high
        * all analog and RF designs are full custom design
  
  **VLSI Design Quality**  
    * **Testability**  
      Design of testable chip  
    * **Yield and Manufacturability**  
      Yield: No. of tested of chips/Total no. of Chips    
      Functional Yield: Checks at lower speed  
      Parametric Yield: Checks at required speed
    * **Reliability**  
      ESD, EOS, Electromigration, Oxide breakdown, Power and ground bouncing, On-chip noise and cross-talk.
    * **Technology Upgradability**  
      Design style must be flexible to technology update so that the design can be use back with minimal cost. 
      Use advanced CAD tools to automatically generate physical layout.
  
  **Package Technology**
    -Chip designers should work closely with package designers to consider various packaging constraints, parasitic, length of bonding wire, no. of bonding pads.  
    * **Classification of Package**  
    * Pin-through-hole (PTH): holes drilled in PCB, not cost effective but soldering process in not inexpensive.
    * Surface Mount Technology (SMT): Directly soldered on the PCB, cost and space effective but expensive equipment's are needed for soldering
    * Plastic: Dominant for many years but it has the disadvantage of being permeable to environmental moisture.
    * Ceramic: Power consumption, performance and environmental requirements
![image](https://user-images.githubusercontent.com/121994033/210987021-f788bed8-7a79-4284-8db6-d7b5e91ada3b.png)

  **CAD Tools**  
  -Execute majority of the computation intensive parts of the design  
  Can be categorized into:
  * High-level synthesis
  * Logic synthesis
  * Circuit optimization
  * Layout
  * Placement and routing
  * Simulation
  * Design rules and checking
  </details>
  
 <Details>
 <summary>Lab</summary>
 
 ### Lab 
 **RC Assignment**  
  * Question 15
  ![image](https://user-images.githubusercontent.com/122186991/212532730-8d76bb1f-0295-4231-8748-06a537a0ed0d.png)
  * Question 16
  ![image](https://user-images.githubusercontent.com/122186991/212532755-b61f00e5-67ff-4268-bd18-9fb4fe39de66.png)
  * Question 17 (a)
  ![image](https://user-images.githubusercontent.com/122186991/212532957-d8754198-f30d-4aa6-af29-c56372ccaa89.png)
  * Question 17 (b)
  ![image](https://user-images.githubusercontent.com/122186991/212532970-65936627-cbaf-4dbb-ab97-61e9cbd9eb0a.png)
  * Question 17 (c)
  ![image](https://user-images.githubusercontent.com/122186991/212532985-25573793-c48c-47c6-b05c-54d69ab8cf27.png)

 </details>

## Day 2
### Topic - Details of IC Manufacturing Process
<details>
 <summary>Theory</summary>
 
### Theory 
**Analog IC Design Process**
![image](https://user-images.githubusercontent.com/122186991/212529891-14d2c0e7-2ca1-4ce0-addc-b7661128fe04.png)

| Electrical Design | Physical Design | Test Design |  
| --- | --- | --- |
| Process of going from the specification to a circuit solution | Process of representing the electrical design in a layout consisting of many distinct geometrical rectangle at various levels | Process of coordinating, planning and implementing the measurement of the analog integrated circuit performance |
| The electrical design requires active and passive device electrical models for creating the design, verifying the design and determining the robustness of the design | The physical design needs entering various geometries, follow DRC, LVS check and parasitic extraction | Types of test: Functional, Parametric, Static, Dynamic |

**Analog IC Design Process and its Relation with CAD and PDK**  
![image](https://user-images.githubusercontent.com/122186991/212529947-b59a3002-63f0-48dd-9488-768563ab57bc.png)

**Role of Circuit Designer**  
  * Circuit designer should always design a practical circuit based on the device limits, technology constraints and physical implementations rather than a ideal circuit
  * Circuit designer should have very good understanding of layout design, so that in less iterations the design can be fridged.
  * Good circuit designer should always discussed with the layout designer for better and efficient circuit design.

**CMOS Technology**  
 *Why CMOS Technology?   
![image](https://user-images.githubusercontent.com/122186991/212530128-86c2e6c2-b292-4dd9-9bc2-d62f3c6d7b82.png)
  
* Comparison made from digital viewpoint will side with CMOS. Since large volume mixed-mode technology will be driven by digital demands, CMOS is an obvious choice.  

**Categorization of the CMOS Technology**  
 * Submicron Technology: Lmin ≥ 0.35 µm
 * Deep Submicron Technology (DSM): 0.1 µm ≤ Lmin ≤ 0.35 µm
 * Ultra-Deep Submicron Technology (UDSM): Lmin ≤ 0.1 µm
 * BiCMOS Technology: Lmin = 0.5 µm
 
 **CMOS Fabrication Process**  
 Process Steps:
 <Details>
 <summary>1. Wafer formation (sand-to-silicon)</summary>  
 
  * The basic raw material used in CMOS fabs is a wafer or disk of silicon, roughly 75 mm to 300 mm (12 inch) in diameter and less than 1 mm thick.  
  * Wafers are cut from boules, cylindrical ingots of singlecrystal silicon, that have been pulled from a crucible of pure molten silicon.  
  * Controlled amounts of impurities are added to the melt to provide the crystal with the required electrical properties.  
  * A seed crystal is dipped into the melt to initiate crystal growth.  
  * The seed is gradually withdrawn vertically from the melt while simultaneously being rotated.  
  * The molten silicon attaches itself to the seed and recrystallizes as it is withdrawn.  
  * The seed withdrawal and rotation rates determine the diameter of the ingot.  
  * Growth rates vary from 30 to 180 mm/hour.
   ![image](https://user-images.githubusercontent.com/122186991/212531647-61112e48-8395-4a97-a4ca-b44d5cf86343.png)

  </details>
  
  <Details>
  <summary>2. Photolithography</summary> 
  
  * The patterning is achieved by a process called photolithography.  
  * The primary method for defining areas of interest (i.e., where we want material to be present or absent) on a wafer is by the use of photoresists.
  * The wafer is coated with the photoresist and subjected to selective illumination through the photomask.
  * A photomask is constructed with chromium (chrome) covered quartz glass. A UV light source is used to expose the photoresist.
  * A developer solvent is then used to dissolve the soluble unexposed photoresist, leaving islands of insoluble exposed photoresist.
    ![image](https://user-images.githubusercontent.com/122186991/212531674-2efa18a0-04f9-4fc8-80c6-861a4947d2c5.png)

   </details>

  <Details>
  <summary>3. Well and Channel Formation</summary>
  
  * N-well process: In a n-well process, the pMOS transistors are built in a n-well and the nMOS transistor is placed in the p-type substrate.
  * P-well process: In a p-well process, the nMOS transistors are built in a p-well and the pMOS transistor is placed in the n-type substrate. p-well processes were used to optimize the pMOS transistor performance.
  * Twin-well process: Twin-well processes accompanied the emergence of n-well processes. A twinwell process allows the optimization of each transistor type.
  * Triple-well process: The triple-well process has emerged to provide good isolation between analog and digital blocks in mixed-signal chips; it is also used to isolate high-density dynamic memory from logic.
  *Differences between types of well: 
    ![image](https://user-images.githubusercontent.com/122186991/212531728-af0ee8a1-575d-4508-a054-b9080b686a89.png)

  </details>
 
  <Details>
  <summary>4. Silicon Dioxide (Sio2) Deposition</summary>
  
  * Oxidation of silicon is achieved by heating silicon wafers in an oxidizing atmosphere. The following are some common approaches:
  * Wet Oxidation: when the oxidizing atmosphere contains water vapor.  
   • The temperature is usually between 900 °C and 1000 °C.  
   • Wet oxidation is a rapid process.  
  * Dry Oxidation: when the oxidizing atmosphere is pure oxygen  
   • Temperatures are in the region of 1200 °C to achieve an acceptable growth rate.  
   • Dry oxidation forms a better quality oxide than wet oxidation.  
   • It is used to form thin, highly controlled gate oxides, while wet oxidation may be used to form thick field oxides.
   * Atomic Layer Deposition (ALD): when a thin chemical layer (material A) is attached to a surface and then a chemical (material B) is introduced to produce a thin layer of the required layer (i.e., SiO2––this can also be used for other various dielectrics and metals).
  </details>
 
  <Details>
  <summary>5. Isolation</summary>

  * Individual devices in a CMOS process need to be isolated from one another so that they do not have unexpected interactions.
  * The transistor gate consists of a thin gate oxide layer.
  * The thick oxide used to be formed by a process called Local Oxidation of Silicon (LOCOS).
  * A problem with LOCOS-based processes is the transition between thick andthin oxide, which extended some distance laterally to form a so-called bird’s beak.
  * Starting around the 0.35 µm node, shallow trench isolation (STI) was introduced to avoid the problems with LOCOS.
  * STI forms insulating trenches of SiO2 surrounding the transistors (everywhere except the active area).
  </details>
 
  <Details>
  <summary>6. Gate Oxide Creation</summary>
  
 * The next step in the process is to form the gate oxide for the transistors. As mentioned, this is most commonly in the form of silicon dioxide (SiO2).The transistor gate consists of a thin gate oxide layer
  </details>
 
  <Details>
  <summary>7. Gate and Source/Drain Formations</summary>
  
  * Grow gate oxide wherever transistors are required (area = source + drain + gate)––elsewhere there will be thick oxide or trench isolation.
  * Deposit polysilicon on chip
  * Pattern polysilicon (both gates and interconnect)
  * Etch exposed gate oxide—i.e., the area of gate oxide where transistors are required that was not covered by polysilicon; at this stage, the chip has windows down to the well or substrate wherever a source/drain diffusion is required
  * Implant pMOS and nMOS source/drain regions
  </details>

 <Details>
 <summary>8. Contacts and Metallization</summary>
 
 * Contact cuts are made to source, drain, and gate according to the contact mask. These are holes etched in the dielectric after the source/drain formation.
 * Older processes commonly use aluminum (Al) for wires, although newer ones offer copper (Cu) for lower resistance.
 * Tungsten (W) can be used as a plug to fill the contact holes (to alleviate problems of aluminum not conforming to small contacts)
 </details>
 
 <Details>
 <summary>9. Passivation</summary>
 
 * The final processing step is to add a protective glass layer called passivation or over glass that prevents the ingress of contaminants.
 * Openings in the passivation layer, called overglass cuts, allow connection to I/O pads and test probe points if needed.
  </details>
  
 <Details>
 <summary>10. Metrology</summary>
 
 * Metrology is the science of measuring. Everything that is built in a semiconductor process has to be measured to give feedback to the manufacturing process.
 </details>

</details>

 <Details>
 <summary>Lab</summary>
[ https://drive.google.com/drive/my-drive](https://drive.google.com/file/d/12-B5kpUTECEOmEQT6COLPabNwM5SaVZY/view?usp=sharing)

</details>
 
## Day 3
### Topic - CMOS Fabrication Process in Deep Submicron(DSM) and Ultra Deep Submicron (UDSM) Technology
<details>
 <summary>Theory</summary>
 
### Theory ###
 
 **Disadvatage of Submicron CMOS**  
 Isolation of the transsistor using reverse bias pn junction is limiting the transistor size and becomes impractical
  ![image](https://user-images.githubusercontent.com/122186991/212532020-3d778d6c-f45a-4fd2-b7c4-d718eb05c196.png)
 
 **Local Oxidation of Silicon (LOCOS) Isolation Process**  
   * Local Oxidation of Silicon is the traditional isolation technique used in submicron processes.
        1. A very thin layer silicon dioxide is grown on the wafer, called as pad oxide. Then a layer of silicon nitride is deposited which is used as an oxide barrier
        2. Then photolithography is done to pattern and etch the nitride and pad oxide where the thick oxide will be grown  
        3. Then by thermal oxidation process thick oxide is grown in the exposed area.  
        4. The last step is the removal of the silicon nitride layer.  
        ![image](https://user-images.githubusercontent.com/122186991/212532069-5d51f6ff-35b5-469e-8954-27a4049e4be8.png)
 
    * Limitation: the bird’s beak effect and the surface area which is lost to this encroachment
    * Advantages: is simple process flow and high oxide quality because the whole LOCOS structure is thermally grown
        
 **Sallow Trench Isolation (STI) Technology**
 * Shallow trench isolation (STI) allows closer spacing of transistors by eliminating the depletion region at the surface and Bird’s beak effect due to LOCOS process.
 * Sallow Trench Isolation (STI) isolation process is the preferred isolation process for deep-submicron process because it completely avoids Bird’s beak shape characteristics.
        a. Cover the wafer with pad oxide and silicon nitride.
        b. First etch nitride and pad oxide. Next, an anisotropic etch is made in the silicon to a depth of 0.4 to 0.5 microns.
        c. Grow a thin thermal oxide layer on the trench walls
        d. A CVD dielectric film is used to fill the trench
        e. A chemical mechanical polishing (CMP) step is used to polish back the dielectric layer until the nitride is reached. The nitride acts like a CMP stop layer.
        f. Densify the dielectric material at 900°C and strip the nitride and pad oxide.
        ![image](https://user-images.githubusercontent.com/121994033/212125269-d0d9beb3-d8e9-4408-9cd4-bd2e915f50c6.png)

  * STI is more suitable for the increased density in a small area because it allows forming smaller isolation regions.
  * The disadvantage is larger number of process steps.
        
 **Deep Submicron (DSM) CMOS Technology other uses**
  *Illustration of DSM Technology: 
  ![image](https://user-images.githubusercontent.com/122186991/212532178-9a54666b-c4de-4501-9b3c-e8f9991cabd9.png)

   In addition to the NMOS and PMOS transistor, the DSM technology provides;
   * A deep n-well that can be utilized to reduce substrate noise coupling.
   * A MOS Varactor that can be used to make voltage controlled oscillators (VCOs).
   * Different kind of resistors like:
    * Diffused and/or implanted resistors
    * Well resistors
    * Poly resistors
    * Metal Resistors  
   * At least 6 levels of metal that can form many useful structures such as inductors, capacitors, and transmission lines.
     
   **Different Types of Resistor in DSM CMOS Technology** 
  ![image](https://user-images.githubusercontent.com/122186991/212532303-d91dce1e-a5f5-48d4-a55a-9a6808236b4b.png)
  
  **Different Types of Capacitor in DSM CMOS Technology** 
  ![image](https://user-images.githubusercontent.com/122186991/212532342-a36eebcd-92b5-4825-8ba1-8d0e8dc5b105.png)

   **Typical Deep Submicron (DSM) CMOS Fabrication Process**  
     Major Fabrication Steps for a DSM CMOS Process  
      1) p and n wells  
      2) Shallow trench isolation  
      3) Threshold shift and anti-punch through implants  
      4) Thin oxide and gate polysilicon  
      5) Lightly doped drains and sources  
      6) Sidewall spacer  
      7) Heavily doped drains and sources  
      8) Siliciding (Salicide and Polycide)  
      9) Bottom metal, tungsten plugs, and oxide  
      10) Higher level metals, tungsten plugs/vias, and oxide  
      11) Top level metal, vias and protective oxide   

**Summary of Deep Submicron (DSM) CMOS Fabrication Process**    
   * DSM technology typically has a minimum channel length between 0.35μm and 0.1μm  
   * DSM technology addresses the problem of excessive depletion region widths in junction isolation techniques by using shallow trench isolation  
   * DSM technology may have from 4 to 8 levels of metal  
   * Lightly doped drains and sources are a key aspect of DSM technology  
        
**Ultra Deep Submicron (UDSM) CMOS Technology**
 * Minimum length is less than 0.1 microns
 * Minimum feature size less than 100 nanometers
 * 22 nm drawn length
 * 5 nm lateral diffusion (12 nm gate length)
 * 1 nm transistor gate oxide
 * 8 layers of copper interconnect
 * Specialized processing is used to increase drive capability and maintain low off currents
        
**Advantage of UDSM CMOS Technology**
 * Digital Viewpoint:
   * Improved Ion/Ioff
   * Reduced gate capacitance
   * Higher drive current capability
   * Reduced interconnect density
   * Reduction of active power
        
 * Analog Viewpoint:
   * More levels of metal
   * Higher cutoff frequency
   * Higher capacitance density
   * Reduced junction capacitance per transconductance
   * More speed
        
**Disadvantage of UDSM CMOS Technology**
 * Analog Viewpoint:
   * Reduction in power supply resulting in reduced headroom
   * Gate leakage currents
   * Reduced small signal intrinsic gain
   * Increased nonlinearity
   * Increased noise and poorer matching
</details>

 <details>
 <summary>Lab</summary>
  
## Lab ##
 
 </Details>

## Day 4
### Topic - Metal Oxide Semiconductor Structure
<details>
 <summary>Theory</summary>
 
### Theory ###
 
 **Metal Oxide Semiconductor (MOS) Device Structure**  
 * Differences betweeen MOS & MOM Capacitor 
 ![image](https://user-images.githubusercontent.com/122186991/212534757-9abcb04f-b5a2-4074-b67c-670b775c0754.png)

 * **MOS Device Structure & Fabrication**
  * Fabrication
      1. Oxidation: process to create SiO2 on top of Silicon.
      2. Metallization: process to deposit poly-silicon on top of SiO2.
  * Device Structure
      1. Gate and substrate are different material so there is a contact potential between them. This expressed as metal to semiconductor work function (ϕms)
      2. Interface: between SiO2 and silicon
 
 * **Ideal MOS Junction or Capacitor**
 ![image](https://user-images.githubusercontent.com/122186991/212537286-c6937e08-382e-44d0-8118-448b1475ab24.png)

 **Local Oxidation of Silicon (LOCOS) Isolation Process**  
   * Local Oxidation of Silicon is the traditional isolation technique used in submicron processes.
        1. A very thin layer silicon dioxide is grown on the wafer, called as pad oxide. Then a layer of silicon nitride is deposited which is used as an oxide barrier
        2. Then photolithography is done to pattern and etch the nitride and pad oxide where the thick oxide will be grown  
        3. Then by thermal oxidation process thick oxide is grown in the exposed area.  
        4. The last step is the removal of the silicon nitride layer.  
        ![image](https://user-images.githubusercontent.com/122186991/212532069-5d51f6ff-35b5-469e-8954-27a4049e4be8.png)
 
    * Limitation: the bird’s beak effect and the surface area which is lost to this encroachment
    * Advantages: is simple process flow and high oxide quality because the whole LOCOS structure is thermally grown
        
 **Sallow Trench Isolation (STI) Technology**
 * Shallow trench isolation (STI) allows closer spacing of transistors by eliminating the depletion region at the surface and Bird’s beak effect due to LOCOS process.
 * Sallow Trench Isolation (STI) isolation process is the preferred isolation process for deep-submicron process because it completely avoids Bird’s beak shape characteristics.
        a. Cover the wafer with pad oxide and silicon nitride.
        b. First etch nitride and pad oxide. Next, an anisotropic etch is made in the silicon to a depth of 0.4 to 0.5 microns.
        c. Grow a thin thermal oxide layer on the trench walls
        d. A CVD dielectric film is used to fill the trench
        e. A chemical mechanical polishing (CMP) step is used to polish back the dielectric layer until the nitride is reached. The nitride acts like a CMP stop layer.
        f. Densify the dielectric material at 900°C and strip the nitride and pad oxide.
        ![image](https://user-images.githubusercontent.com/121994033/212125269-d0d9beb3-d8e9-4408-9cd4-bd2e915f50c6.png)

  * STI is more suitable for the increased density in a small area because it allows forming smaller isolation regions.
  * The disadvantage is larger number of process steps.
        
 **Deep Submicron (DSM) CMOS Technology other uses**
  *Illustration of DSM Technology: 
  ![image](https://user-images.githubusercontent.com/122186991/212532178-9a54666b-c4de-4501-9b3c-e8f9991cabd9.png)

   In addition to the NMOS and PMOS transistor, the DSM technology provides;
   * A deep n-well that can be utilized to reduce substrate noise coupling.
   * A MOS Varactor that can be used to make voltage controlled oscillators (VCOs).
   * Different kind of resistors like:
    * Diffused and/or implanted resistors
    * Well resistors
    * Poly resistors
    * Metal Resistors  
   * At least 6 levels of metal that can form many useful structures such as inductors, capacitors, and transmission lines.
     
   **Different Types of Resistor in DSM CMOS Technology** 
  ![image](https://user-images.githubusercontent.com/122186991/212532303-d91dce1e-a5f5-48d4-a55a-9a6808236b4b.png)
  
  **Different Types of Capacitor in DSM CMOS Technology** 
  ![image](https://user-images.githubusercontent.com/122186991/212532342-a36eebcd-92b5-4825-8ba1-8d0e8dc5b105.png)

   **Typical Deep Submicron (DSM) CMOS Fabrication Process**  
     Major Fabrication Steps for a DSM CMOS Process  
      1) p and n wells  
      2) Shallow trench isolation  
      3) Threshold shift and anti-punch through implants  
      4) Thin oxide and gate polysilicon  
      5) Lightly doped drains and sources  
      6) Sidewall spacer  
      7) Heavily doped drains and sources  
      8) Siliciding (Salicide and Polycide)  
      9) Bottom metal, tungsten plugs, and oxide  
      10) Higher level metals, tungsten plugs/vias, and oxide  
      11) Top level metal, vias and protective oxide   

**Summary of Deep Submicron (DSM) CMOS Fabrication Process**    
   * DSM technology typically has a minimum channel length between 0.35μm and 0.1μm  
   * DSM technology addresses the problem of excessive depletion region widths in junction isolation techniques by using shallow trench isolation  
   * DSM technology may have from 4 to 8 levels of metal  
   * Lightly doped drains and sources are a key aspect of DSM technology  
        
**Ultra Deep Submicron (UDSM) CMOS Technology**
 * Minimum length is less than 0.1 microns
 * Minimum feature size less than 100 nanometers
 * 22 nm drawn length
 * 5 nm lateral diffusion (12 nm gate length)
 * 1 nm transistor gate oxide
 * 8 layers of copper interconnect
 * Specialized processing is used to increase drive capability and maintain low off currents
        
**Advantage of UDSM CMOS Technology**
 * Digital Viewpoint:
   * Improved Ion/Ioff
   * Reduced gate capacitance
   * Higher drive current capability
   * Reduced interconnect density
   * Reduction of active power
        
 * Analog Viewpoint:
   * More levels of metal
   * Higher cutoff frequency
   * Higher capacitance density
   * Reduced junction capacitance per transconductance
   * More speed
        
**Disadvantage of UDSM CMOS Technology**
 * Analog Viewpoint:
   * Reduction in power supply resulting in reduced headroom
   * Gate leakage currents
   * Reduced small signal intrinsic gain
   * Increased nonlinearity
   * Increased noise and poorer matching
</details>

 <details>
 <summary>Lab</summary>
  
## Lab ##
 
 <Details>  
