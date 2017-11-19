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

This is a **Active LOW SR Latch**, _output_ is **HIGH (SET)** when **S** is LOW while _output_ is **LOW (reset)** when **R** is LOW. Another type is Active HIGH SR Latch build using NOR Gate.

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
> [![demo raw video](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/video.png)](https://raw.githubusercontent.com/rishabhc32/flip-flops/master/images/raw-video.mp4)
