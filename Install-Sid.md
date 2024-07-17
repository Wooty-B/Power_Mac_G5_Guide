## Installing Debian Sid for PPC64

#### Preface

    Debian 8 Jessie was the last stable version of Debian for the ppc64 (Big-Endian) architecture, since then Debian has seen continual updates to ppc64 packages and is technically installable to G4 and G5 PowerPC platforms in the form of Debian Sid. For those unaware, Sid is the character from Toy Story who breaks all of his toys, and theres a reason (other than their Toy Story naming convention) Debian Testing is referred to as Sid. Debian Sid is unstable and the development bleading edge release of Debian, making it a rolling release. This sounds fantastic, having all modern up-to-date packages, except for the fact ppc64 hasn't been officially supported since 2015.

    Many packages get broken often, the most commonly used ones usually maintaining compatability, usually. The problem comes when trying to update certain packages, as many dependencies that aren't as regularly updated could be a version behind, leading to dependancy hell where you can't install the correct versions of dependancies. So for example when trying to install 'openmw' from apt, it fails because several libraries haven't been updated, meaning you can wait for the developer to update them but then the other dependencies get updated further leading back to square one. This leads to one needing to scour Debian Package Repository Archives to locate the correct package versions needed, hoping one isn't required by the OS to function. Another example is DE's, where I can get XFCE working but GNOME is missing a couple critical packages.

    Theres a lot more I can go into however my main point is... This is an experimental OS thats breaking further into the future, and at some point may break beyond usability. My theory into Debian 12 possibly being the last bootable version for ppc64 is because images released after May of 2023 don't seem to boot at all, this could be due to something breaking and developers unaware, or something breaking and developers not caring. If you continue, Your Milage May Vary.

#### Downloading

    Current Sid PowerPC images don't appear to boot at all, and get hung after the GRUB bootloader. Older versions of Sid and Stable used Yaboot as that was the best loader for Apple PowerPC machines, however booting was 'fixed' for GRUB and this could be part of why things are broken. To install Debian 12 Sid as of July 2024, please use the archived image below, the last bootable version of Sid at time of writing.

        LINK: http://cdimage.debian.org/cdimage/ports/snapshots/2023-05-16/debian-12.0.0-ppc64-NETINST-1.iso

#### Installing

    1. Download the image from the link above.
        a. Burn the image to a CD/DVD (Preferable, but slower)
        b. Write the image to a USB drive. You will need to go to the Open Firmware Wiki section on the main GitHub repository page, scroll down to the "Installing an Operating System" chapter and follow instructions for "Linux (GRUB)"

    2. Boot the install media following the method you chose
        a. CD/DVD: Press and hold [C] at the boot chime
        b. USB: Press and hold [OPT]/[ALT] at the boot chime, then press [CTRL]+[Z] at the boot menu.

    3. Follow on-screen instructions for installing to an internal SATA drive. The installer takes care of the partitioning and bootloader without issues, in the past some of this needed to be manually configured.

    4. When asked if wanting to install a Desktop Environment, either don't select anything or just XFCE. Most other DE's are currently broken.

    5. After installation is complete, boot into your fresh Debian Sid install to continue with a few more steps.
        NOTE: At this point, you will need to ```su -``` to the root account to install sudo and potentially fix system.

    6. Run ```apt update``` from the terminal and if no errors, then try to install a package such as ```apt install sudo```. If no errors about 'start-stop-daemon' appear, skip to Step #8, otherwise continue.

    7. If you recieved an issue with "start-stop-daemon", we will need to fix "dpkg". Follow the steps below to resolve this issue:
        a. Run ```apt show dpkg``` and note the dpkg version number. We will use "dpkg v1.22.6" as an example.
        b. Download the package from the link below, as it should be close to the version you're using.
            LINK: http://ftp.ports.debian.org/debian-ports/pool-ppc64/main/d/dpkg/
            NOTE: It's in the format of "dpkg_1.22.6_ppc64.deb"
            COMMAND: wget http://ftp.ports.debian.org/debian-ports/pool-ppc64/main/d/dpkg/dpkg_1.22.6_ppc64.deb
        c. Make a "dummy binary" using the commands below:
            ```
            echo '#!/bin/true' > /usr/bin/start-stop-daemon
            chmod +x /usr/bin/start-stop-daemon
            ```
        d. Now reinstall dpkg from the package we downloaded using the following commands. Note this is an example.
            ```
            dpkg -i dpkg_1.22.6_ppc.deb
            ```
    8. Install sudo and promote your user by running the following, replacing with your username where noted:
        ```
        apt install sudo
        usermod -aG sudo *username*
        ```

    9. Reboot the machine by running ```reboot```

    10. If you didn't previously, you may now run ```sudo tasksel``` from the terminal to install XFCE or another supported DE, however you may need to manually install others, if they are functional at all.

#### Final Thoughts

    As I stated at the beginning of this guide, Debian Sid for ppc64 is more unstable than other arcitectures due to packages being updated irregularly due to dwindling developers and the fact users of the Power platform have switched to Little-Endian based CPU's. The only possible way I see Debian Sid being used with stability is if someone managed to comb through all the archival snapshots of the ports repository and built their own repository with packages matching their architectural counterparts package versions for Debian 11 and 12. That may be easier said than done, and if it was that easy I'm sure Fienix OS would have looked into this, or maybe not. Intrusive thoughts.