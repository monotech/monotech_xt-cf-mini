Monotech XT-CF-Mini Rev1.1 ReadMe
----------------------------

8-bit ISA CompactFlash interface + Boot ROM (two separate functions that can be used individually).

Documentation for the switches can be found on the rear silkscreen. More ROM I/O addresses are possible than the information on the silkscreen. See below.

Credit:
-------
Design uses schematic from Sergey Kiselev, with a few small changes to switches, and PCB from scratch.\
www.malinov.com/Home/sergeys-projects/xt-cf-lite

XT-IDE Universal BIOS\
www.xtideuniversalbios.org  
www.xtideuniversalbios.org/binaries  
Use the latest working binary that includes XTIDECFG.COM (config utility), ide_xt.bin (8086/8088), ide_xtp.bin (80186/V20/V30 and up).




Further documentation:
----------------------

SW1 - ON: ROM Enabled; OFF: ROM Disabled\
SW2 - ON: EEPROM Write Enabled; OFF: EEPROM Write Disabled

---

SW3 - ROM I/O Port:  
123 ROM  
111 C0000  
111 C2000*  
110 C4000  
110 C6000*  
101 C8000  
101 CA000  
100 CC000  
100 CE000*  
011 D0000 < Default  
011 D2000*  
010 D4000  
010 D6000*  
001 D8000  
001 DA000*  
000 DC000  
000 DE000*  
111 E0000**  
111 E2000***  
110 E4000**  
110 E6000***  
101 E8000**  
101 EA000***  
100 EC000**  
100 EE000***  
011 F0000**  
011 F2000***  
010 F4000**  

Settings marked with asterisks require solder-jumpers to be opened:

Settings marked with * require JP1 to be opened.\
Settings marked with ** require JP2 to be opened.\
Settings marked with *** require both JP1 and JP2 to be opened.\
Settings marked with no *, are set with the three DIP switches, and require JP1 and JP2 to be closed.\

Make sure that selected I/O and EEPROM addresses do not conflict with other devices.\
Addresses 0xC0000 - 0xC6000 will conflict with EGA/VGA BIOS extension.\
Addresses 0xC8000 - 0xCA000 might conflict with XT Hard Disk BIOS extension.\
Addresses 0xE0000 and up might conflict with system BIOS on newer motherboards.\
It is recommended to disable EEPROM write once XT IDE BIOS extension is programmed and configured.

---

SW4 - IDE I/O Port:  
123 IDE  
111 300 < Default  
011 320  
101 340  
001 360  
110 380  
010 3A0  
100 3C0  
000 3E0  

The A8 line is provided as a solder-jumper JP3, and should change the first digit of the IDE I/O Port from 3 to 2 (so 300 becomes 200, 3C0 becomes 2C0, etc). This is untested at present.\
