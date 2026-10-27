# E103 FAUN - Product manual

## One utility, many possibilities
Assembled FAUN base. MOD1-MOD6 boards are optional.

FAUN is a configurable passive Eurorack utility. Its six sockets are routed using jumpers or wires on the rear header. Socket roles depend on the selected wiring and on any installed optional MOD board.

| BASE: USING JUMPERS / WIRES | OPTIONAL BOARD REQUIRED |
| TRS splitting, CV/Gate breakout, passive multiples, TRS MIDI adaptation, MIDI breakout and links between two FAUN units. | Stereo/mono mixing, R-2R DAC, panning mixer, XOR/rectifier and MOD6 functions. |

Current version: black panel, purple PCB, silver sockets, four black jack bodies and two pale green jack bodies.

The actual product rear

## Installation and cables
Configure the rear before patching.

First installation

1. Switch off the system and unplug the patch cables. Access the rear outside the rack.
2. Remove the previous configuration’s jumpers and any MOD board. Fit only the links required by your chosen mode.
3. Check the X/Y/Z labels and column numbers 1-5; mount the module without stressing its sockets.
4. Connect a single source first and test one path at a time at low level.

FAUN is passive and needs no Eurorack power connection. The rear 3 x 5 header carries signals. It is NOT a connector for a 10/16-pin power ribbon.

TS and TRS are different

| CABLE | CONTACTS | USE |
| Mono TS | Tip = signal; sleeve = ground | Sockets 1, 2, 3, 4 and mono patches |
| Stereo TRS | Tip = L; ring = R; sleeve = ground | A and B for stereo audio or two separate signals |
| TRS MIDI | Tip/ring = MIDI pair | Type A or B pinout as required by the device |

Use TRS-to-TRS cables to reach both contacts of A/B. Inserting a TS plug into A/B grounds the ring. Do not assume that a balanced TRS output is a stereo source.

Passive circuit limits

A multiple does not mix equipment outputs: distribute one source to several inputs, rather than connecting several outputs together. Loading can reduce signal level or affect CV accuracy; use a buffered multiple for precise 1 V/oct pitch. FAUN does not amplify, provide galvanic isolation or directly drive passive loudspeakers.

## The 15-pin map
Identify pins by their silkscreen labels, not wire colors.

This grid is a logical map of the header: rows X, Y, Z and columns 1-5. The physical header may appear rotated. Read the PCB labels before fitting a jumper; each jumper joins only the two named pins.

Links: 

| PIN | CONNECTION |
| X1 / X2 | A tip (L) / A ring (R) |
| X3 / X4 | B ring (R) / B tip (L) |
| X5 | Common sleeve ground |
| Y1 = Z1 ... Y4 = Z4 | Tips of mono sockets 1 ... 4; each pair is already joined on the PCB |
| Y5 | Socket 4 normal contact (4N) |
| Z5 | Socket 2 normal contact (2N) |

Watch the B pair: B Right comes before B Left in the grid. Pins 2N and 4N are switching contacts: they connect to the corresponding socket tip when no plug is inserted and open when a plug is inserted. They are not two extra independent outputs.

The following diagrams show links in green. Row and column identities stay unchanged throughout. Use two-contact shunts for adjacent pins and suitable female-to-female jumper wires for longer links (2.54 mm header pitch).

## Dual TRS / CV-Gate breakout
Base mode: 4 jumpers, no MOD board.

Links: X1-Y1, X2-Y2, X3-Y3, X4-Y4

| TRS | CONTACT | MONO SOCKET |
| A | Tip / Left | 1 |
| A | Ring / Right | 2 |
| B | Tip / Left | 4 |
| B | Ring / Right | 3 |

Stereo audio

Connect a stereo source to A using TRS. Take L from 1 and R from 2 using TS. For the second pair use B: L is on 4 and R on 3. The same passive wiring works in reverse to place two separate signals on a TRS tip/ring; it is not mono summing.

Example: MPC with dual CV/Gate outputs

Connect a compatible dual-signal MPC CV/Gate TRS port to A: its two signals appear on 1 and 2. A second port can feed B, with tip on 4 and ring on 3. Assign pitch, gate or other CVs on the MPC and patch each mono socket to the intended destination. Check the specific MPC model; port layouts vary.

Fit X1-Y1, X2-Y2, X3-Y3 and X4-Y4. Do not add multiple-mode links while separating independent signals.

## Passive multiples
Distribute one source to several destinations.

Two independent 1 x 2 groups

Links: X1-Y1, X4-Y4, Z1-Z2, Z3-Z4

Upper group: 1, 2 and A (tip). Lower group: 3, 4 and B (tip). For example, feed A and take outputs from 1 and 2; feed B and take outputs from 3 and 4. Use TS cables. Any socket in a group may be the input, with only one source per group.

One 1 x 5 group

Links: X1-Y1, X4-Y4, Z1-Z2, Z3-Z4, Y2-Y3

Add Y2-Y3 to the previous setup: all six tips are now joined. Feed one socket and connect up to five destinations to the others. The rings of A and B are not part of the bus; this is mono distribution, not stereo.

Do not use these setups as mixers: directly joining active outputs can make them drive each other. Use a dedicated mixer board to sum signals.

## TRS MIDI Type A / B adapter
Swap tip and ring while retaining common sleeve ground.

Links: X1-Y1, X2-Y2, X3-Y3, X4-Y4

Connection

1. Fit the four splitter-mode jumpers shown above.
2. On the front, patch 1 to 3 and 2 to 4 using two TS cables.
3. Connect the MIDI source to A and the MIDI destination to B using TRS cables/adapters suitable for the two devices.

| PATH | RESULT |
| A tip > 1 > 3 > B ring | Tip routes to ring |
| A ring > 2 > 4 > B tip | Ring routes to tip |
| A sleeve > common ground > B sleeve | Sleeve connection retained |

For this swap, the correct front links are 1-3 and 2-4. Links 1-4 and 2-3 leave tip connected to tip and ring to ring: they do not perform Type A/Type B conversion.

FAUN changes connector wiring only. It does not convert MIDI to CV, add USB MIDI or create a MIDI electrical interface where none exists. The connected devices must already provide suitable MIDI inputs and outputs.

## MIDI breakout + 4-socket mult
For modules with a compatible MIDI expansion header.

Links: Y2-Y3, Z1-Z2, Z3-Z4

The three links join only 1, 2, 3 and 4 as a four-socket passive multiple (one source plus three destinations). A and B remain separate for MIDI. Do not fit the splitter page’s X-Y jumpers.

Reference example: disting EX, Type A

| DISTING EX MIDI HEADER | FAUN PIN | ROLE |
| 1: OUT DIN 4 | X2 | A ring: MIDI Out |
| 2: OUT DIN 5 | X1 | A tip: MIDI Out |
| 3: IN DIN 5 | X4 | B tip: MIDI In |
| 4: IN DIN 4 | X3 | B ring: MIDI In |

With the system off, wire the four female-to-female leads to the disting EX GT4/MIDI header as shown. A becomes MIDI Out and B MIDI In for Type A cables. For Type B, swap the two wires in the relevant pair. On disting EX, pin 1 is nearest the GT4 label; always verify your hardware revision’s manual.

Other models are not automatically identical. Find OUT DIN4/5 and IN DIN5/4 in their manuals, then match them to FAUN tip/ring contacts. Do not guess at power, I2C or CV headers. Handle MIDI ground/shield as instructed by the host module manufacturer.

## Signal mover and patchbay
Requires two FAUN units and rear jumper wires.

Two FAUN units can move signals between rack locations using internal wires. Switch off, remove jumpers and MOD boards from both units and connect matching signal functions. The connection is passive, with no isolation or regeneration.

| PATH | FAUN 1 > FAUN 2 |
| Mono 1 ... 4 | Y1 > Y1; Y2 > Y2; Y3 > Y3; Y4 > Y4 |
| Stereo A | X1 > X1 (tip); X2 > X2 (ring) |
| Stereo B | X4 > X4 (tip); X3 > X3 (ring) |
| Common ground | X5 > X5 |

Practical example

Patch an LFO into socket 1 on the first FAUN. The signal appears at socket 1 on the second, allowing a short front cable to a nearby destination. Repeat for 2, 3 and 4. For stereo paths, use the X connections in the table and TRS cables on A and B.

Using it as a repatching point

Once signals reach the second FAUN, change its front patch cables to send them to the desired destinations. This table describes a direct patchbay with no added normalled routing. Y5/Z5 are not needed for this basic connection.

Link only circuits with compatible ground references. Keep internal wires short and clear of exposed metalwork. Do not connect signal outputs at both ends of the same route.

## Optional MOD boards
The following functions require the corresponding board.

The base FAUN does not contain all these circuits at once. A preset board changes socket functions; MOD1-MOD6 are optional accessories. The three MOD6 functions are selected using its jumpers, rather than being three separate modules.

| BOARD | FUNCTION | PAGE |
| MOD1 | 3-channel passive stereo mixer | 11 |
| MOD2 | 5-input passive mono mixer | 11 |
| MOD3 | 5-bit passive R-2R DAC | 12 |
| MOD4 | Stereo mixer with fixed pan positions | 12 |
| MOD5 | Passive XOR + half-wave rectifier | 13 |
| MOD6 | Dual LPG / VC panner / diode clipper | 14-16 |

Changing configuration

1. Switch off and unplug every cable.
2. Remove all base configuration jumpers and the previous board.
3. Identify the new MOD label and its connector reference. Align corresponding positions on the 3 x 5 header; do not offset it by a row or column.
4. If orientation cannot be identified from that board’s labels/documentation, do not force installation: establish the reference for the specific MOD first.
5. For MOD6, also set U10, U11, U13 and U12 as shown on its dedicated pages.

Do not install a MOD board over base-mode shunts. A board’s mounting orientation cannot be inferred from PCB color alone.

## MOD1 and MOD2: passive mixers
Optional board required. No gain controls.

MOD1 - three stereo channels

| SOCKET | FUNCTION |
| 1 / 2 | Stereo input 1: L / R on two TS cables |
| A | Stereo input 2 on TRS: tip L, ring R |
| 3 / 4 | Stereo input 3: L / R on two TS cables |
| B | Stereo TRS output: tip L, ring R |

Connect sources to the three inputs and route B to a high-impedance stereo input or TRS breakout. In this mode, 3 is L and 4 is R: MOD1 defines the routing, rather than the base splitter configuration.

MOD2 - five mono inputs

| SOCKET | FUNCTION |
| 1 | Mono input 1 |
| 2 | Mono input 2 |
| A | Mono input 3 (TS) |
| 3 | Mono input 4 |
| 4 | Mono input 5 |
| B | Mono output (TS) |

Passive mixing attenuates signals and depends on connected impedances; there is no makeup gain. Set levels at the sources and add gain downstream if needed. These boards are not headphone amplifiers.

## MOD3: DAC / MOD4: panning
Two different boards, two separate applications.

MOD3 - 5-bit R-2R DAC

| SOCKET | BINARY WEIGHT |
| 1 | 1 (least significant bit) |
| 2 | 2 |
| A | 4 |
| 3 | 8 |
| 4 | 16 (most significant bit) |
| B | DAC output in the patch described here |

Feed up to five gates with consistent high/low levels into the five inputs and take a stepped voltage from B. Five bits allow 32 theoretical codes. Absolute voltage and precision depend on levels, tolerances and loading; this is not a calibrated pitch source.

MOD4 - five fixed stereo positions

| SOCKET | POSITION |
| 1 | Hard left |
| 2 | Mid left |
| A | Center |
| 3 | Mid right |
| 4 | Hard right |
| B | Stereo TRS output |

Patch mono sources into the five inputs and route B to a stereo signal path. Pan is determined by the selected socket; it is neither continuously adjustable nor CV-controlled.

## MOD5: XOR and rectifier
Two sections on one optional preset board.

| SOCKET | FUNCTION |
| 1 | XOR input 1 |
| 2 | XOR input 2 |
| A | XOR output |
| 3 | Rectifier input |
| 4 | Positive half-wave output |
| B | Negative half-wave output |

XOR: rhythmic variations

Connect two compatible gates to 1 and 2 and take the result from A. Ideal XOR is high when exactly one input is high and low when both are equal. Route the result to a suitable gate input and experiment with clocks or patterns.

| INPUT 1 | INPUT 2 | IDEAL XOR |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

Rectification: separate half-waves

Feed a bipolar waveform into 3. Take its positive portion from 4 and its negative portion from B. This separates polarities; it is not full-wave rectification and does not automatically turn the negative half-wave positive.

The circuit is passive: diodes, signal amplitude and loading affect thresholds and levels. Do not expect regenerated logic levels or ideal rectification without a voltage drop.

## MOD6: dual LPG
Two voltage-controlled paths using vactrols.

MOD6: U10 1-2, U11 2-3, U13 1-2, U12 1-2

| SOCKET | FUNCTION |
| 1 | LPG1 CV input |
| 2 | LPG1 audio signal input |
| A | LPG1 output |
| 3 | LPG2 CV input |
| 4 | LPG2 audio signal input |
| B | LPG2 output |

Set the four MOD6 jumpers as shown. Feed audio into 2, a control CV or envelope into 1 and route A to a mixer/audio input. For the second channel, use 4 for signal, 3 for control and B for output.

The passive vactrol path changes signal transmission in response to CV. Its response is component-dependent: attack, decay and closure may differ between channels. Try compatible envelopes or gates, starting at low levels.

“LPG” is the project’s mode name. Filter slope, bandwidth, CV threshold and gain are not specified; do not treat the response as a calibrated filter or a linear VCA.

## MOD6: VC panner
One shared CV, two inputs and two outputs.

MOD6: U10 2-3, U11 1-2, U13 2-3, U12 1-2

| SOCKET | FUNCTION |
| 1 | Shared control CV |
| 2 | Signal input 1 |
| A | Output 1 |
| 3 | Not used |
| 4 | Signal input 2 |
| B | Output 2 |

Set the jumpers as shown. Connect a control CV to 1. Feed the first signal path into 2 and the second into 4; take outputs from A and B. Socket 3 is unused in this mode.

A stereo movement patch

To send one signal to both sides, split it first using a multiple or an already duplicated output and feed the two copies into 2 and 4. Route A to the left channel and B to the right of a mixer/recorder; modulate 1 and listen to the changing balance. The initial split requires an external path; MOD6 does not automatically duplicate the input.

Pan law, level consistency and CV range are not specified. Adjust and evaluate the passive vactrol response in the actual patch.

## MOD6: diode clipper
A passive signal path for waveform shaping.

MOD6: U10 2-3, U11 1-2, U13 1-2, U12 2-3

| SOCKET | FUNCTION |
| 1 | Clipper input |
| 2 | Not used |
| A | Clipper output |
| 3 / 4 / B | Not used |

Set U10, U11, U13 and U12 as shown. Feed audio into 1 and route A to your mixer or audio input. Gradually raise source level and compare the result against the original at a similar listening volume.

Diode clipping alters portions of the waveform that exceed the components’ conduction region. The effect may be subtle at low input levels and more pronounced at higher levels. The passive circuit does not restore lost level.

Clipping threshold, symmetry and maximum permitted level are not specified. Do not connect power amplifier outputs, power supplies or unknown voltages to the sockets.

## Troubleshooting
Check wiring, cable type and installed mode first.

| SYMPTOM | CHECK |
| Missing stereo channel | Use TRS at A/B. In splitter mode: A L=1, A R=2, B L=4, B R=3. |
| Multiple joins unexpected signals | Remove every link and rebuild only the chosen setup. Do not connect multiple sources to the same group. |
| Low mixer level | Attenuation and load dependence are inherent to passive summing. Add gain downstream. |
| Inaccurate pitch CV | Loading from several inputs can change voltage. Use buffered distribution for accurate tracking. |
| MIDI does not respond | Check Type A/B, input/output direction and host header pins. MIDI is not converted to CV. |
| Normal contact opens | Inserting a plug into 2 or 4 opens 2N/4N respectively. This is expected behavior. |
| MOD6 does the wrong function | Check all four selectors in order: U10, U11, U13, U12. |
| MOD will not fit / is offset | Switch off, remove it and check 3 x 5 reference and alignment. Do not force installation. |

Care

Handle the module by its edges. Avoid strain on internal wires, liquids and PCB contact with metalwork. Clean the panel using a soft dry cloth; do not spray cleaners into sockets. Reconfigure jumpers and boards only with the system switched off.

## Quick reference and sources
Updated for the colors of the photographed version.

| BASE MODE | REAR LINKS |
| Splitter / CV-Gate / MIDI adapter | X1-Y1; X2-Y2; X3-Y3; X4-Y4 |
| Two 1 x 2 multiples | X1-Y1; X4-Y4; Z1-Z2; Z3-Z4 |
| One 1 x 5 multiple | As above + Y2-Y3 |
| 4-socket mult for MIDI breakout | Y2-Y3; Z1-Z2; Z3-Z4 |

For MIDI conversion, also add front links 1-3 and 2-4. Each table row is an alternative configuration, not an addition to the others.

Documented physical data

Nominal format: 2 HP. Front panel design outline: 10.16 x 128.50 mm. 3.5 mm front sockets; rear 3 x 5 header at 2.54 mm pitch. Total depth with boards/wires and weight are not specified; check case clearance for the installed configuration.

Edition references

Functions and diagrams: “E103 FAUN manual.pdf”, 19 pages. Base header map and trace continuity cross-checked against Gerber_S2XMS_faun-BACK-PCB_2026-10-03.zip. Front outline: V1.2 design dated 29 September 2026. Appearance: IMG_3208-IMG_3224 and photorealistic views based on the current photos.

Type A/B MIDI and host wiring: Expert Sleepers Tiny MIDI Breakout and disting EX user manual. MPC example: Akai Professional MPC One FAQ. Links checked on 26 October 2026:
[expert-sleepers.co.uk/tinymidibreakout.html](https://expert-sleepers.co.uk/tinymidibreakout.html)
[disting EX - user manual](https://expert-sleepers.co.uk/downloads/manuals/disting_EX_user_manual_1.24.pdf)
[Akai Professional - MPC One FAQ](https://support.akaipro.com/en/support/solutions/articles/69000816149-akai-pro-mpc-one-frequently-asked-questions)

This edition documents the available design; trace verification does not replace testing an assembled unit. Images show appearance, while the technical tables define pinout and jumper settings.
