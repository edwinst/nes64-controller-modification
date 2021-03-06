# Modifying a NES64 controller with a 3-way switch

by Edwin Steiner

https://youtube.com/c/EdwinSteiner

## What this is about

**TL;DR:** Modify the NES64 controller to have 3 options ("UP", "A", "UP or A") for the "up" direction.

The [NES64](https://nes64.pryds.eu/) PCB is a great project
for modifying Nintendo Entertainment System (NES) controllers for use
with retro computers like the Commodore 64.

**DISCLAIMER:** I used reproduced NES controllers. No original NES controllers
were harmed in the course of this project!

I find that these controllers make games, in particularly platformers, much
more enjoyable to play. The NES64 in the version I bought has a little 2-way
switch (located in its "shoulder") that defines whether the "up"-signal to the
computer is generated by pressing the "UP" direction on the D-pad or by
pressing the "A" button. The latter setting is great for games like "The Great
Giana Sisters" and other platformers as it gives you a much more natural way to
jump in the game by pressing the "A" button.

There are games like "Sam's Journey", however, where I like to use "A" to jump
but still use "UP" on the map and in menus. I therefore came up with a modification
to the NES64 that replaces the 2-way switch by a 3-way switch, extending the
options for the "up"-direction to:

1. Only "UP" works,
1. both "UP" and "A" work, and
1. only "A" works.

The controller on the left in the image has been modified. Notice the larger switch at the shoulder of the controller:
![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-new-switch.png?raw=true)

## What you need

* the NES64 (PCB + the controller housing, pads, and cable)
* a 3-way slide switch with 2 poles with ON-ON-ON contact configurations (see below for details and alternatives)
* a few inches of low-voltage wire
* some insulating tape or sheet material
* tool for cutting PCB and enclosure (Dremel with cutoff disk works well)
* small tool for polishing (e.g. Dremel) or a piece of fine sand paper
* soldering iron + accessories
* a hot glue gun or some epoxy
* screwdriver to open the NES64
* ruler and marking pen

[The switch I used](https://www.conrad.at/de/p/tru-components-schiebeschalter-250-v-ac-1-5-a-2-x-ein-ein-ein-1-st-1564872.html)
is a "TRU COMPONENTS" slide switch 6259488 (EAN: 4016139210469):
[datasheet](https://github.com/edwinst/nes64-controller-modification/blob/main/switch_datasheet.pdf).
![](https://github.com/edwinst/nes64-controller-modification/blob/main/switch.png?raw=true)

This switch was a perfect fit because it has 2 poles, each one with ON-ON-ON contact type, and the two rows of its pins,
which are designed for vertical print mounting, have the right distance to straddle the edge of the PCB quite exactly.

![](https://github.com/edwinst/nes64-controller-modification/blob/main/switch_connections.png?raw=true)

If you want or have to use a different switch with only one pole (ON-ON-ON type), there is a second circuit variant
below that uses two additional diodes. (You can use any run-of-the-mill diode, e.g. the 1N4148.)

## How to do it

1. Open the NES64 and take the PCB out.

   Here is how the PCB looks before the modification. Note the location of the trace going from the switch to the "A" button:
   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-before-cable-side.png?raw=true)

   The other side looks like this. Note the location of the trace going from the switch to the "UP" button:
   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-before-button-side.png?raw=true)

1. Mark the cutout for the new switch on the PCB.

   Mark the cutout you need to make for the switch on the PCB. The image below shows the dimensions
   I used for my type of switch. The tighter the switch fits the cutout, the easier it will be
   to mechanically secure the switch in place later.

   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-cutout-cable-side.png?raw=true)

1. Cut the PCB, then use the polishing tool to expose the traces going to the "A" button and to the "UP" button.

   Note that for my type of switch, I had to cut grooves into the PCB at the edges of the cutout to accomodate
   the mounting tabs of the switch.

   At the two indicated positions, remove the coating that covers the traces on the PCB. The exposed part should be a few millimeters
   of shiny copper. I used a Dremel with a polishing tool for that, which worked well but take care that you work
   in a well ventilated area since the coating creates some nasty fumes. Alternatively, use some very fine sandpaper
   to remove the coating until you see clean copper.

   Note: It is better to expose the "A"-trace somewhat farther from the PCB edge than I did in the images. That should
   make it easier to position the switch later.

   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-cutout-after-cable-side.png?raw=true)
   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-cutout-after-button-side.png?raw=true)

1. Tin the exposed traces with the soldering iron.

   Make sure the copper is clean before tinning. (Maybe clean it with isopropyl alcohol.)
   Use flux if the tin does not bond to the copper easily.

1. Solder the connections for the 3-way switch according to the wiring diagram (see below).

   Depending on which type of switch you got, there are two variants of wiring. The first, simpler one
   (left schematic diagram) needs a 2x ON-ON-ON switch and requires only direct electrical connections.
   For the second one (right schematic diagram) a 1x ON-ON-ON switch suffices and the wiring uses
   two additional diodes to complete the circuit.

   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-schematics.png?raw=true)

   The new part of the wiring (highlighted in the diagrams) is connected to the PCB in three places:
   1. At the pad where the "1 UP" wire of the cable connects. There is a solder via connection at this
      pad where you can easily connect wires from both sides of the PCB.
   1. At the exposed part of the trace going to the "UP"-button.
   1. At the exposed part of the trace going to the "A"-button.
      
   Wiring with 2x ON-ON-ON switch:
   (Note that there is a connection to the "1 UP" pin of the cable on both sides of the PCB.)

   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-installed-cable-side.png?raw=true)
   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-installed-button-side.png?raw=true)

   Wiring with 1x ON-ON-ON switch and two diodes:
   (Note: The switch in the image is actually a 2x ON-ON-ON switch but I used only one
   pole of the switch in order to try out this circuit variant.)

   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-diode-version-cable-side.png?raw=true)
   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-diode-version-button-side.png?raw=true)

1. Apply isolation as needed.

   You need to avoid any unwanted electrical contact of the pins or other metal parts of the switch with
   the exposed edges of the PCB around the cutout. I simply applied some tape whereever the cutout went
   across copper traces in the PCB. If you use tape, only apply it after you have completed all the soldering,
   otherwise the heat will destroy the tape and defeat its purpose.

1. Make the cutout for the 3-way switch in the enclosure.

   Depending on whether your controller already had a cutout for the original 2-way switch,
   you need to enlarge or create the cutout in the enclosure. The cutout should be
   just large enough so you can slide the switch to its outermost position in either direction.

   Note: If you get the enclosure without a pre-existing cutout, you can create a better fitting
   cutout for the new switch than I did.

   ![](https://github.com/edwinst/nes64-controller-modification/blob/main/nes64-enclosure-cuout.png?raw=true)

1. Test assembly.

   Before you glue the switch in place, I recommend that you assemble the controller provisionally in order
   to test it. To be safe, test the intended connections using a multimeter first and only if they are
   fine, connect the controller to your computer to test the functions of the buttons for all 3 switch
   positions.

1. Apply hot glue or epoxy to mechanically stabilize the switch.

   If everything tested out fine, open the controller again and use hot glue or epoxy to secure the switch
   in place from both sides of the PCB. Take care that the glue does not block any of the screws or plastic parts
   of the enclosure upon assembly and also that the glue does not make its way into the contacts of the switch.

   When applying glue to the "button side" of the PCB, cover the button contact pads with some cardboard
   to avoid dropping any glue on the contacts!

1. Final assembly.

   When you do the final assembly, check that the cable is properly secured in its strain relief.
   
1. Enjoy your new, improved controller!

