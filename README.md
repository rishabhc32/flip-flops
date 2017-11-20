# Flip Flops and Latches

This is a guide for making Flip Flops and Latches using NAND gates. 

> When I was studying about Flip Flops and Latches in my class, all I wondered was how in the world we can store a bit by interconnecting 4 NAND gates. So I decided to make Flip Flops on my own and verify.

##### Material Required
* IC - 7400 (Quad 2-input NAND Gates)
* 4-5 LEDs
* Breadboard
* 5V power supply

These are all the things needed to make FFs.

**IC-7400** is used in each circuit for _NAND_ gates.

![IC-7400](http://www.robodocbd.com/uploads/product_specifications/c7f0549adca1460c8772518a902bf192.png "IC-7400 schematic")
## SR Latch
![SR Latch](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-latch.jpg "SR Latch")

This is a [**Active LOW SR Latch**](https://www.allaboutcircuits.com/textbook/digital/chpt-10/s-r-latch/), _output_ is **HIGH (SET)** when **S** is LOW while _output_ is **LOW (reset)** when **R** is LOW. Another type is Active HIGH SR Latch build using NOR Gate.

Here **Active Low SR Latch** is demonstated.

![circuit diagram](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/schematic.png "Circuit Diagram")

* Using **IC-7400** connect the above shown circuit on a breadboard and supply 5V VCC to IC. 
* Initially set **S** and **R** to 1, i.e. HIGH.

![real life circuit](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/circuit.jpg "My Circuit")

This is how my circuit was looking. I was using Arduino for 5V power supply.
**Don't forget to add resistor before an LED to prevent from over voltage.**

* Now verify the truth table for the Latch.
* Active Low Latch changes output, i.e. SET or RESET only when **S** or **R** is LOW respectively.

S|R|Q|Image|Comment
-|-|-|-----|-
HIGH|HIGH|Don't Care|![first][logo1]|**Initially** output is default set to LOW
LOW|HIGH|HIGH|![second][logo2]|Now ouput (Q) becomes HIGH (SET) as S is LOW
HIGH|HIGH|No Change|![third][logo3]|S is set to HIGH but the previous ouput i.e. **1** is stored
HIGH|LOW|LOW|![fourth][logo4]|Now output (Q) becomes LOW (RESET) as R is LOW
HIGH|HIGH|No Change|![fifth][logo5]|R is HIGH but previous output i.e. **0** is stored
LOW|LOW|Invalid State|![sixth][logo6]|The output is indeterminate


[logo1]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/1.jpg "Initially"
[logo2]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/2.png "SET"
[logo3]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/3.png
"No Change, output HIGH"
[logo4]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/4.png "RESET"
[logo5]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/5.png "No Change, output LOW"
[logo6]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/6.png "Invalid State"

So it is clear that a **Latch** stores a bit after it is **SET** or **RESET** even after the the input is changed. :metal:

_Raw Video of Latch demo \:_
> [![demo raw video](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/video.png "Video Link")](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/raw-video.mp4)

## SR FlipFlop
![SR Flip Flop](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/srffctt.png "SR Flip Flop")
> **CLK** or **CK** is CLOCK

This is a [**SR Flip Flop**](http://www.electronicshub.org/sr-flip-flop-design-with-nor-and-nand-logic-gates/), _output_ is **HIGH (SET)** when **S** and **CLK** is HIGH while _output_ is **LOW (reset)** when **R** and **CLK** is HIGH. SR FF is clock synchronized SR Latch and has several [advantage over SR Latch](http://www.learnabout-electronics.org/Digital/dig52.php).

Due to unavailability of function generator and my laziness of making a square wave generator, I made a [**SR Gated Latch**](https://www.allaboutcircuits.com/textbook/digital/chpt-10/the-gated-s-r-latch/), which is nothing but a SR FF with ENABLE instead of CLK.

![SR gated latch](https://upload.wikimedia.org/wikipedia/en/4/49/Gated_SR_latch.png "SR Gated Latch")
> **EN** or **E** is ENABLE

Here **Gated SR Latch** is demonstated.

![circuit diagram Gated sr latch](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/srff-schematic.png "Circuit Diagram - Gated SR Latch")

* Using **IC-7400** connect the above shown circuit on a breadboard and supply 5V VCC to IC. 
* Initially set **S**, **R** and **EN** to **0**, i.e. LOW.

![real life circuit](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/circuit.jpg "My Circuit")

This is how my circuit was looking. I was using Arduino for 5V power supply.
**Don't forget to add resistor before an LED to prevent from over voltage.**

* Now verify the truth table for the Flip Flop.
* Flip Flop changed _ouput_ when **EN** is HIGH and **S** or **R** is HIGH.

E|S|R|Q|Image|Comment
-|-|-|-|-----|-
LOW|LOW|LOW|Don't Care|![first][logo11]|**Initially** output is default set to LOW
HIGH|HIGH|LOW|HIGH|![second][logo21]|Now ouput (Q) becomes HIGH (SET) as S is HIGH
HIGH|LOW|LOW|No Change|![third][logo31]|S is set to LOW but the previous ouput i.e. **1** is stored
LOW|LOW|HIGH|No Change|![3 & 1/2][logo71]|R is HIGH but Q is HIGH as EN is LOW i.e.**1** is stored 
HIGH|LOW|HIGH|LOW|![fourth][logo41]|Now output (Q) becomes LOW (RESET) as R is HIGH
HIGH|LOW|LOW|No Change|![fifth][logo51]|R is LOW but previous output i.e. **0** is stored
HIGH|HIGH|HIGH|Invalid State|![sixth][logo81]|The output is indeterminate

[logo11]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/1.png "Initially"
[logo21]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/2.png "SET"
[logo31]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/3.png
"No Change, output HIGH"
[logo41]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/4.png "RESET"
[logo51]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/5.png "No Change, output LOW"
[logo71]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/7.png "No Change, R High but EN LOW"
[logo81]:https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/8.png  "Invalid State"

So it is clear that a **Flip Flop** stores a bit after it is **SET** or **RESET** even after the the input is changed. And a **Flip FLop** changes its value only when **EN** or **CLK** is HIGH  :sunglasses:

_Raw Video of Flip Flop demo \:_
> [![demo raw video](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/thubnail.png "Video Link")](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/sr-ff/video.mp4)
