## PSU Information and Pinout

Below are some information about the pinouts and connectors on the PCI-X and PCIe models if you are looking on building your own PSU from an existing PC PSU.

    NOTE: THe PCI-X models use up to a 650W PSU, and replacements/used stock are pretty readily available online at time of writing. It is reccommended to purchase a refurbished unit if possible, however there is always the risk of buying a defective unit from auction sites and individual sellers.
    The PCIe moidel PSU's are much harder to find online, so if your PSU is dead then you may have to resort to getting fairly creative..

PSU Color Codes (AGP-based)

    - Orange = +3.3V
    - Red    = +5V
    - Yellow = +12V#1 & +12V#2
    - Blue   = -12V
    - White  = +25V StandBy
    - Purple = +5V Standby
    - Green  = PSU_ON
    - Black  = Ground

PCI-X PSU

    Model No. 614-0228
    Power Output: 450W Peak
    
    Model No. 
    Power Output: 650W Peak

    Pinout

    P1 Connector
        - 1. Sense      - 13. Ground
        - 2. Ground     - 14. PSU_ON
        - 3. +12V#2     - 15. Ground
        - 4. Ground     - 16. N/C
        - 5. N/C        - 17. Ground
        - 6. Ground     - 18. Ground
        - 7. +12V#1     - 19. Ground
        - 8. Ground     - 20. +5V
        - 9. +3.3V      - 21. Ground
        - 10. Ground    - 22. -12V
        - 11. Ground    - 23. Ground
        - 12. N/C       - 24. N/C

    P2 Connector
        - 1. +3.3V      - 9. +5V
        - 2. +3.3V      - 10. +5V
        - 3. +3.3V      - 11. +5V
        - 4. +3.3V      - 12. +12V#1
        - 5. N/C        - 13. +12V#1
        - 6. +12V#1     - 14. +12V#1
        - 7. +12V#1     - 15. +12V#1
        - 8. +25V_SB    - 16. Ground

    P3 Connector
        - 1. +5V        - 5. +5V
        - 2. Ground     - 6. Ground
        - 3. Ground     - 7. Ground
        - 4. +12V#1     - 8. +12V#1

PCIe PSU Pinout

    Model No.: 614-0379 -OR- 614-0384
    Power Output: 1000W Peak

    Pinout

    P1 Connector
        - 1. +3.3V (?)  - 4. +5V_SB (?)
        - 2. Ground     - 5. Ground
        - 3. -12V (?)   - 6. +25V_SB (?)

    P2 Connector

        - 1. +3.3V (?)   - 6. +5V_SB (?)
        - 2. +25V_SB (?) - 7. Ground
        - 3. Ground      - 8. Ground
        - 4. -12V (?)    - 9. PSU_ON (?)
        - 5. Ground      - 10. PSU_ON (?)

    Power Rail (From LEFT to RIGHT)

        - 1. +3.3V

        - 2. +5V
        - 3. Ground

        - 4. Ground
        - 5. Ground
        - 6. Ground
        - 7. Ground

        - 8. +12V_A
        - 9. +12V_B

