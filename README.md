# Cubesat

This project is my take at the popular satellite soldering sculpture. I am not that great of a craftsman to use just wire to make one, so I designed a PCB as a frame and to simplify mounting of the components.

![what this repo is about](/pictures/cubesat_overview.jpg)


https://github.com/user-attachments/assets/b4cf70d2-edd2-42cd-95d9-c0b70f45f20e


# overview

The PCB contains a simple 555 timer circuit to blink a LED approximately every 2 seconds. It also contains a 10F supercapacitor and 2 solar cells to keep the LED blinking. [Here](http://www.falstad.com/circuit/circuitjs.html?ctz=CQAgjCAMB0l3BWEBmAHAJmgdgGzoRmACzICcpkORICkNNdCApgLRhgBQA7iOluuBy9+IFsgGceyZELBDpQ1HUjdhE+TMFQOAcxSRq6SKn2H01ZRwDyIInHBgBRKg4GWASmtHivLF8ts6NygoaARVBVcUTXFLABNo+SNeVBNY3nAAOSJiVA4AJ3BcFGT0VJKAhBx4XSL5HBMwYrQLbQBjOorOmRNlWHhIMAHhkbdoUiwsHNTkY0gyXCQYOElOptlm5JUedc6jRuLttaJqXd2js5PeY3ArlULdpWPW2eHVfZAnx8s5JA+iEz4IQA2y2aDIBBgcjkMDiWY4LCsUgcOROexQtFBKoZOJMABmAEMAK4AGwALiwSUwEhBaaFBgVAnR2JjOoxqqo7MzilzwKQ3Jz0Y5ElEVHpeUCmV5LB0+AJ0OYvHKQmBWI1wdJNVrtVh6QyeMqFYYRB8xUqTSbypYAPagoaKuh2UiAsKhCDMjhoegAMXdoSQCFdbBAADVreSCTomBwgA) is a falstad simulation of the circuit.

https://github.com/user-attachments/assets/453aff4a-6fac-449e-99ac-6b25f17cfe23

# make your own

Making your own is relatively straight forward. You need soldering tools, some patience and the components in the bom. There is a Ibom availible for easier PCB placement.

## BOM

| Name | Reference | Value | Quantity | Digikey Partnumber | optional |
| --- | --- | --- | --- | --- | --- |
| PCB | - | - | 1 | - |  |
| conducting wire | - | 0.25mm^2 | ~250mm | - |  |
| stiffening rod | - | - | 120mm | - | (✓) |
| test point | - | RCWCTE | 8 | 2019-RCWCTECT-ND | ✓ |
| capacitor | C1 | 10F 5.5V | 1 | 535-ADCM-S05R5SA106RB-ND |  |
| capacitor | C2 | 0.1uF | 1 | 1276-1017-1-ND | ✓ |
| capacitor | C3 | 1uF | 1 | 1276-1097-1-ND |  |
| capacitor | C4 | 10pF | 1 | 1276-1083-1-ND | ✓ |
| LED | D1 | red 4.9mm | 1 | 732-5016-ND |  |
| diode | D2, D3 | 1N4148 | 2 | 1N4148FS-ND |  |
| zener Diode | D4 | 5V5 | 1 | DDZ5V6ASF-7DICT-ND |  |
| resistor | R1 | 3M | 1 | 311-3.00MFRCT-ND |  |
| resistor | R2 | 560 | 1 | 311-560FRCT-ND |  |
| resistor | R3 | 56K | 1 | 311-56.0KFRCT-ND |  |
| solar cell | SC1, SC2 | SM141K04TFV | 2 | 2994-SM141K04TFV-ND |  |
| oscillator | U1 | LMC555xM | 1 | LMC555CMMX/NOPB |  |

## PCB

I made a Gerber package that you can upload to your preferred PCB fabricator (I used JLC PCB). I recommend telling the PCB fabricator to add v-scoring between the PCB's. That way you don't have to cut the PCB's yourself. If you do cut it yourself WEAR A RESPIRATOR! I forgot the V-scoring and used a wood chisel to add v-scoring myself and break the PCB's. I also recommend covering the pcb's with masking tape while you are working to keep scratches to a minimum. 

## Assembly

When you are left with 6 separate small PCB's you can start with the assembly. 

<p align="middle">
  <img src="/pictures/pcbs_pre_assembly.jpg" width="33%"/>
</p>

### SMD / THT components

Every SMD / THT component except C1, SC1, SC2 and D1 can be soldered while the PCB's are still separate. The test points are a mounting point if you want to mount your cubesat in the air. The pads on the side are not just for physical connection but also to route power between the PCB's. See the schematic for the different signal paths.

### PCB assembly

Attaching the PCB's is easiest when you attach the bulky THT components when you have soldered all the side walls except the bottom. The top, front and back PCB's are directional! The PCB's that get attached to the solar cell can be attached either way but are intended to be installed so that the Solar cell faces forward and up.

<p align="middle">
  <img src="/pictures/detail_view/front_top.png" width="49%"/>
  <img src="/pictures/detail_view/back_top.png" width="49%"/>
</p>
<p align="middle">
  <img src="/pictures/detail_view/left_top.png" width="49%"/>
  <img src="/pictures/detail_view/flat.png" width="49%"/>
</p>

### Solar cell

To mount the solar cells, you need some copper wire as connection to the PCB. Check the silkscreen for polarity.

<p align="middle">
  <img src="/pictures/Wire_bending_and_lenght_guide.png" width="49%"/>
  <img src="/pictures/solar_cell.jpg" width="49%"/>
</p>

### stiffening rod

I used a stiffening rod for the solar cells because my copper wire was not stiff enough to hold the solar cells. I used carbon fibre rod insulated with shrink tube. A dab of hot glue fixes the solar cells in place.

### LED

The LED is straight forward and can be mounted to taste. I wanted it to stick out a bit, so I kept the pins long.

### Supercap

The supercap is also very straight forward. At first, I specced a smaller capacitor, but I was not happy with the runtime. So, I used a bigger capacitor. So, the leads must be bent a bit to fit correctly.

### Finishing

I recommend to not solder the bottom until the circuit is proven to work. If it does not, check for small disconnects between the pads and the traces or even ripped out pads. I had some missing pads, so I soldered some cutoff wire from the diodes to the PCB's.

<p align="middle">
  <img src="/pictures/bodge.jpg" width="75%"/>
</p>

# note

Well that's it. If you have any questions open a discussion.

I used the [pcb2blender](https://github.com/30350n/pcb2blender) to make all the renders of the PCB's in this readme.

# a flock of cubesat's

<p align="middle">
  <img src="/pictures/a_flock.jpg" width="75%"/>
</p>
