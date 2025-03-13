W1TKZ Motorola MTR2000
======================

## References

* [Repeater Builder Index Page](https://www.repeater-builder.com/motorola/mtr2k/mtr-index.html)
* [Good Controller Interface Page](https://www.repeater-builder.com/motorola/mtr2k/mtr-interfacing/mtr2000-interfacing.html)

## Controller Interface Cable

Cable out of the back of the controller:

* Blue (A-17) Auxiliary Transmit Audio.
* Green (C-2) Receiver Un-Squelched.  TTL output active high.
* Red (C-10) External PTT.  TTL input active low.  
* Yellow (C-17) Discriminator Audio Output.  +2.5V DC bias measured.
* Shield (C-31) Ground. 
* Black (B-29) UNKNOWN.

Notes on photo below:

* The repeater has a 96 pin (3x32) Euro female connector on the back. The cable described above isn't attached using a formal connector, but instead is a set of pins plugged into the appropriate places on the Euro connector. The cable is tied to the chassis in a few places to provide strain relief.  This is a bit precarious, but it should be fine.   
* The rows on the Euro connector are, from top to bottom: C, B, A. The pins are numbered from left to right: 1-32.
* Using the green wire on the left as an example, this is plugged into the top row, second column from left. Numbering: C-2.
* The connection farthest to the right is the shield.  Appears to be C-31, which is different from what Larry's handwritten notes showed (his notes had A-19). The W7RHC interface notes
indicate that C-31 and A-19 are both grounds.
* The black wire is connected to pin B-29. The purpose of this is unknown and we'll ignore it. It may have been a wiring error.

![System Picture](docs/IMG_1867.jpg)

Larry's notes for reference:

![System Picture](docs/IMG_1860.jpg)

## Programming Cable

The programming connection is the RJ45 jack on the front marked "RSS." This interface uses RS232 levels and can be connected directly to a serial port (DB9 female).

The pin numbers on the RJ45 side provided here follow the T568B standard.

* DB9 pin 2 -> RJ45 pin 6 (solid green)
* DB9 pin 3 -> RJ45 pin 7 (striped write/brown)
* DB9 pin 6 -> RJ45 pin 5 (striped white/blue)

*NOTE:* There are some conflicting pinouts on the Repeater Builder page. Use caution here. The cable explained here has been tested on the W1TKZ MTR2000.

## Notes on PL Tone

Copied from Repeater Builder page: 

> “When you go to hook an MTR2000 to an external controller (like an RLC, Arcom, or Scom) you will discover a known "gotcha!" that the station (repeater) does not transmit PL when using the System Connector auxiliary audio input and EPTT (External PTT). You will need to sum your external PL encoder audio and the transmit audio and then inject the mixed audio into the aux audio input pin. When Zetron was doing paging with MSFs they created their own integrated summing amplifier and built it into a cable (part # 950-9919). Motorola relabeled it as the CDN6321 Zetron interface kit. But try and find one… Or just the schematic… When you create a summing amplifier you should have a low-pass filter after the PL encoder so it only lets the sub-audible (below 250 Hz) tone through. The PL level should be separately controlled, and if possible, independent of the total modulation. Likewise the repeat audio should have a high-pass filter in line, so it doesn't let audio get into the sub-audible range, which will interfere with the PL tone. It too should have its own level control. Ideally, these two sources would be isolated and summed by another amplifier followed by a master audio level control.”
