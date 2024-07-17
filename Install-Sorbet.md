## Installing Sorbet Leopard 10.5.8

#### Preface

    This is another section that can be contributed to user z970 of MacRumors, as they compiled and pulled the team together to peice this "enhanced" version of Leopard for Power Macs. Sorbet Leopard is a pre-installed disk image with OS X 10.5.8 installed, providing the last updates ever released by Apple. This also includes all the OS X drivers for ATI and nVidia GPU's supported under OS X, including flashed cards. Besides drivers and updates, it also includes a new curated App Store that provides applications created by other users.

    A good portion of these sections are taken from the MacRumors forum post, sources will be provided at the bottom of this page.

#### Overview

Sorbet Leopard can be thought of not only as something of an entirely new Mac OS X distribution, but also as an effective version 10.5 and 10.6 hybrid. This means that while the base system was built off of the rock-solid foundation of Mac OS X 10.5.8, as many parts and components as possible have also been transplanted from Mac OS X 10.6.8, in addition to custom updates, refinements, and performance optimizations having been bolted on. As a result, Sorbet Leopard boasts the following system refinements built right in:

    - Improved startup times and application launch times

    - Smoother graphical performance in most applications

    - Faster network performance in all system operations

    - PowerPC-optimized binaries

    - Reduced disk activity

    - Reduced CPU / RAM / disk usage

    - Safari 11 with new security updates and performance improvements, QuickTime 7.7 Pro, Bash 4.3.30, and ntpd 4.2.8

In addition, Sorbet Leopard brings the following new features and enhancements to your Mac:

    - A fully-featured live environment to boot into via FireWire or USB for performing administrative tasks separate from the startup disk

    - A brand new PowerPC-focused app store showcasing the best-in-class applications for 10.5

    - An accessible switch panel for quickly controlling various system functions and advanced settings on-the-fly without needing to manually resort to the command line

    - Full support for the Apple Wireless Keyboard

    - Full support for the Apple Magic Mouse + Momentum Scrolling

    - Full support for Unicode 13.1 emoji characters*1

    - 10.6.8 desktop pictures, user pictures, screen savers, Apple dictionary definitions, fonts, and apps

    - 10.13.6 security certificates pre-installed

    - Readily themeable to OS X Mountain Lion, macOS High Sierra, and iOS (4 through 12) system appearances right out of the box

    - Universal ad blocking

#### System Requirements

    - A PowerPC G4 or G5 processor

    - 512 MB SDRAM or better

    - A 16 GB Apple Partition Map-formatted partition or larger

    - An OpenGL 2.0-capable video card is recommended

    - An installation to flash-based storage is suggested

#### Downloads

    Downloads are hosted at Macintosh Garden due to filesize. Download the following files below:

        1. Sorbet Leopard R15 Disk Image (Link 2 is a backup)
            LINK 1: http://macintoshgarden.org/sites/macintoshgarden.org/files/apps/Sorbet_Leopard_R15.dmg
            LINK 2: https://www.mediafire.com/file/69rtoa8tfxfeool/Sorbet_Leopard_R15.dmg/file

        2. Sorbet Plus  (Updated Mail app, printer drivers, and Sorbet App Store)
            LINK: http://macintoshgarden.org/sites/macintoshgarden.org/files/apps/Sorbet_Plus.zip

        3. Sorbet Supplimentary Update (Sorbet App Store Youtube Playback Fix)
            LINK: http://macintoshgarden.org/sites/macintoshgarden.org/files/apps/Sorbet_Leopard_Supplementary_Update.zip

        4. Carbon Copy Cloner 3.4.7f for PPC (Requires OS X Tiger 10.4 or Leopard 10.5)
            LINK: http://macintoshgarden.org/sites/macintoshgarden.org/files/apps/Carbon_Copy_Cloner_3.4.7.zip

#### Prerequisites

    1. OS X Tiger or Leopard installed on your G5
    2. A blank SATA HDD/SSD connected to internal SATA port or External USB-to-SATA adaptor
    3. A copy of the Sorbet disk image
    4. A copy of Carbon Copy Cloner (for ppc)

#### Installing

    1. Connect your SSD/HDD to your G5 via SATA or External USB adaptor.
        NOTE: Fortunately these are USB 2.0 ports, but install will take much longer using external adaptor.
    2. Power on your G5; in OS X, open Disk Utility and prepare the drive with the following properties:
        Size:       16GB Partition or larger
        Scheme:     Apple Partition Map
        Filesystem: Mac OS Extended (Journaled)
    3. Download the Sorbet disk image and Carbon Copy Cloner (CCC) for PPC to your G5, installing CCC.
    4. Open Carbon Copy Cloner and follow the following steps to write the disk image:
        a. Press "Source: Restore from disk image..."
        b. Select the 'Sorbet_Leopard_R15.dmg' disk image
        c. Select "Destination: (target partition)"
        d. Select "Handling of data already on the destination: Delete anything that doesn't exist on the source"
        e. Finally, press "Clone"
    5. You may now reboot into the new system by holding [OPT]/[ALT] on bootup, and selecting the disk from the menu. You can also swap the drives to change boot order if wanting to keep both versions installed side-by-side.

#### Acknowledgements

    Sorbet Leopard is a project created out of passion and obsession over the G5 platform and dwindling support as it entered the 2020's. It is not intended to be a modern version of OS X or completely up-to-date with security and modern web features, however it's probably the best OS X experience for this platform if you are determined to use this as a daily driver or for any type of media or editing.

    This project was almost entirely constructed by the G5 enthusiest z970, and all credit for this page goes to them since much of this guide was taken from the MacRumors forum post and Macintosh Garden page.

    SOURCE 1: https://forums.macrumors.com/threads/sorbet-leopard-your-power-mac-unleashed-revision-1-5-released.2300924/
    SOURCE 2: http://macintoshgarden.org/apps/sorbet-leopard
    