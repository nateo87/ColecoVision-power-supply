# ColecoVision Replacement Power Supply
This is a design for a replacement power supply for the ColecoVision that should be considerably less expensive than most of the current options for the console. I wanted to purue this for a couple reasons. One of them was that I felt the currently available new alternatives were too expensive; if one already has a 12v 3a power supply on hand, this one can be built for roughly $10. The other reason was that I wanted something that more appropriately met the power needs of the CV. Certain power supplies can be purchased that have the needed 12v/5v/-5v rails, but its so much more power than what the ColecoVision needs; but supplies such as ATX tend to put out a whopping 450w (at minimum), while the CV only needs roughly 36w. 

(note about the below pic - instead of a 4700uf, I recommend a 2200uf, just 'cause they can be made a bit smaller)

![barepcb](https://github.com/nateo87/ColecoVision-power-supply/blob/main/bare%20pcb.jpg)

This design works from a single 12v 3a power supply that can be connected via the common 2.1mmx5.5mm barrel plug. The 12v line is regulated down to 5v with a simple 7805, and the -5v line is achieved by taking the regulated 5v and putting it into a charge pump inverter. The charge pump only allows for a current limit of 0.1 amps, but given that the -5v rail's only use in the console is for the 4116 VRAM, it's plenty sufficient.

The power supply can be installed directly into the ColecoVision (like I've done in the picture) or can be kept external and have a an original CV power cord (with that infernal proprietary plug) grafted onto it. I know there is sometimes trepidation towards case modding, so I like being able to keep the option open for those who would rather avoid doing that.

IF INSTALLING INTERNALLY - I recommend using a smaller height part for the 2200uf cap so it fits in the case of the CV.

![powersupplyinstalled](https://github.com/nateo87/ColecoVision-power-supply/blob/main/installed%20in%20CV.jpg)

Extensive testing hasn't been done just yet; I've had it on long enough for a couple games of Donkey Kong, but nothing like leaving it on all day to see how it performs, much less seeing if things like the Roller Controller work properly with it. I'd love for others to give this a good test though! The gerber files are available above.

BILL OF MATERIALS:
- 2x 7805 regulators. If you can cheaply get a hold of the more efficient alternative being made today (i.e. Traco), those come highly recommended.
- 2200uf electrolytic capacitor
- 2x 100uf electrolytic capacitors
- 2x 1uf electrolytic capacitors
- 2x 0.1uf ceramic capacitors
- 470uf electrolytic capacitor
- LT1054 charge pump inverter IC
