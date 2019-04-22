Mazda giraffe
=============

The Switches
------------

1. Power the panda from the car
2. Passthru CAN1 to Camera
3. Connect Panda's CAN2 to Camera CAN
4. Feed 12V to Panda's ignition pin

Choose between powering the Panda from the car (switch #1) or via external power. Never connect external power if you have the first switch #1 at the ON poistion. You have been warned!

### Switch settings (assuming no external power):

#### Stock
+ 0100 :  CAM is Stock, panda is OFF
+ 1100 :  CAM is Stock, panda CAN1 <=> CAR CAN1

#### non-stock
+ 1010 :  CAM CAN <=> panda CAN2, panda CAN1 <=> CAR CAN1
+ 1011 :  CAM CAN <=> panda CAN2, panda CAN1 <=> CAR CAN1, panda ignition ON

With non-stock settings, you have to have the correct panda firmware that forwards msgs poerperly between CAN1 and CAN2

The last setting is what I use with OP.

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
