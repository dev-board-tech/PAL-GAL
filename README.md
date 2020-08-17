# PAL-GAL
I add this repository because some time we need cheap simple external custom programable logic to add to a microcontroller due to pin count limitation or other reasons ( protection, logic level converters ...), or to do simple logic circuits for learning to compose logic circuits without using too much wires and dedicated logic circuits, a better experience for learning electronics.

This repository will have simple logic designs that can be emulated by a PAL/GAL device.

The difference between PAL and GAL is that PAL are only once programable devices because are ROM based and GAL can be programmed and erased more than 100 times because are EEPROM based.

I know that they are deprecated by all manufacturers except Atmel currently Microchip, but, the good news are that are very cheap and can be found on ebay at a price under half $.

# The compiler that I use

I use PALASM4 in DOSBOX, because the PALASM4 can run only under DOS we need to install DOSBOX.

The version of used DOSBOX is 0.74 that I integrated it in this repository, PALASM come as an archive that need to be deflated in a user desired directory, the example directory that I used is 'D:\DOSBOX\PALASM'.

After installing DOSBOX edit *** {system drive}:\Users\{username}\AppData\Local\DOSBox\dosbox-0.74.conf *** and add these lines at the end of the file:

```
[autoexec]
# Lines in this section will be run at startup.
# You can put your MOUNT lines here.
mount C D:\DOSBOX

REM C:\DOSBOX\PALASM\ PALASM4 Environment Setup
PATH C:\DOSBOX\PALASM\EXE;C:\;"%PATH;C:\DOSBOX\PALASM4\EXE"
SET PALASM=C:\PALASM\

C:
CD C:\PALASM
```

Save it and close the file.

Now when you open DOSBOX will automatically mount the C: virtual drive and navigate to PALASM directory, you can type PALASM and will execute the compiler.

The window is very simple, there are some rendering issues but after you accommodate with the old DOS way all will be very handy.

A simple tutorial you read here: http://s100computers.com/My%20System%20Pages/ISA%20to%20S100%20Bus/Intro%20To%20GALs.htm

PALASM Language guide: http://orion.ipt.pt/~fmbarros/ed/PALASM%20Language%20Guide.htm

Down in the page you can download DOSBOX and PALASM, I included them here for archiving purpose.

#### Pay attention that the enter key selects an action, but with F10 will execute the selected action ( Ehh, the old DOS  :) ).

# Programming the design:

I use XGecu TL866II-Plus Programmer, a Chinese cheap universal programmer that do a pretty good job.

# Examples:

#### 16V8:

* COUNTER.PDS : A counter with 7 + 1 bit, first 7 bits can be reset, the last bit does not have the reset function due to hardware limitations.
* DEC.PDS : A asynchronous decoder.
* DECREG.PDS : A registered decoder.
* DMUX.PDS : A registered logic demultiplexer.
* DMUXREG.PDS : A asynchronous logic demultiplexer.
* REG.PDS : 8 bit register, useful if a registered bus or a rearranged registered BUS is needed.
* WIRED.PDS : 8 in 8 out wired network, useful in case of a rearranged BUS is needed.
