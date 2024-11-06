<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

In wireless communication (e.g., Wi-Fi, Bluetooth), data is often transmitted in bursts or frames. The FlexiPacketEngine IC can be used to structure the transmitted frames and include metadata about the length, sequence, and other characteristics of each frame. Below is the representation of the crafted output Packet.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------
|               Header                     |                                   Payloads                                           |            Footer              |
| Sequence Number | Number of Data Packets | All Input 32-Bit Data appear as output at every Clock Cycle in same order as Input   |       End of Data Frame        |
|   31-16 bit     |      15-0 bit          | Payload 1 | Payload 2 | Payload 3 | Payload 4 | ..................... | Last Payload | All 32 bit Set HIGH 0xFFFFFFFF |
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

The sequence number can help detect packet loss due to interference or signal degradation, enabling retransmission if needed.

Example Flow in a Wi-Fi Transmission:
* Data arrives at the MAC layer for transmission.
* The circuit encapsulates the data by adding a header (sequence number and payload length) and a footer (error detection or static value).
* The frame is then transmitted over the air.
* At the receiver, the frame is decoded, and the sequence number and length are used to reconstruct the original data. The footer is checked for integrity.
* If any frames are missing or corrupted, the receiver can request retransmission of those specific frames.
 

## How to test

Explain how to use your project

## External hardware

List external hardware used in your project (e.g. PMOD, LED display, etc), if any
