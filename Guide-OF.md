## The Open Firmware Wiki - By z970

#### Preface

    This guide is ENTIRELY written up by user 'z970' of the MacRumors forum. Due to the sheer amount of information, to document everything G5 in one place (archival), and too much interesting reading, I will probably not be modifying much other than some basic formating. All sources and credits are found at the bottom of the main section of this GitHub repository.

#### Introduction

Open Firmware is a boot environment developed using the Forth programming language. Open Firmware exists to provide a machine independent means of loading operating systems, from a variety of boot devices. Open Firmware probes the PCI bus for devices and possible Open Firmware device drivers for those devices. These drivers can either be integrated into the Open Firmware or provided on an external device, thus providing plug and play capabilities for new boot devices. Open Firmware is then capable of using these drivers to load an operating system from the device.

Apple's Open Firmware is part of their ROM-in-RAM design approach originally used in the first iMac systems. The approach uses a small ROM that contains sufficient code to initialize the hardware and load an operating system. The rest of the system code, that on previous Mac systems (old world) resided on a physical ROM (chip) is now loaded from disk or from network into RAM. Open Firmware is part of this "New World" boot system.

On the latest revision of Apple systems Open Firmware provides a variety of functions. One of the key functions of Open Firmware is to configure the UniNorth and Keylargo ICs, to construct a device tree, probe devices, include any device drivers and finally select a boot device.

The boot process starts with the PowerPC processor executing its reset vector as specified by the Hardware Initialization code. The boot ROM stored in NVRAM provides power on self test (POST - diagnostics), and initializes enough of the system to load Open Firmware. These POST tests are run in native PowerPC code and involve checksum testing, memory testing, detection of the manufacturing test pin and test manager support. With the new family of iMac systems, additional pre-firmware diagnostics are performed due to the addition of the UniNorth and KeyLargo ICs. When enough initialization has occurred to execute Open Firmware, the boot chime is played and Open Firmware is loaded.

Open Firmware will then probe the system's I/O buses to determine the device configuration and build a device tree, which describes the hardware it has located. The system will then examine the values of its environment variables. If the auto-boot? variable is flagged as true, the system will then read the value contained within the boot-device variable and attempt to boot from that device. If additional information is required the boot-file variable is read. If the auto-boot? variable is flagged as false, the system will halt the boot process and drop to the Open Firmware user interface.

The default boot device on Apple systems is "hd:,\\:tbxi". The system will automatically convert "hd" into the appropriate device path, as hd is simply an alias. The notation "" tells the system to start searching for "blessed" folders (directories) starting on the first HFS or HFS+ partition found on the system. The final part, "tbxi", tells the system to look for files of type tbxi. All versions of MacOS have a folder known as System Folder that is "blessed", and contains a MacOS Boot ROM file which is of type tbxi. The Boot ROM file is simply a stripped ELF executable image wrapped with a forth boot script. A "blessed" folder is simply one with a special attribute (or flag) set on it. The system will search all HFS partitions for a blessed folder and a file of type tbxi within it, if none are located, the boot will fail. The system will always select the first one found, unless the boot-device is modified to a specific partition id.

Source: http://macos9lives.com/smforum/index.php?topic=1965.0

#### Open Firmware Version History

? - Power Macintosh 7500 ("Power Macintosh", "AAPL,7500", "28f1")
1.0.5 - Power Macintosh 9500 ("Power Macintosh", "AAPL,9500", "Open Firmware, 1.0.5")
1.0.5 - Power Macintosh 8600 ("Power Macintosh", "AAPL,8500", "Open Firmware, 1.0.5")

2.0 - Power Macintosh 5400 ("Power Macintosh", "AAPL,Hooper", "Open Firmware, 2.0")
2.0f1 - Power Macintosh G3 Beige ("Power Macintosh", "AAPL,e407", "Open Firmware, 2.0f1")
2.0.1 - PowerBook ? ("PowerBook", "AAPL,PowerBook1998", "Open Firmware, 2.0.1")

3.1.0 - Power Macintosh G3 (B&W) ("Apple PowerMac1,1 1.0f5 BootROM built on 02/15/99 at 18:06:39", "OpenFirmware 3.1.0")
3.1.1 - Power Macintosh G3 (B&W) ("Apple PowerMac1,1 1.1f4 BootROM built on 04/09/99 at 13:57:32", "OpenFirmware 3.1.1")

3 - Power Macintosh G4 (AGP) ("Apple PowerMac3,1 1.3f1 BootROM built on 10/28/99 at 18:10:16", "OpenFirmware 3")
3 - PowerBook G3 (Pizmo) ("Apple PowerBook3,1 2.1f1 BootROM built on 01/29/00 at 22:38:07", "OpenFirmware 3")
3 - iMac G3 350 ("Apple PowerMac2,1 4.1.9f1 BootROM built on 09/14/01 at 13:18:04", "OpenFirmware 3")
3 - iBook G3 ("Apple PowerBook4,1 4.2.7f1 BootROM built on 09/12/01 at 17:47:15", "OpenFirmware 3")
3 - Power Macintosh G4 733 (Digital Audio) ("Apple PowerMac3,4 4.2.8f1 BootROM built on 10/11/01 at 14:12:47", "OpenFirmware 3")
3 - Power Macintosh G4 (MDD) ("Apple PowerMac3,6 4.4.8f2 BootROM built on 09/30/02 at 10:24:31", "OpenFirmware 3")
3 - PowerBook G4 (FW800 - Al) ("Apple PowerBook5,2 4.7.1f1 BootROM built on 09/04/03 at 13:39:26", "OpenFirmware 3")
3 - PowerBook G4 1.33 17" (Al) ("Apple PowerBook5,3 4.7.1f1 BootROM built on 09/04/03 at 13:39:26", "OpenFirmware 3")
3 - iMac G4 1.25 17" "FP" (USB 2.0) ("Apple PowerMac6,3 4.7.8f1 BootROM built on 11/05/03 at 07:54:33", "OpenFirmware 3")
3 - PowerBook G4 1.33 12" (Al) ("Apple PowerBook6,4 4.8.3f1 BootROM built on 04/01/04 at 16:52:06", "OpenFirmware 3")
3 - PowerBook G4 1.67 15" (Al) ("Apple PowerBook5,6 4.9.1f1 BootROM built on 01/21/05 at 10:51:16", "OpenFirmware 3")

4 - Power Macintosh G5 (PCI or PCI-X) ("Apple PowerMac7,2 5.1.5f1 BootROM built on 08/25/04 at 10:43:05", "OpenFirmware 4")
4 - Power Macintosh G5 (Quad Core) ("Apple PowerMac11,2 5.2.7f1 BootROM built on 09/30/05 at 15:31:03", "OpenFirmware 4")


The following are BootROM versions:

4.1.8 - Power Macintosh G4 (Digital Audio, January 2001)
4.2.0 - iBook G3 (Dual USB, May 2001)
4.4.8 - Power Macintosh G4 (Mirror Drive Doors, June 2003)
4.6.2 - PowerBook G4 (February 2003)
4.8.6 - PowerBook G4 (April 2004)
4.8.9 - Mac Mini G4 (January 2005)
4.9.0 - PowerBook G4 12" (January 2005)
4.9.1 - PowerBook G4 (January 2005)
4.9.3 - iBook G4 (July 2005)
5.1.5 - Power Macintosh G5 (Omega, June 2003)
5.2.7 - Power Macintosh G5 (Cypher, October 2005)

Versions 4.9 and 5.2 Feature Set: 'UD' Device Aliasing, Boot Picker Arrow Key Support

#### Accessing Open Firmware

Method I: At the chime, hold down the Option key. The Boot Picker comes up. Press Control + Z to switch to Open Firmware.

Method II: At the chime, hold down Command + Option + O + F until you've arrived at the Open Firmware prompt.

#### Running System Diagnostics

- To reset the system NVRAM, enter reset-nvram

- To reset all changes made to Open Firmware, enter set-defaults

- To reset the machine, enter reset-all

- To display a list of all central device aliases, enter devalias

- To display information for a device, enter dev <device alias> .properties
    EXAMPLE: dev /cpus .properties | dev screen .properties | dev /memory .properties etc.
    NOTE: The capacity values output by dev /memory .properties are saved in the hexadecimal format and will need to be converted to be understood by most.

- To display a list of all utilities, enter printenv
    WARNING: DO NOT RUN setenv little-endian? true ! This will brick your machine beyond trivial repair!

- To check the system hard disk and its partitions without extracting it from the machine, enter target-mode into the prompt. Target Disk Mode comes up. Connect a FireWire cable from the subject machine to another compatible machine. The subject machine's partitions will appear on the other machine, ready for review or remote boot.

#### Booting an Operating System

- To automatically enter Open Firmware upon boot, enter setenv auto-boot? false
    NOTE: Enter setenv auto-boot? true to revert to default. )

- To set a default boot volume, enter setenv boot-device <volume>:<partition ID>,<path>
    EXAMPLE: setenv boot-device hd:1,\\:tbxi | setenv boot-device cd:,\\yaboot | setenv boot-device ud:,ofwboot
    NOTE: If no partition ID is provided, the system will look for the first available OS on the specified volume. If none are found, the system will either revert back to Open Firmware, or display a "do not cross" symbol.

- To boot between locally installed operating systems, enter multi-boot into the prompt. The Boot Picker comes up. 
    NOTE: The utility's interface and control methods may vary between versions.

- To boot from a USB disk, enter one of the following depending on the targeted OS (OF V. 4.9 / 5.2 Only)

    Mac OS X: boot ud:,\\:tbxi

    Linux: boot ud:,\\yaboot

    Linux (GRUB): boot ud:,\\grub.img

    OpenBSD: boot ud:,ofwboot

- To boot from a USB disk on OF V. 4.8 / 5.1 and lower, replace 'ud:,' with 'usb0/disk@1:'. Increase the digit immediately following 'usb' incrementally until successful. Alternatively, also increase the digit immediately following 'disk@' until successful, depending on the OS chosen.

If you are unable to boot Mac OS X using the provided methods, try replacing ':tbxi' with ':3,\System\Library\CoreServices\BootX'.

#### Tricks

- To initialize The Boot Picker faster, enter setenv skip-netboot? true. This will disable scanning for a bootable network OS. To turn NetBoot back on, enter setenv skip-netboot? false.

- To set up a personalized welcome message for Open Firmware to repeat upon activation, enter setenv oem-banner < enter a custom message here > , and setenv oem-banner? true . 

- To spoof machine model - replacing "PowerMac3,5" with the suitable model name for your needs. Note the use of spaces after opening quotation marks is required.
    ```
    dev /
    .properties
    " PowerMac3,5" encode-string " model" property
    " PowerMac3,5" encode-string " MacRISC" encode-string encode+ " MacRISC2" encode-string encode+ " Power Macintosh" encode-string encode+ " compatible" property
    mac-boot
    ```

- To ensure easy USB booting, user DistroHopper39B on MacRumors came up with a pretty solid way for figuring out the device needed to boot:
    1. Acquire a powered USB hub.
    2. Plug the USB drive into the hub, and connect the hub to a wall power source and the computer.
    3. Turn on the computer and boot into Open Firmware.
    4. Type in the following commands:
        ```
        dev usb0
        ls
        ```
        If the disk isn't displayed or the output is just "ok", type the next incrimental number starting with usb1, usb2, usb3, etc.
        ```
        dev usb1
        ls
        ```
        Once the tree is displayed, use it to modify the following command
        ```
        boot usbX/hub@X/disk@X:,\\:tbxi
        ```

#### Actions

    mac-boot: boots either the specified default or first available operating system environment

    shut-down: saves all changes and turns off the machine

    eject cd: ejects the disc tray or loaded optical disc

#### Additional Resources

Resource 1: http://web.archive.org/web/20200529...ook/bonus/ancient/whatismacosx/arch_boot.html

Resource 2: http://www.firmworks.com/QuickRef.html

Original Article: https://forums.macrumors.com/threads/the-open-firmware-wiki.2225024/

#### Version History

Original Post Date: 2/28/2020
Updated Post Date: 5/6/2023
Today's Post Date: 7/14/2024

#### Acknowledgements

This guide was compiled by z970 of MacRumors with a section by DistroHopper39B