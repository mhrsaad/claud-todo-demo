# Analysis of example drawing `AL_mansour__.dwg`

**File:** AutoCAD 2018 DWG, about 30 MB. It is one large model-space file holding many sheets for several livestock carriers: M/V ALMANSOUR 1, TUWIQ 2 and 3, LIMOUSINE EXPRESS, MED SEA, JOAHAR CHILANGER, ALKHDAIR STAR and BM SPIRIDON. Drawings by Eng. Hazem Saad / BLUE MAR.

## Drawing conventions found
| Item | Convention |
|---|---|
| Units | **Metres, drawn full size (1 unit = 1 m)** |
| Print scale | 1/200 (shown in the title block) |
| Sheet frame | 151.85 × 207.70 m in model space, portrait (≈ 760 × 1040 mm at 1:200) |
| Title block | 36.8 × 12.1 m, bottom-right corner. Fields: INDEX / DESCRIPTION / DATE, Approved by, Checked by, Tested by, CLASS, DRAWING BY, email, ship name, drawing title, scale, BLUE MAR logo |
| Sheet layout | Profile at top. Below it, the deck plans stacked from the top deck down to the tank top. Every view has the same AP and stern alignment |
| Main dimensions box | Left of the title block: LOA, LBP, BREADTH, DEPTH, DRAUGHT |
| Text | Arial / romans. Deck titles ≈ 1.4 m high, sheet title 1.75 m, title-block text 0.4–0.95 m |

## Main layers
| Layer | Use |
|---|---|
| `out line` | Hull outline, title block, fire and safety symbols |
| `INER2` | Inner arrangement, deck plans, texts (the most used layer) |
| `inner`, `INTER`, `b` | Secondary interior lines |
| `axe` | Centre lines (CENTER linetype) |
| `hidden line(s)`, `dashed`, `dotted` | Hidden structure, tanks, escape routes |
| `FIRE LINE`, `PIPING` | Fire main and piping (red) |
| `BLOCKS`, `SYMBOL(S)`, `FI-EQUIPMENTS` | Fire and LSA symbols |
| `HATCH` | Escape-route arrows and fills |
| `VENT` | Ventilation |
| `emerjrncy light`, `light` | Lighting |

## Fire plan symbols used in MV HOPE
The fire plans themselves are stored in the DWG as three unplaced group blocks: `A$C6F953480`, `A$C5A922C62` (LETFALLAH I) and `A$C02572AF6` (ABOU KARIM III). Each one holds a complete plan with a LEGEND table.

The MV HOPE file uses the legend of `A$C6F953480`, which has 63 rows covering fire-fighting and life-saving appliances:
- Each legend symbol is now its own block, named `FP-<description>`, for example `FP-WATER FIRE HYDRANT`, `FP-FIRE BOX HOSE WITH NOZZLES`, `FP-EMERGENCY ESCAPE B.DEVICE` and `FP-LIFE JAKET`. Each block's base point is the centre of the symbol.
- The whole legend table is the block `FIRE PLAN LEGEND`. It is placed inside the sheet, with the Nb. (quantity) column left blank for the MV HOPE counts.

## Note on reading the file
The DWG's header section is damaged, so a strict reader rejects it. All of the geometry, layers and blocks still read correctly. If AutoCAD complains, run `RECOVER` and then `AUDIT`.
