## Light and Beep Code Guide

#### Preface

Just a quick reference guide for common diagnostic codes. Onlt the first section about LED Error Codes applies to later G5's, otherwise the Power LED and audible beeps provide the same function on every model of G5.

#### LED Error Codes (PCIe)

Figure A

    LED #1:
        - Red: CPU A (Top) not detected or incompatible
    LED #2:
        - Red: CPU Thermal Overtemp
    LED #3:
        - Red: The power is on (Comes on when wind cover is removed during operation)
    LED #4:
        - Yellow (Trickle): Plugged into wall power correctly
        - Yellow (Solid):   Plastic wind cover removed (Giant clear plexiglass cover)
    LED #5:
        - Green: OpenFirmware booted and running without error (Comes on when wind cover is removed during operation)
    LED #6:
        - Red: CPU B (Bottom) not detected or incompatible
    LED #7:
        - Red (Solid): Checkstop; unknown error with logic. (Offset to botom right of LED's 1-6)
        - Red (Momentary): Displays when first booting then should power off

#### Power LED

    - Solid LED: Computer is powered on
    - 1 Flash:   No RAM Installed/Detected
    - 2 Flashes: Incompatible RAM Detected; RAM Installed Incorrectly; RAM Installed into wrong slots
    - 3 Flashes: RAM Banks Failed Testing
    - 4 Flashes: No boot images detected, Bad boot ROM
    - 5 Flashes: Prossessor Incompatible; Processor Not Functioning Correctly
    - 6 Flashes: Other unknown error with logic

#### Beep Error Codes

    - 1 Beep:  No RAM Installed/Detected
    - 2 Beeps: Incompatible RAM Detected; RAM Installed Incorrectly; RAM Installed into wrong slots
    - 3 Beeps: RAM Banks Failed Testing
    - 4 Beeps: Bad checksum for boot ROM
    - 5 Beeps: No boot images detected; Bad boot ROM

#### No Visual or Audible Codes

    Powers on without Chime:
        - Reseat GPU and determine it is a known working unit
        - After reseating, may need to press SMU reset button
        - May also need to pull wall power and wait about 10-seconds before retrying
    
    Powers on with Chime but no video:
        - Reseat GPU and determine it is a known working unit
        - Verify if your card takes a 6-pin Molex connector for power and that it is connected.
        - After reseating, may need to press SMU reset button
        - May also need to pull wall power and wait about 10-seconds before retrying