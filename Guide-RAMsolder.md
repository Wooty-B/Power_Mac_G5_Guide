## Troubleshooting Failed Solder Joints

    This section assumes you have read through the 'Identifying & Troubleshooting RAM' section, and have identified that you more than likely have failed solder joints. This issue is more common on earlier G5 unit's than on later ones, so be sure you have done as much troubleshooting as possible first as this isn't something you want to perform unless you have to.

    Warning on Hot Air Soldering
    
    You want to do this as fast as possible, as to not allow the board to heat up and possibly affect other nearby components.

        - Typical Lead-free solder melts around 220C.
        - Setting the hot air to lower temp will require more time, the more time heating allows the heat to spread throughout the board, heating components further away from the RAM slots.
        - Setting the hot air to high fan will blow the air more around the board, and can cause too much hot air to be blasted in a concentrated area.
        - The longer the hot air is heating up the board, the higher chance for RAM slot melting to occur. Be sure not to spend too much time in one area as it increases likelyhood of melting plastic.
    
    Required Supplies

        - Hot Air Gun
        - Solder Flux
        - Solder Paste (Optional)

    1. First step is to remove the Logic Board from the machine. Please follow the iFixit guide linked below.
        LINK: https://www.ifixit.com/Device/Power_Mac_G5
    2. Once disassembled, lay the board on it's front to expose the back of the Logic Board.
    3. Depending on model, you may have to remove the Northbridge and Southbridge hatsinks.
        NOTE: These heatsinks should not be removed unless absolutely necessary.
        If removing them, be sure to reapply a high quality thermal paste as these chips get very spicy.
        Some boards have a thermal sensor in the heatsink, be sure to disconnect this wire to avoid damage.
    4. Apply a generous amount of Solder Flux to the exposed pins of the RAM slots.
    5. Turn on your hot air gun on to about 400C with low fan speed.
    6. Work your way around the memory slots in a back and fourth sweeping motion, making sure to direct air only around the memory solder joints.
        NOTE: Solder should start turning a shiny metalic color and look liquidy. Once this occurs, that area should be complete.
    7. Once all solder joints look like they have reflowed, you may want to test while the computer is disassembled.
        a. Make sure all fans, sensors, drives, CPU's and GPU are connected.
        b. Use a makeshift shroud or cardboard around the CPU's for better airflow, if doing extended tests.
        c. Ensure nothing conductive is making contact with the motherboard in its exposed state.
    8. Boot the computer with Apple Service Diagnostics (ASD) media and run memory tests to ensure the issue is fully resolved.
        