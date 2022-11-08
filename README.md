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

The library is applicable not only to physical interfaces (UART, RS485, RS232, SPI, I2C etc) but also to TCP and UDP protocols.
Yes, network protocols are protected with checksums and acknowledged reception (depending on socket settings), but this does not apply to the entire message, but to its parts - packets. For example, if you want to send a message with a length of 10 kilobytes using a 2-3-4-5G modem, at a certain point in the transmission process, some packets of the message may not reach the server due to signal lost or device reboot. TCP guarantees that the packets that reach the server are intact, but the integrity of all 10k massage - is your problem.

# Library features:
 - Byte by byte receive (non-blocking);
 - Dynamic message length;
 - CRC32 support;
 - Recognition of different devices on the same communication line;
 - Functioning in a continuous data stream without pauses and delays.
 
# Library Disadvantages:
 - You need to configure the library to work with each type of messages/addresses/devices/lines separately.
 
# TODO:
 - Support of linear error-correcting Hamming codes;
 - Encryption support (e.g. AES128 or AES256).
