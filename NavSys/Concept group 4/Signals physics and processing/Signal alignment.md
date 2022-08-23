## Signal alignment
Once the signal has been recovered (see [[Signal recovery]]) it needs to be aligned. Alignment means to find the edges of the chips, and then for the bits.

This is done by exploiting the fact that the spreading code rapidly decorrelates over a range of +/- 1 chip:

1. Three copies of the local replica code: early, prompt, and late.
2. Prompt is aligned and early/late are shifted by a chip fraction
3. Autocorrelation is ran on all three codes
4. early minus late yields an error term that can be used for control
5. The error is fed back to an [[NCO]] (Numerically Controlled Oscillator) to steer the local code to track the incoming signal

This architecture is referred to as a [[DLL]] (Delay Locked Loop). There are also [[FLL]] and [[PLL]].

After this we have locked onto the code phase. We still do not have range or time. For this we need to lock onto the bitstream in the message.

## Bit alignment
Even though the signal is tracked, we do not know where the actual data bits start and end, and such we need to align the chips to the data bits. We do however know that (at least for GPS):
* Data bits are 20ms each (i.e. the bit period is 20ms)
* We have many more chips for each bit period

At first acquisition we do not know where in the stream we are, but using this prior knowledge we expect the data stream to contain 20ms intervals of constants, with potentially a transition between intervals. To resolve this and align with the data stream, we use bin histograms with 20 bins - one for each ms in the bit intervals:

1. Bits are determined by taking the sign of the prompt correlator over the interval by [[Coherent integration]] over 1ms.
2. Start at bin 1 during the first code period, and if the sign of the prompt correlator flips, add a point 
3. Do this for all bins up to 20, then go back to 1
4. Do this until one bin has significantly more transitions than the others
5. Verify using a ratio or threshold test - if it fails, restart the process.

After this process we will have found the bit edge, and thus can retrieve a stream of bits that contain actual data. However, we do not know where the start and end of the data stream is. We also do not know if we are "upside down", i.e if + is + or -

## Data alignment
The GPS [[Data frame]] has a preamble which is a fixed sequence of bits, and we search for this and its inverse. Once this has been found the remainder of the 30 bit word is captured, and a parity check is executed. If the parity fails try again the next time the preamble sequence is seen. If it passes, we have synchronization.


## Conclusion
After these steps we are aligned in three ways:
1. ns level with C/A code fine grained alignment
2. ms level with C/A code period alignment
3. 20ms level with bit period alignment
4. 600ms level TLM word alignment 

The aligned signal can be used in a tracking loop for [[Signal tracking]]