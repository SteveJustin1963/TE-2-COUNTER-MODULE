# TE-2-4-Counter-Module

A counter is a very handy piece of equipment. It can be used as test equipment, for display, or for experimentation. Our versatile counter module is especially useful. Many variations and adaptions can be engineered around it, as it is a basic building block. It can be used to count from one cycle per hour to nearly 3MHz. To cater for frequencies higher than 3MHz, additional dividing networks can be included at the front end. This would extend the frequency 100 times or more.  

https://easyeda.com/editor#id=4ca8c114ce5d4840b4bbddc5e2041a07|220caf8c84af4379b00096b862300c44

![](https://github.com/SteveJustin1963/TE-2-4--Counter-Module/blob/master/cm-cct.png)
![](https://github.com/SteveJustin1963/TE-2-4--Counter-Module/blob/master/pic.png)
![](https://github.com/SteveJustin1963/TE-2-4--Counter-Module/blob/master/pinout.png)

Our project will accept 6 different sensors; light, sound, magnetic, unit, oscillator, and infra-red. Actually the counter module is quite an easy project. Most of the complexity is contained within the two chips and only a few outside components such as resistors need be added. These resistors interface (connect between) the counting chip and the display. They provide current limiting for the display segments and driver transistors. The four resistors at the input of the IC provide pull-up and pull-down. This sets the condition HIGH or LOW on the inputs as many have a dual role. At first glance this project may seem expensive compared to a pocket calculator. Some calculators have unit-count facilities incorporated into the plus key and this can be extended externally to an oscillator or reed switch sensor. But a Calculator project doesn't give any constructional experience or enable you to add your own read-out. diagram. Nor does it allow you to add your own read-out. Any of the six sensors can be fed into the 74C926. These will be the basis of the second part of this project. Consider this project as a paying proposition. You have been requested by an engineering firm to design a simple parts counter to tally daily production. Of course it is always possible to bulk-weigh components on a set of ratio-scales, but the management has stipulated an optical counter situated near the operator. You will be required to build a working proto-type for a four week trial-run. How do you think you will fair? The only catch is, you will have to wait for the next issue for the optical sensor. Any manufacturing firm producing a number of similar items such as plastic parts, packaging of small items, adding a label to a bottle or hand preparing or de-burring will find a unit-counting recorder of immense benefit. The main advantage of an electronic counter is the number of sensors it will accept. It's a very simple task to adapt optical, magnetic, or audio sensors to count production parts. And most importantly, it is the simplicity of set-up which will appeal to the operator. 

## PARTS LIST:
* IC1- 74C926
* Display - AND-4145
* Resistors: 1/4 watt
* 7 - 100R
* 7 - 18OR
* 7 - 220R
* 7 - 270R
* 7 - 330R
* 4 - 3k3
* 4 - 1M
* 4 - BC 547
1 - "COUNTER" PC board

## What is multiplexing?
Our four digit "AND" display is multiplexed, but what does it mean? It is a complex scanning process which we will discuss in a very simple way. Looking into the display you will see it is capable of showing four figure "eights" and 7 decimal points. If you count.up all the segments needed to make each eight, you will have ______ (fill it in) plus 7 dots making a total of at least 35 LEDs. To operate this you would need at least 36 leads. But the display has only 24 pins. How does that work? In fact 13 of the pins are connected directly to the dots, leaving only 11 pins for all the segments. Each digit has 7 segments, and you would normally assume you would need 4x7 or at least 28 or 29 pins to select any combination of the 28 segments and be able to display any number or letter. Under normal thinking you would be correct. However the technical boys have devised a method which joins the same segment in each digit with the next. This means all segments "a" are joined and all segments "b" are joined together etc. Again your reasoning would tell you that if a figure "eight" were to be presented as the first digit, then all the digits would show "eight". Correct. Now let us advance a little further. Instead of all the other ends (all the cathodes) of the 28 segments being connected together, we join the seven segments of each digit to a drive transistor making four separate items. This time, when the first digit shows a figure eight, we can choose which other digit becomes illuminated with an "eight" by turning on the relevant transistor. To understand the next portion of our discussion you must change your whole thinking towards displays. They are not a static sign such as that outside a Milk Bar...they are living! They're like a miniature television screen. You know full well that a picture on a TV screen is made up of a single dot flying across the screen to produce 625 lines. And this is repeated 25 times per second. The dot is turned on and off to produce the black and white portions of the picture. Our "AND" display can be thought of as a TV screen. The four drive transistors are turned on and off sequentially sotthat if a single segment of the first digit were illuminated, it would light briefly at the first digit then the second digit then the third and finally the fourth digit, In other words it would run the length of the display at about 25 times per second. Now your Persistence of Vision would interpret this as segment "a" in each digit being lit constantly. You cannot see flickering or jumping across the display beyond about 25 times per second. Follow this experiment. Instead of supplying the display with energy all the time, we pulse it in synchronisation with the. turning on and off of the third transistor. The result would be only segment "a" in the third digit lighting up. By using this method we can accurately pick out any segment of the 28 segment in the display. Try visualising how a top segment of digit three and a lower segment of the fourth digit can be selected with one passing of the scan. It merely requires accurate timing of the 7 pieces of information being fed into the display via pins 10,8,5,11,9,7 and 6 to coincide with the digit select transistors.   

## CHOOSING A DROPPER RESISTOR
To limit the current through each segment of the display we need 7 dropper resistors. The value of these resistors will be governed by the supply voltage. Once this is chosen you will be able to select a particular value of dropper resistor. A range of suitable resistors has been included in the kit of parts. You will not be needing all the resistors as some apply to a higher or lower voltage. They are not absolutely critical and a value either side of the one specified will operate quite satisfactorily. The only requirement is for the 7 resistors to be of the same value. Two or three different values will cause the display to be uneven. Fortunately the "AND" display is not quite so sensitive to slight voltage variations as it is constructed with Gallium Phosphide LED's which are a saturating type and produce a very even display somewhat independent of supply voltage.  

![](https://github.com/SteveJustin1963/TE-2-4--Counter-Module/blob/master/bd.png)
![](https://github.com/SteveJustin1963/TE-2-4--Counter-Module/blob/master/pcb.png)
![](https://github.com/SteveJustin1963/TE-2-4--Counter-Module/blob/master/cf%20and%20volts.png)

The 74C926 counter chip is capable of driving 4 digits. Refer to the block diagram for the sections contained within the chip. The input frequency appears at the "clock" pin, number 12, and passes through 4 divide-by-ten counters. At each stage it emerges to be fed into a 4-bit latch. The outputs pass to a Binary-Coded-Decimal to 7 segment decoder and driver, where it feeds the display via dropper resistors. The multiplexing network generates a set of synchronising pulses, one set feeding each of the 4 latches, the other set feeding A,B,C,Douts. The chip contains its own internal oscillator to drive the multiplex which in turn sets the scan rate for the display. This internal oscillator cannot be adjusted which is a pity really, it would be nice to lower the scan to a point where each of the 4 digits can be viewed turning on and off sequentially so the whole operation of the display could be understood. We will be arranging an alternative to the "AND" display, should supplies become difficult to obtain. Don't forget you can make your own 7 segment display and have no supply problems.  

## MOLEX PINS
Both the 74C526 and the AND 4145 display are mounted on molex pins. We have foupd this to be a fairly successful form of mounting as the 24 pin display has different in-line width to a normal 24 pin IC socket. Molex pins also allow you to remove both chips for other projects as most of the cost is centered in these items. The 4-digit 7 segment display described in the next article is fully compatible with this project and the AND display can be substituted with your own home-made version. 
## MOUNTING THE PARTS
Commence assembly by fitting the molex pins. Cut them into lengths of the exact number of pins required. Push into place and solder quickly and neatly. Bend the unwanted runner backwards and it will break off from the pins. Fit the 4 transistors, 5 jumpers and battery leads. Finally solder all the resistors, including the 7 dropper resistors chosen from the enclosed list. Now comes the two expensive parts. Locate the dot on one corner of the 7426. Do not go by the lettering or numbering on the IC. It is not always printed around the same way. Only go by the tiny dimple or dot or key-way in one end. The AND display has a locating mark as a notch or recess in its lower side. Refer to the drawing. With these in position, it is ready for testing. 
## TESTING 
Connect a lead with an alligator clip to the, positive rail. This will be your test lead. Connect the battery or power supply and the display will illuminate with 0000. Tap the alligator clip onto the resistor marked "clock" and the display will register 1 or maybe 5 or. 6 depending on the number of spikes it detected. You can reset the counter by touching the resistor marked "reset". Next issue we will provide some experiments and details on input sensors.    

![](https://github.com/SteveJustin1963/TE-2-4--Counter-Module/blob/master/pic2.png)

