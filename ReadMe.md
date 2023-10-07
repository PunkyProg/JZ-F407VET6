## STM32F407VET6 Industrial Board
[https://www.aliexpress.com/item/1005002760530120.html](https://www.aliexpress.com/item/1005002760530120.html)
![https://www.aliexpress.com/item/1005002760530120.html](Docs/STM32F407VET6_Industrial_Board.jpg)

I came across this board on AliExpress and naively assumed it would have some software support!

It doesn't, and worse than that it doesn't come with any schematics.
So I set about working out what is connected where with a multimeter.

This repository contains a snapshot of the code generated by CubeMX, along with some tests that check each of the peripherals.

Peripherals
 - CAN1: Working*
   - Needs HW mod (Ground not connected!)
 - CAN2: Working
 - RS485: Working
   - USART2 + GPIO for TX/#RX
 - DB9 Serial Port: Working
   - USART1
 - SD Card: Working
 - RTC: Working
 - Buttons: Working
 - LEDs: Working
 - USB Device: Working
 - USB Host: Working
 - Ethernet: Working*
   - Gets an IP, no further work done

## STM32F407 Pinout
I have all of the on-board peripherals working. This is the pinout from the main SoC as shown in CubeMX:
![](Docs/JZ-F407VET6_Pinout.png)

## HW Modification Required
The CAN transceiver for CAN1 does not have its ground pin connected.

You must make a connection from the bottom of C22 to the bottom of C21.