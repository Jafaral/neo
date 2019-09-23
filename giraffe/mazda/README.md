Mazda giraffe
=============

The Switches
------------

```
                               Switches
                              OFF <=> ON
                       ___________________________  
                   ---|       1  [->O]       +12v |----|__
     Car Connector |  |       2  [->O]      CAN H |----|  |  to CAM
                   ---|       3  [->O]      CAN L |----|__|
                      |       4  [->O]       -GND |----|
                      |            -R-            | 
                      |        /---------\        |
                      |       /   OBDII   \       |
                      | O |-_/_____________\_____ |
Optional External Power ^
```
1. Power the panda from the car
2. Hardware Passthru Stock CAM
3. Connect Panda's CAN1 to CAM CAN
4. Feed 12V to Panda's ignition pin

WARNING WARNING WARNING! Choose between powering the Panda from the car (switch #1) or via external power. Never connect external power if you have the first switch #1 at the ON poistion. You have been warned! Otherwise your car will be transported into another galaxy without you! 

### Switch settings (assuming no external power):

#### Recommended Giraffe Settings

+ 1111 All ON (Best Setting)
  Typically you want to cuttoff stock CAM and let the panda decides what CAN msgs to pass and what to drop,
  but I discovered OP steering doesn't get affected even if I let stock LKAS msgs to pass since we are 
  sending LKAS msgs at much higher rate than stock. 
  
  With this setting the Car is always happy (no dashboard warnings) regardless of whether OP is running or not when you start the car. If EON is off you can start the car and start driving, once EON is up, OP will be available to use.


+ 1011 :  CAM CAN <=> panda CAN3, panda CAN1 <=> CAR CAN1

      Note: With this setting you have to start the car's ignition, and then turn it off immediatly (without pressing on the brakes, push the start button three times). wait for OP to start and then turn the car normally. With this mode, you are guaranteed no to have any interference from stock LKAS (see comment at the bottom). 
   
   With the second, I recommend flashing the panda with safety model set to Mazda. This allows you just turn on the car and go if EON is not connected. 
    

#### Stock
+ 0100 :  CAM is Stock (hardware passthru), panda is OFF (no power to panda/eon)
+ 1100 :  CAM is Stock (hardware passthru), panda is ON , Panda CAN1 <=> CAR CAN1
+ 1110 :  CAM is Stock (hardware passthru), panda is ON , Panda CAN1 <=> CAR CAN1, Panda CAN3 <=> CAM CAN (CAR CAN1),
       
       Note: Once powered panda is always conncted to CAR CAN1, since the CAM is
             in hardware passthru, the car's CAN1 msgs are also read on Panda's CAN3.
             effectively all CAN msgs are read  twice
             

#### Stock if Panda is flashed with default safety model set to Mazda
+ 1010 :  CAM CAN <=> panda CAN3, panda CAN1 <=> CAR CAN1


### Note

  If you power the panda from the car, it takes a couple of seconds to boot and have OP ready to talk to the car. By that time the car might detect that the camera is not connected (panda isn't forwarding msgs yet) and you might git dashboard errors. To avoid that problem, start the car in Accessory mode and turn it off right away. Do that by pressing the car's start button three times without depressing the brake. With Mazda cars, this will provide power for one minute, panda only needs a couple of seconds to boot and you can see OP ready on your EON's screen. Now you are ready to rumble!
  
  
Parts
-----

Switch           :https://www.digikey.com/product-detail/en/grayhill-inc/78F04T/GH7730-ND/2680797

Resistor         : https://www.digikey.com/product-detail/en/te-connectivity-passive-product/CRGH1206F120R/A129547CT-ND/8566751

Female connector : https://www.mouser.com/ProductDetail/538-34824-0124

Male Connector   : https://www.mouser.com/ProductDetail/538-34826-8124

Terminals        :  https://www.mouser.com/ProductDetail/538-560023-0548

OBDII Female connector, these are standard and you can order them form different places. The Ones I got are out of stock, but this is the same item:
https://www.aliexpress.com/item/OBD-16PIN-female-connector-OBD2-Female-Plug-J1962f/32711598516.html

And some wires!
