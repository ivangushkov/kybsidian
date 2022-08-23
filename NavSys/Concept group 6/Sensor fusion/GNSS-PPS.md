## Concept
Send an electrical pulse from the GNSS receiver to other parts of the system. By watching for rising or falling edge of the PPS (Pulse Per Second) signal we can indicate to other parts of the system when the GNSS measurement epoch and synchronization point is.

![[Pasted image 20220529151042.png]]


## Latency
	Just using the time of arrival of the message as the time mark may 
    cause significant timing errors

There is a time delta between receiving signals and when the solution actually is calculated. Connections between sensors also requires packaging of data and transfer.

Ex: RS232: 115200 baud means 11520 Byte/sec, 30 bytes is still 2.6 ms.
A 100Hz IMU will then introduce almost 1/4 of a measurement epoch


## Timing errors

Even in [[INS]] alone, oscillator error can yield 100s of meter of drift per hour!