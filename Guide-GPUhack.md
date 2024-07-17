## GPU Firmware Hacking

This section applies to both AGP & PCIe G5's and requires access to an older PC with AGP or PCIe connectivity. Some important notes are below, followed by the flashing guide.

#### Prerequisites

- Access to an older PC with AGP or PCIe, depending on scenario.

  NOTE: If PCIe, it must be early enough and not have UEFI, or the PC may halt or deactivate the card which will not allow flashing.

- A flashable GPU from the AGP or PCIe GPU sections.

- A 4-pin Molex to 6-pin Molex GPU adaptor (Optional depending on card)

#### ATI Flashing

NOTE: Modification of the guide posted by user z970 on MacRumours forum.

1. If the G5 is on OS X Tiger 10.5.x, install the official drivers provided by ATI below. If it is running (Sorbet) Leopard, no action is required.

   LINK: http://macintoshgarden.org/apps/ati-x1900-driver-powermac-g5-late-2005-pcie

2. Download a copy of FreeDOS from the link below. You can use Linux 'dd', balenaEthcer, or a Windows utility of your choice to write this to USB. Please use the 'FullUSB' image if possible.

   LINK: https://freedos.org/download/

3. Download ATIFlash 4.07 from the link below. (You will have to click "show older versions")

   LINK: https://www.techpowerup.com/download/ati-atiflash/
    
4. Download a copy of the firmware for the GPU you are working with from the link below.

   LINK: http://themacelite.wikidot.com/wikidownloads2

5. Copy the downloaded 'atiflash.exe' to the root directory of the FreeDOS USB drive prepared in Step #2. Rename the ROM file from Step #3 to something compact; we will use 'firmware.rom' going forward.

    EXAMPLE: Rename 'Radeon X1900 GT rev 109.rom' to 'firmware.rom' if you downloaded Radeon X1900 GT firmware.
    
6. Install the GPU we are working with into an AGP or PCIe-enabled x86 PC. If necessary, since the GPU firmware is still built for Windows, you may use it for video output while we flash modified firmware to it.

7. Boot from the FreeDOS USB drive in the PC we are using to flash. Once booted, select your language and choose 'Exit to DOS'.

8. Type 'dir' then press [ENTER]. Verify 'atiflash.exe' and 'firmware.rom' are present in the current directory.

9. Run the following command:

    COMMAND: atiflash -i
    
This will show the adapter number of the installed GPU, which is identifiable by the GPU die in the middle column. Usually, the adapter number to the far left will read '0' if the card was installed into the AGP slot or primary PCIe slot, the number increasing if it was installed into a secondary PCIe slot.

10. Backup the ROM by running the following command:

    COMMAND: atiflash -s backup.rom.

This will backup the firmware on the USB drive to a file named 'backup.rom'. Make sure to save this somewhere safe after flashing in the event something goes wrong or you'd like to flash back to the cards original firmware.

11. To flash the modified ROM to the GPU, run the following command:

    COMMAND: atiflash -p -f 0 firmware.rom 

If your card displayed a number other than '0' in Step #9, replace the 0 in the command above with the number displayed previously.

12. After a few moments, the ATIFlash utility should complete and let you know if the flashing was successful. If so, you may type the command 'shutdown' to power off the machine. Otherwise, if you recieve an error, you can type the following command below to restore the original firmware:

    COMMAND: atiflash -p -f 0 backup.rom
        
13. You may now remove the card and install it into your G5. If all went well, it should produce and audible chime and start booting without issue. If it doesn't boot, verify that your card is actually on the supported GPU list and that you are using the correct ROM file for your GPU.

#### nVidia Flashing

1. Download a copy of FreeDOS from the link below. You can use Linux 'dd', balenaEthcer, or a Windows utility of your choice to write this to USB. Please use the 'FullUSB' image if possible.

   LINK: https://freedos.org/download/

2. Download NVFLASH from the link below.

    LINK: https://www.techpowerup.com/download/nvidia-nvflash/
    
3. Download a copy of the firmware for the GPU you are working with from the link below.

    LINK: http://themacelite.wikidot.com/wikidownloads2

4. Copy the downloaded 'nvflash.exe' and 'cwsdpmi.exe' to the root directory of the FreeDOS USB drive prepared in Step #2. Rename the ROM file from Step #3 to something compact; we will use 'firmware.rom' going forward.

    EXAMPLE: Rename 'Quadro FX4500 2149.rom.rom' to 'firmware.rom' if you downloaded Quadro FX 4500 firmware.
    
5. Install the GPU we are working with into an AGP or PCIe-enabled x86 PC. If necessary, since the GPU firmware is still built for Windows, you may use it for video output while we flash modified firmware to it.

6. Boot from the FreeDOS USB drive in the PC we are using to flash. Once booted, select your language and choose 'Exit to DOS'.

7. Type 'dir' then press [ENTER]. Verify 'nvflash.exe', 'cwsdpmi.exe' and 'firmware.rom' are present in the current directory.

8. Run the following command:

    COMMAND: nvflash.exe --check

This will show the adapter number of the installed GPU. Usually, the adapter number to the far left will read '0' if the card was installed into the AGP slot or primary PCIe slot, the number increasing if it was installed into a secondary PCIe slot.

9. To flash the modified ROM to the GPU, run the following command:

    COMMAND: nvflash.exe --index=0 -4 -5 -6 -j firmware.rom

If your card displayed a number other than '0' in Step #8, replace the 0 in the command above with the number displayed previously.

10. After a few moments, the ATIFlash utility should complete and let you know if the flashing was successful. If so, you may type the command 'shutdown' to power off the machine.
        
11. You may now remove the card and install it into your G5. If all went well, it should produce and audible chime and start booting without issue. If it doesn't boot, verify that your card is actually on the supported GPU list and that you are using the correct ROM file for your GPU.

#### Sources

Source 1: https://forums.macrumors.com/threads/radeon-x1900-g5-mac-edition-cheap-n-easy-flashing-guide.2308103/

Source 2: http://themacelite.wikidot.com/nvidia-general-flashing
