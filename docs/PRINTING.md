# Print notes

All values on this page were read from the metadata and the tool paths of the sliced files in `gcode/prusa-mk4/`. They describe how the parts were sliced, not a tuned recommendation for other printers.

## Settings

| Setting | Value |
|---|---|
| Slicer | PrusaSlicer 2.9.6 |
| Printer profile | Original Prusa MK4, 0.4 mm nozzle |
| Filament profile | Generic PLA @PG, 1.75 mm, density 1.24 g/cm³ |
| Layer height | 0.20 mm, first layer 0.20 mm |
| Perimeters | 2 |
| Top and bottom solid layers | 5 top, 4 bottom |
| Infill | 15 %, gyroid |
| Supports | None |
| Brim | None; 5 mm in the alternative file for the Full Shield base |
| Nozzle temperature | 215 °C for the first layer, then 210 °C |
| Bed temperature | 60 °C |
| Date sliced | 14 September 2026 |

The metadata names only the generic PLA profile. The printed units used an ordinary PLA filament in a light brown, almost beige color. The brand is not recorded.

## Orientation

- Bases: open rim on the bed, closed panel on top. The panel is printed last as a bridge across the cavity, starting at 16.8 mm for the Shield base and at 12.2 mm for the Stella base. No supports are used.
- Lids: plate on the bed, snap tabs pointing up.

The STL files are already in this orientation, so they can be placed on the bed without rotating them.

With the rim on the bed, the first layer of a base is only a ring. `shield-base-full-brim5_0.4n_0.2mm_PLA_MK4_1h39m.bgcode` is the same part sliced with a 5 mm brim.

The slicer rounds part heights to whole layers. Printed heights can differ from the model by up to 0.1 mm: the Shield base prints 19.6 mm tall instead of 19.5 mm, the Shield lid 5.2 mm instead of 5.3 mm, and the Stella lid 4.2 mm instead of 4.1 mm.

## Sliced files

Mass and time are slicer estimates.

| File in `gcode/prusa-mk4/` | Part | Layers | Mass (g) | Print time |
|---|---|---|---|---|
| `shield-base-full_0.4n_0.2mm_PLA_MK4_1h36m.bgcode` | Shield base, Full | 98 | 21.79 | 1 h 36 min |
| `shield-base-full-brim5_0.4n_0.2mm_PLA_MK4_1h39m.bgcode` | Shield base, Full, 5 mm brim | 98 | 22.10 | 1 h 39 min |
| `shield-lid-full_0.4n_0.2mm_PLA_MK4_40m.bgcode` | Shield lid, Full | 26 | 10.94 | 40 min |
| `shield-base-gaps_0.4n_0.2mm_PLA_MK4_1h35m.bgcode` | Shield base, Gaps | 98 | 15.82 | 1 h 35 min |
| `shield-lid-gaps_0.4n_0.2mm_PLA_MK4_38m.bgcode` | Shield lid, Gaps | 26 | 6.96 | 38 min |
| `stella-base-full_0.4n_0.2mm_PLA_MK4_38m.bgcode` | Stella base, Full | 70 | 8.41 | 38 min |
| `stella-lid-full_0.4n_0.2mm_PLA_MK4_15m.bgcode` | Stella lid, Full | 21 | 4.18 | 15 min |
| `stella-base-gaps_0.4n_0.2mm_PLA_MK4_38m.bgcode` | Stella base, Gaps | 70 | 5.74 | 38 min |
| `stella-lid-gaps_0.4n_0.2mm_PLA_MK4_14m.bgcode` | Stella lid, Gaps | 21 | 2.67 | 14 min |

The `.bgcode` files keep the original STL file names in their metadata (for example `Baza Portenta C33.stl`).

## Assembly

1. Remove the brim if one was printed.
2. Shield: plug the Portenta UWB Shield onto the Portenta C33. Lower the assembly into the base with the USB-C connector in the end-wall opening and the board resting on the four standoffs.
3. Shield, optional: fix the board with M2 screws in the standoff holes (1.8 mm diameter, about 3.5 mm deep). The units tested so far were run without screws.
4. Stella: insert the CR2032 battery if the unit is to run untethered. Press the board into the base with the USB-C connector in the opening of the diagonal face, until it rests on the three corner pads.
5. Press the lid onto the base until the tabs engage. The Shield lid fits in two orientations and the Stella lid in eight.
6. To open, pull the lid off by hand.

The position of the USB-C openings fixes the orientation of each board: the USB-C connector is on the side of the closed panel.
