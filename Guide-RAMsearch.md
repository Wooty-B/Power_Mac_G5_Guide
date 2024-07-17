## Identifying and Troubleshooting RAM

### Memory Table

Memory Type:
- PCI-X: DDR SDRAM
- PCIe:  DDR2 SDRAM
  
Minimum RAM:
- Low-End PCI-X (Pre-2005):     2x 128MB DDR PC-2700 (Total: 256MB)
- Low-End PCI-X (Post-2005):    2x 256MB DDR PC-3200 (Total: 512MB)
- High-End PCI-X:               2x 256MB DDR PC-3200 (Total: 512MB)
- PCIe:                         2x 256MB DDR2 PC2-4200 (Total: 512MB)

Maximum RAM:
- Low-End PCI-X (Pre-2005):     4x 1GB DDR PC-2700 (Total: 4GB)
- Low-End PCI-X (Post-2005):    4x 1GB DDR PC-3200 (Total: 4GB)
- High-End PCI-X:               8x 1GB DDR PC-3200 (Total: 8GB)
- PCIe:                         8x 2GB DDR2 PC2-4200 (Total: 16GB)

ECC support:
- PCI-X: No
- PCIe:  Yes; Un-registered, un-buffered only

Memory Standards:
- JEDEC
- 18 modules per stick maximum

Notes:
- Using lower than recommended speeds 'may' not allow the G5 to boot.
- Using higher than recommended 'should' clock down and work; 2x2GB sticks of PC2-6200U booted but with errors in ASD.
- Sticks must be installed in pairs of matching size and specifications.
- Apple reccommends installing RAM in the innermost slots, and working outwards; however the G5 should boot with RAM only in the outer slots, provided they are still paired in matching slots.

### Purchasing Options

Other World Computing:

DDR 2x1GB PC-3200: https://eshop.macsales.com/item/OWC/3200DDR2GBP/

DDR2 Non-ECC 2x2GB PC2-4200: http://eshop.macsales.com/item/OWC/4200DDR2M4GP/
DDR2 ECC 2x2GB PC2-4200:     http://eshop.macsales.com/item/OWC/42ECDDR2M4GP/

eBay, AliExpress, $ Etc...

NOTE: As time progresses aquiring these older compatible sticks will be harder to obtain meaning an auction platform, classified ads and cheap Chinese retail sites will be your best bet. A word of caution is to be careful when purchasing memory or storage products from un-verified sources as counterfeit storage and memory chips are rampant across auction and Chinese retail platforms. Purchasing fake or defective memory chips may permenantly damage your computer, so be sure to test purchased components on a 'disposable' machine if possible.

### Troubleshooting

#### Before Booting

1. Be sure the RAM module meets the specifications required by your G5 model.

   EXAMPLE: DDR PC-3200 for early High-End PCI-X machines

2. Be sure there are no more than 18 Memory chips on the stick.

   NOTE: Most 1GB & 2GB sticks of DDR2 have on average 16 memory chips

   NOTE: Most 512M & 1GB sticks of DDR have an average of 16 memory chips

#### If No Boot or Audible Beep Codes

1. Be sure the memory modules are seated properly and are clean of any debris
    
2. If swapping out memory, sometimes pulling wall power for 10 seconds will clear errors
    
3. If pulling wall power doesnt work, press the PMU_RESET button on your board with wall power applied

4. If using more than two sticks of RAM, and have 4 Pairs of RAM slots (8 total slots):

   a. Verify RAM in slots 1/2 are working with no other RAM present, verify each pair of RAM boots in slots 1/2

   b. Remove 2 sticks of RAM in slots 3/4, 5/6, and/or 7/8 until error clears

   c. If slots 1/2 don't seem to work, try in slots 3/4, 4/6 and 7/8

5. If issue persists, you may have:

   a. Faulty or Incompatible Memory

   b. Bad RAM slot solder joints (More common on PCI-X models)

   c. Faulty Processor (Review Beep and Light codes section)

#### If Boots with OS Crashing

1. Firstly, run the Apple Service Diagnostics (ASD) media for your device; at minimum run all Memory tests for each bank of RAM.

   a. If there are any failures, note the bank/slot that failed the test and swap memory modules around

   b. Retest to verify if the test failure follows the stick to a different slot or remains on that slot

2. If issue persists, you may have:

   a. Faulty or Incompatible Memory (Most likely)

   b. Bad RAM slot solder joints (More common on PCI-X models)

   NOTE: OS X 10.5.8 doesn't use as much memory as Linux, therefore it's possible to see the memory detected in OS X and get a somewhat stable experience most of the time. As soon as your OS accesses the faulty section of memory things can immediately crash the system. Since modern Linux accesses more RAM if it's available you are likely to get crashing during the installer portion. This is why I highly recommend running ASD even if you think your system is running smoothly, just to be on the safe side of things.
