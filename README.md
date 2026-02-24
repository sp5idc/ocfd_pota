*Read this in other languages: [🇵🇱 Polski](README_pl.md)*

# OCFD POTA - 4:1 Guanella Current Balun (2x FT82-43)

This project provides a printed circuit board (PCB) for a lightweight and highly efficient 4:1 Guanella Current Balun. The design is specifically tailored for portable operations (SOTA, POTA, fibreglass mast deployments) and is perfectly suited for feeding asymmetrical wire antennas, such as the Off-Center Fed Dipole (OCFD).

![Assembled balun](images/ocfd_pota_completed.jpg)

The PCB features a narrow profile (35 mm x 90 mm), offering minimal wind resistance and aligning perfectly along the top sections of carbon fibre or fibreglass masts. It includes an integrated lanyard/suspension hole and dedicated slots for zip-ties to securely mount the toroidal cores.

## Project Assumptions
A small field antenna designed to be easily carried in a backpack alongside a lightweight fishing pole or a compact travel mast. Utilizing wire legs of approximately ~7 m and ~14 m, it is intended to operate on the 40-20-10m bands without an antenna tuner (ATU). The design assumes a relatively low deployment height of about ~6m.
* **40m band:** NVIS operation, highly useful for local field activations, POTA programs, or EMCOMM.
* **20m band:** Global communication with slight DX characteristics; provides the best impedance match.
* **10m band:** Taking advantage of the current solar cycle.

![Antenna installation](images/antenna_installation_schematic.jpg)

Expected performance using the assumed leg lengths for a total span of ~21 m:
* **40m** - SWR 1.3:1 - 1.6:1 - NVIS mode due to the expected low suspension height (~6m)
* 30m   - SWR > 5.0:1 - Poor match
* **20m** - SWR 1.1:1 - 1.4:1 - Expected best performing band
* 17m - SWR 2.5:1 - 3.5:1 - ATU required
* 15m - SWR 3.0:1 - 6:0:1 - Poor match
* 12m - SWR 2.0:1 - 3.0:1 - ATU required
* **10m** - SWR 1.5:1 - 2.0:1 - Expected to operate without an ATU

## Specifications & Capabilities
* **Design Type:** 4:1 Current Balun (Guanella configuration)
* **Cores:** 2x Amidon FT82-43 (stacked vertically)
* **Intended Use:** Portable operations, QRP, lightweight wire antennas (optimal for 80m through 10m bands).
* **Estimated Safe Power Rating (with SWR < 2:1 and 0.5 mm wire):**
  * **SSB:** up to 100W (intermittent operation, ideal for 50W transceivers)
  * **CW:** up to 50W
  * **FT8 / Digital Modes:** 15W - 20W (monitor core temperature during continuous duty cycles)

## Bill of Materials (BOM)
This is a DIY project; the PCB does not include factory-assembled SMD components. To build this balun, you will need:
1. **PCB** (manufactured using the files from the `fabrication/` folder).
2. **RF Connector:** 1x Right-angle PCB mount BNC connector (Example connector used by me: https://pl.aliexpress.com/item/1005003804586650.html).
3. **Ferrite Cores:** 2x Amidon FT82-43.
4. **Magnet Wire:** Enamelled Copper Wire (ECW) with a diameter of **0.5 mm up to a maximum of 0.8 mm** (larger diameters, e.g., 1.0 mm, will not fit through the standard via holes on this PCB).
5. **Mounting Hardware:** Small zip-ties (cable ties) to secure the cores to the PCB.

## Assembly Instructions

### 1. Winding the Cores (Transformers T1 and T2)
Both cores must be wound identically.
* Use a bifilar line (preferably two enamelled wires lightly twisted together or running parallel). It is highly recommended to use wires with two different enamel colours to easily identify the lines (e.g., Wire "A" and Wire "B").
* Wind an optimal **14 bifilar turns** on each core. Using 0.5 mm wire, these will fit easily, and this number of turns ensures excellent choking impedance on the 40m and 80m bands.
* Leave about 2-3 cm of wire pigtails and trim the excess.
* Mechanically remove the enamel/insulation from the wire ends and use a multimeter to identify the corresponding ends of each wire.

### 2. Soldering to the PCB
The 4:1 Guanella balun works on the principle of **parallel input connections and series output connections**. The PCB traces handle all the routing logic for you.

Soldering the correct wire ends to the correct pads is critical for the balun to function properly.

![PCB Front](images/2D_ocfd_pota_front_small.jpg)

The PCB silkscreen uses the following nomenclature:
* **T1A1** - Transformer 1, Wire A, End 1
* **T1A2** - Transformer 1, Wire A, End 2 (the opposite end of the same Wire A)
* **T1B1** - Transformer 1, Wire B, End 1
* ...

On the rear side of the PCB, there are two pads where the antenna radiator wires should be soldered. Adjacent to these pads are strain-relief holes through which the radiator wires must be threaded.
Due to the balun's electrical symmetry, it does not matter which OCFD leg is connected to the left or right pad.

![PCB Rear](images/2D_ocfd_pota_rear_small.jpg)

Route the zip-ties through the designated holes in the PCB and firmly secure the cores. 
The windings should not move. If the zip-ties do not provide enough stability, apply a few drops of glue, epoxy, or varnish.

### 3. Radiator Wire and Tuning
To allow a margin for tuning, cut the initial antenna elements to the following lengths:
* Longer leg: **14 m**
* Shorter leg: **7 m**
Total span is approximately 21 m.

After field tuning with an antenna analyzer, the final dimensions will likely settle around:
* **13.75 m**
* **6.85 m**

When trimming the antenna, remember to maintain the **67% / 33%** proportion between the legs. 
Always preserve a **2:1 ratio** when cutting the wires.

## How to order the PCB
If you want to get this board manufactured (e.g., at JLCPCB, PCBWay), follow these steps:
1. Download the Gerber ZIP file located in the `fabrication/` folder.
2. Upload this file on your chosen PCB manufacturer's website.
3. Select the standard board thickness (**1.6 mm**) and standard copper weight (**1 oz** / 35 µm). The PCB has properly sized traces and pads for these parameters.

## License
Copyright 2026 Maciej Chmielewski SP5IDC

This Source describes Open Hardware and is licensed under the CERN-OHL-S v2.

You may redistribute and modify this Source and make products using it under the terms of the CERN-OHL-S v2 (https://ohwr.org/cern_ohl_s_v2.txt).

This Source is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE. Please see the CERN-OHL-S v2 for applicable conditions.

Source location: https://github.com/sp5idc/ocfd_pota

As per CERN-OHL-S v2 section 4, should You produce hardware based on this Source, You must make the complete, corresponding Source available under the same licence.

---
*Project distributed as Open Source Hardware.*
