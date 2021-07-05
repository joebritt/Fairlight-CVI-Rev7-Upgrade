# Fairlight-CVI-Rev7-Upgrade
Board set to upgrade a Rev5 Fairlight CVI to Rev7. This upgrade also eliminates the need for backup batteries.

See overview and installation guide [here](https://docs.google.com/document/d/1melksT-DwwU80pforqxVVXWFiSj0hJ2Gdj74KaH-A6M/edit?usp=sharing).

### All PCB designs were done in Eagle.

There are 4 different PCBs. Two of these are just DIP-to-PLCC EPROM adapter boards. 
I made these because I had a bunch of PLCC 27C010 EPROMS I wanted to use!

There are 4 EPROM images for inside the CVI unit. You'll replace the Rev5 EPROMs with parts programmed with these images:

CVI1R70.BIN and CVI2R70.BIN are images of Rev7 firmware EPROMs CVI1 and CVI2. These each go in a 27C128 16KB EPROM.

CVIHO52.BIN is the Horizonal timing control EPROM. This goes into a 2716 2KB EPROM.
CVIVE50.BIN is the Vertical timing control EPROM. This goes into a 2716 2KB EPROM.

### PCB Designs

27C128_adapter: 
Adapts a PLCC32 27C010 style memory to a DIP 27C128 style memory footprint.
Program just the bottom 16KB of the 27C010 before soldering it to the board.

2716_adapter:
Adapts a PLCC32 27C010 style memory to a DIP 2716 style memory footprint.
Program just the bottom 2KB of the 27C010 before soldering it to the board.

NoBattNVRAM:
Replaces the CVI SRAM / 3V Lithium battery with FRAM. Nonvolatile memory, no battery needed.
A wire with a grabber clip is used to pick up the 6809 /E clock, which is needed to qualify accesses to the FRAM.

CVI06A:
The main attraction. Replacement for the original CVI06 expansion board. Smaller, easier to attach, and also uses FRAM for battery-free nonvolatile storage. Program the 27C010 for this board with the CVI43_CVI06A_v11 file in the low 32KB. This image contains the CVI3 and CVI4 Rev7 firmware EPROM images in a single part.

### Enclosure

CVI06A_box.stl and CVI06A_lid.stl can be 3D printed to make a small enclosure to protect the CVI06A PCB.
The box is held together by friction. Note the capture features and line them up when closing.



