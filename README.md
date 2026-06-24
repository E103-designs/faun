# faun
E103 faun is an open source multi-utility 2HP eurorack module that can change function by changing the preset boards on its back, called "MODS".

Its name comes from the first four letters of the italian phrase "Fa un po' di tutto", as written on the front panel.

It translate to "It does a little bit of everything", to remark its flexibility in being an experimenting playgroud.

# The idea behind it
I had the idea of faun while trying to revamp my first eurorack passive modules (S2XM and picoMID1U). 
faun started as the middle point between the two, being simply half the size of S2XM and with the pin headers of the picoMID1U in the back, but soon I thought: "Why not using faun in its basic form as a blank canvas for all sorts of passive eurorack projects?".

I started pushing the boundaries of how many different things you can achieve by simply connecting the pins of the available jacks to each other. Then I started creating backpack protoboards to attach to the module. 

So the idea of the MODS PCBs as expansions came to life!
By using the "MODS" you can use any signal going IN or OUT from the mono and stereo jacks on the front and treat them how you want ;)

I started collecting ideas and experimenting for various passive designs and I collected a bunch of them and made them as real PCBs. 

# Basic usage
At its core, faun is simply made of 6x 3.5mm jacks (4 mono and 2 stereo) with various pins exposed on the back.
They are grouped in the top and bottom triplet (named 1, 2, A and 3, 4, B, where A and B being the stereo jacks). This is to recall the function of the S2XM, which is a module that splits a stereo channel into two mono channels, or as a CV breakout for MPC One and Live. 
In the back, a 3x5 pin header matrix exposes various connection, arranged in a way that allows useful jumper settings to achieve different uses without any additional MODS (see relative page for explanations [here](https://github.com/E103-designs/faun/blob/7ad7701eaba7f7385ea16005ce7d22d27b760d93/faun%20Main%20Module%20overview.md)


faun, in its basic form, allows (by using jumpers or not) to be used in the following ways:
- Two independent Stereo to Dual Mono (L&R) signal splitter
- 3.5" MIDI breakout for ES Disting(s), Michigan synthworks F8R and much more.
- MIDI Type A to B converter by simply re-routing exposed connectors
- Dual MPC Gate/CV breakout
- Dual 1x2 passive mult
- Single 1x5 passive mult

# The MODS
MODS are PCB that are rear mounted onto faun to give the module additional functions. Here's a quick summary of currently available MODS:
- MOD1: 3 Channels Stereo passive mixer
- MOD2: 5 Channels Mono passive mixer
- MOD3: 5-BIT R-2R Ladder DAC (for creative signal combining/mangling)
- MOD4: Stereo 4 inputs Passive Panning mixer
- MOD5: Passive XOR gate and Passive Rectifier (1 in -> 2 rectified outs)
- MOD6: Passive Diode Clipper/Dual LPG/VC Panner (by changing jumper positions)
- MOD7 (WIP): Playground -> Every faun pin is available as a female connector, allowing to mount directly components or male dupont cables to create custom routing!

# Future development
Currently I only developed passive MODS, but no one is stopping me (OR YOU!) to design active modules! The biggest limitation is PCB space being 2HP only.
But I think that a simple LM13700 VCA can be obtained by using SMD components and creative workarounds :)
