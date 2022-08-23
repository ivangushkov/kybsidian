## GPS data frame
1500 bit frame -> 300 bit subframe -> 30 bit word

* Data is laid out in 1500 bit frames with repeating organized subframes of 300 bits 
* Each subframe is divided into ten "words" of 30 bit length. 
* Each subframe starts with a **TLM** (TeLeMetry) word and a **HOW** (HandOver Word).

Each telemetry word starts with a known sequence called a **preamble** which is:

	10001011

and can be used for data alignment in [[Signal alignment]]

## Z-count
Every 6 seconds (300 bits) a HOW is transmitted- containing the TOW (Time Of Week), which is 6*(seconds since the start of the week)

## Message segmentation
A full message is 25 full frames, which is 3750 bits (12.5 minutes). Since we dont want to wait this long to know where we are, the data is split in *direct* and *indirect*.

Of every frame the first 3 subframes are direct data (900 bits). Direct data is information only about the transmitting satellite (orbit terms, clock correction, health etc). Direct data is also referred to as the [[Ephemeris]]

The remaining 2 subframes  are indirect data and contain information about the constellation (where all sats are, health etc) and the time offset between GPS time and UTC. Indirect datta is also referred to as the [[Almanac]]

This segmentation means that we can use the satellite after only around 30 seconds.

