## Removing and Refilling LCS - By CircuitBored

#### Preface

This was one of the best guides I have found online for rebuilding and refilling the Liquid Cooling Systems (LCS) on the G5, as it can be used to repair and flush the old system, or adding a modern aftermarket pump to keep the rest of the LCS intact. Once I apply this mod to my LCS, I may update the pictures on this guide to a higher quality. That being said I have modified some of the formatting to help things stick out a little more, but this is pretty much all the original authors works. Sources at bottom of the page.

#### Introduction

Hi all, this is a guide to my personal modifications to the Apple PowerMac G5 Quad rev.2 "dual-pump Delphi", pictured above. I will do my best to be thorough in my descriptions. Sadly I do not have pictures of my process in this version of the guide but I will be repeating this mod on another machine at some point in the next year or so in order to document the process properly and make a better-illustrated guide. 

In short, my mod involves removing the original DDC pump tops and replacing them with third-party blocks with multiple ports. This facilitates far easier draining and refilling of the system and should ostensibly improve the longevity of these machines by reducing the risk of pump failure. The chosen pump tops are a near-perfect fit for the G5's case, but require the removal of the G5 faceplate. You can still fit the acrylic air baffle in the machine but it sits under pressure, which I'm not a huge fan of. 

The Mac pictured was one of the very last Quads built - the 531st unit built in week 50 of 2005. As a result it was unlikely that this Liquid Cooling System (LCS going forward) would ever leak, instead it was the coolant inside the system that was a concern. My procedure involves draining all the GM Dexcool and flushing the LCS with distilled water before refilling it with conventional PC coolant.

This guide is written under the assumption that your Quad is currently working as it should. This is a maintenance mod, not a repair. 

#### Inventory

    - Apple PowerMac G5 Quad rev.2 "dual-pump Delphi" 
    - Alphacool Eisdecke DDC V.4 Acrylic Top ( x 2 ) 
    - 40mm M4 bolts ( x 8 )
    - 3/8" Inner-Diameter 1/2" Outer-Diameter acrylic tubing (buy a metre or more to facilitate fiddling and potential errors) 
    - 10-16mm adjustable hose clips ( x 8 ) 
    - XSPC G1/4 hose tail barb 3/8" ( x 4 )
    - Bitspower manual air outlet ( x 2 ) 
    - 1 litre XSPC EC6 coolant (I chose red to make any leaks extra easy to see, beside the fact that it looks brilliant)
    - 10 litres distilled water
    - Isopropyl alcohol 
    - Your preferred thermal compound (I used Noctua NTH4 because it's what I had to hand) 
    - A guitar pick 
    - Apple Service Diagnostics 2.6.3 boot CD
    - Patience

IMG_2648.jpeg

#### Tools

    - A multi-bit screwdriver with a very long spindle (my solution pictured above)
    - 3mm flathead hex bit
    - 4mm ballhead hex bit (you can use a flathead but be careful)
    - T10 hex bit or equivalent size Allen-key (one is included with the Eisdecke)
    - EKWB hose cutting tool, any with a sharp blade will do
    - A clean siphon pump with hoses 
    - Two clean syringe bottles (I prefer the n-neck style)
    - Lots of tins/boxes/baggies to keep your screws and parts separate in
    - Rubber gloves
    - A large glass jar
    - A funnel
    - Heavy duty scissors 
    - Pliers/tin snips
    - Two large anti-static bags 
    - A kitchen roll 

#### Disassembly

Please follow the official Apple Service Source guide to removing the CPU assembly. Pay attention to how things come apart so you can better understand how to put them back together later. Don't be afraid to take notes and photos.

    1. To free the CPU cards you must remove ten black positioning bolts and four sprung retaining bolts from each half of the LCS assembly. 

    2. Do not remove the centremost black bolt on the copper heat spreader unless you also wish to remove the heatsink from the card. Mishandling during this process can prove fatal to your machine - take care. Take note of which side of the assembly each card comes from. I put a small dot of sharpie on the left card to distinguish it.

Screenshot 2020-11-14 at 13.18.37.png

    NOTE: Be sure to put these screws in a safe place.

    3. With the screws removed, carefully twist the first card a fews degrees one way then the other before tilting it off the LCS assembly. If you're keeping the small heatsink attached it's a little more fiddle but it's very doable. Be sure to remove the two floating bolts in the LCS assembly and put them in a safe place. 

    4. Repeat this procedure for the second card.

    5. Put each card in its own anti-static bag and then find a safe place for them. Avoid handling the card by the heatsink during these steps.

    6. It is likely that you will find the remains of two O-rings during these steps. You can ignore and discard them; they are superfluous to the design.

#### Draining 

During the following steps it is important to remember that you are dealing with a toxic fluid which should not be flushed down the drain. Wash any contaminated skin immediately and seek medical help if you experience any adverse reaction to it. Work in a well ventilated area with access to a wash basin nearby. 

For your information: the cooling system in dual-pump G5s is actually dual-loop too. You are essentially working with two small cooling systems built around one radiator during this section.

With the LCS out of the machine and the processor cards removed we must now focus on draining the coolant. For these steps it is best to accept that you are going to make a bit of a mess of things and work with that fact. Don't be careless but don't panic if you get a bit fluid here or there. Dab up any spills with tissue paper and rinse with distilled water. 

    1. Set up a funnel in the top of your glass jar. (I recommend getting a second pair of hands to help hold things steady during this bit)

    2. Don your rubber gloves for this bit. 

    3. With the LCS module sat flat on your worktop, cut the hose at the output port of one pump. The port you should cut by is marked with an arrow on the pump top. Remember that there is a barb underneath which you need to avoid damaging.  The freed hose should afford enough movement for you to angle it away from the assembly. If your hoses are too stiff to manipulate you should remove the hose entirely and attach some new tubing to make draining less messy. 

    4. Using this hose to aim the flow of fluid, tilt the assembly so that liquid starts to pour out of the loop.

    5. Place a gloved thumb over the other freed port to avoid draining fluid from that side. 

    6. Drain the fluid into your glass jar and dispose of it responsibly at your local refuse authority. It is likely that you will see pink crystals in the liquid coming out of the loop, this is normal and part of why this mod is important to do. 

    7. You will have to rotate the assembly around every axis to get all the fluid out - it is not easy or dignified. Expect roughly 200ml to come out per loop. 

    NOTE: This is the part of the process where you question Apple and all of their design decisions ever and wonder why you're even bothering to do this. 

    8. Repeat these steps for the other coolant loop. 

    9. Once you have drained all the coolant from the system, remove the remaining hoses.

    10. Remove the crimps from the hose clips. You can either pry them apart with a flathead screwdriver or simply cut them off with tin snips or large pliers. 

    11. Your LCS should now be empty and have no hoses on it.

#### Flushing the Radiator

Remember that radiators are fragile. A single thumb out of place can ruin a good radiator. I won't pretend like I didn't smudge mine once or twice while I experimented with this mod. I paid for my carelessness by spending hours realigning the fins - don't be a mug. Hold it by its edges and remind yourself what you're dealing with every time you pick it up. 

    1. To flush the radiator, attach the output of your siphon pump to the first radiator port and put the input side into your bottle of distilled water. 

    2. Attach another piece of hose to the next port on the radiator and aim it into a clear drainage container.

    3. Move the bottle of distilled water higher up than the radiator and use the siphon pump to get water flowing through the radiator. Pay attention to the colour of the water as it flows out of the radiator and watch for particulate coming out with the water. Use your best judgement to determine when it is running clean and stop when it is done. 

    NOTE: You may need a lot of water. My system was not clogged so I used only 8L but recommend acquiring 10L.

    WARNING: You should reverse the flow of the water at least once.

    4. Once you have flushed that loop of the radiator move on to the next two ports and repeat the process. 

    5. You may find it easier to remove the pumps from the assembly before this step. Empty the radiator again before moving on.

#### Disassembling the Pumps and Applying the "Mod"

    1. To remove the DDC pumps from the LCS you must first remove the bracket they are attached to. Remove the two screws on the pull-handle between the pumps and the four screws attached to the base of the assembly to free the bracket and then remove the screws on the underside of the pumps. Depending on the week your G5 was built there will be four or six screws holding the pumps on. 

    2. Unscrew the four bolts in the underside of each pump and remove the top section with the hose barbs. Remove the large O-ring and put it to one side. During this step any congestion in the pump will be revealed. Work carefully to remove any unwanted bits and bobs in the mechanism. 

    WARNING: It is very important that you do not twist or tilt the rotor of the pump at all. Do not be tempted to wiggle it around to get bits out. You risk ruining a component that will cost you a lot of time and money to replace.

    WARNING: Be warned that the lower half of this assembly is spring-loaded and will explode once the glue loses its hold. It's best to disassemble it entirely in a controlled fashion before it decides to surprise you while you work. 

    WARNING: All this glue is overkill prevention for a leak that never happens so don't worry about removing it entirely. Use a flathead screwdriver or similar to chip it away but avoid chipping the plastic pump body.

    3. Use this opportunity to inspect the removed O-ring and the exposed rubber diaphragms for any wear or discolouration. It is unlikely that there is any substantial damage if you are working on an LCS that was still functional.

    NOTE: Replacement DDC O-rings can be easily sourced from most PC cooling specialists. 

    4. Now you should unpack your replacement pump top.
    
    NOTE: I used an Alphacool Eisdecke V.4 because I figured out it is a perfect fit, with the caveats mentioned above. Your pump top needs to be exactly the same height as the Alphacool model or smaller. There is no wiggle room at all here. The replacement tops are as big as they could possibly be. 

    NOTE: Be wary of dust and contaminants when handling the new blocks. A clean cooling system is a more efficient cooling system. 

    5. Remove the LED strips from the DDC top if you purchased the exact same model as me, working gently to avoid cracking the acrylic. 

    6. Fit the DDC O-ring back on to the block and attach the new top with four 40mm M4 bolts. Be sure to orient the top correctly so that the in/out ports face the radiator. 

    WARNING: Take care when applying pressure to the new top and work in a circle when fitting the bolts. Do not overtighten. You will be able to see when pressure is applied through the clear acrylic. 

    7. Take this time to curse whoever designed this computer before repeating all the previous steps for the second pump. 

You should now have two pumps with crystal-clear tops that look incredible. You'll feel a little pride in yourself and you will be tantalised by the gratification of a completed mod. 

If you had an especially clogged system you should flush the pumps before moving on. Use the power pinout from 360alaska's guide to power the pumps externally and rinse distilled water through them until you are satisfied that they are clean.
    LINK: https://68kmla.org/bb/topic/26539-how-to-repair-a-g5-quad-dual-pump-lcs/ (broken...)

#### Rebuilding the LCS 

    1. Screw your chosen hose barbs onto the IN and OUT ports on the side of the new pump tops. 

    2. Leave the G1/4 ports on the top side of each pump open. This is where you will be filling the system from. 

    3. Use the plugs included with your DDC tops to fill the G1/4 ports you will not be needing. Fit the manual air outlets to the sides of the pumps as pictured. (the air outlets are mostly used as an easy-open port solution in this situ)

    NOTE: Use the winged plastic tool that was included and avoid over-tightening. 

    4. Reattach the pumps to the bracket and offer up the bracket to the LCS' frame. It won't immediately look like the ports line up but it will work. 

    5. Use the offered up bracket to measure how long your new pieces of hose will have to be and cut them to size. 

    6. Fit the hoses and their clips to the barbs on the pumps. Don't forget to put enough clips on for both ends of each hose. 

    7. Slowly offer up the hosed-up pumps to the radiator, sliding each end onto the corresponding barb. Take your time. Double check you have fitted enough hose clips as it is very hard to work backwards from here.

    8. You will have to pry the metal "Z-tube" in the LCS in order to align it properly with the IN port on the pump. Bend it gently a few millimetres at a time in order to make it line up, being careful to observe for pinch points and obstructions. Be very gentle with this part. It has a lot more flexibility left and right than it does back and forth. Cushion it and apply adverse pressure when pushing the hoses on. 

    9. Reattach the screws for the bracket once you are satisfied that your hoses are fitted properly.

    10. Tighten the hose clamps. Be careful not to unscrew the barbs from the pump top while you tighten the clamps onto them. 

#### Refilling the LCS

IMG_2617.jpeg

Finally, it gets good again. You'll only get red stuff everywhere if you're fiddling intensely like I was.

    1. Put the LCS radiator-side down on an old tea-towel or a square of kitchen roll, being careful not to put anything underneath it that might damage the fins. 

    2. Fill a syringe bottle with the coolant you have chosen to use.

    3. Using the OUT port left open earlier, slowly squirt fluid into the system so that it flows down the longer hose and into the radiator. Try to avoid getting fluid in the pumps yet.

    NOTE: You should see the hose start to fill up after not putting much fluid in, this is expected.

    4. Once the hose is full, slowly tilt the whole LCS assembly back and to the right to allow the air to escape through the other side of the system.

    NOTE: You should see the fluid drain from the hose into the radiator once the air has moved.

    5. Repeat the previous four steps until you see fluid start to come out of the other side of the radiator. 

    6. Once the radiator is adequately drained of air and the hoses are brimmed with fluid, flip the LCS back "upright" (as pictured above).

    7. Use your syringe bottle to replace as much air with fluid as you can before putting plugs in the open G1/4 ports.  

    8. Put your LCS on its side with the radiator to the left, as it sits when it's in the machine. Observe any air bubbles and rotate the LCS to manoeuvre them through the system and into the pump. 

Finally, this modular liquid cooling system can play into its strengths for a moment. 

    9. Once you have amassed as much air in the pump as you can remove the air outlet you fitted earlier and add more fluid to expel the air.

    NOTE: If you take your time and remind yourself how fluids work before you make your moves this is a fairly painless process. Safe to say, I made a few mistakes figuring all this out. 

You won't get all the air out first time, don't worry. I'll describe how to bleed the system once it's "settled" further down. 

    10. Once you are satisfied that you have expelled most of the air from your loop, repeat the whole process for the second pump. 

You should now have a completely retrofitted cooling system full of new fluid. 

#### Reassembly and Calibration

Now you have to put the whole thing back together. 

    1. With the LCS upside down, carefully reattach the processor cards. You have to apply thermal compound to the card with it die-side-up and then put it onto the LCS assembly upside down. 

    2. Put each card back on the side you removed it from and be careful while handling. 

    NOTE: Remember that video of how little thermal compound you actually need. 

    3. Be sure to refit each piece of the four sprung retention screws in the right order.

    4. Don't forget to put the four floating bolts we put aside earlier back in their proper place. Two per processor.  DO this before you put the card on.

    5. Replace the black bolts, making sure the cards are aligned properly with the LCS frame and each other. 

    6. With the LCS fully reassembled, put it back into your PowerMac. 

You're allowed to take a break now. Take a moment to appreciate how cool your creation looks. 

IMG_2647.jpeg

    7. Put a guitar pick in the rightmost hole for the acrylic air baffle. This tricks the system into thinking the baffle is still fitted.

    NOTE: If you're feeling nervous, put some tissue paper beneath the pumps for the next step. If you've done a good job there is no reason to expect any leaks.

    8. Go right ahead and plug the power in. Power up the Mac and listen to the sweet sound of a cold G5 Quad getting into gear.

    9. Get the Apple Service Diagnostics CD into the drive ASAP and boot the firmware version of the tool. 

    10. Run Thermal Calibration and wait for both processors to pass the tests.

    11. Once you have verified the results you can reboot the machine and continue to enjoy your Quad as normal. 

#### Results

I have found temps to have dropped around 10C in all scenarios with an absolute highest observed temp of 70C when a heavy load first spikes. The pumps run much quieter than they did before too. In fact, in their newfound quietness they have revealed to me just how annoyingly loud some of the fans in my Quad are. Upgrading the fans is likely going to be part two of this G5 modification journey. It's really weird to see a Quad idling below 40C. 

I have tried my very best to be thorough in writing up this process. It took me a whole lot longer than I expected it to but I think it will have been worth it. 

Please feel free to ask away with any question you may have. Naturally please also let me know if there are any holes in this guide!

I will try to produce an illustrated version of this guide in the next 6-12 month period, depending on how easily I track down more G5 quads. 

Thanks for reading, have a great day!

#### Acknowledgements

"Special thanks to 360alaska and the reddit water cooling community for the inspiration!" - CircuitBored

SOURCE: https://68kmla.org/bb/index.php?threads/powermac-g5-quad-the-new-blood-mod-a-guide-to-flushing-modifying-and-refilling-the-dual-pump-cooling-system.37474/