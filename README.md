# arduino-bit-manupulation


Just some research before doing some decoder work

## Javascript Reference





## Arduino Refernece
https://www.arduino.cc/en/Tutorial/Foundations/BitMask



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





