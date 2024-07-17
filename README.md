# Apple Power Mac G5 Maintenance & Modernization Guide


#### Information on the Apple PowerMac G5 (AGP & PCIe) including repair, preventatve maintenance, upgrades and software.

## Quick Notes

  - This guide is compiled from personal experience using an Apple G5 "Quad" as well as other users hard work and research.
    
  - I am working on obtaining a functional AGP based machine, so information gathered from other sources on this platform is untested.

  - Anything missing, desired, copyrighted, incorrect or unclear should be reported using the Issue tracker to be reviewed.

  - THIS GUIDE IS UNDER CONSTRUCTION; THIS MESSAGE WILL BE REMOVED WHEN ALL LINKS AND IMAGES ARE FINALIZED!!!

## Table of Contents:

1. [Specifications](#specs)
1. [Introduction](#intro)
1. [Apple Service Diagnostics Media](#diag)
1. [Beep and Light Codes](#codes)
1. [Dissasembly & Service Manuals](#service)
1. [Thermal Management](#thermal)
1. [RAM Information](#ram)
1. [PCIe & PCI-X Cards](#pci)
1. [IDE & SATA Information](#storage)
1. [Power Supply Information](#psu)
1. [Installing an Operating System](#os)
1. [OpenFirmware Information](#firmware)
1. [Logic Board Information](#mobo)
1. [Other Information & Troubleshooting](#other)
1. [Credits](#credits)

<a name="specs"/>

## Specifications

- Board form factor
  - Proprietary G5 Layout
- CPU
  - IBM PowerPC 970 64-bit; single-core, up to dual CPU's; POWER4 w/ AltiVec Extensions; 1.6GHz - 2GHz
  - IBM PowerPC 970FX 64-bit; single-core, up to dual CPU's; POWER4 w/ AltiVec Extensions; 1.8GHz - 2.7GHz
  - IBM PowerPC 970MP 64-bit; dual-core, up to dual CPU's; POWER4 w/ AltiVec Extensions; 2GHz - 2.5GHz
- RAM
  - IBM PowerPC 970 & 970FX: Up to 8x PC-3200 DDR 1GB Modules
  - IBM PowerPC 970 MP:      Up to 8x PC2-4200 DDR2 2GB Modules
  - ECC Supported 970MP (NOTE: Must be Non-registered/Unbuffered)
  - Up to 8GB on 970 & 970FX; Up to 16GB on 970MP (Possibly up to 32GB)
- Storage
  - PowerPC 970 & 970FX: 2x SATA I
  - PowerPC 970MP: 2x SATA II
  - 1x IDE CD/DVD-Drive
  - Optional: 3x PCI/PCIe Add-in Cards (Support varies under OS X)
- Network
  - 2x Gigabit Ethernet with RJ-45 connector
  - Optional: AirPort Extreme with WiFi b/g; APE with WiFi b/g + Bluetooth 2.0; 56k Modem
- PCI
  - PowerPC 970 & 970FX (Low End):
    - 3x PCI 32-bit Connectors
    - 1x AGP Pro Connector (OpenFirmware GPU only; won't boot without)
  - PowerPC 970 & 970FX (High End):
    - 2x PCI-X 64-bit Connectors @ 100MHz
    - 1x PCI-X 64-bit Connector @ 133MHz
    - 1x AGP Pro Connector (OpenFirmware GPU only; won't boot without)
  - PowerPC 970MP:
    - 1x PCIe x16 Connector (OpenFirmware GPU only; won't boot without)
    - 1x PCIe x8 Connector (PCIe x16 profile)
    - 2x PCIE x4 Connectors (PCIE x16 profile)
- USB & FireWire
  - PowerPC 970 & 970FX:
    - 3x USB 2.0 (1F + 2R)
    - 2x FireWire 400 (1F + 1R)
    - 1x FireWire 800 (Rear)
- Audio
  - 2x 3.5mm Audio Out (1F + 1R)
  - 1x 3.5mm Audio In (Rear)
  - 1x Optical S/PDIF Input (Rear)
  - 1x Optical S/PDIF Output (Rear)
- Cooling
  - Aluminum/Copper Heatsink (Single and Dual CPU's under 2.5GHz)
  - Liquid Cooling System (Dual CPU's over 2.3GHz)

<a name="intro"/>

## Introduction

  The G5 series of computer's by Apple were their last line to contain an IBM PowerPC processor before moving to Intel's x86. This article focuses on the Power Mac G5 workstations, since their appears to be a community of people still using them for retro and modern computing and the fact they have some powerful expandability. The Power Mac G5 was proprietary and a very powerful workstation at the time and this has lead to many hardware and software issues as time progresses. Hardware issues include Coolant Leaks, Corrosion, Memory Failures, PSU Failures, etc.; Software issues mainly being depreciated OS X and Linux. Assuming all hardware is working 100%, due to software concerns breifly mentioned above, these computers are slowly becoming more in the realm of retro enthusiests than using this as a fun/weird daily driver.

  All that said, the aim of this guide is to compile information and provide the tools to get your machine working as best as possible for your use case. If you have a Liquid Cooled (LCS) machine, I have provided a new and much easier method for converting to Air Cooling that most people should be able to perform, as well as information for rebuilding the existing LCS. From my experiences trying to run Linux, to questionable mods, to old resources with broken links, I felt compelled to compile this all in one place. If there is anything not well explained, a missing issue, or an error with information on this guide, please open an Issue so I can review.

<a name="diag"/>

## Apple Service Diagnostics Media

Before you continue further, if you are reading this documentation in order to repair or maintain your device, please grab one of the ASD ISO's below. This image contains the ASD boot media with diagnostic tools and thermal calibration utility. This is an essential tool for diagnosing Memory, CPU, Thermals, and any other hardware issues on your device.

[Apple Service Diagnostics v2.6.3](Download-ASD263.md)
  NOTE: For Mid-Late 2005 Apple PowerPC devices

[Apple Service Diagnostics v2.5.8](Download-ASD258.md)
  NOTE: For Late 2003 to Early 2005 PowerPC devices

<a name="codes"/>

## Light and Beep Codes

  The G5 comes with a few on-board diagnostic hardware tests that produce a visual or audible error code. The PowerPC 970MP models come with a set of LED diagnostic lights to the left of the top-most memory slots. The rest applies to all machines.

[Light and Beep Code Guide](Guide-codes.md)

<a name="service"/>

## Disassembly & Service Manuals

  The G5 is an Apple product, and it is only meant to be taken apart so far by consumers and service technicians alike. That said it's not hard to take this apart, but it can be tedious since the board is so large and has some quirks to how it was installed. That being said, the people over at iFixit have written an excellent teardown of the PCI-X based models and mostly applies to the PCIe models other than some 'power screws' at the botom and the CPU standoff's.

  iFixit Power Mac G5 Disassembly: https://www.ifixit.com/Device/Power_Mac_G5

  Apple G5 Late-2005 Service Manual: https://www.applerepairmanuals.com/the_manuals_are_in_here/powermac_g5_late2005.pdf
  Apple G5 Launch to June 2004, Early-2005: https://www.applerepairmanuals.com/the_manuals_are_in_here/powermac_g5.pdf
  Apple G5 Late-2004 Service Manual: https://www.applerepairmanuals.com/the_manuals_are_in_here/powermac_g5_late2004.pdf
  Apple xServer G5 Service Manual: https://www.applerepairmanuals.com/the_manuals_are_in_here/powermac_g5_late2005.pdf

  G5 Thermal Calibration Guide: https://www.applerepairmanuals.com/the_manuals_are_in_here/thermalcalibration-resultsguide-rev5.pdf

<a name="thermal"/>

## Thermal Management

  The PowerPC 970 is a very hot running processor; Apple, Microsoft and Sony had their work cut out for them trying to cool down IBM's complex chip. Below are a few sections covering everything cooling related, as well as a warnings as there is no Integrated Heat Spreader (IHS) and just the exposed CPU die.

[Removing and Refilling LCS](Guide-LCS.md)

[Converting LCS to Air Cooling](Guide-Aircool.md)

<a name="ram"/>

## RAM Information

  The G5 is very peculiar when it comes to the issue of memory. These CPU's and memory controllers were used in specific lines of computers versus x86-based machines needing to support a wider variety of 3rd party vendors. This means that mixed result's can occur when using non-supported memory, as well as with some that seemingly should work. Some models even experience bad enough overheating that solder joints can fail around the RAM slots on some older models. Any of these issues can cause a headache, combine these together with potentially bad used RAM online, and you'll be convinced the machine is possesed. Hopefully some of the sections below can help you determine your issue.

[Identifying & Troubleshooting RAM](Guide-RAMsearch.md)

[Troubleshooting Failed Solder Joints](Guide-RAMsolder.md)

<a name="pci"/>

## PCIe & PCI-X Cards

  The G5 Series has a couple of different configurations of PCI I/O depending on year and configurations. Under OS X, non-GPU cards are limited by their driver support and GPU's are limited by OpenFirmware; under Linux non-GPU cards have much better support with a modern kernel while GPU's are a very mixed bag due to several issues. Below sections cover cards I have tested and researched online. Due to the further depreciation of stable "ppc64" based Linux distributions, information on GPU support is changing as things break. Information is subject to change.

[PCI & PCI-X I/O Cards](Guide-PCIio.md)

[AGP GPU Cards](Guide-PCIgpu.md)

[PCIe I/O Cards](Guide-PCIEio.md)

[PCIe GPU Cards](Guide-PCIEgpu.md)

[GPU Firmware Hacking](Guide-GPUhack.md)

<a name="storage"/>

## IDE & SATA Information

  The most important thing to note is the earlier PowerPC 970 and 970FX processors only came with SATA I, while 970MP models came equipped with SATA II. This means if using a newer SATA drive it is best to confirm whether it supports SATA I/II backwards compatability, which a good number of drives do. As far as IDE optical drives I haven't ran accross any aftermarket drives which didn't just work. Below is a breif of this section.

  <b>SATA</b>

  PowerPC 970 & 970FX:
      These models only support SATA-I on-board, meaning you need to be careful if you are purchasing a drive so that it will work without issue. You may also purchase a PCI SATA II controller for expansion, some of these even allowing to be booted from.

  PowerPC 970MP:
      These models have on-board SATA-II ports and have better compatability with SATA-III drives, but only drives that support SATA-II backwards compatability. There's little info on botable PCIe SATA-III cards, however there are SATA-III PCIe cards that can be detected undr OS X just fine.

  <b>IDE</b>

  Not much to be said here, as all the IDE drives I was able to test were able to boot media and had no issues under OS X. However I recommend keeping to a period correct replacement IDE-drive (Manufactured between 2000-2006) from Lite-On, Samsung, Hitachi, or Panasonic. Make sure the length is shorter to match the G5 drives dimensions. 

  The only thing needed to modify on the new IDE optical drive is to remove the drive door "cover", a var of plastic that sits on the front of the CD tray. This plastic bar can be lifted upwards when the CD tray is ejected/exposed. Once removed, you may also take the metal brace and plastic Apple coverings off the old drive and transfer them to the new one.

<a name="psu"/>

## Power Supply Information

  The PSU in the G5 is a workhorse, and has to manage massive amounts of power with some being threatened by a leaky coolant system. Depending on model you have, the machine can range from a maximum power draw of up to 430watts all the way over 1000watts for the G5 Quad. Idle power draw can be from 40watts up to almost 200watts for the Quad. Essentially these are beefy supplies that can be put through a lot of stress, and when it comes to the Quad's power supply there really aren't any replacements to be found online due to limited ammount.

[PSU Information and Pinout](Guide-PSUopen.md)

<a name="os"/>

## Installing an Operating System

  Nowadays the G5 is limited in alternative distributions, however the scene has become very interesting due to this. As far as OS X the last version supported was OS X Leopard 10.5.8 and is missing maany modern features and security updates. A project called Sorbet Leopard aims to remedy this by providing some features from Snow Leopard as well as including scripts and a curated app store for enthusiests of the OS X experience. It is a nice little OS and gave me a nostalgia trip, however due to it trying to keep an unmaintained OS alive itdoes have caveats with the modern internet.

  Linux is another beast, as much of the architectural support for ppc64 big-endian dropped off at the end of the 2010's. The industry has since adopted ppc64le and has almost entirely switched over to that architecture. Debian 8 "Jessie" was released in 2015 and got it's last updates for ppc64 in 2019.This means at time of writing it's been over 5 years since any updates, almost 10 years since the last major supported release, and that any support on Debian 12 (sid) is a miracle within itself. The OpenFirmware bootloader is a nightware to work with, and it took many years after support dropped for the bootloader to finally switch from Yaboot to GRUB without major issues.

  There is a project called Feinix OS which is designed for most all PowerPC 64-bit Big-endian systems, and is designed specifically to keep these kind of systems alive in the modern world. It is Debian derived with the Apt package manager, howevever it lacks many modern packages for Debian due to the constantly updating nature of Debian Sid/Testing. By curating it's packages it aims to provide a stable distribution with minimal breakage. This means that it's harder to use it as a testing platform for compiling modern software, but at the same time this issue exists on Debian Sid because dependancies are regularly on different versions causing dependancy hell.

  All of that said, the below sections walk through locating install media as well as tips for getting certain things working.

[Installing Mac OS X Leopard 10.5.4](Install-OSX.md)

[Installing Sorbet Leopard 10.5.8](Install-Sorbet.md)

[Installing Fienix OS for PPC64](Install-Fienix.md)

[Installing Debian Sid for PPC64](Install-Sid.md)

<a name="firmware"/>

## OpenFirmware Information

  OpenFirmware is the "BIOS" used by Apple and their G5 line of computers, which is a derivitive of OpenBoot that was developed by Sun Microsystems. These system firmware uses the Fourth programming language and aren't very user friendly by design. OpenFirmware actually has a lot of modern features compared to BIOS at the time and was targeted more primarily at UNIX workstations and servers. As far as we are concerned, we won't be spending much time in the OpenFirmware environment, however one area we may want to explore is USB booting.

  OpenFirmware being Fourth-based will look different very foregn even to most Linux users, and many guides covering USB boot generally ask you to "guess" the usb port since they are hardcoded and vary by platform. Since we are specifically using the G5 here, let's break down a little of these commands and USB port locations to better understand it.

[Open Firmware Wiki](Guide-OF.md)

<a name="mobo"/>

## Logic Board Information

  The mainboard in the Apple G5 is inhernetly proprietary, whith design being derived from IBM big iron. This board is absolutely massive, and can comes in a nice deep-blue color. Depending on the model, ports and layout's change, which is why I compiled a few pictures of boards with front and back images with details to help identify areas of the board for education and troubleshooting.

<a name="other"/>

## Other Information & Troubleshooting

  This area is for issues that don't fit into the categories above, or may be less encountered.

  Bent CPU Pins:

  If you have a bent mezzaine pin on the Logic Board or CPU carrier board, it's not the end of the world! I noticed disassembling my unit I had a shorted pin across the connector on the Logic Board, pictured above. After using a cheap handheld microscope I was able to see how the pin needed to be set back into place. Using some Electro-Static Safe tweezers, I was able to nudge the bent pin close enough into the original position. Please note great care is needed when bending one of these mezzaine pins back into place, as too much force could damage that or other surrounding pins which may render the repair more costly/time consuming than worth it.

  CPU Replacement/Upgrade:

  Even thought the CPU carrier connector may be compatible with your motherboards revision, the CPU will generally not be swappable into most other machines if they came with a different CPU configuration. Unlike many x86 motherboards at the time, the Front Side Bus (FSB) is locked to half of what the CPU is running at; the Late 2004 "PowerMac9,1" FSB is clocked to 1/3rd the CPU speed. The machines are also configured to throw an error if one of the CPU's aren't detected, expecting a major issue requiring Apple technicians to repair.

  That said, it's not generally possible to either remove a single CPU from a dual-CPU configured system, nor change to a CPU of a different clock frequency. If you have a bad CPU however, you can swap it in for a like model CPU are they are not serially tied to the Logic Board.

  CPU Overclocking:

  Nope. Not possible. Only false claims of this for internet fame/infamy. Partly due to what I mentioned about the FSB above, these boards are configured for the exact processor and speeds in which they were designed for. Overclocking the CPU would require several things which have yet come to fruition:

  1. Figuring out if the CPU clock is hard-coded on-die, on the carrier board via resistors or IC, or from an IC on the Logic Board.
  2. Figuring out how to talk to the chips that control the FSB, or if it's hard-coded into logic.
  3. Being able to read and write to said control logic.
  4. Schematics or information on how all of this logic flows and talks to eachother.
  5. A power supply able to handle increased currents; PSU north of 1400W minimum for a G5 Quad.
  6. A way to cool the machine better and faster on its already strained thermals.

<a name="credits"/>

## Special Thanks and Sources

  This guide was made using some of my own personal findings, but also couldn't have been made without others putting time and effort into many different aspects of this platform, even those performing risky air conversion mods, which I highly commend for taking the time and risks. I am absolutely obsessed with RISC computing, especially for modern use cases, so this has been a very educational experience for me and hope at minimum you learn something new from this. As they say it's not about the goal but the journey, and this machine even today will take you for a trip!


Source: http://www.jcsenterprises.com/Japamacs_Page/All_Things_PPC.html

Source: http://themacelite.wikidot.com/start

Source: https://forums.macrumors.com/threads/radeon-x1900-g5-mac-edition-cheap-n-easy-flashing-guide.2308103/

Source: https://forums.macrumors.com/threads/sorbet-leopard-your-power-mac-unleashed-revision-1-5-released.2300924/

Source: https://forums.macrumors.com/threads/snow-leopard-on-unsupported-powerpc-macs.2232031/

Source: https://68kmla.org/bb/index.php?threads/powermac-g5-quad-the-new-blood-mod-a-guide-to-flushing-modifying-and-refilling-the-dual-pump-cooling-system.37474/

Source: https://www.applerepairmanuals.com/gseries.php
