## Installing Fienix OS for PPC

#### Preface

Fienix is a community driven OS, based on Debian and designed for Big-Endian 32-bit and 64-bit PowerPC systems as well as 64-bit Little-Endian PowerPC systems. By curating a list of most commonly used packages, it appears Fienix has frozen certain packages to provide a stable desktop experience for PowerPC users, especially those running Big-Endian CPU's. It's goal is to provide a PowerPC focused OS with the idea that most PowerPC devices dont have any CPU management chip that may phone home, and have OpenFirmware that allows command-line access to the on-board firmware. This also pertains to the Power architecture now being open sourced, leading to Power9 and Power10 CPU's being entirely auditable, and at least one manufacturer making consumer desktops with a completely auditable platform.
    
Tne biggest downside to Fienix is that you don't have access to every Debian PowerPC package out of the box, meaning you may not be able to compile certain complex packages from source as dependencies may not be available. The flipside to that is that the current Debian Sid image is very unstable, and you will usually be met with conflicting package versions and have to search for older archives of said dependancies and hope you don't break anything further. There is also the very high chance that when Debian 13+ rolls around, booting on Apple hardware will become a heavy chore, if not nearly impossible for most users. This is why Fienis may be the best choice for a stable modern OS on your G5 if you are purely in it for the love of the Big-Endian PowerPC architecture and Linux.

#### Downloads

Downloads are available from the link below. Be sure to select the OpenFirmware (OF) image.

LINK: https://fienixppc.blogspot.com/p/download.html

#### Installation

Installing is pretty straightforward if you burn the image to a DVD, as you can boot directly into the installer by holding [C] after the boot chime.

If wanting to install from USB, please refer to the Open Firmware Wiki section of this GitHub repository, as booting from USB isn't very straightforward and would cause lots of repeating in this guide...

#### Issues

I got an undocumented issue when installing the first time, right after running Debian and testing hardware. The issue was a failute during the install related to yaboot bot being able to find the root partition. I realized an internal PCIe NVMe drive was still attachexd which caused Yaboot to bug out. Once I removed the NVMe adaptor the install completed with no issues, after completing I was able to re-install the NVMe adaptor and boot into Fienix with no issues.

