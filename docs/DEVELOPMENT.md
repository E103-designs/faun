# Developing faun and MOD boards

faun is a passive interconnect platform. The base module and MOD1–MOD6 have no MCU, bootloader, firmware or software dependencies. Development means changing electrical routing or designing a compatible rear board.

## Header reference

Use the viewing orientation in the [manual](USER_MANUAL.md), not an assumed mirrored PCB view. X/Y/Z are logical rows and 1–5 are logical columns; the transposed table below lists their electrical functions:

| Row | X | Y | Z |
| --- | --- | --- | --- |
| 1 | A tip | Socket 1 signal | Socket 1 signal |
| 2 | A ring | Socket 2 signal | Socket 2 signal |
| 3 | B ring | Socket 3 signal | Socket 3 signal |
| 4 | B tip | Socket 4 signal | Socket 4 signal |
| 5 | Ground | Socket 4 normal contact (4N) | Socket 2 normal contact (2N) |

Y1=Z1 through Y4=Z4 are already connected on the PCB. Confirm all connections against the manual and continuity of your actual board before reusing them. Do not infer a supply rail. The header is 3 × 5 at 2.54 mm pitch. Inserting a plug into sockets 2/4 opens the corresponding normal contacts.

## A useful development sequence

1. Choose inputs, outputs and mono/TRS cable requirements. Draw a socket-to-header table before making traces.
2. Check every net against a bare board with a continuity tester. Verify orientation and clearance for the actual header and enclosure.
3. Start with a passive breadboard/backpack. Include mixing resistors for summing and appropriate current limiting for LEDs/vactrols. Check loading, attenuation and thresholds in the intended patch.
4. Create native editable CAD and document the tool/version, revision, BOM and assembly orientation. Export PDF and Gerbers from that same revision.
5. Test all jumper settings with known signal levels. Record measurements, connected impedances and component choices; do not extrapolate a safe voltage range from appearance.
6. Publish the CAD, socket mapping, verified jumpers and limitations together. Update the manual when changing pin assignments.

Active designs require a separately engineered supply and signal interface; do not use signal/header contacts as assumed power pins. Keep supply and mounting polarity explicit.

## Existing documentation and gaps

The source manuals are editable Markdown. The corrected native PCB/schematic files are reserved in [hardware/schematics](../hardware/schematics/README.md); current CAD is not included yet. Historical MOD files are useful references, not proof that every revision mates electrically/mechanically. Recheck bottom TRS B: **tip=4, ring=3** in the base splitter.
