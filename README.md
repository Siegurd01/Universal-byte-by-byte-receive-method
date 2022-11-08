# Universal byte-by-byte receive method
This is light and universal library for solving send-receive bytes problem

The transfer of data between devices is often associated with certain problems in receiving bytes.
There are simplified methods for receiving packets, for example:
 - Fixed pause between packets
 - Fixed packet ending
 - Fixed packet length
 - and etc.

They are suitable when you need to transfer several bytes between devices.
But what if there are interferences in the channel, the transmission is continuous, and the packets come with different lengths and from different devices?
To solve this problem, I developed a small library that can take over the processing of input data, providing the user with a ready-made array of uncorrupted data with separation on categories/devices/types.
Because of the fast processing, library methods can be called during interrupts in MCU.
