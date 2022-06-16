# arduino-bit-manupulation

## Helium Console decoders

https://github.com/helium/console-decoders


## Good ones to decode

Easy:
https://github.com/helium/console-decoders/blob/master/Wisblock/1906/decoder.js

Good with definitions

https://github.com/helium/console-decoders/blob/master/Ursalink/AM100%20-%20AM102%20Payload%20Decoder/decoder.js

https://github.com/helium/console-decoders/blob/master/StregaTechnologies/DECODER-V3-V4.js

https://github.com/helium/console-decoders/blob/master/SEEED/Seeeduino_LoRaWAN/decoder.js




Advanced:

https://github.com/helium/console-decoders/blob/master/senstick/decoder.js




## Bitwise Online Calculators

best

https://www.rapidtables.com/convert/number/binary-converter.html


https://www.rapidtables.com/calc/math/binary-calculator.html

https://bitwisecmd.com/

https://truthtablemaker.com/    



https://www.omnicalculator.com/math/twos-complement

https://www.omnicalculator.com/math/xor


https://onlinetoolz.net/bitshift#base=8&value=255&bits=8&steps=1&dir=l&type=ari&allsteps=1

https://miniwebtool.com/bitwise-calculator/bit-shift/?data_type=10&number=45&place=4&operator=Shift+Right

https://www.omnicalculator.com/math/bit-shift

https://www.omnicalculator.com/math/bitwise

https://www.omnicalculator.com/math/binary-operations


https://www.omnicalculator.com/math/ones-complement


https://www.omnicalculator.com/math/binary-subtraction

Just some research before doing some decoder work

## Javascript Reference

https://www.w3schools.com/js/js_bitwise.asp

https://www.programiz.com/javascript/bitwise-operators



## Arduino Refernece
https://www.arduino.cc/en/Tutorial/Foundations/BitMask

https://www.arduino.cc/reference/tr/language/structure/bitwise-operators/bitshiftleft/

https://www.bluetin.io/robot-control/arduino-port-access-bitwise-op/


```
For a practical example, let's take the value 170, binary 10101010. To pulse this value out of pin 7 the code might look as follows:

byte transmit = 7; //define our transmit pin
byte data = 170; //value to transmit, binary 10101010
byte mask = 1; //our bitmask
byte bitDelay = 100;

void setup()
{

   pinMode(transmit,OUTPUT);
}

void loop()
{

  for (mask = 00000001; mask>0; mask <<= 1) { //iterate through bit mask

    if (data & mask){ // if bitwise AND resolves to true

      digitalWrite(transmit,HIGH); // send 1

    }

    else{ //if bitwise and resolves to false

      digitalWrite(transmit,LOW); // send 0

    }

    delayMicroseconds(bitDelay); //delay

  }
}

```





```
 Operation  Result
   ---------  ------
    1 <<  0      1
    1 <<  1      2
    1 <<  2      4
    1 <<  3      8
    ...
    1 <<  8    256
    1 <<  9    512
    1 << 10   1024
    ...
The following example can be used to print out the value of a received byte to the serial monitor, using the left shift operator to move along the byte from bottom(LSB) to top (MSB), and print out its Binary value:

// Prints out Binary value (1 or 0) of byte
void printOut1(int c) {
  for (int bits = 7; bits > -1; bits--) {
    // Compare bits 7-0 in byte
    if (c & (1 << bits)) {
      Serial.print("1");
    }
    else {
      Serial.print("0");
    }
  }
}
```





