_Please do not throw sausage pizza away_

Layers
- Physical 
- Data link
- network
- transport
- session
- presentation
- application

> Information is called with different name in different layer of osi model


![[Screenshot from 2024-05-10 07-03-24.png|200]]

### Layer 1: Physical

Where transmission of bits across the network occurs and includes physical and electrical network characteristics.

Copper wire for cat5/cat6 netwok - 1s represented by +- 5 volt and 0s by 0 volt
Fiber optics cable - 1st represented by light, 0s by no light

__Transition Modulation__
if it changes during the clock cycle, then a is represented(other a 0 is represented)

Layer 1 devices view networks from physical topology perspective{{Need to revise}}


How is communication synced?
Asynchoronous
Uses start and stop bits to indicate when transmissions occur from the sender to the receiver.

Synchronous
uses a reference clock to co-ordination the transmissionsion by both sender and receiver.

How is bandwith utilized?
Broadband
Diveds bandwith into separate channels
ex - Cable TV

Baseband
Uses all available frequencies on a medium(cable) to transmit data.
Uses a reference clock.
ex - Telephone, wired ethernet cable

How can we get more out of limited network?

Multiplexing - getting more out of limited network, allows simultaneous use of a baseband connection.

Time-Division Multiplexing(TDM)
Each session takes a turn, using time slots, to share the medium between all users.

Statistical TIme-Division Multiplexing(StatTDM)
Dynamically allocates the time slots on an as-needed basis.

Frequency-Division Multiplexing(FDM)
Divides the medim into channels based on frequencies and each session is transmitted over a different channel (similar to broadband)



Layer 1 devices
Cables, Bluetooth, Wifi, Hubs, access points, media convertors


### Layer 2- Data Link
Package data into frames and transmits those frames on the network

Media access control(MAC)
Physical addressing system of a device which operates on a logical topology.
Uses a 48-bit address assigned to a network interface card(NIC).
![[Pasted image 20240510073454.png]]

Layers 2 devices view networks logically.

Logical Link Control(LLC)
Provides connection services and allows acknowledgement of receipt of messages
It is the most basic form of flow control.

provides basic error control functions
(ex - receiver can inform that data received was corrupted or resend the data) done by checksum - everything received is bunch of 1s and 0s, receiver sums it up compare total with last bit it total is odd and last bit is 1 OR total is even and last bit is 0 then it means the data is good otherwise bad and receiver ask to retransmit the data.

Isochronous
Network devices use a common reference clock source and create time slots for transmission
Network devices know when they can communicate and for how long.

Synchronous
Network devices agree on clocking method to indicate beginning and end of frames and can use control characters.

Asynchronous
Network devices references their own internal clocks and use start and stop bits.
No real control over when devices are allowed to communicate.

Devices Examples
Network cards, bridges, switches{{use logic to learn which physical port is connected to which devices using their mac address}}















