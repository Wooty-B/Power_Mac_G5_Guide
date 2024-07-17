## PCIe GPU Cards

This section covers known working GPU's for OS X and Linux, as well as some useful notes. If you have any cards that have been tested working/not working please reach out using the Issue tracker so I can update this list.

NOTE: The G5's with PCIe use PCIe Gen 1, meaning you may need to be careful about bandwidth and backwards compatability when obtaining a card.

### OS X and Linux Supported Cards

#### nVidia

- GeForce 6600 LE           | Mac Version
- GeForce 6600              | Mac Version
- GeForce 7800 GT           | Mac Version | Windows Flash
- GeForce 7800 GTX          | Windows Flash
- Quadro FX 4500            | Mac Version | Windows Flash

#### ATI

- Radeon X1900 GT           | Mac Version | Windows Flash
- Radeon X1950              | Windows Flash

### Newer PCIe Cards Under Linux

At some point in the past few years, support was a little better for alternative cards, but as time progresses regressions have occured in ppc64 drivers causing mixed results. Below are some notes on the matter.

1. Any newer cards that cannot be flashed for OS X (and thus boot from) may be used under Linux using the x8 PCIe slot
2. The G5 with PCIe is generation 1, meaning theres a few things to take note of
   a. Running PCIE Gen 2 or Gen3 cards will be bottlenecked by half to a quarter available bandwidth, especially when running in x8 or x4 mode.
   b. The G5 must have a Mac supported GPU in the x16 slot to boot, meaning you will need to use the x8 slot, and less preferably the x4 slots.
   c. In my testing some older nVidia cards require an x16 slot to boot such as the Quadro 3700 FX, and may not be able to run in x8 mode.
3. Video drivers are regressing as ppc64 support dwindles, as focus has shifted primarily to ppc64le (little endian) as it is the successor to ppc64.

    
If you have had recent success running certain PCIe combinations under Linux, please let me know so I can post as much information on the subject!
