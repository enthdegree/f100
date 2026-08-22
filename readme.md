# Nikon F100 Notes

I repaired a Nikon F100 film camera sold for-parts.
For my camera, an internal cleaning was all that was actually needed to get it working.
Unfortunately, for lack of documentation and knowledge I created a lot more work for myself than was necessary.
Here is what I wish I knew before starting.

## Preliminaries 

### Documentation

The Nikon F100 repair manual and parts list are necessary but not sufficient. They are terse, vague and narrow in scope. Copies circulating online are low-quality scans. 
Afotandovy has some useful disassembly photographs and comments: https://afotandovoy.blogspot.com/2013/02/reparacion-nikon-f100.html 

If I could go back in time I would urge several points to past-me:

- Read Richard Haw’s brief general camera repair fundamentals articles https://richardhaw.com/lens-camera-repair-fundamentals/  Forcing things when I should have taken a break led to unnecessary damage that was difficult to repair
- Almost the instant you take off each tiny screw you will drop it on the floor and forget the hole it came out of.  Come up with some system to defend against these things.  Many of the screws look near-identical and almost none of them are interchangeable.  Pill tray systems will get knocked over and you will mix up the compartments.  I should have disassembled everything over a magnetic screw mat, and sorted screws according to their names from the repair manual.  
- If I had known how annoying everything was to clean before reassembly I would have worn disposable gloves for everything. 

### Common tools

- JIS 0 screwdrivers. iFixIt Minnow has JIS-compatible ones.
- Fine tweezers
- Rocket blower
- Cleaning materials: 
    - Coffee filters
    - Microfibre cloth
    - Toothpicks and Q-tips 
- Cleaning chemicals:
    - Distilled water
    - 99% Isopropyl alcohol (be really limited with using this on the internal "PC-GF20.AL" plastic body as it makes it brittle)
    - white vinegar (not for use on the plastic but rather for cleaning rust for metal parts that were removed from it)
    - acetone (turns the plastic into mush instantly on contact. essentially destructive. extremely limited applicability if any. only thing I’d use it for is as a last resort for extremely tight screws, applied with a toothpick)
- Strong double-sided tape. I used Scotch 9495LE.
- Soldering iron (to get some delicate ground wires off without damage)
- Box of 100 nitride gloves 

A lot of for-parts F100s on sale already have some essential components gutted. 
This makes the economics of repairing them pretty bad. 
Here are common missing parts I noticed, together with replacement status:

- Eyepiece
    - The standard is Nikon Viewfinder Eyepiece 2927. Ebay price is $25.
    - It is a very simple part. Metal aftermarket versions are currently manufactured and cost $12 shipped. 
    - The ring for the F100 seems to have dimensions close or identical to the Nikon DK-17 (for which free replacement models are published), but I haven’t yet found empirical evidence they are interchangeable. You’d still need to find a glass window for those too.
- Battery cartridge
    - The standard is Nikon MS-12 (4xAA batteries). Ebay price exceeds $100 which is obscene. 
    - Bogdanbogvzyan sells compatible design files for $10 at Cults3D: https://cults3d.com/en/3d-model/gadget/nikon-ms-12-aa-battery-holder-for-f100 . 3D prints of that can be found for $30 shipped. 
    - I attempted to print that design with PLA (Thank you HackManhattan) but it failed during assembly due to layer separation and the screws sheared out of their holes. 
      If I tried printing it again, against the designer's recommendation I’d print it on its side instead of vetically. 
- Focus screen
    - The standard is Nikon Type B Focusing Screen 2599. Ebay price is $28. 
    - There are actually aftermarket screens (with split prism!) with correct dimensions on aliexpress: "Dual 45 degree Split Image Focus Focusing Screen for Nikon D1 D1H D1X F100 PR129"
    - Richard Haw has described cutting down and shimming an existing focus screen of a different model. I don’t know why ground glass of the right thickness wouldn’t work OK. Dimensions in Figure 1.
- Film door
    - The assembly is 1B999-938 in the parts list. Replacements sell for $100 which is obscene. 
    - The latch hooks frequently fail and a simple repair jig + metal hook kit can be bought for $20 which seems reasonable.
    - The whole film door is actually a simple passive electromechanical part that would be feasible (if a bit complex) to fully remanufacture, if/when it becomes economical to do so. I don’t have the expertise to do this, though.


<figure>
<img src="./images/f100_focus_screen_dims.jpg" alt=“f100_focus_screen_dims.jpg" width="50%"> 
<figcaption>
<i>Figure 1: F100 focus screen dimensions. Numbers are mm.</i>
</figcaption> 
</figure>


## Symptoms out of the box

My broken F100 came without the eyepiece and its battery cartridge was shattered. 
The seller said this camera died from battery corrosion.
By the time they cleaned the battery compartment the corrosion had already corrupted the inside of the camera.
Its behavior was erratic:

- 1. Typically the camera would appear totally dead. Sometimes putting batteries in, the LCD would show garbage, sometimes fading out.  
- 2. Rarely the camera would turn on and show the low battery indicator. No function or button worked in this state. If you pushed any button  here the indicator would start blinking.
- 3. Very rarely inserting the batteries would power up the camera into an ostensibly-working state for a minute or so. Here the shutter would behave like it was being held down forever after its first press, until a power-cycle. Shutter releases 1/2000 and faster would usually misfire and show Err.

The batteries would sometimes heat up quickly. Scary.
As soon as I noticed this I stopped testing. 

## Disassembly and cleanup

Corrosion was visible at the seams around the battery compartment/grip.
The top cover, baseplate and grip had to be removed to expose the contaminants that had leaked into the body.
I followed the “Disassembly 1. Exterior" section of the F100 repair manual. 
Also helpful are the afotandovy photographs up to and not including removal of the LCD screen’s screws. 

Fine points of disassembly: 

- There is an FPC connecting the top cover to the camera body under the side opposite the LCD. It is easy to rip if you don’t know it’s there. To remove the top cover safely I lifted it off lift it off as pictured in Figure 2. You have to lift the cover off with one hand and unscrew the two retainer screws with the other. 
- The metal grip/battery compartment is electrically grounded with a copper clip retained by one of the screws. A blue wire is soldered onto that clip, and the wire’s opposite end leads to some FPC deep inside the body. I desoldered the wire from the clip to avoid the wire snapping during grip removal. The wire and clip is visible in Figure 3, circled in white. 



<figure>
<img src="./images/f100_top_cover_removal.jpg" alt=“f100_top_cover_removal.jpg" width="95%"> 
<figcaption>
<i>Figure 2: Top Cover removal, FPC in red. Contrary to the illustration the film door/rear cover is probably off the camera at this point. </i>
</figcaption> 
</figure>




<figure>
<img src="./images/f100_grip_ground_clip.jpg" alt=“f100_grip_ground_clip.jpg" width="50%"> 
<figcaption>
<i>Figure 3: F100 grip ground clip, soldered onto a blue wire. I desoldered this during disassembly for cleaning and safe handling.</i>
</figcaption> 
</figure>


Corrosion cleanup for all the electronics followed the same pattern: 

- Flaked off what corrosion I could see with a toothpick
- Wiped with water to dissolve the rest of the corrosion
- Final wipe with isopropyl alcohol
- all the while blasting air at it with a rocket blower

Much of the contamination was almost-completely invisible:

- There was contamination around the power FPC ribbon. Something around here was the plausibly cause for symptom 1. See Figure 4, red arrow. 
- A window at the ceiling of the battery compartment exposes a spring-loaded contact. Normally a peg on the MS-12 battery cartridge pushes the switch open, indicating to the body that 4xAA power is expected. A plausible explanation for symptom 2 is that corrosion kept this switch shorted, thus the body expected a higher voltage. See Figure 4, white arrow. 
- Buttons on the top cover signal depression to the body by shorting a radial pad on the FPC to a ground rail. Symptom 3 was due to contaminants shorting the shutter switch closed around some contact arms. See Figures 5a and 5b.

Separately, removing the metal grip revealed rust-red corrosion that I cleaned off with white vinegar, rinsing thoroughly with water afterwards.



<figure>
<img src="./images/f100_corroded_power_fpc.jpg" alt=“f100_corroded_power_fpc.jpg" width="50%"> 
<figcaption>
<i>Figure 4:  Power FPC with corrosion. The white arrow points to the MS-12 indicator spring-loaded contact. The red arrow points to an FPC area. Besides the obvious green corrosion around their edges both seemed otherwise clean. They weren't. Symptoms did not resolve until thorough cleaning. Both sides of the spring-loaded contact and the surrounding FPC extend fairly deep into the camera’s interior. Those areas had to be reached carefully with a toothpick saturated with distilled water, then isopropyl alcohol the same way. It was sufficient to reach them this way rather than through more disassembly.</i> 
</figcaption> 
</figure>




<figure>
<img src="./images/f100_shutter_prongs.jpg" alt=“f100_shutter_prongs.jpg" width="50%"> 
<figcaption>
<i>Figure 5a: F100 shutter spring contacts inside the top cover, above the front dial. There are 3 prongs in a stack around the white arrow. Flecks of some contaminant visible on the base prong. You need a toothpick saturated in cleaning material to get close to the base of each prong. I could only detect the cleaning was effective by measuring the shutter-to-ground ‘open’ resistance slowly climb on the multimeter up from 7 kOhm pre-cleaning (see Figure 5b). </i> 
</figcaption> 
</figure>



<figure>
<img src="./images/f100_top_cover_radial_pads.jpg" alt=“f100_top_cover_radial_pads.jpg" width="50%"> 
<figcaption>
<i>Figure 5b: F100 top cover FPC radial pads used for communicating button state to the body. Button depression is supposed to short each of those pads to a ground rail. Ground is electrically connected to some other exposed metal which is a more convenient measurement point. </i> 
</figcaption> 
</figure>


..and then everything is supposed to go back on the way it came off. 
The grip rubber and diopter cover need new double-sided tape.
It could’ve been that simple… 

## Addressing damage caused during disassembly (The Odyssey)

### Stripped screw

During disassembly I stripped the head of a stuck screw. 
Richard Haw, linked above, has advice on this. 
I managed to remove it with a dot of white vinegar and a lot of friction. 


Of course you don’t know what screw you need until it is lost or destroyed.
If you are lucky the screw is one that came in a pair so a twin is available for measurements.
One way to measure a machine screws is to paint it in ink with a ballpoint pen and take a print of it on ruled paper (rules are often 6.35mm apart). A picture of the print provides thread pitch, length and diameter via the ruler tool in Gimp or Inkscape. 
See Figure 6.

Sometimes you can cross-reference the F100 repair manual to a parts list to find the screw name. 
For example CKT #778 appears on page D-1 of the repair manual, and in the parts list it has Part No. B1-14030FD indicating it is some 3.0mm-length M1.4 screw. 
Not all the screws are named like this.


<figure>
<img src="./images/machine_screw_print.jpg" alt="machine_screw_print.jpg" width="50%"> 
<figcaption>
<i>Figure 6: A print of a machine screw. 7 threads span 96 px and 6.35mm spans 173 px indicating a thread pitch of around 0.5 mm.</i>
</figcaption> 
</figure>



### Reattaching the focus selector D-pad to the film door

The film door’s focus-selector D-pad popped off during cleaning. 
That button is mechanically attached to the film door by a collar that’s pressed on from the inside of the door. 
It’s impossible to reattach without disassembling the door. 
Avoid this situation. It isn’t fun… 

This is an obscure repair, I can’t find anyone doing it. 
Actually there is a nice explosion diagram of it on Page D-26 of the F100 assembly manual (“rear cover"). 
The delicate part is lifting the internal black panel off the rear cover. 
Figure 7 shows the backside of what you are lifting off.

- Like the top cover FPC, the area of the FPC near the focus area selector dial area is screwed down and you will rip it if you don’t know it’s there. As you lift it off you have to unscrew a screw normally holding the FPC at the red arrow in Figure 7.
- The FPC on the panel is tacked to the cover’s body with two pieces of double-sided tape (white arrows in Figure 7). The tape can be loosened with a toothpick saturated with isopropyl alcohol. 

For reassembly the hard part is getting the dial assembly back in place. 
You need to tape the dial into place from the outside of the rear cover during their reassembly so that it stays suspended, so that you can screw the rotating contact pin assembly + FPC back down into it as you replace the internal panel assembly. 


<figure>
<img src="./images/f100_rear_cover_internal_panel.jpg" alt="f100_rear_cover_internal_panel.jpg" width="50%"> 
<figcaption>
<i>Figure 7: F100 rear cover internal panel. Red arrow at an FPC that sits under the focus area selector dial. The FPC is normally screwed onto the body of the back. Tape on the FPC (white arrows) also tacks the FPC to the body of the rear cover. </i>
</figcaption> 
</figure>


### Screw boss replacement with a heat insert

Negligently, I failed to notice an obvious screw on the battery compartment while removing the baseplate and I ripped it off, taking most of its boss along with it. 
Bad!
I should not have used so much force, should have paid closer attention to the repair manual’s exploded diagrams and counted screws more.

The camera would likely have been OK without this one screw but I wanted to set things “right."
My approach was to replace it with a similarly shaped M1.6 screw and a brass heat insert encased in epoxy.

I carved away a segment of the shattered boss so the brass heat-insert could be brought nearly into position in free space:

<figure>
<img src="./images/f100_shattered_boss.jpg" alt="f100_shattered_boss.jpg" width="50%"> 
<figcaption>
<i>Figure 8: F100 with a shattered screw boss :(. Some plastic has been gauged out of the shattered area to make room for a heat insert… </i>
</figcaption> 
</figure>

Then I used the baseplate as a jig. 
With the baseplate+screw+insert set on the body I held a soldering iron on the screwhead at 380 C, which eventually softened the plastic enough for the baseplate to set the insert into position.

<figure>
<img src="./images/f100_baseplate_with_insert.jpg" alt="f100_baseplate_with_insert.jpg" width="50%"> 
<figcaption>
<i>Figure 9: F100 baseplate with the insert on. </i>
</figcaption> 
</figure>


<figure>
<img src="./images/f100_baseplate_set_as_jig.jpg" alt="f100_baseplate_set_as_jig.jpg" width="50%"> 
<figcaption>
<i>Figure 10: Baseplate as shown in Figure 9 set on the body. A hot iron was held onto the screwhead to conduct heat onto the brass insert, to melt the insert onto what remained of the boss.</i>
</figcaption> 
</figure>


<figure>
<img src="./images/f100_insert_embedded_into_boss.jpg" alt="f100_insert_embedded_into_boss.jpg" width="50%"> 
<figcaption>
<i>Figure 11: Partially-set brass insert after melting. </i>
</figcaption> 
</figure>

Finally I used a toothpick to coat the partially-mounted insert and surrounding area with epoxy. 
I quickly reinstalled the baseplate+screw before letting the epoxy set. 

Gorilla Ultimate epoxy is one of the most foul things I have smelled in my life. 
Do this outside!


<figure>
<img src="./images/f100_epoxied_insert.jpg" alt="f100_epoxied_insert.jpg" width="50%"> 
<figcaption>
<i>Figure 10: Finished insert attachment. </i>
</figcaption> 
</figure>


This ordeal took two tries to get right: in the first try I tried to eyeball the insert position without the baseplate as a jig.
Although position seemed OK to the eye, in reality it was poor enough that trying to reassemble it sheared off the head of my screw.

## Obscure true fact

In the early 2000s Leo Bodnar did some fascinating work on the F100’s predecessor, the F90X:
- https://geocities.ws/leobodnar/F90X_rewind.html 
- https://geocities.ws/leobodnar/f90secrets.html 

Pads near the DX reading pins have an undocumented serial line that let you overwrite EEPROM registers. 
Leo succeeded in writing to a register on an F90x that controls how much of the film leader the rewind operation leaves exposed.
Unfortunately the zips on that page are not available anymore. 
They likely would have described the serial interface. 

I speculate the interface may be the same as the one on the 10-pin, which does have known, surviving implementations.
F100 manual’s EEPROM register table suspiciously names a “FILM TONGUE" register at 0x0081 for “Ver 4.XX" and at 0x006E for “Ver 5.XX"… there is also a “CHECK SUM" register which may need handling too.

# Tirade 

On the outset a successful repair seemed too hard and low-likelihood.
Looking back I think it only seemed so because of poor information availability.
Finding obscure technical information is pretty miserable in the age of AI.
Google hasn’t worked right since before covid. 
Its replacement, Claude, always tells me I’m a dangerous incompetent who should give up on everything and call 988. 
Sometimes through its ugly condescension Claude accidentally leaks valuable information and who it learned from.
Sadly I think this will be patched soon. 

Forums, especially Reddit, are virtually exclusively populated by deeply low-rent people.
The Redditor is a uniquely brittle, ignorant, over-socialized, navel-gazing, low-agency creature. 
If you do anything outside its very limited script of interactions (e.g. seek or provide novel information) they will seize up and start shrieking like at the end of Body Snatchers (1978). 
The small, over-moderated ‘specialist sub-Reddits,’ the ones everyone’s always insisting are different, are equally if not more bad.
If you use Reddit that is embarrassing and you are a bad person.

<figure>
<img src="./images/bonzi_buddy.jpg" alt="bonzi_buddy.jpg" width="50%"> 
<figcaption>
<i>A wider communication gamut than Redditors are capable of. </i>
</figcaption> 
</figure>

