## Converting LCS to Air Cooling - By WootyB

#### Preface

After recieving my G5 Quad from a questionable eBay purchase, one of the first things I noticed was pretty much all of the coolant was dried out. My unit came with a "coolant diaper" which I haven't seen in almost any other pictures online, and not sure if this was Apple authorized or an aftermarket addition but just goes to show this was a serious issue with these machines. After taking apart the unit and doing some research online I tried draining and replacing the coolant and it turned into a whole ordeal... Suffice to say I started looking at Air Cool conversion mods online, and to be honest... I was horrified by most methods.

The problem with most G5 air conversion mods is there's a few different methods floating around online with questionable practices, which can be counter-intuitive if this is being done for the sake of longevity. A few things I have seen in these mods:

- Bending, cutting, removing heatsink fins for clearance. (Should not have to sacrifice looks and potential cooling)

- Removing the copper CPU carrier heatsink/fin. (Not meant to be removed, especially on older CPU's as they are glued)

- Using a hot air gun to remove the copper CPU carrier heatsink/fin. (Uneccesary heating of CPU carrier and potential issue for nearby SMD components)

- Using the stock black plastic spacers on heatsinks. (I have seen some intense bending of the CPU carrier board due to too much die clearance from heatsink. I have also seen bad spacing where the die actually doesnt make any contact with the heatsink.)

As I was looking at some of these guides after obtaining my heatsinks, I happened to notice something pretty interesting. If I turned the Apple G5 heatsinks 180 degrees so that they were mounted in reverse, the existing screw holes would line up perfectly and gave clearance in the back so the CPU carrier didn't have to be modified at all, no cutting of heatsinks or heat guns needed. The only thing I needed to do was to notch out a small section on each heatsink to clear one screw on each side of the metal bracer that the front cooling assembly mounts to. Once this tiny modification was done, there was nothing else that needed to be altered with the stock parts. I just replaced the plastic spacers with some long threaded screws, used a dremel to cut the heads off, then used nuts to secure the screws and rest the carrier board on top of. This now gave me the ability to also dial in the exact spacing I wanted to achieve, and once everything was exacly how I wanted, I used thread locker to secure the nuts in place so when tightening the 4 springed CPU mounting screws, everything was mounted firmly within safe tolerances.

This mod makes it more accessible for people wanting to forgo their LCS as this brings the skill level required down a few notches. Here are some of the benefits of performing this version of the air conversion mod:

- Only one 6mmx6mm minimum slot needs to be dremel/sanded out of each heatsink, although the size can be wider/deeper with no issues.

- Notched hole in heatsinks key each assembly so the Top and Bottom CPU's will only fit into their respective slots.

- No additional 'destructive' modifications to heatsink fins or CPU assembly needed!

- Heatsink height is fully adjustable to get exact clearance desired. No bending of CPU carrier board or risk of exposed die damage!

With all of that out of the way, I hope someone finds this guide helpful and intuitive, so feedback is appreciated!

#### Prerequisites

You will need the following items in order to perform this mod:
    
    1. 2mm Allen wrench
    2. Pliers or small crescent wrench
    3. Philips head screwdriver
    4. 2x Apple Power Mac G5 CPU Heatsinks (Obtained from a donor G5 or 3rd party; copper heat pipe version recommended)
    5. 8x M3-0.5mm screws at 30mm length or longer; set screw (If screws have heads on them, will need to be cut off)
    6. 24x M3-0.5mm nuts
    7. Rotary tool
    8. Rotary tool aluminum grinding bit
    9. Rotary tool sanding drum bit (optional, but helps clean up grinding)
    10. Rotary tool cutting bit
    11. Small metal sheet scrap (optional, but recommended)
    12. Thermal paste
    13. Thread Locker Blue & Red (Red for securing shaft to heatsink, blue for securing nut to shaft)
    14. Permanant Marker
    15. Millimeter ruler (optional)
  
#### Dissassembly

Refer to the main disassembly guide or service manual on the main page in order to remove the CPU/LCS assembly from the machine. Once this is removed from the system, we can begin removing it from the CPU carrier board.

1. Remove ten black screws (red) and the four CPU spring screws (green) from each CPU, leaving the center copper heatsink screw in place.

2. Rotate each card slowly until they seperate from the LCS assembly. There should be four floating screws in the LCS assembly that can be removed.

ac_fig-a.jpg

#### Clearing the Heatsinks

We need to grind in a minimum of 6mm X 6mm hole/slot from one side of each heatsink so they can clear a screw on the front cooling fan mounting bracket. If this part isn't performed you will be unable to mount the assembly to the logic board.

ac_fig-b.jpg

1. Please take a look at the picture above. Using a permanant marker, draw a 6mm X 6mm circle, which should cut halfway into an old screw thread. Repeat for the back side of the heatsink.

2. Draw a line connecting the top and bottom marks you made. These will be our guides when cutting in from the side.

3. Using a rotary tool and aluminum grinding bit, start pressing it into the side, working it up and down to start taking material away. If you have a cylindrical grinding bit, you can grind flush from the side and get a pretty clean cut.

4. After working back and fourth for a while, you should now have a cutout. You can use this time to clean up any sharp edges with a rotary sanding drum bit.

ac_fig-c.jpg

#### Adding Adjustable Standoffs to Heatsinks

If you purchased set screws/headless screws then you are good to continue. If all you have are standard screws with the correct length and thread spacing, you may use a rotary tool and cutting wheel to remove them now.

1. Place one heatsink on a workspace in front of you, heatpipes down and copper block side up.

2. Take 4 set screws and thread them into the mounting holes on the heatsink. These will thread through two of the four holes on one end of the CPU board, and two holes through the copper CPU plate.

3. Adjust the height of the screws and use your CPU board to make sure it mounts without issue, taking note to leave several extra millimeters to account for tightening nuts.

4. Once the 4x set screws are in place, we need to use 4x nuts to tighten the base of the new posts to the heatsink. Applying pressure to the side of the set screw to avoid movement, start threading on a nut until tightened firmly at the base. Repeat for all 4 posts.

   WARNING: The following steps are the most critical part of the mod, as we will be clearancing the exposed CPU die to our heatsink. As long as you are not rushing and following instructions, there should be no risk of damage.

5. Take 4 more nuts and screw them down a couple of turns, making them as close to the same hight from the base as possible. At this point it may be handy to have a small ruler to help equalize spacing between nuts.

   NOTE: At this stage you can use a sharpie to mark a point on each nut and screw, using them as markers to keep track of height adjustments.

ac_fig-d.jpg

6. Slowly lower the CPU carrier onto each post, so the nuts hold the card in place above the heatsink.

    - If the die touches the heatsink, rotate the nuts up until there is a 0.1mm clearance between CPU die and heatsink.

    - If the die has space between heatsink, rotate nuts down until there is only a 0.1mm spacing between CPU die and heatsink.

    NOTE: It's hard to eyeball the exact height needed, but I found that if I could barely but definitively see light between die and heatsink from all angles then it was good to go; if I couldn't tell if light was between die and heatsink I would adjust up 1/6th of a rotation until I did. (A nut has 6 sides)

ac_fig-e.jpg

ac_fig-f.jpg

7. Once adjustments have been made to the 4 nuts, we need to test one more thing. Attach the CPU board and use the 4 spring loaded screws to tighten the die to the heatsink. Be sure to screw them down in an X pattern, changing screws every few turns until the die is pressed flat against the heatsink.

   NOTE: The four CPU screws should only pull the CPU board down by about 1mm, causing an unnoticable amount of flexing as they make contact. This should give enough contact pressure for good thermal properties, but not enough to strain die.

8. If you are happy with your adjustments an spacing, remove the CPU board from the newly modified assembly and follow thread locking procedures below:

   a. Use Thread Locker Red to secure the nuts at the base of each set screw, as these should become our permanent mounting posts.

   b. Use Thread Locker Blue to secure the nuts the CPU carrier board rests on, as we may want to loosen these to make adjustments in the future.

   NOTE: You may want to skip Step #8b for now until after you have performed a Thermal Calibration, as you may want to make adjustemnts afterwards.

   c. Let the heatsink sit for at least 8 hours to allow Thread Locker substance to cure. I used generic brand and after an hour noticed it still hadn't cured and if installed would slowly leak down the post.

9. While the Thread Locker substance cures on the first one, repeat Steps #2-#8 so that you end up with two modified heatsink assemblies.

10. Once everything is cured and ready to go, place a small rice grain sized bead of thermal paste onto the CPU die and lower the CPU board onto the heatsink assembly. Use a nut on each of the 4 posts to dighten the CPU board to heatsink, sandwiching the CPU board between two nuts on each standoff. Then tighten the 4 CPU spring screws in an X pattern until it is tightened. Repeat for the last CPU board.

ac_fig-g.jpg

#### Adding Support Brace

This step can be optional, however I recommend it for CPU stability and not putting too much pressure on the CPU 'power" screws. These CPU's are heavy and irreplaceable and it's better to be safe than sorry.

Cut out, 3D print, or find a bracket to match one of the two specifications below of your choice. I recommend 'full' for stability.

Full Bracket:
        
ac_adapt-full.jpg

Split Bracket:
        
ac_adapt.jpg

This will be mounted on the new back side of the heatsink, where the CPU copper fins rise parallel to the larger heatsink. These will be mounted in the existing heatsinks threaded holes and you can use the existing galvenized screws that were used to mount your LCS.

#### Reassembly

Mount the CPU's back into the case one at a time, making sure the heatsink clears the screw we made the cutout for. If all goes well, this should be able to be mounted relitively easy with a total of 6 screws (4 without brace):

- 2x screws at front of heatsink

- 2x screws attached to support brace

- 2x screws attached to CPU rear

As far as my research has gone, all Apple G5 heatsinks should be threaded the same, so if you followed this guide everything should just mount up without issue. There's only two issues you may run across:

1. Heatsink wont sit flush towards front side of assembly.

   NOTE: Make sure you cut out enough material from heatsink to clear the screws that mount the metal fan connector to the case.

3. Original screws wont clear through front of heatsink.

   NOTE: Heatsink may be thicker than the screws provided by the LCS, if this is the case, you may need an aftermarket screw to gain the proper length.

ac_fig-h.jpg

#### Thermal Calibration and Testing

First thing to do when powering on the G5 after reassembly is to load the Apple Service Diagnostics media and run a Thermal Calibration test.

1. Load the ASD media into your G5, and boot from it.

   a. If using CD/DVD, hold [C] at bootup chime.

   b. If using USB, follow the Open Firmware Wiki section and see the chaper "Installing an Operating System"

3. Once ASD has loaded, at the top, click Thermal Calibration.

4. Start the test and wait to see if any errors come back. If errors come up, you will probably need to disassemble the unit and make slight adjustments to the nuts so that the board sits a hair lower. Otherwise your G5 now has been succesfully converted to Air Cooling, and should look prety cool!

5. This is an optional step, but if you have the smaller G5 heatsink decorative covers, you can use your rotary cutting tool to cut the two large rounded tabs that prevent them from being mounted in the proper direction. Then you can have G5 covers on the heatsinks, and then the larger G5 cover to slove over those. This makes the machine at first glance look like an older unit. Pretty cool!

#### Final Thoughts

No information in this guide was taken or based on any other resources other than observations about existing air conversion methods. Everything compiled was from personal experience through trial and error and took a few revisions to nail down. If you found this guide helpful, confusing, incorrect or have any comments, please let me know using the Issue tracker on this repositories main page. Happy modding!
