# UNION examples: Annotation, details and materials

67 drafting jobs, each the request in plain words, the exact calls an AI sends to UNION, and UNION's answer to each, played green on UNION 1.0.0-beta.2.

## 5001. Draw a 1:10 eaves detail for our timber frame wall: stud frame, rafter, batt insulation, plasterboard, notes and a dimension.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Timber Eaves Detail" holding a framed wall, rafter, batt, plasterboard strip, two notes with leaders, a dimension and a title
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Timber Eaves Detail\" scale=1:10",
  "op:add detail line points=(0,-900) (140,-900) (140,0) (0,0) (0,-900) view=\"Timber Eaves Detail\"",
  "op:add detail line points=(-20,0) (160,0) (160,45) (-20,45) (-20,0) view=\"Timber Eaves Detail\"",
  "op:add detail line points=(-300,45) (700,445) (700,585) (-300,185) (-300,45) view=\"Timber Eaves Detail\"",
  "op:add insulation from=(70,-880) to=(70,-20) view=\"Timber Eaves Detail\" width=100",
  "op:add filled region boundary=(-13,-900) (0,-900) (0,0) (-13,0) view=\"Timber Eaves Detail\" pattern=\"Solid fill\"",
  "op:add text at=(450,-400) view=\"Timber Eaves Detail\" text=\"140 x 45 STUD FRAME\" leader_to=(140,-450)",
  "op:add text at=(-600,-500) view=\"Timber Eaves Detail\" text=\"13 PLASTERBOARD LINING\" leader_to=(-6,-500)",
  "op:add dimension from=(0,-900) to=(140,-900) view=\"Timber Eaves Detail\" offset=-150",
  "op:add text at=(0,-1400) view=\"Timber Eaves Detail\" text=\"TIMBER EAVES 1:10\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Timber Eaves Detail" scale=1:10` | green: op:add drafting view made=826303e3fc304b02965e00cd46d187e3 changed= ms=18 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,-900) (140,-900) (140,0) (0,0) (0,-900) view="Timber Eaves Detail"` | green: op:add detail line made=detail-97e0a09521ed4ea7,detail-d152cb9d8cd346ca,detail-2c6f7c7714fe48e8,detail-fabf3463e9f440d5 changed= ms=5 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(-20,0) (160,0) (160,45) (-20,45) (-20,0) view="Timber Eaves Detail"` | green: op:add detail line made=detail-ddcbd0b489314ffa,detail-963f621777814e78,detail-c33eccb73d7a4883,detail-be45c09b5f474791 changed= ms=4 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-300,45) (700,445) (700,585) (-300,185) (-300,45) view="Timber Eaves Detail"` | green: op:add detail line made=detail-c7e83e581d89499c,detail-517ead84b9454912,detail-2579ad6f396548ce,detail-5b3e773f2b474e50 changed= ms=4 Check "Lines +4": Lines 8 -> 12 (+4, expected +4) |
| `op:add insulation from=(70,-880) to=(70,-20) view="Timber Eaves Detail" width=100` | green: op:add insulation made=insul-5032be30154f2f32 changed= ms=3 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(-13,-900) (0,-900) (0,0) (-13,0) view="Timber Eaves Detail" pattern="Solid fill"` | green: op:add filled region made=region-8807e696061342f7 changed= ms=3 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add text at=(450,-400) view="Timber Eaves Detail" text="140 x 45 STUD FRAME" leader_to=(140,-450)` | green: op:add text made=text-173b7466327e4cca changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(-600,-500) view="Timber Eaves Detail" text="13 PLASTERBOARD LINING" leader_to=(-6,-500)` | green: op:add text made=text-3f930321529c485e changed= ms=2 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(0,-900) to=(140,-900) view="Timber Eaves Detail" offset=-150` | green: op:add dimension made=dim-c7cd316f484d4faf changed= ms=149 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-1400) view="Timber Eaves Detail" text="TIMBER EAVES 1:10"` | green: op:add text made=text-7cdaa65f28e54594 changed= ms=2 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |

### The result

The model holds: Detail Items 1,Dimensions 1,Filled Regions 1,Levels 3,Lines 12,Text Notes 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5002. I need a 1:20 strip footing detail under a brick wall with a ground slab, DPM, gravel and the footing dimensions.

- Starts from: a new Architectural project
- Ends with: a 1:20 drafting view "Strip Footing Detail" holding the footing, brick wall, slab edge, DPM line, gravel and concrete hatches, three notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Strip Footing Detail\" scale=1:20",
  "op:add detail line points=(0,-300) (600,-300) (600,0) (0,0) (0,-300) view=\"Strip Footing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(185,0) (415,0) (415,800) (185,800) (185,0) view=\"Strip Footing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(415,0) (1400,0) (1400,100) (415,100) view=\"Strip Footing Detail\"",
  "op:add filled region boundary=(0,-300) (600,-300) (600,0) (0,0) view=\"Strip Footing Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add filled region boundary=(415,-120) (1400,-120) (1400,0) (415,0) view=\"Strip Footing Detail\" pattern=Gravel",
  "op:add detail line points=(415,10) (1400,10) view=\"Strip Footing Detail\" style=\"Medium Lines\"",
  "op:add text at=(1000,500) view=\"Strip Footing Detail\" text=\"100 CONCRETE SLAB ON DPM\" leader_to=(900,100)",
  "op:add text at=(900,-500) view=\"Strip Footing Detail\" text=\"CRUSHED ROCK BEDDING\" leader_to=(900,-60)",
  "op:add text at=(-700,-450) view=\"Strip Footing Detail\" text=\"N12 BARS CONTINUOUS\" leader_to=(150,-200)",
  "op:add dimension from=(0,-300) to=(600,-300) view=\"Strip Footing Detail\" offset=-200",
  "op:add dimension from=(600,-300) to=(600,0) view=\"Strip Footing Detail\" offset=-250"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Strip Footing Detail" scale=1:20` | green: op:add drafting view made=9f924ec363544cae921eadd824cf5de6 changed= ms=617 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,-300) (600,-300) (600,0) (0,0) (0,-300) view="Strip Footing Detail" style="Wide Lines"` | green: op:add detail line made=detail-2f301475065c4ec1,detail-4418d8c7ee1044d6,detail-d3144c5e16204fc7,detail-75f1ff61ee6b4207 changed= ms=3 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(185,0) (415,0) (415,800) (185,800) (185,0) view="Strip Footing Detail" style="Wide Lines"` | green: op:add detail line made=detail-14915f01427d43cd,detail-1f586c2fa75d46e6,detail-014a6ca7488346f2,detail-e1606ac06be4472e changed= ms=4 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(415,0) (1400,0) (1400,100) (415,100) view="Strip Footing Detail"` | green: op:add detail line made=detail-b024d9f1daa04e90,detail-5821b99123914af2,detail-ff4538b10f8143f3 changed= ms=4 Check "Lines +3": Lines 8 -> 11 (+3, expected +3) |
| `op:add filled region boundary=(0,-300) (600,-300) (600,0) (0,0) view="Strip Footing Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-0e5eea4ba8e74a8e changed= ms=6 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(415,-120) (1400,-120) (1400,0) (415,0) view="Strip Footing Detail" pattern=Gravel` | green: op:add filled region made=region-ffdccd6a09344433 changed= ms=7 Check "Filled Regions +1": Filled Regions 1 -> 2 (+1, expected +1) |
| `op:add detail line points=(415,10) (1400,10) view="Strip Footing Detail" style="Medium Lines"` | green: op:add detail line made=detail-43848d8e9f1742c3 changed= ms=3 Check "Lines +1": Lines 11 -> 12 (+1, expected +1) |
| `op:add text at=(1000,500) view="Strip Footing Detail" text="100 CONCRETE SLAB ON DPM" leader_to=(900,100)` | green: op:add text made=text-fe1f0bf9f5f642b2 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(900,-500) view="Strip Footing Detail" text="CRUSHED ROCK BEDDING" leader_to=(900,-60)` | green: op:add text made=text-4675f5c3a81440be changed= ms=2 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(-700,-450) view="Strip Footing Detail" text="N12 BARS CONTINUOUS" leader_to=(150,-200)` | green: op:add text made=text-31bb5f4b7ccd4dd8 changed= ms=3 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add dimension from=(0,-300) to=(600,-300) view="Strip Footing Detail" offset=-200` | green: op:add dimension made=dim-532b46e6a4f24eac changed= ms=39 note=offset -200: the dimension line stands 200 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(600,-300) to=(600,0) view="Strip Footing Detail" offset=-250` | green: op:add dimension made=dim-75e33b81b1284dc2 changed= ms=4 note=offset -250: the dimension line stands 250 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Filled Regions 2,Levels 3,Lines 12,Text Notes 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5003. Detail a steel column base plate on a pad at 1:10 with the grout, two anchor bolts and the plate size noted.

- Starts from: a new Structural project
- Ends with: a 1:10 drafting view "Column Base Plate Detail" with the column flange, plate, grout bed, pad outline, two anchor bolts, hatch, notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Column Base Plate Detail\" scale=1:10",
  "op:add detail line points=(0,0) (400,0) (400,20) (0,20) (0,0) view=\"Column Base Plate Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(190,20) (210,20) (210,600) (190,600) (190,20) view=\"Column Base Plate Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-100,-30) (500,-30) (500,0) (-100,0) (-100,-30) view=\"Column Base Plate Detail\"",
  "op:add detail line points=(-300,-300) (700,-300) (700,-30) (-300,-30) (-300,-300) view=\"Column Base Plate Detail\"",
  "op:add detail line points=(40,-250) (40,60) (60,60) (60,-250) view=\"Column Base Plate Detail\"",
  "op:add detail line points=(340,-250) (340,60) (360,60) (360,-250) view=\"Column Base Plate Detail\"",
  "op:add filled region boundary=(-300,-300) (700,-300) (700,-30) (-300,-30) view=\"Column Base Plate Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add text at=(500,300) view=\"Column Base Plate Detail\" text=\"400 x 400 x 20 BASE PLATE\" leader_to=(400,10)",
  "op:add text at=(-700,-120) view=\"Column Base Plate Detail\" text=\"30 NON-SHRINK GROUT\" leader_to=(-100,-15)",
  "op:add dimension from=(0,0) to=(400,0) view=\"Column Base Plate Detail\" offset=-400",
  "op:add dimension from=(-300,-300) to=(700,-300) view=\"Column Base Plate Detail\" offset=-150"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Column Base Plate Detail" scale=1:10` | green: op:add drafting view made=29b0ad9da9804d7fa73fa62e5325e7de changed= ms=465 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (400,0) (400,20) (0,20) (0,0) view="Column Base Plate Detail" style="Wide Lines"` | green: op:add detail line made=detail-26213d46f8224adc,detail-8bb2de5f737d4020,detail-45ab95f1297c48c1,detail-da1b8e55afd945f4 changed= ms=4 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(190,20) (210,20) (210,600) (190,600) (190,20) view="Column Base Plate Detail" style="Wide Lines"` | green: op:add detail line made=detail-dffd3075dc164a21,detail-f8a91f41e653472d,detail-3d81b42016244440,detail-2668875904d04507 changed= ms=2 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-100,-30) (500,-30) (500,0) (-100,0) (-100,-30) view="Column Base Plate Detail"` | green: op:add detail line made=detail-acfc0ba4723444c2,detail-e6f98c18bf444b36,detail-5fa65218d11d4675,detail-5b66c2e7a14b4f39 changed= ms=2 Check "Lines +4": Lines 8 -> 12 (+4, expected +4) |
| `op:add detail line points=(-300,-300) (700,-300) (700,-30) (-300,-30) (-300,-300) view="Column Base Plate Detail"` | green: op:add detail line made=detail-eb1a2262b4734154,detail-3ec4a517e5b84fd3,detail-49634086a2b342ab,detail-df843c901d144ee7 changed= ms=2 Check "Lines +4": Lines 12 -> 16 (+4, expected +4) |
| `op:add detail line points=(40,-250) (40,60) (60,60) (60,-250) view="Column Base Plate Detail"` | green: op:add detail line made=detail-eec53ce1b7704ce4,detail-edbd8e404f5946e9,detail-f4ae522dbf6443e9 changed= ms=2 Check "Lines +3": Lines 16 -> 19 (+3, expected +3) |
| `op:add detail line points=(340,-250) (340,60) (360,60) (360,-250) view="Column Base Plate Detail"` | green: op:add detail line made=detail-390b000927ff4f0f,detail-ba07c044af564d4d,detail-a6616d54304b4fb3 changed= ms=2 Check "Lines +3": Lines 19 -> 22 (+3, expected +3) |
| `op:add filled region boundary=(-300,-300) (700,-300) (700,-30) (-300,-30) view="Column Base Plate Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-a2b60397b31d46f0 changed= ms=5 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,300) view="Column Base Plate Detail" text="400 x 400 x 20 BASE PLATE" leader_to=(400,10)` | green: op:add text made=text-9c2a471c3d3b494f changed= ms=2 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(-700,-120) view="Column Base Plate Detail" text="30 NON-SHRINK GROUT" leader_to=(-100,-15)` | green: op:add text made=text-454821bc988e4547 changed= ms=2 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(400,0) view="Column Base Plate Detail" offset=-400` | green: op:add dimension made=dim-322ff8ea40284a18 changed= ms=632 note=offset -400: the dimension line stands 400 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(-300,-300) to=(700,-300) view="Column Base Plate Detail" offset=-150` | green: op:add dimension made=dim-2d9a4d8af548420f changed= ms=327 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Filled Regions 1,Levels 2,Lines 22,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5004. Draw the 1:10 hanger detail for our rectangular ducts: the duct, two threaded rods, the angle bearer and a note on the rod size.

- Starts from: a new Mechanical project
- Ends with: a 1:10 drafting view "Duct Hanger Detail" with the duct section, wrapped lagging, two rods, a bearer angle, two notes and one dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Duct Hanger Detail\" scale=1:10",
  "op:add detail line points=(0,0) (600,0) (600,300) (0,300) (0,0) view=\"Duct Hanger Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-40,-40) (640,-40) (640,340) (-40,340) (-40,-40) view=\"Duct Hanger Detail\"",
  "op:add detail line points=(-60,-60) (-60,-40) (660,-40) (660,-60) (-60,-60) view=\"Duct Hanger Detail\"",
  "op:add detail line points=(-30,-60) (-30,900) view=\"Duct Hanger Detail\"",
  "op:add detail line points=(630,-60) (630,900) view=\"Duct Hanger Detail\"",
  "op:add insulation from=(-20,170) to=(-20,310) view=\"Duct Hanger Detail\" width=40",
  "op:add text at=(900,500) view=\"Duct Hanger Detail\" text=\"M10 GALV. THREADED ROD\" leader_to=(630,500)",
  "op:add text at=(900,-200) view=\"Duct Hanger Detail\" text=\"40 x 40 x 5 GALV. ANGLE BEARER\" leader_to=(400,-50)",
  "op:add dimension from=(0,0) to=(600,0) view=\"Duct Hanger Detail\" offset=-250"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Duct Hanger Detail" scale=1:10` | green: op:add drafting view made=1728d79ebd054ffa88864d582cde181a changed= ms=14 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (600,0) (600,300) (0,300) (0,0) view="Duct Hanger Detail" style="Wide Lines"` | green: op:add detail line made=detail-c24efdbd7bb94d95,detail-770686e97a514621,detail-9006ee8459554390,detail-9b00e14fb2d44c1a changed= ms=2 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(-40,-40) (640,-40) (640,340) (-40,340) (-40,-40) view="Duct Hanger Detail"` | green: op:add detail line made=detail-e742b5bc58834495,detail-39ba5d48e7db4bf3,detail-1f9f44b24e744ec2,detail-269ee73940a1407f changed= ms=2 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-60,-60) (-60,-40) (660,-40) (660,-60) (-60,-60) view="Duct Hanger Detail"` | green: op:add detail line made=detail-9dfb2dba94cb4fd1,detail-5984f5110c0a4db1,detail-8a7bbf0200414948,detail-e7b0d126a0c84daa changed= ms=2 Check "Lines +4": Lines 8 -> 12 (+4, expected +4) |
| `op:add detail line points=(-30,-60) (-30,900) view="Duct Hanger Detail"` | green: op:add detail line made=detail-2225bd135bbd443c changed= ms=2 Check "Lines +1": Lines 12 -> 13 (+1, expected +1) |
| `op:add detail line points=(630,-60) (630,900) view="Duct Hanger Detail"` | green: op:add detail line made=detail-b0e0ecbfb25042ba changed= ms=2 Check "Lines +1": Lines 13 -> 14 (+1, expected +1) |
| `op:add insulation from=(-20,170) to=(-20,310) view="Duct Hanger Detail" width=40` | green: op:add insulation made=insul-4452ea7dce8907d2 changed= ms=2 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) |
| `op:add text at=(900,500) view="Duct Hanger Detail" text="M10 GALV. THREADED ROD" leader_to=(630,500)` | green: op:add text made=text-539df8a617cc4f37 changed= ms=2 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(900,-200) view="Duct Hanger Detail" text="40 x 40 x 5 GALV. ANGLE BEARER" leader_to=(400,-50)` | green: op:add text made=text-e75cb202ca9649f9 changed= ms=2 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(600,0) view="Duct Hanger Detail" offset=-250` | green: op:add dimension made=dim-595b58abffa84750 changed= ms=11 note=offset -250: the dimension line stands 250 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Detail Items 1,Dimensions 1,Levels 2,Lines 14,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5005. Show how a 100 mm pipe passes through a 200 mm slab at 1:10 with a sleeve, fire collar note and the sleeve dimension.

- Starts from: a new Hydraulic project
- Ends with: a 1:10 drafting view "Pipe Through Slab Detail" with the slab outline, sleeve, pipe, concrete hatch, two notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Pipe Through Slab Detail\" scale=1:10",
  "op:add detail line points=(-600,0) (-80,0) (-80,200) (-600,200) (-600,0) view=\"Pipe Through Slab Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(80,0) (600,0) (600,200) (80,200) (80,0) view=\"Pipe Through Slab Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-80,-300) (-80,500) view=\"Pipe Through Slab Detail\"",
  "op:add detail line points=(80,-300) (80,500) view=\"Pipe Through Slab Detail\"",
  "op:add detail line points=(-50,-300) (-50,500) (50,500) (50,-300) view=\"Pipe Through Slab Detail\" style=\"Medium Lines\"",
  "op:add filled region boundary=(-600,0) (-80,0) (-80,200) (-600,200) view=\"Pipe Through Slab Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add filled region boundary=(80,0) (600,0) (600,200) (80,200) view=\"Pipe Through Slab Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add text at=(300,450) view=\"Pipe Through Slab Detail\" text=\"100 UPVC PIPE\" leader_to=(50,400)",
  "op:add text at=(300,-250) view=\"Pipe Through Slab Detail\" text=\"FIRE COLLAR TO SLAB SOFFIT\" leader_to=(80,-100)",
  "op:add dimension from=(-80,200) to=(80,200) view=\"Pipe Through Slab Detail\" offset=-150",
  "op:add dimension from=(600,0) to=(600,200) view=\"Pipe Through Slab Detail\" offset=100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Pipe Through Slab Detail" scale=1:10` | green: op:add drafting view made=f21ae057e10e4a4383e5232bfd1ca69c changed= ms=14 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-600,0) (-80,0) (-80,200) (-600,200) (-600,0) view="Pipe Through Slab Detail" style="Wide Lines"` | green: op:add detail line made=detail-9df45cb8faff4efa,detail-5a53a8522d144eb5,detail-a5e69957bcbe42db,detail-df4afee167834440 changed= ms=2 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(80,0) (600,0) (600,200) (80,200) (80,0) view="Pipe Through Slab Detail" style="Wide Lines"` | green: op:add detail line made=detail-cb16ba4f6e6341e9,detail-844e50f703a34cad,detail-a09fc762944544b5,detail-ef7fdd231e2043e1 changed= ms=2 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-80,-300) (-80,500) view="Pipe Through Slab Detail"` | green: op:add detail line made=detail-f626eebe0ee64641 changed= ms=2 Check "Lines +1": Lines 8 -> 9 (+1, expected +1) |
| `op:add detail line points=(80,-300) (80,500) view="Pipe Through Slab Detail"` | green: op:add detail line made=detail-6a9967d52cf34999 changed= ms=2 Check "Lines +1": Lines 9 -> 10 (+1, expected +1) |
| `op:add detail line points=(-50,-300) (-50,500) (50,500) (50,-300) view="Pipe Through Slab Detail" style="Medium Lines"` | green: op:add detail line made=detail-0e2391ca68254626,detail-7fc8b5df91824293,detail-f19099f724fd4373 changed= ms=3 Check "Lines +3": Lines 10 -> 13 (+3, expected +3) |
| `op:add filled region boundary=(-600,0) (-80,0) (-80,200) (-600,200) view="Pipe Through Slab Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-788e6bb26f104f13 changed= ms=2 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(80,0) (600,0) (600,200) (80,200) view="Pipe Through Slab Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-0e604b38c4e04503 changed= ms=2 Check "Filled Regions +1": Filled Regions 1 -> 2 (+1, expected +1) |
| `op:add text at=(300,450) view="Pipe Through Slab Detail" text="100 UPVC PIPE" leader_to=(50,400)` | green: op:add text made=text-30e7235de8af4af5 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(300,-250) view="Pipe Through Slab Detail" text="FIRE COLLAR TO SLAB SOFFIT" leader_to=(80,-100)` | green: op:add text made=text-74fde71a8dd54dc7 changed= ms=44 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-80,200) to=(80,200) view="Pipe Through Slab Detail" offset=-150` | green: op:add dimension made=dim-556b1e985f964b98 changed= ms=70 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(600,0) to=(600,200) view="Pipe Through Slab Detail" offset=100` | green: op:add dimension made=dim-8f40fc923945426f changed= ms=3 note=offset 100: the dimension line stands 100 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Filled Regions 2,Levels 2,Lines 13,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5006. Please draw the window head detail at 1:5 for a brick veneer wall: lintel, frame, sealant, flashing and notes.

- Starts from: a new Architectural project
- Ends with: a 1:5 drafting view "Window Head Detail" holding the lintel, window frame, brick veneer, flashing line, a blockwork hatch and three notes
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Window Head Detail\" scale=1:5",
  "op:add detail line points=(0,0) (110,0) (110,-300) (0,-300) (0,0) view=\"Window Head Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(150,0) (250,0) (250,-300) (150,-300) (150,0) view=\"Window Head Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-10,-300) (260,-300) (260,-380) (-10,-380) (-10,-300) view=\"Window Head Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(100,-380) (100,-700) (140,-700) (140,-380) view=\"Window Head Detail\"",
  "op:add detail line points=(110,-300) (110,-290) (330,-290) view=\"Window Head Detail\" style=\"Medium Lines\"",
  "op:add filled region boundary=(0,0) (110,0) (110,-300) (0,-300) view=\"Window Head Detail\" pattern=Blockwork",
  "op:add text at=(400,-100) view=\"Window Head Detail\" text=\"90 BRICK VENEER\" leader_to=(40,-100)",
  "op:add text at=(400,-340) view=\"Window Head Detail\" text=\"150 x 90 x 10 ANGLE LINTEL\" leader_to=(260,-340)",
  "op:add text at=(400,-600) view=\"Window Head Detail\" text=\"SEALANT AND BACKING ROD\" leader_to=(120,-540)",
  "op:add dimension from=(-10,-380) to=(-10,-300) view=\"Window Head Detail\" offset=60"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Window Head Detail" scale=1:5` | green: op:add drafting view made=c86c90979a7240359f75330cbef208b3 changed= ms=23 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (110,0) (110,-300) (0,-300) (0,0) view="Window Head Detail" style="Wide Lines"` | green: op:add detail line made=detail-55524332bcda4bf3,detail-a31e97db20154388,detail-233efd75725741f9,detail-2a7a1b8a6890446c changed= ms=4 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(150,0) (250,0) (250,-300) (150,-300) (150,0) view="Window Head Detail" style="Wide Lines"` | green: op:add detail line made=detail-9791a5a8118445d2,detail-fc5f7ad69428428e,detail-31a1e3924fc340ff,detail-dc19d44ae0464590 changed= ms=4 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-10,-300) (260,-300) (260,-380) (-10,-380) (-10,-300) view="Window Head Detail" style="Wide Lines"` | green: op:add detail line made=detail-d27ce35131814571,detail-3e3533e8d2134572,detail-7073510f8248448d,detail-4e4b71bb20884ffa changed= ms=5 Check "Lines +4": Lines 8 -> 12 (+4, expected +4) |
| `op:add detail line points=(100,-380) (100,-700) (140,-700) (140,-380) view="Window Head Detail"` | green: op:add detail line made=detail-48a34a751142416a,detail-3bba1d6ac4ab41fd,detail-1bed18016c4e4ce5 changed= ms=3 Check "Lines +3": Lines 12 -> 15 (+3, expected +3) |
| `op:add detail line points=(110,-300) (110,-290) (330,-290) view="Window Head Detail" style="Medium Lines"` | green: op:add detail line made=detail-1241241a6bfd4c93,detail-19cac4ef6db94de3 changed= ms=3 Check "Lines +2": Lines 15 -> 17 (+2, expected +2) |
| `op:add filled region boundary=(0,0) (110,0) (110,-300) (0,-300) view="Window Head Detail" pattern=Blockwork` | green: op:add filled region made=region-cb9ed34d0c094538 changed= ms=5 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add text at=(400,-100) view="Window Head Detail" text="90 BRICK VENEER" leader_to=(40,-100)` | green: op:add text made=text-78ce6b6a168f42f5 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(400,-340) view="Window Head Detail" text="150 x 90 x 10 ANGLE LINTEL" leader_to=(260,-340)` | green: op:add text made=text-dfd52e00aa924330 changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(400,-600) view="Window Head Detail" text="SEALANT AND BACKING ROD" leader_to=(120,-540)` | green: op:add text made=text-f2352045a2f24a0d changed= ms=3 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add dimension from=(-10,-380) to=(-10,-300) view="Window Head Detail" offset=60` | green: op:add dimension made=dim-2d896c1af8044e9c changed= ms=31 note=offset 60: the dimension line stands 60 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Filled Regions 1,Levels 3,Lines 17,Text Notes 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5007. Draw our cable tray support bracket at 1:10: wall fixing, bracket arm, a 300 mm tray and a note on the anchor.

- Starts from: a new Electrical project
- Ends with: a 1:10 drafting view "Cable Tray Bracket Detail" with the wall edge, bracket, tray section, anchor bolt, notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Cable Tray Bracket Detail\" scale=1:10",
  "op:add detail line points=(0,-400) (0,500) view=\"Cable Tray Bracket Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(0,100) (330,100) (330,60) (0,60) view=\"Cable Tray Bracket Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(30,160) (330,160) (330,100) view=\"Cable Tray Bracket Detail\"",
  "op:add detail line points=(60,160) (60,260) (360,260) (360,160) view=\"Cable Tray Bracket Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(-100,80) (60,80) view=\"Cable Tray Bracket Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(-100,70) (60,70) (60,90) (-100,90) view=\"Cable Tray Bracket Detail\"",
  "op:add text at=(500,350) view=\"Cable Tray Bracket Detail\" text=\"300 x 60 LADDER CABLE TRAY\" leader_to=(360,230)",
  "op:add text at=(-600,-200) view=\"Cable Tray Bracket Detail\" text=\"M10 CHEMICAL ANCHOR 100 EMBED\" leader_to=(-50,80)",
  "op:add dimension from=(0,60) to=(330,60) view=\"Cable Tray Bracket Detail\" offset=-150",
  "op:add dimension from=(360,160) to=(360,260) view=\"Cable Tray Bracket Detail\" offset=-100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Cable Tray Bracket Detail" scale=1:10` | green: op:add drafting view made=0f5758e0cc1f4c4ab38c449c55a8b399 changed= ms=8 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,-400) (0,500) view="Cable Tray Bracket Detail" style="Wide Lines"` | green: op:add detail line made=detail-e53bbbcb3bb64ed2 changed= ms=4 Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,100) (330,100) (330,60) (0,60) view="Cable Tray Bracket Detail" style="Wide Lines"` | green: op:add detail line made=detail-b60a00c61e9040b7,detail-f4284db6e0754f6f,detail-db822153e99343a7 changed= ms=3 Check "Lines +3": Lines 1 -> 4 (+3, expected +3) |
| `op:add detail line points=(30,160) (330,160) (330,100) view="Cable Tray Bracket Detail"` | green: op:add detail line made=detail-d2e9774d56614d92,detail-0fb4bf7b512241e6 changed= ms=4 Check "Lines +2": Lines 4 -> 6 (+2, expected +2) |
| `op:add detail line points=(60,160) (60,260) (360,260) (360,160) view="Cable Tray Bracket Detail" style="Medium Lines"` | green: op:add detail line made=detail-0384d957a3f64b48,detail-9c6319788bbe4e5f,detail-5cf7f2e30cf945f6 changed= ms=3 Check "Lines +3": Lines 6 -> 9 (+3, expected +3) |
| `op:add detail line points=(-100,80) (60,80) view="Cable Tray Bracket Detail" style="Medium Lines"` | green: op:add detail line made=detail-5d682fc7f3714dfe changed= ms=3 Check "Lines +1": Lines 9 -> 10 (+1, expected +1) |
| `op:add detail line points=(-100,70) (60,70) (60,90) (-100,90) view="Cable Tray Bracket Detail"` | green: op:add detail line made=detail-511c2c64539542d2,detail-ac2793429d4a41cd,detail-e1153853b6294415 changed= ms=2 Check "Lines +3": Lines 10 -> 13 (+3, expected +3) |
| `op:add text at=(500,350) view="Cable Tray Bracket Detail" text="300 x 60 LADDER CABLE TRAY" leader_to=(360,230)` | green: op:add text made=text-6639ebf9f5794360 changed= ms=2 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(-600,-200) view="Cable Tray Bracket Detail" text="M10 CHEMICAL ANCHOR 100 EMBED" leader_to=(-50,80)` | green: op:add text made=text-c6fb831dbb3847d2 changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(0,60) to=(330,60) view="Cable Tray Bracket Detail" offset=-150` | green: op:add dimension made=dim-be5ca3e7ad4041dd changed= ms=11 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(360,160) to=(360,260) view="Cable Tray Bracket Detail" offset=-100` | green: op:add dimension made=dim-4494b9cc2f174c60 changed= ms=6 note=offset -100: the dimension line stands 100 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Levels 2,Lines 13,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5008. Detail a pendant sprinkler head through a plasterboard ceiling at 1:5, with the drop pipe, escutcheon and ceiling dimension.

- Starts from: a new Fire Protection project
- Ends with: a 1:5 drafting view "Sprinkler Head Detail" with ceiling lining, pipe, escutcheon, head, hatch, two notes and a dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Sprinkler Head Detail\" scale=1:5",
  "op:add detail line points=(-300,0) (-25,0) (-25,13) (-300,13) (-300,0) view=\"Sprinkler Head Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(25,0) (300,0) (300,13) (25,13) (25,0) view=\"Sprinkler Head Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-10,13) (-10,200) (10,200) (10,13) view=\"Sprinkler Head Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-30,-5) (30,-5) (30,0) (-30,0) (-30,-5) view=\"Sprinkler Head Detail\"",
  "op:add detail line points=(-8,-5) (-8,-45) (8,-45) (8,-5) view=\"Sprinkler Head Detail\"",
  "op:add detail line points=(-20,-45) (20,-45) view=\"Sprinkler Head Detail\" style=\"Medium Lines\"",
  "op:add filled region boundary=(-300,0) (-25,0) (-25,13) (-300,13) view=\"Sprinkler Head Detail\" pattern=\"Solid fill\"",
  "op:add text at=(150,150) view=\"Sprinkler Head Detail\" text=\"DN25 DROP FROM RETICULATION\" leader_to=(10,120)",
  "op:add text at=(120,-120) view=\"Sprinkler Head Detail\" text=\"CHROME PENDANT HEAD, 68 DEG C\" leader_to=(8,-40)",
  "op:add dimension from=(-8,-45) to=(8,-45) view=\"Sprinkler Head Detail\" offset=-40"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Sprinkler Head Detail" scale=1:5` | green: op:add drafting view made=2f69a9b2c6454b01ae38905a64eed5e8 changed= ms=46 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-300,0) (-25,0) (-25,13) (-300,13) (-300,0) view="Sprinkler Head Detail" style="Wide Lines"` | green: op:add detail line made=detail-9a2332241e484ec1,detail-b5bb1885214d4714,detail-58f2ad45ebae4f19,detail-cc480e4ecc5e4b1a changed= ms=3 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(25,0) (300,0) (300,13) (25,13) (25,0) view="Sprinkler Head Detail" style="Wide Lines"` | green: op:add detail line made=detail-de76148a86a74574,detail-0cf466881f234534,detail-25c88d5ab287415d,detail-182a2cc4fc9f4fd8 changed= ms=86 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-10,13) (-10,200) (10,200) (10,13) view="Sprinkler Head Detail" style="Wide Lines"` | green: op:add detail line made=detail-7e8090ae70074a57,detail-c271c3b738d14f2e,detail-eb5dd5a9289444f0 changed= ms=3 Check "Lines +3": Lines 8 -> 11 (+3, expected +3) |
| `op:add detail line points=(-30,-5) (30,-5) (30,0) (-30,0) (-30,-5) view="Sprinkler Head Detail"` | green: op:add detail line made=detail-3f47959cbea34565,detail-62d0c3a707984e3e,detail-f668f64f5ef54027,detail-501462df985d46d3 changed= ms=4 Check "Lines +4": Lines 11 -> 15 (+4, expected +4) |
| `op:add detail line points=(-8,-5) (-8,-45) (8,-45) (8,-5) view="Sprinkler Head Detail"` | green: op:add detail line made=detail-91ffb5b51f744c78,detail-c7fe4c56e0194f1c,detail-4a757d1f92b84b9c changed= ms=2 Check "Lines +3": Lines 15 -> 18 (+3, expected +3) |
| `op:add detail line points=(-20,-45) (20,-45) view="Sprinkler Head Detail" style="Medium Lines"` | green: op:add detail line made=detail-0cf6ed271b204391 changed= ms=4 Check "Lines +1": Lines 18 -> 19 (+1, expected +1) |
| `op:add filled region boundary=(-300,0) (-25,0) (-25,13) (-300,13) view="Sprinkler Head Detail" pattern="Solid fill"` | green: op:add filled region made=region-39966a22c8044d07 changed= ms=2 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add text at=(150,150) view="Sprinkler Head Detail" text="DN25 DROP FROM RETICULATION" leader_to=(10,120)` | green: op:add text made=text-6659d2590c914396 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(120,-120) view="Sprinkler Head Detail" text="CHROME PENDANT HEAD, 68 DEG C" leader_to=(8,-40)` | green: op:add text made=text-1d21f8da85ad40db changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-8,-45) to=(8,-45) view="Sprinkler Head Detail" offset=-40` | green: op:add dimension made=dim-b937c307272e4448 changed= ms=14 note=offset -40: the dimension line stands 40 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Filled Regions 1,Levels 2,Lines 19,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5009. Give me a 1:10 slab edge detail with a rebate for the brick, a drip groove, a rebate hatch and the slab depth noted.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Slab Edge Detail" with the slab outline, brick rebate, drip groove, concrete hatch, bar dots, two notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Slab Edge Detail; Scale=1:10 · expect view: Drafting View +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Slab Edge Detail; Scale=1:10 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 85 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Slab Edge Detail reads 'Slab Edge Detail'; Scale=1:10 reads '1:10' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add detail line points=(0,0) (800,0) (800,250) (200,250) (200,150) (0,150) (0,0) view=\"Slab Edge Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(60,0) (60,-20) (100,-20) (100,0) view=\"Slab Edge Detail\"",
  "op:add filled region boundary=(0,0) (800,0) (800,250) (200,250) (200,150) (0,150) view=\"Slab Edge Detail\" pattern=\"Diagonal crosshatch\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add detail line points=(0,0) (800,0) (800,250) (200,250) (200,150) (0,150) (0,0) view="Slab Edge Detail" style="Wide Lines"` | green: op:add detail line made=detail-ab7d1040faf44575,detail-6bbd86493b9b4328,detail-59453c2cef1a4d71,detail-12b561701e2f4a7c,detail-8c2b6fd7409f41a1,detail-32bf5c5b2ac2478b changed= ms=68 Check "Lines +6": Lines 0 -> 6 (+6, expected +6) |
| `op:add detail line points=(60,0) (60,-20) (100,-20) (100,0) view="Slab Edge Detail"` | green: op:add detail line made=detail-6823ab01c0274258,detail-e6da1a620c714eb6,detail-85ab27dc69854aea changed= ms=141 Check "Lines +3": Lines 6 -> 9 (+3, expected +3) |
| `op:add filled region boundary=(0,0) (800,0) (800,250) (200,250) (200,150) (0,150) view="Slab Edge Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-71e6c392b4ae4b23 changed= ms=51 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Detail Line · picks (100,60) (112,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (300,60) (312,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Detail Line · picks (100,60) (112,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (100,60) mm at px (696.0,398.2) on the Drafting View 'Slab Edge Detail' view \| (112,60) mm at px (701.8,398.2) on the Drafting View 'Slab Edge Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 9 -> 10 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (300,60) (312,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (300,60) mm at px (792.0,398.2) on the Drafting View 'Slab Edge Detail' view \| (312,60) mm at px (797.8,398.2) on the Drafting View 'Slab Edge Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 10 -> 11 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add text at=(1000,300) view=\"Slab Edge Detail\" text=\"250 SLAB, N16 BARS AT 200 CTS\" leader_to=(800,200)",
  "op:add text at=(-500,-150) view=\"Slab Edge Detail\" text=\"DRIP GROOVE 20 x 40\" leader_to=(80,-10)",
  "op:add dimension from=(800,0) to=(800,250) view=\"Slab Edge Detail\" offset=-150",
  "op:add dimension from=(0,0) to=(0,150) view=\"Slab Edge Detail\" offset=200"
]}
```

| Line | UNION answered |
|---|---|
| `op:add text at=(1000,300) view="Slab Edge Detail" text="250 SLAB, N16 BARS AT 200 CTS" leader_to=(800,200)` | green: op:add text made=text-c540964d5bec4e33 changed= ms=275 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(-500,-150) view="Slab Edge Detail" text="DRIP GROOVE 20 x 40" leader_to=(80,-10)` | green: op:add text made=text-d4687ef279ef44ad changed= ms=329 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(800,0) to=(800,250) view="Slab Edge Detail" offset=-150` | green: op:add dimension made=dim-59b5789e14cf4ec4 changed= ms=49 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(0,150) view="Slab Edge Detail" offset=200` | green: op:add dimension made=dim-45796ea1c4da4d0d changed= ms=29 note=offset 200: the dimension line stands 200 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Filled Regions 1,Levels 3,Lines 11,Text Notes 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5010. Detail a 1200 square pad footing at 1:20 with the column stub, bottom bars as dots and a cogged bar, and the pad dimensions.

- Starts from: a new Structural project
- Ends with: a 1:20 drafting view "Pad Footing Detail" holding the pad, column stub, a row of bar sections drawn as circles, a cogged bar, notes and dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Pad Footing Detail; Scale=1:20 · expect view: Drafting View +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Pad Footing Detail; Scale=1:20 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 56 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Pad Footing Detail reads 'Pad Footing Detail'; Scale=1:20 reads '1:20' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add detail line points=(0,0) (1200,0) (1200,400) (0,400) (0,0) view=\"Pad Footing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(450,400) (450,900) (750,900) (750,400) view=\"Pad Footing Detail\" style=\"Wide Lines\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add detail line points=(0,0) (1200,0) (1200,400) (0,400) (0,0) view="Pad Footing Detail" style="Wide Lines"` | green: op:add detail line made=detail-1a2d6cf8a8924e8f,detail-d4b2e911ee24492a,detail-bbffb0f9b1aa4a55,detail-70c0e698d79c470d changed= ms=6 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(450,400) (450,900) (750,900) (750,400) view="Pad Footing Detail" style="Wide Lines"` | green: op:add detail line made=detail-456c41cd12974c8a,detail-e109998dce0a4db6,detail-9b93c878a48948ac changed= ms=10 Check "Lines +3": Lines 4 -> 7 (+3, expected +3) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Detail Line · picks (100,70) (114,70) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (400,70) (414,70) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (800,70) (814,70) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (1100,70) (1114,70) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line › Line · picks (520,420) (520,100) (900,100) · keys Escape Escape · fields — · expect Lines +2"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Detail Line · picks (100,70) (114,70) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (100,70) mm at px (672.0,410.2) on the Drafting View 'Pad Footing Detail' view \| (114,70) mm at px (675.4,410.2) on the Drafting View 'Pad Footing Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 7 -> 8 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (400,70) (414,70) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (400,70) mm at px (744.0,410.2) on the Drafting View 'Pad Footing Detail' view \| (414,70) mm at px (747.4,410.2) on the Drafting View 'Pad Footing Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 8 -> 9 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (800,70) (814,70) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (800,70) mm at px (840.0,410.2) on the Drafting View 'Pad Footing Detail' view \| (814,70) mm at px (843.4,410.2) on the Drafting View 'Pad Footing Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 9 -> 10 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (1100,70) (1114,70) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (1100,70) mm at px (912.0,410.2) on the Drafting View 'Pad Footing Detail' view \| (1114,70) mm at px (915.4,410.2) on the Drafting View 'Pad Footing Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 10 -> 11 (+1, expected +1) |
| `ribbon:Annotate:Detail Line › Line · picks (520,420) (520,100) (900,100) · keys Escape Escape · fields — · expect Lines +2` | green: pressed 'Detail Line › Line' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Line'; the press stood 344 ms (the menu stood at 25 ms; its row ran 318 ms; it made 0 child widgets native)): the command 'Detail Line › Line' ran; status 'Click to start the detail line' \| picks: (520,420) mm at px (772.8,326.2) on the Drafting View 'Pad Footing Detail' view \| (520,100) mm at px (772.8,403.0) on the Drafting View 'Pad Footing Detail' view \| (900,100) mm at px (864.0,403.0) on the Drafting View 'Pad Footing Detail' view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Detail Line -> tool Detail Line, 'Detail Line' still stands (the key went to union_shell::Viewport)); Escape (tool Detail Line -> no tool) Check "Lines +2": Lines 11 -> 13 (+2, expected +2) |

```json
ops_run {"lines":[
  "op:add text at=(1500,200) view=\"Pad Footing Detail\" text=\"N16 BOTH WAYS BOTTOM\" leader_to=(1114,70)",
  "op:add text at=(1100,800) view=\"Pad Footing Detail\" text=\"COLUMN STUB 300 x 500\" leader_to=(750,700)",
  "op:add dimension from=(0,0) to=(1200,0) view=\"Pad Footing Detail\" offset=-250",
  "op:add dimension from=(1200,0) to=(1200,400) view=\"Pad Footing Detail\" offset=-250"
]}
```

| Line | UNION answered |
|---|---|
| `op:add text at=(1500,200) view="Pad Footing Detail" text="N16 BOTH WAYS BOTTOM" leader_to=(1114,70)` | green: op:add text made=text-fd42e83d206b41e1 changed= ms=158 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(1100,800) view="Pad Footing Detail" text="COLUMN STUB 300 x 500" leader_to=(750,700)` | green: op:add text made=text-97116166e71d4d41 changed= ms=55 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(1200,0) view="Pad Footing Detail" offset=-250` | green: op:add dimension made=dim-f421da854dd74ff7 changed= ms=127 note=offset -250: the dimension line stands 250 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(1200,0) to=(1200,400) view="Pad Footing Detail" offset=-250` | green: op:add dimension made=dim-1b44b5e8227f4ac9 changed= ms=315 note=offset -250: the dimension line stands 250 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Levels 2,Lines 13,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5011. Draw the stair nosing at 1:5: tread, riser, a 20 mm nosing projection and an anti-slip strip, with the sizes noted.

- Starts from: a new Architectural project
- Ends with: a 1:5 drafting view "Stair Nosing Detail" with tread, riser, nosing, anti-slip strip, notes and three dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Stair Nosing Detail\" scale=1:5",
  "op:add detail line points=(0,0) (300,0) (300,-35) (0,-35) (0,0) view=\"Stair Nosing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(20,-35) (20,-190) (0,-190) view=\"Stair Nosing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-20,-35) (-20,0) view=\"Stair Nosing Detail\"",
  "op:add detail line points=(-20,0) (-20,-35) (0,-35) view=\"Stair Nosing Detail\"",
  "op:add detail line points=(-20,3) (60,3) (60,6) (-20,6) (-20,3) view=\"Stair Nosing Detail\" style=\"Medium Lines\"",
  "op:add text at=(200,150) view=\"Stair Nosing Detail\" text=\"35 TIMBER TREAD\" leader_to=(150,-17)",
  "op:add text at=(200,50) view=\"Stair Nosing Detail\" text=\"ANTI-SLIP INSERT\" leader_to=(20,5)",
  "op:add dimension from=(0,0) to=(300,0) view=\"Stair Nosing Detail\" offset=-60",
  "op:add dimension from=(0,-35) to=(0,-190) view=\"Stair Nosing Detail\" offset=60"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Stair Nosing Detail" scale=1:5` | green: op:add drafting view made=21997d7c462146e2b08ecfa2b7c9b491 changed= ms=69 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (300,0) (300,-35) (0,-35) (0,0) view="Stair Nosing Detail" style="Wide Lines"` | green: op:add detail line made=detail-60b982d4f4f54ebf,detail-0f81a2fea180417e,detail-6e538e450b724331,detail-89245f1f82ea4e58 changed= ms=4 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(20,-35) (20,-190) (0,-190) view="Stair Nosing Detail" style="Wide Lines"` | green: op:add detail line made=detail-c3ec81511dc24aaa,detail-c933884b944845ae changed= ms=4 Check "Lines +2": Lines 4 -> 6 (+2, expected +2) |
| `op:add detail line points=(-20,-35) (-20,0) view="Stair Nosing Detail"` | green: op:add detail line made=detail-464dcf4cc41849d6 changed= ms=4 Check "Lines +1": Lines 6 -> 7 (+1, expected +1) |
| `op:add detail line points=(-20,0) (-20,-35) (0,-35) view="Stair Nosing Detail"` | green: op:add detail line made=detail-894a868819204791,detail-c5fc80d045774e9f changed= ms=3 Check "Lines +2": Lines 7 -> 9 (+2, expected +2) |
| `op:add detail line points=(-20,3) (60,3) (60,6) (-20,6) (-20,3) view="Stair Nosing Detail" style="Medium Lines"` | green: op:add detail line made=detail-c97a22092f6f4ae6,detail-fb4037e53b7a49e6,detail-b39457028dc44d9a,detail-c9e66a5d994b424b changed= ms=4 Check "Lines +4": Lines 9 -> 13 (+4, expected +4) |
| `op:add text at=(200,150) view="Stair Nosing Detail" text="35 TIMBER TREAD" leader_to=(150,-17)` | green: op:add text made=text-b384101f323448aa changed= ms=2 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(200,50) view="Stair Nosing Detail" text="ANTI-SLIP INSERT" leader_to=(20,5)` | green: op:add text made=text-cec8a57f523c4822 changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(300,0) view="Stair Nosing Detail" offset=-60` | green: op:add dimension made=dim-5ab6bd42ada4444c changed= ms=135 note=offset -60: the dimension line stands 60 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(0,-35) to=(0,-190) view="Stair Nosing Detail" offset=60` | green: op:add dimension made=dim-4f8219fa4b704e87 changed= ms=7 note=offset 60: the dimension line stands 60 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Levels 3,Lines 13,Text Notes 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5012. Detail a flat roof parapet at 1:10: concrete upstand, membrane turned up, capping, insulation and the heights noted.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Parapet Detail" with the upstand, roof slab, capping, membrane line, insulation, hatch, three notes and one dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Parapet Detail\" scale=1:10",
  "op:add detail line points=(0,0) (900,0) (900,200) (200,200) (200,600) (0,600) (0,0) view=\"Parapet Detail\" style=\"Wide Lines\"",
  "op:add filled region boundary=(0,0) (900,0) (900,200) (200,200) (200,600) (0,600) view=\"Parapet Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add insulation from=(900,220) to=(260,220) view=\"Parapet Detail\" width=100",
  "op:add detail line points=(900,205) (210,205) (210,610) (260,610) view=\"Parapet Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(-30,600) (230,600) (230,650) (-30,650) (-30,600) view=\"Parapet Detail\"",
  "op:add text at=(500,800) view=\"Parapet Detail\" text=\"COLORBOND CAPPING OVER PARAPET\" leader_to=(100,650)",
  "op:add text at=(800,450) view=\"Parapet Detail\" text=\"SHEET MEMBRANE TURNED UP 150 ABOVE ROOF\" leader_to=(215,420)",
  "op:add text at=(800,-250) view=\"Parapet Detail\" text=\"100 RIGID INSULATION\" leader_to=(600,260)",
  "op:add dimension from=(0,0) to=(0,600) view=\"Parapet Detail\" offset=150"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Parapet Detail" scale=1:10` | green: op:add drafting view made=fb59de376d0e4628b4a91e8c662e0f6e changed= ms=24 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (900,0) (900,200) (200,200) (200,600) (0,600) (0,0) view="Parapet Detail" style="Wide Lines"` | green: op:add detail line made=detail-b93d9eca5fe6488e,detail-17bede3954e94f6e,detail-a62eee2780ec4809,detail-918066927d7e41d1,detail-b28ce0793a234e06,detail-1e35577122854007 changed= ms=5 Check "Lines +6": Lines 0 -> 6 (+6, expected +6) |
| `op:add filled region boundary=(0,0) (900,0) (900,200) (200,200) (200,600) (0,600) view="Parapet Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-31b7bb382785417e changed= ms=5 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add insulation from=(900,220) to=(260,220) view="Parapet Detail" width=100` | green: op:add insulation made=insul-ac71161de7e03723 changed= ms=3 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(900,205) (210,205) (210,610) (260,610) view="Parapet Detail" style="Medium Lines"` | green: op:add detail line made=detail-0d7927f8385e4a96,detail-b34bf34b690646db,detail-5c027f22fd674b54 changed= ms=2 Check "Lines +3": Lines 6 -> 9 (+3, expected +3) |
| `op:add detail line points=(-30,600) (230,600) (230,650) (-30,650) (-30,600) view="Parapet Detail"` | green: op:add detail line made=detail-46723a4390154f2a,detail-f3a308e15012406a,detail-706ef68cf0364abf,detail-8db636be4ffc42ef changed= ms=3 Check "Lines +4": Lines 9 -> 13 (+4, expected +4) |
| `op:add text at=(500,800) view="Parapet Detail" text="COLORBOND CAPPING OVER PARAPET" leader_to=(100,650)` | green: op:add text made=text-256c9ce171ba4910 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(800,450) view="Parapet Detail" text="SHEET MEMBRANE TURNED UP 150 ABOVE ROOF" leader_to=(215,420)` | green: op:add text made=text-471ced93ca484f3a changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(800,-250) view="Parapet Detail" text="100 RIGID INSULATION" leader_to=(600,260)` | green: op:add text made=text-35cd85a06ff9487e changed= ms=2 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(0,600) view="Parapet Detail" offset=150` | green: op:add dimension made=dim-b929ef84e06c4d1b changed= ms=26 note=offset 150: the dimension line stands 150 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Detail Items 1,Dimensions 1,Filled Regions 1,Levels 3,Lines 13,Text Notes 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5013. Dimension the outside of our 6 by 4 m site office: both long walls and both short walls.

- Starts from: a new Architectural project
- Ends with: four walls on Ground with four aligned dimensions outside them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-20a9405db739e6dd changed= ms=19 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-ad87ad53570217b7 changed=wall-20a9405db739e6dd ms=35 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-525b6af70b31d71b changed=wall-ad87ad53570217b7 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-67150b1a28a60cb7 changed=wall-525b6af70b31d71b,wall-20a9405db739e6dd ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Aligned · picks (0,0) (6000,0) (3000,-800) · keys Escape Escape · fields — · expect Dimensions +1",
  "ribbon:Annotate:Aligned · picks (6000,0) (6000,4000) (6800,2000) · keys Escape Escape · fields — · expect Dimensions +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Aligned · picks (0,0) (6000,0) (3000,-800) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Aligned' on Annotate's Dimension panel: the tool 'Aligned' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (6000,0) mm at px (824.0,427.0) on the plan view \| (3000,-800) mm at px (736.0,450.5) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Aligned -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Aligned · picks (6000,0) (6000,4000) (6800,2000) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Aligned' on Annotate's Dimension panel: the tool 'Aligned' stands \| picks: (6000,0) mm at px (824.0,427.0) on the plan view \| (6000,4000) mm at px (824.0,309.7) on the plan view \| (6800,2000) mm at px (847.5,368.3) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Aligned -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add dimension from=(0,4000) to=(6000,4000) view=48660e38a721430d899d5d8a96df3bec offset=800",
  "op:add dimension from=(0,0) to=(0,4000) view=48660e38a721430d899d5d8a96df3bec offset=800"
]}
```

| Line | UNION answered |
|---|---|
| `op:add dimension from=(0,4000) to=(6000,4000) view=48660e38a721430d899d5d8a96df3bec offset=800` | green: op:add dimension made=dim-a500166393c54c96 changed= ms=18 note=offset 800: the dimension line stands 800 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 2 -> 3 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(0,4000) view=48660e38a721430d899d5d8a96df3bec offset=800` | green: op:add dimension made=dim-69f8b43f89fb4b01 changed= ms=276 note=offset 800: the dimension line stands 800 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 3 -> 4 (+1, expected +1) |

### The result

The model holds: Dimensions 4,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5014. Set out three grids each way at 8 m and put a dimension string along each direction.

- Starts from: a new Architectural project
- Ends with: grids A, B, C and 1, 2, 3 on Ground with a dimension chain along grids A to C and another along 1 to 3
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,18000) name=A",
  "op:add grid from=(8000,-2000) to=(8000,18000) name=B",
  "op:add grid from=(16000,-2000) to=(16000,18000) name=C",
  "op:add grid from=(-2000,0) to=(18000,0) name=1",
  "op:add grid from=(-2000,8000) to=(18000,8000) name=2",
  "op:add grid from=(-2000,16000) to=(18000,16000) name=3",
  "op:add dimension chain points=(0,-1000) (8000,-1000) (16000,-1000) view=48660e38a721430d899d5d8a96df3bec offset=-3000",
  "op:add dimension chain points=(-1000,0) (-1000,8000) (-1000,16000) view=48660e38a721430d899d5d8a96df3bec offset=-3000"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,18000) name=A` | green: op:add grid made=grid-A changed= ms=35 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(8000,-2000) to=(8000,18000) name=B` | green: op:add grid made=grid-B changed= ms=3 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(16000,-2000) to=(16000,18000) name=C` | green: op:add grid made=grid-C changed= ms=3 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add grid from=(-2000,0) to=(18000,0) name=1` | green: op:add grid made=grid-1 changed= ms=3 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:add grid from=(-2000,8000) to=(18000,8000) name=2` | green: op:add grid made=grid-2 changed= ms=3 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |
| `op:add grid from=(-2000,16000) to=(18000,16000) name=3` | green: op:add grid made=grid-3 changed= ms=3 Check "Grids +1": Grids 5 -> 6 (+1, expected +1) |
| `op:add dimension chain points=(0,-1000) (8000,-1000) (16000,-1000) view=48660e38a721430d899d5d8a96df3bec offset=-3000` | green: op:add dimension chain made=dimstr-c641b36cc9284c3e changed= ms=2414 note=segments 8000, 8000; offset -3000: the dimension line stands 3000 mm to the right of the direction from the first point to the last (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension chain points=(-1000,0) (-1000,8000) (-1000,16000) view=48660e38a721430d899d5d8a96df3bec offset=-3000` | green: op:add dimension chain made=dimstr-87bbcca3aeef4f7f changed= ms=96 note=segments 8000, 8000; offset -3000: the dimension line stands 3000 mm to the right of the direction from the first point to the last (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Grids 6,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5015. Put two doors in the site office and tag both of them.

- Starts from: a new Architectural project
- Ends with: a four-wall office on Ground with two doors, each carrying a door tag
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-c7e781f6e69893d5 changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-bac82ec38ff3444a changed=wall-c7e781f6e69893d5 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-a5b8d59e16a3ea58 changed=wall-bac82ec38ff3444a ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-175b64ff7138b52e changed=wall-a5b8d59e16a3ea58,wall-c7e781f6e69893d5 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Door · picks (6000,2000) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Annotate:Tag by Category · picks (2000,0) · keys Escape Escape · fields — · expect Tags +1",
  "ribbon:Annotate:Tag by Category · picks (6000,2000) · keys Escape Escape · fields — · expect Tags +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (2000,0) mm at px (706.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (6000,2000) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (6000,2000) mm at px (824.0,368.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |
| `ribbon:Annotate:Tag by Category · picks (2000,0) · keys Escape Escape · fields — · expect Tags +1` | green: pressed 'Tag by Category' on Annotate's Tag panel (through its fold): the tool 'Tag by Category' stands \| picks: (2000,0) mm at px (706.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Tag by Category -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Tags +1": Tags 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Tag by Category · picks (6000,2000) · keys Escape Escape · fields — · expect Tags +1` | green: pressed 'Tag by Category' on Annotate's Tag panel (through its fold): the tool 'Tag by Category' stands \| picks: (6000,2000) mm at px (824.0,368.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Tag by Category -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Tags +1": Tags 1 -> 2 (+1, expected +1) |

### The result

The model holds: Doors 2,Doors Tags 2,Levels 3,Openings 2,Tags 2,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5016. Make the 6 by 4 m office a named room, "Office 101", and tag it.

- Starts from: a new Architectural project
- Ends with: a closed four-wall office with one room named Office, number 101, and a room tag
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(20000,20000) to=(26000,20000) level=Ground",
  "op:add wall from=(26000,20000) to=(26000,24000) level=Ground",
  "op:add wall from=(26000,24000) to=(20000,24000) level=Ground",
  "op:add wall from=(20000,24000) to=(20000,20000) level=Ground",
  "op:add room at=(23000,22000) level=Ground name=Office number=101"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(20000,20000) to=(26000,20000) level=Ground` | green: op:add wall made=wall-77cc3029f2372efe changed= ms=35 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(26000,20000) to=(26000,24000) level=Ground` | green: op:add wall made=wall-32dba5846334bc27 changed=wall-77cc3029f2372efe ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(26000,24000) to=(20000,24000) level=Ground` | green: op:add wall made=wall-d145f67293be846f changed=wall-32dba5846334bc27 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(20000,24000) to=(20000,20000) level=Ground` | green: op:add wall made=wall-44fb814d745de18f changed=wall-77cc3029f2372efe,wall-d145f67293be846f ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add room at=(23000,22000) level=Ground name=Office number=101` | green: op:add room made=room-4291b2fcab158388 changed= ms=15 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Room Tag · picks (23000,22000) · keys Escape Escape · fields — · expect Rooms Tags +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Room Tag · picks (23000,22000) · keys Escape Escape · fields — · expect Rooms Tags +1` | green: pressed 'Room Tag' on Architecture's Room & Area panel (through its fold): the tool 'Room Tag' stands \| picks: (23000,22000) mm at px (1000.1,73.8) on the plan view \| presses to the tool 1, selection changed \| keys: Escape (tool Room Tag -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Rooms Tags +1": Rooms Tags 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Rooms 1,Rooms Tags 1,Tags 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5017. Put a north arrow and a scale bar beside the building on the Ground plan.

- Starts from: a new Architectural project
- Ends with: a building outline on Ground with a north arrow and a scale bar placed to its right
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground",
  "op:add wall from=(12000,0) to=(12000,8000) level=Ground",
  "op:add wall from=(12000,8000) to=(0,8000) level=Ground",
  "op:add wall from=(0,8000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground` | green: op:add wall made=wall-57d7ad7e9834b44a changed= ms=14 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,8000) level=Ground` | green: op:add wall made=wall-a8b896ef516e46ce changed=wall-57d7ad7e9834b44a ms=76 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(0,8000) level=Ground` | green: op:add wall made=wall-b58251d83ebd972b changed=wall-a8b896ef516e46ce ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground` | green: op:add wall made=wall-eabbb312046be7ec changed=wall-57d7ad7e9834b44a,wall-b58251d83ebd972b ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Symbol · picks (15000,6000) · keys Escape Escape · fields Options Strip: Symbol=North Arrow · expect Symbol +1",
  "ribbon:Annotate:Symbol · picks (14000,1000) · keys Escape Escape · fields Options Strip: Symbol=Scale Bar · expect Symbol +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Symbol · picks (15000,6000) · keys Escape Escape · fields Options Strip: Symbol=North Arrow · expect Symbol +1` | green: pressed 'Symbol' on Annotate's Symbol panel (through its fold): the tool 'Symbol' stands \| fields: Symbol=North Arrow reads 'North Arrow' \| picks: (15000,6000) mm at px (1088.0,251.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Symbol -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Symbol +1": Symbol 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Symbol · picks (14000,1000) · keys Escape Escape · fields Options Strip: Symbol=Scale Bar · expect Symbol +1` | green: pressed 'Symbol' on Annotate's Symbol panel (through its fold): the tool 'Symbol' stands \| fields: Symbol=Scale Bar reads 'Scale Bar' \| picks: (14000,1000) mm at px (1058.7,397.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Symbol -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Symbol +1": Symbol 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add symbol at=(15000,3000) view=48660e38a721430d899d5d8a96df3bec rotation=15"
]}
```

| Line | UNION answered |
|---|---|
| `op:add symbol at=(15000,3000) view=48660e38a721430d899d5d8a96df3bec rotation=15` | green: op:add symbol made=symbol-8f2841a01fca4c0e changed= ms=4 Check "Symbol +1": Symbol 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 3,Symbol 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5018. Mark spot elevations on the north and south walls of the plant room.

- Starts from: a new Architectural project
- Ends with: a four-wall plant room on Ground with a spot elevation on its south wall and one on its north wall
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(20000,20000) to=(26000,20000) level=Ground",
  "op:add wall from=(26000,20000) to=(26000,24000) level=Ground",
  "op:add wall from=(26000,24000) to=(20000,24000) level=Ground",
  "op:add wall from=(20000,24000) to=(20000,20000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(20000,20000) to=(26000,20000) level=Ground` | green: op:add wall made=wall-45127968a80292d4 changed= ms=22 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(26000,20000) to=(26000,24000) level=Ground` | green: op:add wall made=wall-94cebaa5d87d424b changed=wall-45127968a80292d4 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(26000,24000) to=(20000,24000) level=Ground` | green: op:add wall made=wall-ebaac5a20b6ccc2e changed=wall-94cebaa5d87d424b ms=5 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(20000,24000) to=(20000,20000) level=Ground` | green: op:add wall made=wall-f25ae49bcbfe0fb5 changed=wall-45127968a80292d4,wall-ebaac5a20b6ccc2e ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Spot Elevation · picks (23000,20000) · keys Escape Escape · fields — · expect Spot Elevations +1",
  "ribbon:Annotate:Spot Elevation · picks (23000,24000) · keys Escape Escape · fields — · expect Spot Elevations +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Spot Elevation · picks (23000,20000) · keys Escape Escape · fields — · expect Spot Elevations +1` | green: pressed 'Spot Elevation' on Annotate's Dimension panel: the tool 'Spot Elevation' stands \| picks: (23000,20000) lay outside the view: panned to bring it to px (648.0,445.0); (23000,20000) mm at px (648.0,445.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Spot Elevation -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Spot Elevations +1": Spot Elevations 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Spot Elevation · picks (23000,24000) · keys Escape Escape · fields — · expect Spot Elevations +1` | green: pressed 'Spot Elevation' on Annotate's Dimension panel: the tool 'Spot Elevation' stands \| picks: (23000,24000) mm at px (648.0,327.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Spot Elevation -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Spot Elevations +1": Spot Elevations 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Spot Elevations 2,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5019. Tag the material on the east and west walls of the store.

- Starts from: a new Architectural project
- Ends with: a four-wall store on Ground with a material tag on its east wall and one on its west wall
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(20000,20000) to=(26000,20000) level=Ground",
  "op:add wall from=(26000,20000) to=(26000,24000) level=Ground",
  "op:add wall from=(26000,24000) to=(20000,24000) level=Ground",
  "op:add wall from=(20000,24000) to=(20000,20000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(20000,20000) to=(26000,20000) level=Ground` | green: op:add wall made=wall-25f45dfe579730f9 changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(26000,20000) to=(26000,24000) level=Ground` | green: op:add wall made=wall-e94806c7338ab4f0 changed=wall-25f45dfe579730f9 ms=26 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(26000,24000) to=(20000,24000) level=Ground` | green: op:add wall made=wall-c3215fd0a52741f5 changed=wall-e94806c7338ab4f0 ms=5 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(20000,24000) to=(20000,20000) level=Ground` | green: op:add wall made=wall-ee5cd2ec42477edf changed=wall-25f45dfe579730f9,wall-c3215fd0a52741f5 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Material Tag · picks (26000,22000) · keys Escape Escape · fields — · expect Walls Tags +1",
  "ribbon:Annotate:Material Tag · picks (20000,22000) · keys Escape Escape · fields — · expect Walls Tags +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Material Tag · picks (26000,22000) · keys Escape Escape · fields — · expect Walls Tags +1` | green: pressed 'Material Tag' on Annotate's Tag panel (through its fold): the tool 'Material Tag' stands \| picks: (26000,22000) mm at px (1062.3,75.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Material Tag -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Walls Tags +1": Walls Tags 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Material Tag · picks (20000,22000) · keys Escape Escape · fields — · expect Walls Tags +1` | green: pressed 'Material Tag' on Annotate's Tag panel (through its fold): the tool 'Material Tag' stands \| picks: (20000,22000) mm at px (936.1,75.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Material Tag -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Walls Tags +1": Walls Tags 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Tags 2,Walls 4,Walls Tags 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5020. Add a note with a leader to the east wall of the workshop that reads "FIRE WALL".

- Starts from: a new Architectural project
- Ends with: a four-wall workshop on Ground with the text note FIRE WALL and a leader pointing at its east wall
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(20000,20000) to=(26000,20000) level=Ground",
  "op:add wall from=(26000,20000) to=(26000,24000) level=Ground",
  "op:add wall from=(26000,24000) to=(20000,24000) level=Ground",
  "op:add wall from=(20000,24000) to=(20000,20000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(20000,20000) to=(26000,20000) level=Ground` | green: op:add wall made=wall-21acc0dfe69c8376 changed= ms=17 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(26000,20000) to=(26000,24000) level=Ground` | green: op:add wall made=wall-0619c5a18584f3f4 changed=wall-21acc0dfe69c8376 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(26000,24000) to=(20000,24000) level=Ground` | green: op:add wall made=wall-ea7ae64cef313aae changed=wall-0619c5a18584f3f4 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(20000,24000) to=(20000,20000) level=Ground` | green: op:add wall made=wall-3db24d46364f5c3b changed=wall-21acc0dfe69c8376,wall-ea7ae64cef313aae ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Text · picks (26000,22000) (28000,22000) · keys F I R E Space W A L L Return Escape · fields Options Strip: Leader=on · expect Text Notes +1",
  "ribbon:Annotate:Text · picks (22000,22000) · keys W O R K S H O P Return Escape · fields Options Strip: Leader=off · expect Text Notes +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Text · picks (26000,22000) (28000,22000) · keys F I R E Space W A L L Return Escape · fields Options Strip: Leader=on · expect Text Notes +1` | green: pressed 'Text' on Annotate's Text panel (through its fold): the tool 'Text' stands \| fields: Leader=on reads yes \| picks: (26000,22000) mm at px (1063.4,73.8) on the plan view \| (28000,22000) mm at px (1105.6,73.8) on the plan view \| presses to the tool 2, selection unchanged \| keys: F delivered to QLineEdit (taken); I delivered to QLineEdit (taken); R delivered to QLineEdit (taken); E delivered to QLineEdit (taken); Space delivered to QLineEdit (taken); W delivered to QLineEdit (taken); A delivered to QLineEdit (taken); L delivered to QLineEdit (taken); L delivered to QLineEdit (taken); Return (tool Text -> tool Text, the edit field took it and closed); Escape (tool Text -> no tool) Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Text · picks (22000,22000) · keys W O R K S H O P Return Escape · fields Options Strip: Leader=off · expect Text Notes +1` | green: pressed 'Text' on Annotate's Text panel (through its fold): the tool 'Text' stands \| fields: Leader=off reads no \| picks: (22000,22000) mm at px (979.0,73.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: W delivered to QLineEdit (taken); O delivered to QLineEdit (taken); R delivered to QLineEdit (taken); K delivered to QLineEdit (taken); S delivered to QLineEdit (taken); H delivered to QLineEdit (taken); O delivered to QLineEdit (taken); P delivered to QLineEdit (taken); Return (tool Text -> tool Text, the edit field took it and closed); Escape (tool Text -> no tool) Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Text Notes 2,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5021. Write our six standard architectural general notes into a drafting view so I can put it on a sheet.

- Starts from: a new Architectural project
- Ends with: a drafting view "General Notes" at 1:1 holding a heading and six numbered notes
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"General Notes\" scale=1:1",
  "op:add text at=(0,0) view=\"General Notes\" text=\"GENERAL NOTES\" type=\"5mm Arial Bold\"",
  "op:add text at=(0,-12) view=\"General Notes\" text=\"1. All dimensions are in millimetres.\"",
  "op:add text at=(0,-20) view=\"General Notes\" text=\"2. Do not scale from drawings.\"",
  "op:add text at=(0,-28) view=\"General Notes\" text=\"3. Verify all dimensions on site before ordering.\"",
  "op:add text at=(0,-36) view=\"General Notes\" text=\"4. All work to comply with the National Construction Code.\"",
  "op:add text at=(0,-44) view=\"General Notes\" text=\"5. Levels are in metres to Australian Height Datum.\"",
  "op:add text at=(0,-52) view=\"General Notes\" text=\"6. Refer to the structural drawings for all concrete and steel.\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="General Notes" scale=1:1` | green: op:add drafting view made=0db0eb8cc2cd4679900801405b322ddb changed= ms=19 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,0) view="General Notes" text="GENERAL NOTES" type="5mm Arial Bold"` | green: op:add text made=text-afa395478caa4c84 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-12) view="General Notes" text="1. All dimensions are in millimetres."` | green: op:add text made=text-aea66d14bf394fc4 changed= ms=4 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(0,-20) view="General Notes" text="2. Do not scale from drawings."` | green: op:add text made=text-00f00629c49b4ba2 changed= ms=4 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add text at=(0,-28) view="General Notes" text="3. Verify all dimensions on site before ordering."` | green: op:add text made=text-1c5d7aa66ad2447b changed= ms=6 Check "Text Notes +1": Text Notes 3 -> 4 (+1, expected +1) |
| `op:add text at=(0,-36) view="General Notes" text="4. All work to comply with the National Construction Code."` | green: op:add text made=text-afa09a9ad12e47a7 changed= ms=5 Check "Text Notes +1": Text Notes 4 -> 5 (+1, expected +1) |
| `op:add text at=(0,-44) view="General Notes" text="5. Levels are in metres to Australian Height Datum."` | green: op:add text made=text-5493ccb7c81449e3 changed= ms=4 Check "Text Notes +1": Text Notes 5 -> 6 (+1, expected +1) |
| `op:add text at=(0,-52) view="General Notes" text="6. Refer to the structural drawings for all concrete and steel."` | green: op:add text made=text-5b8a691be2c7413c changed= ms=4 Check "Text Notes +1": Text Notes 6 -> 7 (+1, expected +1) |

### The result

The model holds: Levels 3,Text Notes 7,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5022. Make a structural notes view with a heading, concrete and steel notes in the small text type, and one long note that wraps.

- Starts from: a new Structural project
- Ends with: a drafting view "Structural Notes" at 1:1 with a bold heading, four notes in 2.5 mm text and one wrapped note
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Structural Notes\" scale=1:1",
  "op:add text at=(0,0) view=\"Structural Notes\" text=\"STRUCTURAL NOTES\" type=\"5mm Arial Bold\"",
  "op:add text at=(0,-12) view=\"Structural Notes\" text=\"1. Concrete grade N32 U.N.O.\" type=\"2.5mm Arial\"",
  "op:add text at=(0,-18) view=\"Structural Notes\" text=\"2. Reinforcement is 500N bar. Cover 40 mm U.N.O.\" type=\"2.5mm Arial\"",
  "op:add text at=(0,-24) view=\"Structural Notes\" text=\"3. Structural steel to AS/NZS 3678 Grade 250.\" type=\"2.5mm Arial\"",
  "op:add text at=(0,-30) view=\"Structural Notes\" text=\"4. Bolts are 8.8/S unless noted otherwise.\" type=\"2.5mm Arial\"",
  "op:add text at=(0,-40) view=\"Structural Notes\" text=\"5. All footings to bear on natural ground of at least 100 kPa allowable bearing pressure confirmed by the geotechnical engineer before pouring.\" type=\"2.5mm Arial\" width=120"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Structural Notes" scale=1:1` | green: op:add drafting view made=8f31771cbc954dbbae7046426b65107d changed= ms=22 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,0) view="Structural Notes" text="STRUCTURAL NOTES" type="5mm Arial Bold"` | green: op:add text made=text-a96ffe046d23428e changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-12) view="Structural Notes" text="1. Concrete grade N32 U.N.O." type="2.5mm Arial"` | green: op:add text made=text-f00dcedee7554db4 changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(0,-18) view="Structural Notes" text="2. Reinforcement is 500N bar. Cover 40 mm U.N.O." type="2.5mm Arial"` | green: op:add text made=text-217c05b2487b437a changed= ms=4 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add text at=(0,-24) view="Structural Notes" text="3. Structural steel to AS/NZS 3678 Grade 250." type="2.5mm Arial"` | green: op:add text made=text-3003ef67230e4861 changed= ms=4 Check "Text Notes +1": Text Notes 3 -> 4 (+1, expected +1) |
| `op:add text at=(0,-30) view="Structural Notes" text="4. Bolts are 8.8/S unless noted otherwise." type="2.5mm Arial"` | green: op:add text made=text-7275c0301dbb4d10 changed= ms=4 Check "Text Notes +1": Text Notes 4 -> 5 (+1, expected +1) |
| `op:add text at=(0,-40) view="Structural Notes" text="5. All footings to bear on natural ground of at least 100 kPa allowable bearing pressure confirmed by the geotechnical engineer before pouring." type="2.5mm Arial" width=120` | green: op:add text made=text-460e98d49e4c473a changed= ms=3 Check "Text Notes +1": Text Notes 5 -> 6 (+1, expected +1) |

### The result

The model holds: Levels 2,Text Notes 6,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5023. List our mechanical abbreviations in a drafting view: SA, RA, EA, FCU and VAV, each with its meaning.

- Starts from: a new Mechanical project
- Ends with: a drafting view "Mechanical Abbreviations" holding a bold heading and five abbreviation lines
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Mechanical Abbreviations\" scale=1:1",
  "op:add text at=(0,0) view=\"Mechanical Abbreviations\" text=\"ABBREVIATIONS\" type=\"5mm Arial Bold\"",
  "op:add text at=(0,-12) view=\"Mechanical Abbreviations\" text=\"SA   SUPPLY AIR\"",
  "op:add text at=(0,-20) view=\"Mechanical Abbreviations\" text=\"RA   RETURN AIR\"",
  "op:add text at=(0,-28) view=\"Mechanical Abbreviations\" text=\"EA   EXHAUST AIR\"",
  "op:add text at=(0,-36) view=\"Mechanical Abbreviations\" text=\"FCU  FAN COIL UNIT\"",
  "op:add text at=(0,-44) view=\"Mechanical Abbreviations\" text=\"VAV  VARIABLE AIR VOLUME BOX\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Mechanical Abbreviations" scale=1:1` | green: op:add drafting view made=8026bb01f3b540bd949de05af34af984 changed= ms=82 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,0) view="Mechanical Abbreviations" text="ABBREVIATIONS" type="5mm Arial Bold"` | green: op:add text made=text-24b39a6847f343b7 changed= ms=5 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-12) view="Mechanical Abbreviations" text="SA   SUPPLY AIR"` | green: op:add text made=text-edc28cda5f5a4cae changed= ms=4 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(0,-20) view="Mechanical Abbreviations" text="RA   RETURN AIR"` | green: op:add text made=text-7ee079d325b14e80 changed= ms=4 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add text at=(0,-28) view="Mechanical Abbreviations" text="EA   EXHAUST AIR"` | green: op:add text made=text-cb6fb18ea489421e changed= ms=4 Check "Text Notes +1": Text Notes 3 -> 4 (+1, expected +1) |
| `op:add text at=(0,-36) view="Mechanical Abbreviations" text="FCU  FAN COIL UNIT"` | green: op:add text made=text-289a24cadfcc494e changed= ms=4 Check "Text Notes +1": Text Notes 4 -> 5 (+1, expected +1) |
| `op:add text at=(0,-44) view="Mechanical Abbreviations" text="VAV  VARIABLE AIR VOLUME BOX"` | green: op:add text made=text-dd60b2ed118f4bf2 changed= ms=6 Check "Text Notes +1": Text Notes 5 -> 6 (+1, expected +1) |

### The result

The model holds: Levels 2,Text Notes 6,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5024. Draw a 100 mm pipe and a 50 mm riser in section at 1:5 and give each a diameter or radius dimension.

- Starts from: a new Hydraulic project
- Ends with: a 1:5 drafting view "Pipe Sizes Detail" with two circles and a diameter dimension on one and a radius dimension on the other
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Pipe Sizes Detail; Scale=1:5 · expect view: Drafting View +1",
  "ribbon:Annotate:Detail Line · picks (0,0) (50,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (300,0) (325,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Diameter · picks (50,0) (120,60) · keys Escape Escape · fields — · expect Dimensions +1",
  "ribbon:Annotate:Radial · picks (325,0) (400,50) · keys Escape Escape · fields — · expect Dimensions +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Pipe Sizes Detail; Scale=1:5 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 269 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Pipe Sizes Detail reads 'Pipe Sizes Detail'; Scale=1:5 reads '1:5' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (0,0) (50,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (0,0) mm at px (648.0,427.0) on the Drafting View 'Pipe Sizes Detail' view \| (50,0) mm at px (696.0,427.0) on the Drafting View 'Pipe Sizes Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (300,0) (325,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (300,0) mm at px (936.0,427.0) on the Drafting View 'Pipe Sizes Detail' view \| (325,0) mm at px (960.0,427.0) on the Drafting View 'Pipe Sizes Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 1 -> 2 (+1, expected +1) |
| `ribbon:Annotate:Diameter · picks (50,0) (120,60) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Diameter' on Annotate's Dimension panel: the tool 'Diameter' stands \| picks: (50,0) mm at px (696.0,427.0) on the Drafting View 'Pipe Sizes Detail' view \| (120,60) mm at px (763.2,369.4) on the Drafting View 'Pipe Sizes Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Diameter -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Radial · picks (325,0) (400,50) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Radial' on Annotate's Dimension panel: the tool 'Radial' stands \| picks: (325,0) mm at px (960.0,427.0) on the Drafting View 'Pipe Sizes Detail' view \| (400,50) mm at px (1032.0,379.0) on the Drafting View 'Pipe Sizes Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Radial -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add text at=(-60,-150) view=\"Pipe Sizes Detail\" text=\"100 SEWER AND 50 VENT RISER\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add text at=(-60,-150) view="Pipe Sizes Detail" text="100 SEWER AND 50 VENT RISER"` | green: op:add text made=text-615efbd0e1214acf changed= ms=27 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Levels 2,Lines 2,Text Notes 1,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5025. Dimension the three outer legs of an L-shaped shed with linear dimensions.

- Starts from: a new Architectural project
- Ends with: six walls forming an L on Ground with three linear dimensions along its long outer faces
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(20000,20000) to=(32000,20000) level=Ground",
  "op:add wall from=(32000,20000) to=(32000,24000) level=Ground",
  "op:add wall from=(32000,24000) to=(26000,24000) level=Ground",
  "op:add wall from=(26000,24000) to=(26000,28000) level=Ground",
  "op:add wall from=(26000,28000) to=(20000,28000) level=Ground",
  "op:add wall from=(20000,28000) to=(20000,20000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(20000,20000) to=(32000,20000) level=Ground` | green: op:add wall made=wall-e1aadde2f6d78266 changed= ms=19 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(32000,20000) to=(32000,24000) level=Ground` | green: op:add wall made=wall-aec83929b4c7497e changed=wall-e1aadde2f6d78266 ms=5 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(32000,24000) to=(26000,24000) level=Ground` | green: op:add wall made=wall-e765b79af3dc7183 changed=wall-aec83929b4c7497e ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(26000,24000) to=(26000,28000) level=Ground` | green: op:add wall made=wall-8dade7aee44b6849 changed=wall-e765b79af3dc7183 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(26000,28000) to=(20000,28000) level=Ground` | green: op:add wall made=wall-f8379e447d36369e changed=wall-8dade7aee44b6849 ms=4 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(20000,28000) to=(20000,20000) level=Ground` | green: op:add wall made=wall-f7e9b8d97d81a9a7 changed=wall-f8379e447d36369e,wall-e1aadde2f6d78266 ms=4 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Linear · picks (20000,20000) (32000,20000) (26000,18500) · keys Escape Escape · fields — · expect Dimensions +1",
  "ribbon:Annotate:Linear · picks (20000,28000) (20000,20000) (18500,24000) · keys Escape Escape · fields — · expect Dimensions +1",
  "ribbon:Annotate:Linear · picks (32000,20000) (32000,24000) (33500,22000) · keys Escape Escape · fields — · expect Dimensions +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Linear · picks (20000,20000) (32000,20000) (26000,18500) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Linear' on Annotate's Dimension panel: the tool 'Linear' stands \| picks: (20000,20000) mm at px (872.9,117.9) on the plan view \| (32000,20000) mm at px (1125.4,117.9) on the plan view \| (26000,18500) mm at px (999.2,149.5) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Linear -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Linear · picks (20000,28000) (20000,20000) (18500,24000) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Linear' on Annotate's Dimension panel: the tool 'Linear' stands \| picks: (20000,28000) lay outside the view: panned to bring it to px (648.0,445.0); (20000,28000) mm at px (648.0,445.0) on the plan view \| (20000,20000) mm at px (648.0,613.3) on the plan view \| (18500,24000) mm at px (616.4,529.2) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Linear -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |
| `ribbon:Annotate:Linear · picks (32000,20000) (32000,24000) (33500,22000) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Linear' on Annotate's Dimension panel: the tool 'Linear' stands \| picks: (32000,20000) mm at px (900.5,613.3) on the plan view \| (32000,24000) mm at px (900.5,529.2) on the plan view \| (33500,22000) mm at px (932.1,571.3) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Linear -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 2 -> 3 (+1, expected +1) |

### The result

The model holds: Dimensions 3,Levels 3,Walls 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5026. Add our three facade materials to the project: red brick, white render and zinc cladding, each set to its texture.

- Starts from: a new Architectural project
- Ends with: three file materials named Facade Brick, Facade Render and Facade Zinc, with texture sizes and colours set
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material library=brick_red name=\"Facade Brick\"",
  "op:set material name=\"Facade Brick\" key=texture_size value=1200",
  "op:add material library=render_white name=\"Facade Render\"",
  "op:set material name=\"Facade Render\" key=glow value=0.2",
  "op:set material name=\"Facade Render\" key=roughness value=0.85",
  "op:add material library=zinc_cladding name=\"Facade Zinc\"",
  "op:set material name=\"Facade Zinc\" key=metallic value=0.7",
  "op:set material name=\"Facade Zinc\" key=roughness value=0.35"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material library=brick_red name="Facade Brick"` | green: op:add material made="Facade Brick" changed= ms=748 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Facade Brick" key=texture_size value=1200` | green: op:set material made= changed="Facade Brick" ms=51 Check "every count unchanged": the counts: no count changed |
| `op:add material library=render_white name="Facade Render"` | green: op:add material made="Facade Render" changed= ms=58 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Facade Render" key=glow value=0.2` | green: op:set material made= changed="Facade Render" ms=31 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Facade Render" key=roughness value=0.85` | green: op:set material made= changed="Facade Render" ms=28 Check "every count unchanged": the counts: no count changed |
| `op:add material library=zinc_cladding name="Facade Zinc"` | green: op:add material made="Facade Zinc" changed= ms=57 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Facade Zinc" key=metallic value=0.7` | green: op:set material made= changed="Facade Zinc" ms=29 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Facade Zinc" key=roughness value=0.35` | green: op:set material made= changed="Facade Zinc" ms=100 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5027. Make a blue-grey glazing material for the shopfront: mostly see-through, very smooth, with a blue-grey colour.

- Starts from: a new Architectural project
- Ends with: a file material named Shopfront Glass with a blue-grey render and shading colour, transparency 0.6 and roughness 0.05
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material name=\"Shopfront Glass\"",
  "op:set material name=\"Shopfront Glass\" key=render_colour value=#7E9AAE",
  "op:set material name=\"Shopfront Glass\" key=shading_colour value=#7E9AAE",
  "op:set material name=\"Shopfront Glass\" key=transparency value=0.6",
  "op:set material name=\"Shopfront Glass\" key=roughness value=0.05"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material name="Shopfront Glass"` | green: op:add material made="Shopfront Glass" changed= ms=71 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Shopfront Glass" key=render_colour value=#7E9AAE` | green: op:set material made= changed="Shopfront Glass" ms=12 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Shopfront Glass" key=shading_colour value=#7E9AAE` | green: op:set material made= changed="Shopfront Glass" ms=11 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Shopfront Glass" key=transparency value=0.6` | green: op:set material made= changed="Shopfront Glass" ms=38 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Shopfront Glass" key=roughness value=0.05` | green: op:set material made= changed="Shopfront Glass" ms=11 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5028. Add brushed stainless steel for the balustrade handrail: grey, mostly metal, with a satin finish.

- Starts from: a new Architectural project
- Ends with: a file material named Stainless Steel Brushed with colour #B9BEC4, metallic 0.9 and roughness 0.3
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material name=\"Stainless Steel Brushed\"",
  "op:set material name=\"Stainless Steel Brushed\" key=render_colour value=#B9BEC4",
  "op:set material name=\"Stainless Steel Brushed\" key=shading_colour value=#B9BEC4",
  "op:set material name=\"Stainless Steel Brushed\" key=metallic value=0.9",
  "op:set material name=\"Stainless Steel Brushed\" key=roughness value=0.3"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material name="Stainless Steel Brushed"` | green: op:add material made="Stainless Steel Brushed" changed= ms=178 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Stainless Steel Brushed" key=render_colour value=#B9BEC4` | green: op:set material made= changed="Stainless Steel Brushed" ms=39 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Stainless Steel Brushed" key=shading_colour value=#B9BEC4` | green: op:set material made= changed="Stainless Steel Brushed" ms=25 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Stainless Steel Brushed" key=metallic value=0.9` | green: op:set material made= changed="Stainless Steel Brushed" ms=29 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Stainless Steel Brushed" key=roughness value=0.3` | green: op:set material made= changed="Stainless Steel Brushed" ms=22 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5029. Set up two structural materials with their engineering properties: N32 concrete and grade 250 steel.

- Starts from: a new Structural project
- Ends with: file materials Concrete N32 and Steel Grade 250 holding density, elastic modulus, yield or compressive strength and a keynote
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material library=concrete_smooth name=\"Concrete N32\"",
  "op:set material name=\"Concrete N32\" key=density value=2400",
  "op:set material name=\"Concrete N32\" key=elastic_modulus value=30000",
  "op:set material name=\"Concrete N32\" key=compressive_strength value=32",
  "op:set material name=\"Concrete N32\" key=material_keynote value=03300",
  "op:add material library=steel_painted name=\"Steel Grade 250\"",
  "op:set material name=\"Steel Grade 250\" key=density value=7850",
  "op:set material name=\"Steel Grade 250\" key=elastic_modulus value=200000",
  "op:set material name=\"Steel Grade 250\" key=yield_strength value=250",
  "op:set material name=\"Steel Grade 250\" key=material_keynote value=05120"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material library=concrete_smooth name="Concrete N32"` | green: op:add material made="Concrete N32" changed= ms=627 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete N32" key=density value=2400` | green: op:set material made= changed= ms=11 state=unchanged Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete N32" key=elastic_modulus value=30000` | green: op:set material made= changed= ms=8 state=unchanged Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete N32" key=compressive_strength value=32` | green: op:set material made= changed="Concrete N32" ms=26 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete N32" key=material_keynote value=03300` | green: op:set material made= changed="Concrete N32" ms=22 Check "every count unchanged": the counts: no count changed |
| `op:add material library=steel_painted name="Steel Grade 250"` | green: op:add material made="Steel Grade 250" changed= ms=136 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Steel Grade 250" key=density value=7850` | green: op:set material made= changed= ms=14 state=unchanged Check "every count unchanged": the counts: no count changed |
| `op:set material name="Steel Grade 250" key=elastic_modulus value=200000` | green: op:set material made= changed= ms=14 state=unchanged Check "every count unchanged": the counts: no count changed |
| `op:set material name="Steel Grade 250" key=yield_strength value=250` | green: op:set material made= changed= ms=15 state=unchanged Check "every count unchanged": the counts: no count changed |
| `op:set material name="Steel Grade 250" key=material_keynote value=05120` | green: op:set material made= changed="Steel Grade 250" ms=24 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5030. Add galvanised sheet and duct lining to the project materials, with the supplier and cost on each.

- Starts from: a new Mechanical project
- Ends with: file materials Galvanised Duct Sheet and Duct Lining with manufacturer, cost, description and thermal values set
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material library=steel_galvanised name=\"Galvanised Duct Sheet\"",
  "op:set material name=\"Galvanised Duct Sheet\" key=manufacturer value=\"Metal Duct Supplies\"",
  "op:set material name=\"Galvanised Duct Sheet\" key=cost value=38",
  "op:set material name=\"Galvanised Duct Sheet\" key=description value=\"0.8 mm Z275 galvanised steel sheet\"",
  "op:add material name=\"Duct Lining\"",
  "op:set material name=\"Duct Lining\" key=render_colour value=#D8C84A",
  "op:set material name=\"Duct Lining\" key=heat_conductivity value=0.036",
  "op:set material name=\"Duct Lining\" key=description value=\"25 mm glass wool lining\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add material library=steel_galvanised name="Galvanised Duct Sheet"` | green: op:add material made="Galvanised Duct Sheet" changed= ms=216 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Galvanised Duct Sheet" key=manufacturer value="Metal Duct Supplies"` | green: op:set material made= changed="Galvanised Duct Sheet" ms=11 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Galvanised Duct Sheet" key=cost value=38` | green: op:set material made= changed="Galvanised Duct Sheet" ms=21 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Galvanised Duct Sheet" key=description value="0.8 mm Z275 galvanised steel sheet"` | green: op:set material made= changed="Galvanised Duct Sheet" ms=15 Check "every count unchanged": the counts: no count changed |
| `op:add material name="Duct Lining"` | green: op:add material made="Duct Lining" changed= ms=21 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Duct Lining" key=render_colour value=#D8C84A` | green: op:set material made= changed="Duct Lining" ms=15 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Duct Lining" key=heat_conductivity value=0.036` | green: op:set material made= changed="Duct Lining" ms=12 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Duct Lining" key=description value="25 mm glass wool lining"` | green: op:set material made= changed="Duct Lining" ms=22 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 5031. Add a spotted gum floor finish with boards 150 mm wide, turned 90 degrees so they run across the room.

- Starts from: a new Architectural project
- Ends with: a file material named Spotted Gum Floor from the wide timber floor set with texture size 900, rotation 90 and roughness 0.6
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material library=timber_floor_wide name=\"Spotted Gum Floor\"",
  "op:set material name=\"Spotted Gum Floor\" key=texture_size value=900",
  "op:set material name=\"Spotted Gum Floor\" key=texture_rotation value=90",
  "op:set material name=\"Spotted Gum Floor\" key=roughness value=0.6",
  "op:set material name=\"Spotted Gum Floor\" key=material_mark value=TF1"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material library=timber_floor_wide name="Spotted Gum Floor"` | green: op:add material made="Spotted Gum Floor" changed= ms=214 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Spotted Gum Floor" key=texture_size value=900` | green: op:set material made= changed="Spotted Gum Floor" ms=24 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Spotted Gum Floor" key=texture_rotation value=90` | green: op:set material made= changed="Spotted Gum Floor" ms=15 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Spotted Gum Floor" key=roughness value=0.6` | green: op:set material made= changed="Spotted Gum Floor" ms=18 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Spotted Gum Floor" key=material_mark value=TF1` | green: op:set material made= changed="Spotted Gum Floor" ms=12 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5032. Set up the interior paint schedule as materials: warm white, sage green and charcoal, each lifted so it does not go grey in shade.

- Starts from: a new Architectural project
- Ends with: three plain file materials Paint Warm White, Paint Sage and Paint Charcoal, each with a colour and a glow
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material name=\"Paint Warm White\"",
  "op:set material name=\"Paint Warm White\" key=render_colour value=#f4f1ea",
  "op:set material name=\"Paint Warm White\" key=glow value=0.2",
  "op:set material name=\"Paint Warm White\" key=material_mark value=P1",
  "op:add material name=\"Paint Sage\"",
  "op:set material name=\"Paint Sage\" key=render_colour value=#9CAF88",
  "op:set material name=\"Paint Sage\" key=glow value=0.3",
  "op:set material name=\"Paint Sage\" key=material_mark value=P2",
  "op:add material name=\"Paint Charcoal\"",
  "op:set material name=\"Paint Charcoal\" key=render_colour value=#36393D",
  "op:set material name=\"Paint Charcoal\" key=glow value=0.45",
  "op:set material name=\"Paint Charcoal\" key=material_mark value=P3"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material name="Paint Warm White"` | green: op:add material made="Paint Warm White" changed= ms=408 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Warm White" key=render_colour value=#f4f1ea` | green: op:set material made= changed="Paint Warm White" ms=14 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Warm White" key=glow value=0.2` | green: op:set material made= changed="Paint Warm White" ms=20 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Warm White" key=material_mark value=P1` | green: op:set material made= changed="Paint Warm White" ms=16 Check "every count unchanged": the counts: no count changed |
| `op:add material name="Paint Sage"` | green: op:add material made="Paint Sage" changed= ms=13 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Sage" key=render_colour value=#9CAF88` | green: op:set material made= changed="Paint Sage" ms=17 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Sage" key=glow value=0.3` | green: op:set material made= changed="Paint Sage" ms=42 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Sage" key=material_mark value=P2` | green: op:set material made= changed="Paint Sage" ms=10 Check "every count unchanged": the counts: no count changed |
| `op:add material name="Paint Charcoal"` | green: op:add material made="Paint Charcoal" changed= ms=14 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Charcoal" key=render_colour value=#36393D` | green: op:set material made= changed="Paint Charcoal" ms=18 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Charcoal" key=glow value=0.45` | green: op:set material made= changed="Paint Charcoal" ms=21 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Paint Charcoal" key=material_mark value=P3` | green: op:set material made= changed="Paint Charcoal" ms=15 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5033. Draw the base of our brick cavity wall at 1:10: inner blockwork, outer brick, a 50 mm cavity, weep holes and the slab.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Cavity Wall Base Detail" holding brick leaf, blockwork leaf, cavity, slab, hatches, two notes and a cavity dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Cavity Wall Base Detail\" scale=1:10",
  "op:add detail line points=(0,0) (110,0) (110,900) (0,900) (0,0) view=\"Cavity Wall Base Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(160,0) (350,0) (350,900) (160,900) (160,0) view=\"Cavity Wall Base Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(350,0) (1200,0) (1200,100) (350,100) view=\"Cavity Wall Base Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-100,-300) (1200,-300) (1200,0) (-100,0) (-100,-300) view=\"Cavity Wall Base Detail\"",
  "op:add filled region boundary=(160,0) (350,0) (350,900) (160,900) view=\"Cavity Wall Base Detail\" pattern=Blockwork",
  "op:add filled region boundary=(-100,-300) (1200,-300) (1200,0) (-100,0) view=\"Cavity Wall Base Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add text at=(700,500) view=\"Cavity Wall Base Detail\" text=\"90 FACE BRICK\" leader_to=(55,450)",
  "op:add text at=(700,300) view=\"Cavity Wall Base Detail\" text=\"190 BLOCKWORK, CORE FILLED\" leader_to=(255,300)",
  "op:add dimension from=(110,900) to=(160,900) view=\"Cavity Wall Base Detail\" offset=-100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Cavity Wall Base Detail" scale=1:10` | green: op:add drafting view made=acbc78cb11e047a4b0e17507ce81faf8 changed= ms=18 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (110,0) (110,900) (0,900) (0,0) view="Cavity Wall Base Detail" style="Wide Lines"` | green: op:add detail line made=detail-d3fb76d9e6774458,detail-8aed5ddc624d4563,detail-64e3e57dd9954492,detail-670aaf88172e4aa9 changed= ms=4 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(160,0) (350,0) (350,900) (160,900) (160,0) view="Cavity Wall Base Detail" style="Wide Lines"` | green: op:add detail line made=detail-f362d6c6826d436c,detail-5b3982aaafc44ad0,detail-12d9e50c853840c3,detail-f696230165c7427b changed= ms=3 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(350,0) (1200,0) (1200,100) (350,100) view="Cavity Wall Base Detail" style="Wide Lines"` | green: op:add detail line made=detail-203829406bee4a25,detail-c0cbfe23e2d041ea,detail-1b8793c7da5f4936 changed= ms=3 Check "Lines +3": Lines 8 -> 11 (+3, expected +3) |
| `op:add detail line points=(-100,-300) (1200,-300) (1200,0) (-100,0) (-100,-300) view="Cavity Wall Base Detail"` | green: op:add detail line made=detail-88638a55693344d2,detail-e9730baf599c400a,detail-710ce50c993c4e19,detail-aa8e5dc647154713 changed= ms=3 Check "Lines +4": Lines 11 -> 15 (+4, expected +4) |
| `op:add filled region boundary=(160,0) (350,0) (350,900) (160,900) view="Cavity Wall Base Detail" pattern=Blockwork` | green: op:add filled region made=region-54aa67ce4f774a6f changed= ms=6 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(-100,-300) (1200,-300) (1200,0) (-100,0) view="Cavity Wall Base Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-7149e3f65f3d4987 changed= ms=4 Check "Filled Regions +1": Filled Regions 1 -> 2 (+1, expected +1) |
| `op:add text at=(700,500) view="Cavity Wall Base Detail" text="90 FACE BRICK" leader_to=(55,450)` | green: op:add text made=text-127819be5d5d4bec changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(700,300) view="Cavity Wall Base Detail" text="190 BLOCKWORK, CORE FILLED" leader_to=(255,300)` | green: op:add text made=text-4729383cafa4429e changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(110,900) to=(160,900) view="Cavity Wall Base Detail" offset=-100` | green: op:add dimension made=dim-6f766fd3748e4b64 changed= ms=118 note=offset -100: the dimension line stands 100 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Filled Regions 2,Levels 3,Lines 15,Text Notes 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5034. Detail the ridge of our tiled roof at 1:10: two rafters, ridge board, ridge capping and the tile battens.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Roof Ridge Detail" with two rafters meeting a ridge board, capping, battens, three notes and a ridge-board dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Roof Ridge Detail\" scale=1:10",
  "op:add detail line points=(-20,-100) (-600,-370) (-600,-230) (-20,40) (-20,-100) view=\"Roof Ridge Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(20,-100) (600,-370) (600,-230) (20,40) (20,-100) view=\"Roof Ridge Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-20,40) (-20,240) (20,240) (20,40) view=\"Roof Ridge Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-60,250) (0,300) (60,250) (60,235) (0,285) (-60,235) (-60,250) view=\"Roof Ridge Detail\"",
  "op:add detail line points=(-600,-205) (-30,65) view=\"Roof Ridge Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(600,-205) (30,65) view=\"Roof Ridge Detail\" style=\"Medium Lines\"",
  "op:add text at=(500,350) view=\"Roof Ridge Detail\" text=\"RIDGE CAPPING, MORTAR BEDDED\" leader_to=(40,280)",
  "op:add text at=(500,-100) view=\"Roof Ridge Detail\" text=\"190 x 35 RIDGE BOARD\" leader_to=(10,100)",
  "op:add text at=(-1100,-450) view=\"Roof Ridge Detail\" text=\"70 x 35 TILE BATTENS AT 330 CTS\" leader_to=(-400,-290)",
  "op:add dimension from=(-20,40) to=(-20,240) view=\"Roof Ridge Detail\" offset=100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Roof Ridge Detail" scale=1:10` | green: op:add drafting view made=b86d2cd8b42f42a384314d1669786d8e changed= ms=23 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-20,-100) (-600,-370) (-600,-230) (-20,40) (-20,-100) view="Roof Ridge Detail" style="Wide Lines"` | green: op:add detail line made=detail-9573bedb63024ad1,detail-c3733ca5bf96495b,detail-38ac72d99a6a4f8e,detail-8b5cba4ebb9245d9 changed= ms=6 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(20,-100) (600,-370) (600,-230) (20,40) (20,-100) view="Roof Ridge Detail" style="Wide Lines"` | green: op:add detail line made=detail-7cdbcfc1f8b24a5b,detail-54bdcb2f8e184d1d,detail-c0a3d75fd2004e75,detail-99435dd79cae4422 changed= ms=3 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-20,40) (-20,240) (20,240) (20,40) view="Roof Ridge Detail" style="Wide Lines"` | green: op:add detail line made=detail-4394695d73ef486d,detail-d179158cdeba496b,detail-bff1f35da90d4264 changed= ms=3 Check "Lines +3": Lines 8 -> 11 (+3, expected +3) |
| `op:add detail line points=(-60,250) (0,300) (60,250) (60,235) (0,285) (-60,235) (-60,250) view="Roof Ridge Detail"` | green: op:add detail line made=detail-ebca3712a3e74d91,detail-90b16e3f17154516,detail-bb2ecee9e5fe4b3d,detail-0ed600dff64b4278,detail-53f7abacfc9f4ec8,detail-19fd1649be054752 changed= ms=3 Check "Lines +6": Lines 11 -> 17 (+6, expected +6) |
| `op:add detail line points=(-600,-205) (-30,65) view="Roof Ridge Detail" style="Medium Lines"` | green: op:add detail line made=detail-bc1421404d604562 changed= ms=3 Check "Lines +1": Lines 17 -> 18 (+1, expected +1) |
| `op:add detail line points=(600,-205) (30,65) view="Roof Ridge Detail" style="Medium Lines"` | green: op:add detail line made=detail-f5075b9381fc44e6 changed= ms=4 Check "Lines +1": Lines 18 -> 19 (+1, expected +1) |
| `op:add text at=(500,350) view="Roof Ridge Detail" text="RIDGE CAPPING, MORTAR BEDDED" leader_to=(40,280)` | green: op:add text made=text-1ea7d8af47a741a7 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,-100) view="Roof Ridge Detail" text="190 x 35 RIDGE BOARD" leader_to=(10,100)` | green: op:add text made=text-3c19f1425bbc45ac changed= ms=5 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(-1100,-450) view="Roof Ridge Detail" text="70 x 35 TILE BATTENS AT 330 CTS" leader_to=(-400,-290)` | green: op:add text made=text-179bd962a19e45ed changed= ms=3 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add dimension from=(-20,40) to=(-20,240) view="Roof Ridge Detail" offset=100` | green: op:add dimension made=dim-0934fc7b9b8e4f5c changed= ms=37 note=offset 100: the dimension line stands 100 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Levels 3,Lines 19,Text Notes 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5035. Draw the window sill flashing at 1:5 with a 5 degree fall, a drip edge and the end dam noted.

- Starts from: a new Architectural project
- Ends with: a 1:5 drafting view "Sill Flashing Detail" with wall, sill, a sloped flashing line, drip edge, notes and a dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Sill Flashing Detail\" scale=1:5",
  "op:add detail line points=(0,0) (110,0) (110,-400) (0,-400) (0,0) view=\"Sill Flashing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(110,-40) (230,-40) (230,-60) (110,-60) view=\"Sill Flashing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(110,-60) (230,-70) (260,-72) (260,-110) (250,-110) view=\"Sill Flashing Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(230,-40) (230,200) (260,200) (260,-40) view=\"Sill Flashing Detail\"",
  "op:add text at=(450,-250) view=\"Sill Flashing Detail\" text=\"ALUMINIUM SILL FLASHING\" leader_to=(190,-66)",
  "op:add text at=(450,-420) view=\"Sill Flashing Detail\" text=\"DRIP EDGE 10 BEYOND FACE\" leader_to=(255,-108)",
  "op:add dimension from=(110,-60) to=(260,-72) view=\"Sill Flashing Detail\" offset=-80"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Sill Flashing Detail" scale=1:5` | green: op:add drafting view made=90245d1ceb7b48f8b47c0659badc26f8 changed= ms=21 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (110,0) (110,-400) (0,-400) (0,0) view="Sill Flashing Detail" style="Wide Lines"` | green: op:add detail line made=detail-0601c6746aac441b,detail-bdf3fd06dc00472a,detail-96df56b5cb014b77,detail-2165f603e67c495c changed= ms=5 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(110,-40) (230,-40) (230,-60) (110,-60) view="Sill Flashing Detail" style="Wide Lines"` | green: op:add detail line made=detail-d052b93509c0462a,detail-19a03ef31bbd4aed,detail-aa5cb6bbba574fff changed= ms=4 Check "Lines +3": Lines 4 -> 7 (+3, expected +3) |
| `op:add detail line points=(110,-60) (230,-70) (260,-72) (260,-110) (250,-110) view="Sill Flashing Detail" style="Medium Lines"` | green: op:add detail line made=detail-b612b005bfac409d,detail-13aa22a491394baf,detail-eb2e6602a5a74e7c,detail-5aa034d1f5c14d14 changed= ms=4 Check "Lines +4": Lines 7 -> 11 (+4, expected +4) |
| `op:add detail line points=(230,-40) (230,200) (260,200) (260,-40) view="Sill Flashing Detail"` | green: op:add detail line made=detail-506f83de711d4aa4,detail-583956c534c34ed8,detail-74bb49f4b535405f changed= ms=4 Check "Lines +3": Lines 11 -> 14 (+3, expected +3) |
| `op:add text at=(450,-250) view="Sill Flashing Detail" text="ALUMINIUM SILL FLASHING" leader_to=(190,-66)` | green: op:add text made=text-62982e4897874f7a changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(450,-420) view="Sill Flashing Detail" text="DRIP EDGE 10 BEYOND FACE" leader_to=(255,-108)` | green: op:add text made=text-993c814a4d734aa3 changed= ms=21 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(110,-60) to=(260,-72) view="Sill Flashing Detail" offset=-80` | green: op:add dimension made=dim-035c7ac9990846a6 changed= ms=43 note=offset -80: the dimension line stands 80 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Levels 3,Lines 14,Text Notes 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5036. Detail the accessible door threshold at 1:5: a 10 mm ramped threshold, slab edge and the floor finish on either side.

- Starts from: a new Architectural project
- Ends with: a 1:5 drafting view "Door Threshold Detail" with the slab, a ramped threshold plate, tile and carpet strips, hatches, two notes and a dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Door Threshold Detail\" scale=1:5",
  "op:add detail line points=(-400,-100) (400,-100) (400,0) (-400,0) (-400,-100) view=\"Door Threshold Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-400,0) (-400,10) (-40,10) (-40,0) view=\"Door Threshold Detail\"",
  "op:add detail line points=(40,0) (40,10) (400,10) (400,0) view=\"Door Threshold Detail\"",
  "op:add detail line points=(-40,10) (-30,15) (30,15) (40,10) view=\"Door Threshold Detail\" style=\"Wide Lines\"",
  "op:add filled region boundary=(-400,-100) (400,-100) (400,0) (-400,0) view=\"Door Threshold Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add filled region boundary=(40,0) (400,0) (400,10) (40,10) view=\"Door Threshold Detail\" pattern=\"Solid fill\"",
  "op:add text at=(-300,120) view=\"Door Threshold Detail\" text=\"CARPET TO INTERIOR\" leader_to=(-250,10)",
  "op:add text at=(250,120) view=\"Door Threshold Detail\" text=\"10 TILE TO EXTERIOR\" leader_to=(250,10)",
  "op:add dimension from=(-30,15) to=(30,15) view=\"Door Threshold Detail\" offset=-60"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Door Threshold Detail" scale=1:5` | green: op:add drafting view made=a78706bebd4f49a28c0bd10903fccf62 changed= ms=25 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-400,-100) (400,-100) (400,0) (-400,0) (-400,-100) view="Door Threshold Detail" style="Wide Lines"` | green: op:add detail line made=detail-f23fd5354b374304,detail-437760901e964075,detail-a335045f6a824ce3,detail-4441a7512c874c51 changed= ms=5 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(-400,0) (-400,10) (-40,10) (-40,0) view="Door Threshold Detail"` | green: op:add detail line made=detail-e90e459b35de4031,detail-2dcf49d53df34ba4,detail-bd85bc3bde3b484e changed= ms=3 Check "Lines +3": Lines 4 -> 7 (+3, expected +3) |
| `op:add detail line points=(40,0) (40,10) (400,10) (400,0) view="Door Threshold Detail"` | green: op:add detail line made=detail-0a796cfcc15d4454,detail-d0691c943013480d,detail-0bf480e609fb413b changed= ms=3 Check "Lines +3": Lines 7 -> 10 (+3, expected +3) |
| `op:add detail line points=(-40,10) (-30,15) (30,15) (40,10) view="Door Threshold Detail" style="Wide Lines"` | green: op:add detail line made=detail-81f043674efd42ad,detail-82a1bb64eb1a4dfd,detail-1c3d6afb272042e3 changed= ms=3 Check "Lines +3": Lines 10 -> 13 (+3, expected +3) |
| `op:add filled region boundary=(-400,-100) (400,-100) (400,0) (-400,0) view="Door Threshold Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-2821460bb5b7431b changed= ms=4 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(40,0) (400,0) (400,10) (40,10) view="Door Threshold Detail" pattern="Solid fill"` | green: op:add filled region made=region-1c20b02f938c4a68 changed= ms=5 Check "Filled Regions +1": Filled Regions 1 -> 2 (+1, expected +1) |
| `op:add text at=(-300,120) view="Door Threshold Detail" text="CARPET TO INTERIOR" leader_to=(-250,10)` | green: op:add text made=text-a60bca4024b848fe changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(250,120) view="Door Threshold Detail" text="10 TILE TO EXTERIOR" leader_to=(250,10)` | green: op:add text made=text-490fcfa1ec67412e changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-30,15) to=(30,15) view="Door Threshold Detail" offset=-60` | green: op:add dimension made=dim-56b056f5157c4dc2 changed= ms=31 note=offset -60: the dimension line stands 60 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Filled Regions 2,Levels 3,Lines 13,Text Notes 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5037. Show how the balustrade post is fixed to the slab edge at 1:10: base plate, two bolts and the rail height.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Balustrade Post Fixing Detail" with the slab edge, base plate, post, handrail, two bolts, notes and a rail height dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Balustrade Post Fixing Detail\" scale=1:10",
  "op:add detail line points=(-500,-200) (0,-200) (0,0) (-500,0) (-500,-200) view=\"Balustrade Post Fixing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-120,0) (-120,10) (-20,10) (-20,0) view=\"Balustrade Post Fixing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-90,10) (-90,1000) (-50,1000) (-50,10) view=\"Balustrade Post Fixing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-150,1000) (50,1000) (50,1040) (-150,1040) (-150,1000) view=\"Balustrade Post Fixing Detail\"",
  "op:add detail line points=(-105,-100) (-105,10) view=\"Balustrade Post Fixing Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(-35,-100) (-35,10) view=\"Balustrade Post Fixing Detail\" style=\"Medium Lines\"",
  "op:add text at=(300,500) view=\"Balustrade Post Fixing Detail\" text=\"50 x 50 SHS POST\" leader_to=(-50,500)",
  "op:add text at=(300,-120) view=\"Balustrade Post Fixing Detail\" text=\"2 x M12 HD BOLTS\" leader_to=(-35,-60)",
  "op:add dimension from=(-90,10) to=(-90,1000) view=\"Balustrade Post Fixing Detail\" offset=250"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Balustrade Post Fixing Detail" scale=1:10` | green: op:add drafting view made=413aa0aa79894ca39d7639496faf57d3 changed= ms=19 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-500,-200) (0,-200) (0,0) (-500,0) (-500,-200) view="Balustrade Post Fixing Detail" style="Wide Lines"` | green: op:add detail line made=detail-94be6bac1a5145ff,detail-8f478078a40c48f0,detail-59371451e7b84f5d,detail-db2184bdfe6148ed changed= ms=3 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(-120,0) (-120,10) (-20,10) (-20,0) view="Balustrade Post Fixing Detail" style="Wide Lines"` | green: op:add detail line made=detail-9b09a6f899664d26,detail-61abe26ca16a4997,detail-4230cebfa5294585 changed= ms=47 Check "Lines +3": Lines 4 -> 7 (+3, expected +3) |
| `op:add detail line points=(-90,10) (-90,1000) (-50,1000) (-50,10) view="Balustrade Post Fixing Detail" style="Wide Lines"` | green: op:add detail line made=detail-398457aebe084db5,detail-b518b6f501ee44f9,detail-9fc5f316448c4981 changed= ms=58 Check "Lines +3": Lines 7 -> 10 (+3, expected +3) |
| `op:add detail line points=(-150,1000) (50,1000) (50,1040) (-150,1040) (-150,1000) view="Balustrade Post Fixing Detail"` | green: op:add detail line made=detail-b9bf957b54db4ac6,detail-f0d56a18a5694b4a,detail-979b666a826b4838,detail-acdbff1ca8294c66 changed= ms=33 Check "Lines +4": Lines 10 -> 14 (+4, expected +4) |
| `op:add detail line points=(-105,-100) (-105,10) view="Balustrade Post Fixing Detail" style="Medium Lines"` | green: op:add detail line made=detail-caf9093fe41841bb changed= ms=3 Check "Lines +1": Lines 14 -> 15 (+1, expected +1) |
| `op:add detail line points=(-35,-100) (-35,10) view="Balustrade Post Fixing Detail" style="Medium Lines"` | green: op:add detail line made=detail-07420241ee374158 changed= ms=3 Check "Lines +1": Lines 15 -> 16 (+1, expected +1) |
| `op:add text at=(300,500) view="Balustrade Post Fixing Detail" text="50 x 50 SHS POST" leader_to=(-50,500)` | green: op:add text made=text-b62209d85e8748c2 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(300,-120) view="Balustrade Post Fixing Detail" text="2 x M12 HD BOLTS" leader_to=(-35,-60)` | green: op:add text made=text-459a3b8fe268450d changed= ms=6 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-90,10) to=(-90,1000) view="Balustrade Post Fixing Detail" offset=250` | green: op:add dimension made=dim-ba1e074846ee4e20 changed= ms=22 note=offset 250: the dimension line stands 250 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Levels 3,Lines 16,Text Notes 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5038. Detail a 1.2 m concrete retaining wall at 1:20: stem, base, gravel drain, a keyed toe and the key sizes.

- Starts from: a new Structural project
- Ends with: a 1:20 drafting view "Retaining Wall Detail" with stem and base outline, concrete hatch, gravel drain, notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Retaining Wall Detail\" scale=1:20",
  "op:add detail line points=(0,0) (1400,0) (1400,300) (700,300) (700,1500) (400,1500) (400,300) (0,300) (0,0) view=\"Retaining Wall Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(0,0) (0,-150) (300,-150) (300,0) view=\"Retaining Wall Detail\" style=\"Wide Lines\"",
  "op:add filled region boundary=(0,0) (1400,0) (1400,300) (700,300) (700,1500) (400,1500) (400,300) (0,300) view=\"Retaining Wall Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add filled region boundary=(700,300) (1100,300) (1100,1500) (700,1500) view=\"Retaining Wall Detail\" pattern=Gravel",
  "op:add text at=(1700,900) view=\"Retaining Wall Detail\" text=\"300 THICK STEM TAPERING TO 300\" leader_to=(550,900)",
  "op:add text at=(1700,1300) view=\"Retaining Wall Detail\" text=\"100 AG DRAIN WITH FILTER SOCK\" leader_to=(900,1300)",
  "op:add text at=(-900,-400) view=\"Retaining Wall Detail\" text=\"SHEAR KEY 300 x 150\" leader_to=(150,-100)",
  "op:add dimension from=(0,0) to=(1400,0) view=\"Retaining Wall Detail\" offset=-450",
  "op:add dimension from=(400,1500) to=(700,1500) view=\"Retaining Wall Detail\" offset=-200"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Retaining Wall Detail" scale=1:20` | green: op:add drafting view made=9ad8c3ea19304d25bf6eb6c75e2264e1 changed= ms=387 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (1400,0) (1400,300) (700,300) (700,1500) (400,1500) (400,300) (0,300) (0,0) view="Retaining Wall Detail" style="Wide Lines"` | green: op:add detail line made=detail-b35488be8fbf404d,detail-c8b3263909534c26,detail-0ce676b1af724ebf,detail-1fec85f1caad4da5,detail-33ed6e3125b94bce,detail-e4228cd8e3e84ba5,detail-96c8dc4a0d364ef1,detail-91425c81674a45eb changed= ms=4 Check "Lines +8": Lines 0 -> 8 (+8, expected +8) |
| `op:add detail line points=(0,0) (0,-150) (300,-150) (300,0) view="Retaining Wall Detail" style="Wide Lines"` | green: op:add detail line made=detail-96ff29af97414c4b,detail-51b97f23e06449b4,detail-9959451bc4b04603 changed= ms=4 Check "Lines +3": Lines 8 -> 11 (+3, expected +3) |
| `op:add filled region boundary=(0,0) (1400,0) (1400,300) (700,300) (700,1500) (400,1500) (400,300) (0,300) view="Retaining Wall Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-d766907ae3f8416b changed= ms=8 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(700,300) (1100,300) (1100,1500) (700,1500) view="Retaining Wall Detail" pattern=Gravel` | green: op:add filled region made=region-c1e942571baa4a55 changed= ms=7 Check "Filled Regions +1": Filled Regions 1 -> 2 (+1, expected +1) |
| `op:add text at=(1700,900) view="Retaining Wall Detail" text="300 THICK STEM TAPERING TO 300" leader_to=(550,900)` | green: op:add text made=text-72f95791b80d4ba8 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(1700,1300) view="Retaining Wall Detail" text="100 AG DRAIN WITH FILTER SOCK" leader_to=(900,1300)` | green: op:add text made=text-6b73d9dd295b43a1 changed= ms=2 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(-900,-400) view="Retaining Wall Detail" text="SHEAR KEY 300 x 150" leader_to=(150,-100)` | green: op:add text made=text-0d24701139c34865 changed= ms=3 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(1400,0) view="Retaining Wall Detail" offset=-450` | green: op:add dimension made=dim-c8fc2099af844477 changed= ms=67 note=offset -450: the dimension line stands 450 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(400,1500) to=(700,1500) view="Retaining Wall Detail" offset=-200` | green: op:add dimension made=dim-91883d6a81744e28 changed= ms=6 note=offset -200: the dimension line stands 200 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Filled Regions 2,Levels 2,Lines 11,Text Notes 3,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5039. Detail a timber floor joist bearing on a brick wall at 1:10, with the bearer plate, noggin and the bearing length.

- Starts from: a new Structural project
- Ends with: a 1:10 drafting view "Joist Bearing Detail" with the wall, bearer plate, joist, noggin, notes and a bearing dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Joist Bearing Detail\" scale=1:10",
  "op:add detail line points=(0,-600) (230,-600) (230,0) (0,0) (0,-600) view=\"Joist Bearing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(30,0) (30,45) (200,45) (200,0) view=\"Joist Bearing Detail\"",
  "op:add detail line points=(30,45) (30,235) (900,235) (900,45) (30,45) view=\"Joist Bearing Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(500,45) (500,235) view=\"Joist Bearing Detail\" style=\"Medium Lines\"",
  "op:add filled region boundary=(0,-600) (230,-600) (230,0) (0,0) view=\"Joist Bearing Detail\" pattern=Blockwork",
  "op:add text at=(500,450) view=\"Joist Bearing Detail\" text=\"190 x 45 F17 JOIST AT 450 CTS\" leader_to=(700,235)",
  "op:add text at=(450,-300) view=\"Joist Bearing Detail\" text=\"45 x 90 BEARER PLATE ON DPC\" leader_to=(115,22)",
  "op:add dimension from=(30,45) to=(200,45) view=\"Joist Bearing Detail\" offset=-120"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Joist Bearing Detail" scale=1:10` | green: op:add drafting view made=1ea235230e9247e9bf2844b1c5bc3ecb changed= ms=18 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,-600) (230,-600) (230,0) (0,0) (0,-600) view="Joist Bearing Detail" style="Wide Lines"` | green: op:add detail line made=detail-9e6920b13ca04c79,detail-c08150b0c6114956,detail-f8c5fbefe8ce4aa0,detail-8d82f26e0487407e changed= ms=4 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(30,0) (30,45) (200,45) (200,0) view="Joist Bearing Detail"` | green: op:add detail line made=detail-9afeab5662fd42cf,detail-cf08c1517d394ba2,detail-97812a4abf3944fb changed= ms=3 Check "Lines +3": Lines 4 -> 7 (+3, expected +3) |
| `op:add detail line points=(30,45) (30,235) (900,235) (900,45) (30,45) view="Joist Bearing Detail" style="Wide Lines"` | green: op:add detail line made=detail-3ab5fce4f175448a,detail-19db479fee7a4300,detail-6c206d3a06f542fd,detail-75617a4b653f4a73 changed= ms=4 Check "Lines +4": Lines 7 -> 11 (+4, expected +4) |
| `op:add detail line points=(500,45) (500,235) view="Joist Bearing Detail" style="Medium Lines"` | green: op:add detail line made=detail-3e956969aac34c0b changed= ms=2 Check "Lines +1": Lines 11 -> 12 (+1, expected +1) |
| `op:add filled region boundary=(0,-600) (230,-600) (230,0) (0,0) view="Joist Bearing Detail" pattern=Blockwork` | green: op:add filled region made=region-fd3eef22558d4787 changed= ms=5 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,450) view="Joist Bearing Detail" text="190 x 45 F17 JOIST AT 450 CTS" leader_to=(700,235)` | green: op:add text made=text-f363fba7b8d642f5 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(450,-300) view="Joist Bearing Detail" text="45 x 90 BEARER PLATE ON DPC" leader_to=(115,22)` | green: op:add text made=text-b9909aae3da44dc9 changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(30,45) to=(200,45) view="Joist Bearing Detail" offset=-120` | green: op:add dimension made=dim-7f6313dfc71945c5 changed= ms=63 note=offset -120: the dimension line stands 120 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Filled Regions 1,Levels 2,Lines 12,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5040. Detail a 600 by 300 concrete beam section at 1:10: stirrup, three top and three bottom bars as circles, and the cover noted.

- Starts from: a new Structural project
- Ends with: a 1:10 drafting view "Concrete Beam Section" with the outline, a stirrup line, six bar circles, a concrete hatch, two notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Concrete Beam Section; Scale=1:10 · expect view: Drafting View +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Concrete Beam Section; Scale=1:10 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 175 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Concrete Beam Section reads 'Concrete Beam Section'; Scale=1:10 reads '1:10' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add detail line points=(0,0) (300,0) (300,600) (0,600) (0,0) view=\"Concrete Beam Section\" style=\"Wide Lines\"",
  "op:add detail line points=(40,40) (260,40) (260,560) (40,560) (40,40) view=\"Concrete Beam Section\" style=\"Medium Lines\"",
  "op:add filled region boundary=(0,0) (300,0) (300,600) (0,600) view=\"Concrete Beam Section\" pattern=\"Diagonal crosshatch\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add detail line points=(0,0) (300,0) (300,600) (0,600) (0,0) view="Concrete Beam Section" style="Wide Lines"` | green: op:add detail line made=detail-0cc22e5637f44834,detail-b7c9e8cdad264acc,detail-5c6b2b82953d48dc,detail-9e8e33c1bf084651 changed= ms=299 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(40,40) (260,40) (260,560) (40,560) (40,40) view="Concrete Beam Section" style="Medium Lines"` | green: op:add detail line made=detail-ca06af7bef4d42a4,detail-ab0485c3ea3446d3,detail-219aa922680d4d47,detail-b1329a579d294d25 changed= ms=10 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add filled region boundary=(0,0) (300,0) (300,600) (0,600) view="Concrete Beam Section" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-257c003300ec4e09 changed= ms=17 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Detail Line · picks (60,60) (76,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (150,60) (166,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (240,60) (256,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (60,540) (76,540) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (150,540) (166,540) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (240,540) (256,540) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Detail Line · picks (60,60) (76,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (60,60) mm at px (676.8,398.2) on the Drafting View 'Concrete Beam Section' view \| (76,60) mm at px (684.5,398.2) on the Drafting View 'Concrete Beam Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 8 -> 9 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (150,60) (166,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (150,60) mm at px (720.0,398.2) on the Drafting View 'Concrete Beam Section' view \| (166,60) mm at px (727.7,398.2) on the Drafting View 'Concrete Beam Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 9 -> 10 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (240,60) (256,60) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (240,60) mm at px (763.2,398.2) on the Drafting View 'Concrete Beam Section' view \| (256,60) mm at px (770.9,398.2) on the Drafting View 'Concrete Beam Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 10 -> 11 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (60,540) (76,540) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (60,540) mm at px (676.8,167.8) on the Drafting View 'Concrete Beam Section' view \| (76,540) mm at px (684.5,167.8) on the Drafting View 'Concrete Beam Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 11 -> 12 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (150,540) (166,540) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (150,540) mm at px (720.0,167.8) on the Drafting View 'Concrete Beam Section' view \| (166,540) mm at px (727.7,167.8) on the Drafting View 'Concrete Beam Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 12 -> 13 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (240,540) (256,540) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (240,540) mm at px (763.2,167.8) on the Drafting View 'Concrete Beam Section' view \| (256,540) mm at px (770.9,167.8) on the Drafting View 'Concrete Beam Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 13 -> 14 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add text at=(550,300) view=\"Concrete Beam Section\" text=\"N10 STIRRUPS AT 200 CTS\" leader_to=(260,300)",
  "op:add text at=(550,60) view=\"Concrete Beam Section\" text=\"3 N20 BOTTOM, COVER 40\" leader_to=(256,60)",
  "op:add dimension from=(300,0) to=(300,600) view=\"Concrete Beam Section\" offset=-120",
  "op:add dimension from=(0,0) to=(300,0) view=\"Concrete Beam Section\" offset=-120"
]}
```

| Line | UNION answered |
|---|---|
| `op:add text at=(550,300) view="Concrete Beam Section" text="N10 STIRRUPS AT 200 CTS" leader_to=(260,300)` | green: op:add text made=text-55d4d5a9c1844818 changed= ms=14 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(550,60) view="Concrete Beam Section" text="3 N20 BOTTOM, COVER 40" leader_to=(256,60)` | green: op:add text made=text-22530a1dec5544a3 changed= ms=169 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(300,0) to=(300,600) view="Concrete Beam Section" offset=-120` | green: op:add dimension made=dim-89ec4f187d0e45ad changed= ms=436 note=offset -120: the dimension line stands 120 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(300,0) view="Concrete Beam Section" offset=-120` | green: op:add dimension made=dim-9c748fe1ce544246 changed= ms=34 note=offset -120: the dimension line stands 120 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Filled Regions 1,Levels 2,Lines 14,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5041. Detail the flexible duct connection to a ceiling diffuser at 1:10 with the spigot, clamp and the plenum box.

- Starts from: a new Mechanical project
- Ends with: a 1:10 drafting view "Diffuser Connection Detail" with the ceiling line, diffuser neck, flexible duct, clamp, lagging, notes and a neck dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Diffuser Connection Detail\" scale=1:10",
  "op:add detail line points=(-600,0) (-150,0) (-150,12) (-600,12) (-600,0) view=\"Diffuser Connection Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(150,0) (600,0) (600,12) (150,12) (150,0) view=\"Diffuser Connection Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-150,0) (-150,-60) (150,-60) (150,0) view=\"Diffuser Connection Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-125,12) (-125,400) (125,12) view=\"Diffuser Connection Detail\"",
  "op:add detail line points=(-140,60) (140,60) (140,80) (-140,80) (-140,60) view=\"Diffuser Connection Detail\" style=\"Medium Lines\"",
  "op:add insulation from=(-125,100) to=(-125,380) view=\"Diffuser Connection Detail\" width=25",
  "op:add text at=(500,250) view=\"Diffuser Connection Detail\" text=\"250 DIA INSULATED FLEXIBLE DUCT\" leader_to=(125,200)",
  "op:add text at=(500,100) view=\"Diffuser Connection Detail\" text=\"WORM-DRIVE CLAMP AT SPIGOT\" leader_to=(140,70)",
  "op:add dimension from=(-150,-60) to=(150,-60) view=\"Diffuser Connection Detail\" offset=-100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Diffuser Connection Detail" scale=1:10` | green: op:add drafting view made=e77d1f9adeaf4ca3b59feae15ea9913b changed= ms=23 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-600,0) (-150,0) (-150,12) (-600,12) (-600,0) view="Diffuser Connection Detail" style="Wide Lines"` | green: op:add detail line made=detail-fdaf71b956d1439a,detail-36ee8ff25fac4d98,detail-656e8618e16e455b,detail-08ae1df8b4d14031 changed= ms=4 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(150,0) (600,0) (600,12) (150,12) (150,0) view="Diffuser Connection Detail" style="Wide Lines"` | green: op:add detail line made=detail-74d3b3d1fbed47ab,detail-e44a35f8dde64be9,detail-aca1007272f94fdf,detail-acecdb4817254c08 changed= ms=4 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-150,0) (-150,-60) (150,-60) (150,0) view="Diffuser Connection Detail" style="Wide Lines"` | green: op:add detail line made=detail-8e17d414666f4485,detail-1fb84d2953db4621,detail-2efb9d50d8d44834 changed= ms=3 Check "Lines +3": Lines 8 -> 11 (+3, expected +3) |
| `op:add detail line points=(-125,12) (-125,400) (125,12) view="Diffuser Connection Detail"` | green: op:add detail line made=detail-e952874e44784adf,detail-48fa76832c6747c9 changed= ms=2 Check "Lines +2": Lines 11 -> 13 (+2, expected +2) |
| `op:add detail line points=(-140,60) (140,60) (140,80) (-140,80) (-140,60) view="Diffuser Connection Detail" style="Medium Lines"` | green: op:add detail line made=detail-e80d21616b4c4316,detail-3ea1901753464dbf,detail-65c6f86f7e9a4677,detail-2b6f8529b5424859 changed= ms=3 Check "Lines +4": Lines 13 -> 17 (+4, expected +4) |
| `op:add insulation from=(-125,100) to=(-125,380) view="Diffuser Connection Detail" width=25` | green: op:add insulation made=insul-a80e8317acbc88d5 changed= ms=3 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,250) view="Diffuser Connection Detail" text="250 DIA INSULATED FLEXIBLE DUCT" leader_to=(125,200)` | green: op:add text made=text-5a6288cfc7d743c4 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,100) view="Diffuser Connection Detail" text="WORM-DRIVE CLAMP AT SPIGOT" leader_to=(140,70)` | green: op:add text made=text-dd8212960e564290 changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-150,-60) to=(150,-60) view="Diffuser Connection Detail" offset=-100` | green: op:add dimension made=dim-4101c4e7f2c24411 changed= ms=16 note=offset -100: the dimension line stands 100 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Detail Items 1,Dimensions 1,Levels 2,Lines 17,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5042. Draw the floor waste in a bathroom slab at 1:5: the waste body, a 100 mm grate, the waterproofing turn-down and the screed fall.

- Starts from: a new Hydraulic project
- Ends with: a 1:5 drafting view "Floor Waste Detail" with the slab, screed hatch, waste body, grate, waterproofing line, notes and a grate dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Floor Waste Detail\" scale=1:5",
  "op:add detail line points=(-400,-150) (-60,-150) (-60,0) (-400,0) (-400,-150) view=\"Floor Waste Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(60,-150) (400,-150) (400,0) (60,0) (60,-150) view=\"Floor Waste Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-60,0) (-60,-120) (-35,-170) (35,-170) (60,-120) (60,0) view=\"Floor Waste Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-50,0) (50,0) view=\"Floor Waste Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(-400,40) (-60,5) view=\"Floor Waste Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(400,40) (60,5) view=\"Floor Waste Detail\" style=\"Medium Lines\"",
  "op:add filled region boundary=(-400,0) (-60,0) (-60,5) (-400,40) view=\"Floor Waste Detail\" pattern=Sand",
  "op:add text at=(500,150) view=\"Floor Waste Detail\" text=\"100 SQUARE STAINLESS GRATE\" leader_to=(0,2)",
  "op:add text at=(500,-300) view=\"Floor Waste Detail\" text=\"MEMBRANE TURNED DOWN INTO FLANGE\" leader_to=(60,-20)",
  "op:add dimension from=(-50,0) to=(50,0) view=\"Floor Waste Detail\" offset=-60"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Floor Waste Detail" scale=1:5` | green: op:add drafting view made=30acd1a45b944e53abae70a0ca755bcd changed= ms=13 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-400,-150) (-60,-150) (-60,0) (-400,0) (-400,-150) view="Floor Waste Detail" style="Wide Lines"` | green: op:add detail line made=detail-112b6ff0a33a436b,detail-727955738efb4392,detail-43fc78db84464fe9,detail-eb2d45b0e5744287 changed= ms=4 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(60,-150) (400,-150) (400,0) (60,0) (60,-150) view="Floor Waste Detail" style="Wide Lines"` | green: op:add detail line made=detail-9df4baa8f4544920,detail-10d0c8186f224b81,detail-1bd319062fc94390,detail-a0235bb875e34d66 changed= ms=85 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-60,0) (-60,-120) (-35,-170) (35,-170) (60,-120) (60,0) view="Floor Waste Detail" style="Wide Lines"` | green: op:add detail line made=detail-9fe970d953104d17,detail-e006be9fc5a44fa0,detail-2a5b60a2059a472a,detail-88f2b7b80c36497d,detail-e5813566e44b4e64 changed= ms=3 Check "Lines +5": Lines 8 -> 13 (+5, expected +5) |
| `op:add detail line points=(-50,0) (50,0) view="Floor Waste Detail" style="Medium Lines"` | green: op:add detail line made=detail-6b899e861abb45da changed= ms=2 Check "Lines +1": Lines 13 -> 14 (+1, expected +1) |
| `op:add detail line points=(-400,40) (-60,5) view="Floor Waste Detail" style="Medium Lines"` | green: op:add detail line made=detail-dcad1c9e4b5c41be changed= ms=2 Check "Lines +1": Lines 14 -> 15 (+1, expected +1) |
| `op:add detail line points=(400,40) (60,5) view="Floor Waste Detail" style="Medium Lines"` | green: op:add detail line made=detail-fa03810f3bfb4d1c changed= ms=48 Check "Lines +1": Lines 15 -> 16 (+1, expected +1) |
| `op:add filled region boundary=(-400,0) (-60,0) (-60,5) (-400,40) view="Floor Waste Detail" pattern=Sand` | green: op:add filled region made=region-027fe90033b44713 changed= ms=4 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,150) view="Floor Waste Detail" text="100 SQUARE STAINLESS GRATE" leader_to=(0,2)` | green: op:add text made=text-48a25e862ee644e7 changed= ms=2 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,-300) view="Floor Waste Detail" text="MEMBRANE TURNED DOWN INTO FLANGE" leader_to=(60,-20)` | green: op:add text made=text-414b69988efe41cb changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-50,0) to=(50,0) view="Floor Waste Detail" offset=-60` | green: op:add dimension made=dim-100b5d1b38dd43bc changed= ms=16 note=offset -60: the dimension line stands 60 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Filled Regions 1,Levels 2,Lines 16,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5043. Detail a pipe passing through a 90 minute fire-rated plasterboard wall at 1:10: both linings, the studs, a collar and the sealant.

- Starts from: a new Fire Protection project
- Ends with: a 1:10 drafting view "Fire Wall Penetration Detail" with two plasterboard layers each side, studs, pipe, collar, hatches, notes and a dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Fire Wall Penetration Detail\" scale=1:10",
  "op:add detail line points=(0,-800) (26,-800) (26,800) (0,800) (0,-800) view=\"Fire Wall Penetration Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(26,-800) (116,-800) (116,800) (26,800) view=\"Fire Wall Penetration Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(116,-800) (142,-800) (142,800) (116,800) view=\"Fire Wall Penetration Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-300,-50) (450,-50) (450,50) (-300,50) (-300,-50) view=\"Fire Wall Penetration Detail\" style=\"Medium Lines\"",
  "op:add filled region boundary=(0,-800) (26,-800) (26,800) (0,800) view=\"Fire Wall Penetration Detail\" pattern=\"Solid fill\"",
  "op:add filled region boundary=(116,-800) (142,-800) (142,800) (116,800) view=\"Fire Wall Penetration Detail\" pattern=\"Solid fill\"",
  "op:add text at=(500,300) view=\"Fire Wall Penetration Detail\" text=\"2 x 13 FIRE-RATED BOARD EACH SIDE\" leader_to=(142,300)",
  "op:add text at=(500,-250) view=\"Fire Wall Penetration Detail\" text=\"INTUMESCENT COLLAR TO BOTH FACES\" leader_to=(142,-60)",
  "op:add dimension from=(0,-800) to=(142,-800) view=\"Fire Wall Penetration Detail\" offset=-150"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Fire Wall Penetration Detail" scale=1:10` | green: op:add drafting view made=f84eb13aa77043cdaf0be3b8cafa4433 changed= ms=13 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,-800) (26,-800) (26,800) (0,800) (0,-800) view="Fire Wall Penetration Detail" style="Wide Lines"` | green: op:add detail line made=detail-dcc9871576a5411f,detail-4ed0f301574e4acf,detail-761201d709f94073,detail-5e29bb72b2524daa changed= ms=4 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(26,-800) (116,-800) (116,800) (26,800) view="Fire Wall Penetration Detail" style="Wide Lines"` | green: op:add detail line made=detail-f0e2fe569fe84130,detail-90d8790fd9124e51,detail-cbb3e1eb4cc949ed changed= ms=5 Check "Lines +3": Lines 4 -> 7 (+3, expected +3) |
| `op:add detail line points=(116,-800) (142,-800) (142,800) (116,800) view="Fire Wall Penetration Detail" style="Wide Lines"` | green: op:add detail line made=detail-ce059f3fafc44dd2,detail-db7565e37ee141d9,detail-37c08a100eb34684 changed= ms=13 Check "Lines +3": Lines 7 -> 10 (+3, expected +3) |
| `op:add detail line points=(-300,-50) (450,-50) (450,50) (-300,50) (-300,-50) view="Fire Wall Penetration Detail" style="Medium Lines"` | green: op:add detail line made=detail-d51fd448f2624a89,detail-a70ba20878b8447b,detail-710c8d2e610e49f3,detail-f8d1ab847a784924 changed= ms=2 Check "Lines +4": Lines 10 -> 14 (+4, expected +4) |
| `op:add filled region boundary=(0,-800) (26,-800) (26,800) (0,800) view="Fire Wall Penetration Detail" pattern="Solid fill"` | green: op:add filled region made=region-c68efccd03514c0b changed= ms=2 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(116,-800) (142,-800) (142,800) (116,800) view="Fire Wall Penetration Detail" pattern="Solid fill"` | green: op:add filled region made=region-a2d398c3304d461f changed= ms=56 Check "Filled Regions +1": Filled Regions 1 -> 2 (+1, expected +1) |
| `op:add text at=(500,300) view="Fire Wall Penetration Detail" text="2 x 13 FIRE-RATED BOARD EACH SIDE" leader_to=(142,300)` | green: op:add text made=text-cd990ef6ffe74e1d changed= ms=42 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,-250) view="Fire Wall Penetration Detail" text="INTUMESCENT COLLAR TO BOTH FACES" leader_to=(142,-60)` | green: op:add text made=text-2996067454de4555 changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(0,-800) to=(142,-800) view="Fire Wall Penetration Detail" offset=-150` | green: op:add dimension made=dim-e763690bb7214543 changed= ms=11 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Filled Regions 2,Levels 2,Lines 14,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5044. Draw the standard mounting heights for sockets and switches on a stud wall at 1:10 with the heights dimensioned.

- Starts from: a new Electrical project
- Ends with: a 1:10 drafting view "Mounting Heights Detail" with a floor line, wall face, a switch, a socket and a bench socket, notes and three height dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Mounting Heights Detail\" scale=1:10",
  "op:add detail line points=(-300,0) (300,0) view=\"Mounting Heights Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(0,0) (0,2400) view=\"Mounting Heights Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(0,1200) (-16,1200) (-16,1280) (0,1280) view=\"Mounting Heights Detail\"",
  "op:add detail line points=(0,300) (-16,300) (-16,380) (0,380) view=\"Mounting Heights Detail\"",
  "op:add detail line points=(0,1050) (-16,1050) (-16,1130) (0,1130) view=\"Mounting Heights Detail\"",
  "op:add text at=(600,1240) view=\"Mounting Heights Detail\" text=\"LIGHT SWITCH 1200 AFFL\" leader_to=(-16,1240)",
  "op:add text at=(600,340) view=\"Mounting Heights Detail\" text=\"GENERAL POWER OUTLET 300 AFFL\" leader_to=(-16,340)",
  "op:add text at=(600,1090) view=\"Mounting Heights Detail\" text=\"BENCH POWER OUTLET 1050 AFFL\" leader_to=(-16,1090)",
  "op:add dimension from=(0,0) to=(0,300) view=\"Mounting Heights Detail\" offset=200",
  "op:add dimension from=(0,300) to=(0,1050) view=\"Mounting Heights Detail\" offset=200",
  "op:add dimension from=(0,1050) to=(0,1200) view=\"Mounting Heights Detail\" offset=200"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Mounting Heights Detail" scale=1:10` | green: op:add drafting view made=47d594a28ec146cdb0bb1149b3e0cae0 changed= ms=28 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-300,0) (300,0) view="Mounting Heights Detail" style="Wide Lines"` | green: op:add detail line made=detail-1828bc5619c246b9 changed= ms=2 Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (0,2400) view="Mounting Heights Detail" style="Wide Lines"` | green: op:add detail line made=detail-f904daa96c6d4eb1 changed= ms=3 Check "Lines +1": Lines 1 -> 2 (+1, expected +1) |
| `op:add detail line points=(0,1200) (-16,1200) (-16,1280) (0,1280) view="Mounting Heights Detail"` | green: op:add detail line made=detail-dddc2c646250492d,detail-61c9b5732dcb4cf3,detail-2f4884c5de754d42 changed= ms=3 Check "Lines +3": Lines 2 -> 5 (+3, expected +3) |
| `op:add detail line points=(0,300) (-16,300) (-16,380) (0,380) view="Mounting Heights Detail"` | green: op:add detail line made=detail-34ae42ed591e486e,detail-2b25c057916b4d03,detail-fc0d280b3dd64e1a changed= ms=3 Check "Lines +3": Lines 5 -> 8 (+3, expected +3) |
| `op:add detail line points=(0,1050) (-16,1050) (-16,1130) (0,1130) view="Mounting Heights Detail"` | green: op:add detail line made=detail-9bdd5a43099a4057,detail-c9f6e39f9c364936,detail-59f149293f594d0a changed= ms=3 Check "Lines +3": Lines 8 -> 11 (+3, expected +3) |
| `op:add text at=(600,1240) view="Mounting Heights Detail" text="LIGHT SWITCH 1200 AFFL" leader_to=(-16,1240)` | green: op:add text made=text-7820cd65a4984904 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(600,340) view="Mounting Heights Detail" text="GENERAL POWER OUTLET 300 AFFL" leader_to=(-16,340)` | green: op:add text made=text-8a2a40153b794de4 changed= ms=4 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(600,1090) view="Mounting Heights Detail" text="BENCH POWER OUTLET 1050 AFFL" leader_to=(-16,1090)` | green: op:add text made=text-34a4fd313e204a53 changed= ms=2 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(0,300) view="Mounting Heights Detail" offset=200` | green: op:add dimension made=dim-72e5ac73aa3c4b38 changed= ms=9 note=offset 200: the dimension line stands 200 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(0,300) to=(0,1050) view="Mounting Heights Detail" offset=200` | green: op:add dimension made=dim-61a3723c52824fac changed= ms=4 note=offset 200: the dimension line stands 200 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(0,1050) to=(0,1200) view="Mounting Heights Detail" offset=200` | green: op:add dimension made=dim-396445402f164f10 changed= ms=4 note=offset 200: the dimension line stands 200 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 2 -> 3 (+1, expected +1) |

### The result

The model holds: Dimensions 3,Levels 2,Lines 11,Text Notes 3,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5045. Make me a sample view of the six hatch patterns we use in details, each in a box with its name under it.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Hatch Samples" with six filled-region boxes (Solid fill, Diagonal crosshatch, Blockwork, Gravel, Insulation, Sand) and six name notes
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Hatch Samples\" scale=1:10",
  "op:add filled region boundary=(0,0) (400,0) (400,300) (0,300) view=\"Hatch Samples\" pattern=\"Solid fill\"",
  "op:add filled region boundary=(500,0) (900,0) (900,300) (500,300) view=\"Hatch Samples\" pattern=\"Diagonal crosshatch\"",
  "op:add filled region boundary=(1000,0) (1400,0) (1400,300) (1000,300) view=\"Hatch Samples\" pattern=Blockwork",
  "op:add filled region boundary=(0,-500) (400,-500) (400,-200) (0,-200) view=\"Hatch Samples\" pattern=Gravel",
  "op:add filled region boundary=(500,-500) (900,-500) (900,-200) (500,-200) view=\"Hatch Samples\" pattern=Insulation",
  "op:add filled region boundary=(1000,-500) (1400,-500) (1400,-200) (1000,-200) view=\"Hatch Samples\" pattern=Sand",
  "op:add text at=(0,-60) view=\"Hatch Samples\" text=\"SOLID\"",
  "op:add text at=(500,-60) view=\"Hatch Samples\" text=\"CONCRETE\"",
  "op:add text at=(1000,-60) view=\"Hatch Samples\" text=\"BLOCKWORK\"",
  "op:add text at=(0,-560) view=\"Hatch Samples\" text=\"GRAVEL\"",
  "op:add text at=(500,-560) view=\"Hatch Samples\" text=\"INSULATION\"",
  "op:add text at=(1000,-560) view=\"Hatch Samples\" text=\"SAND\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Hatch Samples" scale=1:10` | green: op:add drafting view made=c24187b198044dda8b3090b1807d94cc changed= ms=1417 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(0,0) (400,0) (400,300) (0,300) view="Hatch Samples" pattern="Solid fill"` | green: op:add filled region made=region-2561accb8d38442b changed= ms=3 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(500,0) (900,0) (900,300) (500,300) view="Hatch Samples" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-343e251745124310 changed= ms=6 Check "Filled Regions +1": Filled Regions 1 -> 2 (+1, expected +1) |
| `op:add filled region boundary=(1000,0) (1400,0) (1400,300) (1000,300) view="Hatch Samples" pattern=Blockwork` | green: op:add filled region made=region-8cc1ba5b3aa64cdb changed= ms=8 Check "Filled Regions +1": Filled Regions 2 -> 3 (+1, expected +1) |
| `op:add filled region boundary=(0,-500) (400,-500) (400,-200) (0,-200) view="Hatch Samples" pattern=Gravel` | green: op:add filled region made=region-7aa52ca16f024c99 changed= ms=5 Check "Filled Regions +1": Filled Regions 3 -> 4 (+1, expected +1) |
| `op:add filled region boundary=(500,-500) (900,-500) (900,-200) (500,-200) view="Hatch Samples" pattern=Insulation` | green: op:add filled region made=region-bf16b4dd7a6548de changed= ms=45 Check "Filled Regions +1": Filled Regions 4 -> 5 (+1, expected +1) |
| `op:add filled region boundary=(1000,-500) (1400,-500) (1400,-200) (1000,-200) view="Hatch Samples" pattern=Sand` | green: op:add filled region made=region-4d626e065ac44dc3 changed= ms=8 Check "Filled Regions +1": Filled Regions 5 -> 6 (+1, expected +1) |
| `op:add text at=(0,-60) view="Hatch Samples" text="SOLID"` | green: op:add text made=text-fc518422ef054368 changed= ms=7 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,-60) view="Hatch Samples" text="CONCRETE"` | green: op:add text made=text-f0e38b85e9814a6d changed= ms=11 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(1000,-60) view="Hatch Samples" text="BLOCKWORK"` | green: op:add text made=text-5af505ff78794e51 changed= ms=17 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add text at=(0,-560) view="Hatch Samples" text="GRAVEL"` | green: op:add text made=text-edddb04bb1904e5b changed= ms=6 Check "Text Notes +1": Text Notes 3 -> 4 (+1, expected +1) |
| `op:add text at=(500,-560) view="Hatch Samples" text="INSULATION"` | green: op:add text made=text-3930da41dc77460c changed= ms=4 Check "Text Notes +1": Text Notes 4 -> 5 (+1, expected +1) |
| `op:add text at=(1000,-560) view="Hatch Samples" text="SAND"` | green: op:add text made=text-20081fd4dbbb4ca8 changed= ms=69 Check "Text Notes +1": Text Notes 5 -> 6 (+1, expected +1) |

### The result

The model holds: Filled Regions 6,Levels 3,Text Notes 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5046. Show our three wall batt sizes side by side in a stud wall section: 70, 90 and 140 mm.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Batt Sizes" with three stud-wall boxes each holding a batt of its own width and a note naming it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Batt Sizes\" scale=1:10",
  "op:add detail line points=(0,0) (70,0) (70,900) (0,900) (0,0) view=\"Batt Sizes\"",
  "op:add insulation from=(35,20) to=(35,880) view=\"Batt Sizes\" width=70",
  "op:add detail line points=(300,0) (390,0) (390,900) (300,900) (300,0) view=\"Batt Sizes\"",
  "op:add insulation from=(345,20) to=(345,880) view=\"Batt Sizes\" width=90",
  "op:add detail line points=(600,0) (740,0) (740,900) (600,900) (600,0) view=\"Batt Sizes\"",
  "op:add insulation from=(670,20) to=(670,880) view=\"Batt Sizes\" width=140",
  "op:add text at=(0,-80) view=\"Batt Sizes\" text=\"R1.5 70 BATT\"",
  "op:add text at=(300,-80) view=\"Batt Sizes\" text=\"R2.0 90 BATT\"",
  "op:add text at=(600,-80) view=\"Batt Sizes\" text=\"R3.5 140 BATT\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Batt Sizes" scale=1:10` | green: op:add drafting view made=fef67d831d7547b1af60ddb02656fb18 changed= ms=18 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (70,0) (70,900) (0,900) (0,0) view="Batt Sizes"` | green: op:add detail line made=detail-318a490ad8524e13,detail-a6eb0df4bcba4628,detail-6a82023c6acf49bf,detail-32730d9aa2c04d8e changed= ms=13 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add insulation from=(35,20) to=(35,880) view="Batt Sizes" width=70` | green: op:add insulation made=insul-a4e64da3cf5b464f changed= ms=4 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(300,0) (390,0) (390,900) (300,900) (300,0) view="Batt Sizes"` | green: op:add detail line made=detail-6d5a593dd9ed46ae,detail-5a023b98f2224706,detail-1debcc33a1444a5e,detail-f6beabd9815a4376 changed= ms=4 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add insulation from=(345,20) to=(345,880) view="Batt Sizes" width=90` | green: op:add insulation made=insul-e4438afb9b085c17 changed= ms=6 Check "Detail Items +1": Detail Items 1 -> 2 (+1, expected +1) |
| `op:add detail line points=(600,0) (740,0) (740,900) (600,900) (600,0) view="Batt Sizes"` | green: op:add detail line made=detail-63289ecc19f04472,detail-7f352f6a19214b78,detail-8f948428e8af49c9,detail-26a108285f0c412c changed= ms=4 Check "Lines +4": Lines 8 -> 12 (+4, expected +4) |
| `op:add insulation from=(670,20) to=(670,880) view="Batt Sizes" width=140` | green: op:add insulation made=insul-b98461e33e6e82d7 changed= ms=5 Check "Detail Items +1": Detail Items 2 -> 3 (+1, expected +1) |
| `op:add text at=(0,-80) view="Batt Sizes" text="R1.5 70 BATT"` | green: op:add text made=text-0fc38166a7b34f54 changed= ms=52 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(300,-80) view="Batt Sizes" text="R2.0 90 BATT"` | green: op:add text made=text-3cc86ef56f4f46dd changed= ms=4 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(600,-80) view="Batt Sizes" text="R3.5 140 BATT"` | green: op:add text made=text-7e6fd31b20364fcc changed= ms=9 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |

### The result

The model holds: Detail Items 3,Levels 3,Lines 12,Text Notes 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5047. Draw an externally lagged round duct section at 1:5: the duct wall, 50 mm lagging all round and a foil jacket.

- Starts from: a new Mechanical project
- Ends with: a 1:5 drafting view "Lagged Duct Section" with a duct circle, an outer lagging circle, a jacket circle, straight insulation batts along the top, notes and a diameter dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Lagged Duct Section; Scale=1:5 · expect view: Drafting View +1",
  "ribbon:Annotate:Detail Line · picks (0,0) (150,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (0,0) (200,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (0,0) (205,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Lagged Duct Section; Scale=1:5 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 177 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Lagged Duct Section reads 'Lagged Duct Section'; Scale=1:5 reads '1:5' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (0,0) (150,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (0,0) mm at px (648.0,427.0) on the Drafting View 'Lagged Duct Section' view \| (150,0) mm at px (792.0,427.0) on the Drafting View 'Lagged Duct Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (0,0) (200,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (0,0) mm at px (648.0,427.0) on the Drafting View 'Lagged Duct Section' view \| (200,0) mm at px (840.0,427.0) on the Drafting View 'Lagged Duct Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 1 -> 2 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (0,0) (205,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (0,0) mm at px (648.0,427.0) on the Drafting View 'Lagged Duct Section' view \| (205,0) mm at px (844.8,427.0) on the Drafting View 'Lagged Duct Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 2 -> 3 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add insulation from=(-350,250) to=(350,250) view=\"Lagged Duct Section\" width=50"
]}
```

| Line | UNION answered |
|---|---|
| `op:add insulation from=(-350,250) to=(350,250) view="Lagged Duct Section" width=50` | green: op:add insulation made=insul-1953ffb3c2576790 changed= ms=18 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Diameter · picks (150,0) (400,-100) · keys Escape Escape · fields — · expect Dimensions +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Diameter · picks (150,0) (400,-100) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Diameter' on Annotate's Dimension panel: the tool 'Diameter' stands \| picks: (150,0) mm at px (792.0,427.0) on the Drafting View 'Lagged Duct Section' view \| (400,-100) mm at px (1032.0,523.0) on the Drafting View 'Lagged Duct Section' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Diameter -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add text at=(500,150) view=\"Lagged Duct Section\" text=\"50 FOIL-FACED LAGGING\" leader_to=(180,100)",
  "op:add text at=(500,-250) view=\"Lagged Duct Section\" text=\"300 DIA SPIRAL DUCT\" leader_to=(0,-150)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add text at=(500,150) view="Lagged Duct Section" text="50 FOIL-FACED LAGGING" leader_to=(180,100)` | green: op:add text made=text-94289aeb8e3a4e65 changed= ms=259 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(500,-250) view="Lagged Duct Section" text="300 DIA SPIRAL DUCT" leader_to=(0,-150)` | green: op:add text made=text-e0ec12f664da44be changed= ms=50 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |

### The result

The model holds: Detail Items 1,Dimensions 1,Levels 2,Lines 3,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5048. Draw one sample of each detail line weight we use, Wide, Medium and Thin, and label them.

- Starts from: a new Hydraulic project
- Ends with: a 1:1 drafting view "Line Weight Samples" with three horizontal lines in the three line styles, three labels and a box around them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Line Weight Samples\" scale=1:1",
  "op:add detail line points=(0,0) (60,0) view=\"Line Weight Samples\" style=\"Wide Lines\"",
  "op:add detail line points=(0,-10) (60,-10) view=\"Line Weight Samples\" style=\"Medium Lines\"",
  "op:add detail line points=(0,-20) (60,-20) view=\"Line Weight Samples\" style=\"Thin Lines\"",
  "op:add detail line points=(-5,5) (110,5) (110,-30) (-5,-30) (-5,5) view=\"Line Weight Samples\" style=\"Thin Lines\"",
  "op:add text at=(70,0) view=\"Line Weight Samples\" text=\"WIDE: CUT PROFILES\"",
  "op:add text at=(70,-10) view=\"Line Weight Samples\" text=\"MEDIUM: BEYOND\"",
  "op:add text at=(70,-20) view=\"Line Weight Samples\" text=\"THIN: DIMENSIONS\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Line Weight Samples" scale=1:1` | green: op:add drafting view made=ed05c05322084966b40948dd9101884e changed= ms=16 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (60,0) view="Line Weight Samples" style="Wide Lines"` | green: op:add detail line made=detail-525404909de1450b changed= ms=7 Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,-10) (60,-10) view="Line Weight Samples" style="Medium Lines"` | green: op:add detail line made=detail-0c7f4b653b90473d changed= ms=4 Check "Lines +1": Lines 1 -> 2 (+1, expected +1) |
| `op:add detail line points=(0,-20) (60,-20) view="Line Weight Samples" style="Thin Lines"` | green: op:add detail line made=detail-4eed39fff1a94b71 changed= ms=3 Check "Lines +1": Lines 2 -> 3 (+1, expected +1) |
| `op:add detail line points=(-5,5) (110,5) (110,-30) (-5,-30) (-5,5) view="Line Weight Samples" style="Thin Lines"` | green: op:add detail line made=detail-79e147b3b5bc43e8,detail-de9cc682c12a4bf9,detail-a69bf48ac5294ad1,detail-4e3889f2e7e94a65 changed= ms=5 Check "Lines +4": Lines 3 -> 7 (+4, expected +4) |
| `op:add text at=(70,0) view="Line Weight Samples" text="WIDE: CUT PROFILES"` | green: op:add text made=text-273004b901184f11 changed= ms=6 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(70,-10) view="Line Weight Samples" text="MEDIUM: BEYOND"` | green: op:add text made=text-ec74ae75d22a4a6f changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(70,-20) view="Line Weight Samples" text="THIN: DIMENSIONS"` | green: op:add text made=text-423a004ea2de4777 changed= ms=12 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 2,Lines 7,Text Notes 3,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5049. Sketch a hex nut in plan, a washer circle and a curved cable run in a drafting view to show our bolted joint symbol.

- Starts from: a new Structural project
- Ends with: a 1:2 drafting view "Bolt Symbol" with a hexagon from the Inscribed Polygon mode, two concentric circles and a spline line
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Bolt Symbol; Scale=1:2 · expect view: Drafting View +1",
  "ribbon:Annotate:Detail Line · picks (0,0) (12,0) · keys Escape Escape · fields Options Strip: Draw=Inscribed Polygon · expect Lines +6",
  "ribbon:Annotate:Detail Line · picks (0,0) (10,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (0,0) (20,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1",
  "ribbon:Annotate:Detail Line · picks (40,0) (60,25) (80,-10) (100,20) · keys Return Escape Escape · fields Options Strip: Draw=Spline · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Bolt Symbol; Scale=1:2 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 54 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Bolt Symbol reads 'Bolt Symbol'; Scale=1:2 reads '1:2' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (0,0) (12,0) · keys Escape Escape · fields Options Strip: Draw=Inscribed Polygon · expect Lines +6` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Inscribed Polygon set \| picks: (0,0) mm at px (648.0,427.0) on the Drafting View 'Bolt Symbol' view \| (12,0) mm at px (676.8,427.0) on the Drafting View 'Bolt Symbol' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +6": Lines 0 -> 6 (+6, expected +6) |
| `ribbon:Annotate:Detail Line · picks (0,0) (10,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (0,0) mm at px (648.0,427.0) on the Drafting View 'Bolt Symbol' view \| (10,0) mm at px (672.0,427.0) on the Drafting View 'Bolt Symbol' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 6 -> 7 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (0,0) (20,0) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (0,0) mm at px (648.0,427.0) on the Drafting View 'Bolt Symbol' view \| (20,0) mm at px (696.0,427.0) on the Drafting View 'Bolt Symbol' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 7 -> 8 (+1, expected +1) |
| `ribbon:Annotate:Detail Line · picks (40,0) (60,25) (80,-10) (100,20) · keys Return Escape Escape · fields Options Strip: Draw=Spline · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Spline set \| picks: (40,0) mm at px (744.0,427.0) on the Drafting View 'Bolt Symbol' view \| (60,25) mm at px (792.0,367.0) on the Drafting View 'Bolt Symbol' view \| (80,-10) mm at px (840.0,451.0) on the Drafting View 'Bolt Symbol' view \| (100,20) mm at px (888.0,379.0) on the Drafting View 'Bolt Symbol' view \| presses to the tool 4, selection unchanged \| keys: Return (tool Detail Line -> tool Detail Line); Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 8 -> 9 (+1, expected +1) |

### The result

The model holds: Levels 2,Lines 9,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5050. Lay out a switchboard front at 1:10: the cabinet, three breaker rows as rectangles and a label strip.

- Starts from: a new Electrical project
- Ends with: a 1:10 drafting view "Switchboard Front" with a cabinet rectangle, three breaker-row rectangles, a label rectangle and notes
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Switchboard Front; Scale=1:10 · expect view: Drafting View +1",
  "ribbon:Annotate:Detail Line › Rectangle · picks (0,0) (600,900) · keys Escape Escape · fields — · expect Lines +4",
  "ribbon:Annotate:Detail Line › Rectangle · picks (50,600) (550,820) · keys Escape Escape · fields — · expect Lines +4",
  "ribbon:Annotate:Detail Line › Rectangle · picks (50,340) (550,560) · keys Escape Escape · fields — · expect Lines +4",
  "ribbon:Annotate:Detail Line › Rectangle · picks (50,80) (550,300) · keys Escape Escape · fields — · expect Lines +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Switchboard Front; Scale=1:10 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 135 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Switchboard Front reads 'Switchboard Front'; Scale=1:10 reads '1:10' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Detail Line › Rectangle · picks (0,0) (600,900) · keys Escape Escape · fields — · expect Lines +4` | green: pressed 'Detail Line › Rectangle' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Rectangle'; the press stood 92 ms (the menu stood at 45 ms; its row ran 17 ms; it made 0 child widgets native)): the command 'Detail Line › Rectangle' ran; status 'Click the first corner' \| picks: (0,0) mm at px (648.0,427.0) on the Drafting View 'Switchboard Front' view \| (600,900) lay outside the view: panned to bring it to px (972.0,445.0); (600,900) mm at px (972.0,445.0) on the Drafting View 'Switchboard Front' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `ribbon:Annotate:Detail Line › Rectangle · picks (50,600) (550,820) · keys Escape Escape · fields — · expect Lines +4` | green: pressed 'Detail Line › Rectangle' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Rectangle'; the press stood 321 ms (the menu stood at 60 ms; its row ran 234 ms; it made 0 child widgets native)): the command 'Detail Line › Rectangle' ran; status 'Click the first corner' \| picks: (50,600) mm at px (708.0,589.0) on the Drafting View 'Switchboard Front' view \| (550,820) mm at px (948.0,483.4) on the Drafting View 'Switchboard Front' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `ribbon:Annotate:Detail Line › Rectangle · picks (50,340) (550,560) · keys Escape Escape · fields — · expect Lines +4` | green: pressed 'Detail Line › Rectangle' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Rectangle'; the press stood 190 ms (the menu stood at 26 ms; its row ran 146 ms; it made 0 child widgets native)): the command 'Detail Line › Rectangle' ran; status 'Click the first corner' \| picks: (50,340) mm at px (708.0,713.8) on the Drafting View 'Switchboard Front' view \| (550,560) mm at px (948.0,608.2) on the Drafting View 'Switchboard Front' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +4": Lines 8 -> 12 (+4, expected +4) |
| `ribbon:Annotate:Detail Line › Rectangle · picks (50,80) (550,300) · keys Escape Escape · fields — · expect Lines +4` | green: pressed 'Detail Line › Rectangle' on Annotate's Detail panel (through its fold) (through its parent 'Detail Line''s arrow, the row 'Rectangle'; the press stood 140 ms (the menu stood at 31 ms; its row ran 87 ms; it made 0 child widgets native)): the command 'Detail Line › Rectangle' ran; status 'Click the first corner' \| picks: (50,80) mm at px (708.0,838.6) on the Drafting View 'Switchboard Front' view \| (550,300) mm at px (948.0,733.0) on the Drafting View 'Switchboard Front' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +4": Lines 12 -> 16 (+4, expected +4) |

```json
ops_run {"lines":[
  "op:add text at=(100,850) view=\"Switchboard Front\" text=\"MSB-1 MAIN SWITCHBOARD\"",
  "op:add text at=(650,700) view=\"Switchboard Front\" text=\"ROW 1: LIGHTING, 10 A\"",
  "op:add text at=(650,440) view=\"Switchboard Front\" text=\"ROW 2: POWER, 20 A\"",
  "op:add text at=(650,180) view=\"Switchboard Front\" text=\"ROW 3: AIR CONDITIONING, 32 A\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add text at=(100,850) view="Switchboard Front" text="MSB-1 MAIN SWITCHBOARD"` | green: op:add text made=text-bc194c00aecd484a changed= ms=14 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(650,700) view="Switchboard Front" text="ROW 1: LIGHTING, 10 A"` | green: op:add text made=text-4e8e401906824668 changed= ms=12 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(650,440) view="Switchboard Front" text="ROW 2: POWER, 20 A"` | green: op:add text made=text-2c6eed8da4bf47e6 changed= ms=150 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add text at=(650,180) view="Switchboard Front" text="ROW 3: AIR CONDITIONING, 32 A"` | green: op:add text made=text-4a1231cf54b74d3d changed= ms=10 Check "Text Notes +1": Text Notes 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 2,Lines 16,Text Notes 4,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5051. Hatch a concrete block, then put a masking region over the middle so the label has a clean background.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Masked Label Detail" with a crosshatched block, a masking region in its centre and a text note on top
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Masked Label Detail\" scale=1:10",
  "op:add filled region boundary=(0,0) (800,0) (800,500) (0,500) view=\"Masked Label Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add filled region boundary=(150,150) (650,150) (650,350) (150,350) view=\"Masked Label Detail\" type=\"Masking Region\"",
  "op:add text at=(200,230) view=\"Masked Label Detail\" text=\"MASS CONCRETE\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Masked Label Detail" scale=1:10` | green: op:add drafting view made=57ab57ffb63a4471a20ab7a1c075e3cb changed= ms=18 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(0,0) (800,0) (800,500) (0,500) view="Masked Label Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-7258950e04c143fb changed= ms=4 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add filled region boundary=(150,150) (650,150) (650,350) (150,350) view="Masked Label Detail" type="Masking Region"` | green: op:add filled region made=region-1845522a8049426a changed= ms=5 Check "Masking Regions +1": Masking Regions 0 -> 1 (+1, expected +1) |
| `op:add text at=(200,230) view="Masked Label Detail" text="MASS CONCRETE"` | green: op:add text made=text-c453ba5bcf0c4aea changed= ms=10 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |

### The result

The model holds: Filled Regions 1,Levels 3,Masking Regions 1,Text Notes 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5052. Tag the corner column and the first beam on the Level 1 structural plan.

- Starts from: a new Structural project
- Ends with: a column at the origin and an 8 m beam from it on Level 1, each carrying a tag
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\"",
  "op:add beam from=(0,0) to=(8000,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1"` | green: op:add column made=column-1328f9b05c51b3eb changed= ms=16 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,0) to=(8000,0) level="Level 1"` | green: op:add beam made=beam-5341df2098cb5185 changed= ms=9 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Tag by Category · picks (4000,0) · keys Escape Escape · fields — · expect Tags +1",
  "ribbon:Annotate:Tag by Category · picks (0,0) · keys Escape Escape · fields — · expect Tags +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Tag by Category · picks (4000,0) · keys Escape Escape · fields — · expect Tags +1` | green: pressed 'Tag by Category' on Annotate's Tag panel (through its fold): the tool 'Tag by Category' stands \| picks: (4000,0) mm at px (722.4,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Tag by Category -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Tags +1": Tags 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Tag by Category · picks (0,0) · keys Escape Escape · fields — · expect Tags +1` | green: pressed 'Tag by Category' on Annotate's Tag panel (through its fold): the tool 'Tag by Category' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Tag by Category -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Tags +1": Tags 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 1,Structural Columns Tags 1,Structural Framing 1,Structural Framing Tags 1,Tags 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5053. Run a supply duct with one air terminal on it and tag the duct.

- Starts from: a new Mechanical project
- Ends with: one 4 m duct on Level 1 with an air terminal on it and a tag on the duct
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Duct · picks (1000,1000) (5000,1000) · keys Escape Escape · fields — · expect Ducts +1",
  "ribbon:Systems:Air Terminal · picks (3000,1000) · keys Escape Escape · fields — · expect Air Terminals +1",
  "ribbon:Annotate:Tag by Category · picks (1500,1000) · keys Escape Escape · fields — · expect Tags +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Duct · picks (1000,1000) (5000,1000) · keys Escape Escape · fields — · expect Ducts +1` | green: pressed 'Duct' on Systems's HVAC panel: the tool 'Duct' stands \| picks: (1000,1000) mm at px (666.6,408.4) on the plan view \| (5000,1000) mm at px (741.1,408.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ducts +1": Ducts 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Air Terminal · picks (3000,1000) · keys Escape Escape · fields — · expect Air Terminals +1` | green: pressed 'Air Terminal' on Systems's HVAC panel: the command 'Air Terminal' ran; status 'Click a face to place the air terminal' \| picks: (3000,1000) mm at px (703.8,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Diffuser -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `ribbon:Annotate:Tag by Category · picks (1500,1000) · keys Escape Escape · fields — · expect Tags +1` | green: pressed 'Tag by Category' on Annotate's Tag panel (through its fold): the tool 'Tag by Category' stands \| picks: (1500,1000) mm at px (675.9,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Tag by Category -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Tags +1": Tags 0 -> 1 (+1, expected +1) |

### The result

The model holds: Air Terminals 1,Duct Systems 1,Ducts 1,Ducts Tags 1,Levels 2,Tags 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 5054. Put a note on the plant room plan pointing at the south wall: "120/120/120 FIRE RATED WALL".

- Starts from: a new Fire Protection project
- Ends with: four walls on Level 1 and a text note with a leader pointing at the south wall
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=\"Level 1\"",
  "op:add wall from=(6000,0) to=(6000,4000) level=\"Level 1\"",
  "op:add wall from=(6000,4000) to=(0,4000) level=\"Level 1\"",
  "op:add wall from=(0,4000) to=(0,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level="Level 1"` | green: op:add wall made=wall-ba135e15f83a72be changed= ms=41 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level="Level 1"` | green: op:add wall made=wall-1a71f074ca869a23 changed=wall-ba135e15f83a72be ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level="Level 1"` | green: op:add wall made=wall-dcfc20aed4e0181c changed=wall-1a71f074ca869a23 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-400c87c3748ce85c changed=wall-dcfc20aed4e0181c,wall-ba135e15f83a72be ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Text · picks (3000,0) (3000,-1500) · keys 1 2 0 / 1 2 0 / 1 2 0 Space F I R E Space R A T E D Space W A L L Return Escape · fields Options Strip: Leader=on · expect Text Notes +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Text · picks (3000,0) (3000,-1500) · keys 1 2 0 / 1 2 0 / 1 2 0 Space F I R E Space R A T E D Space W A L L Return Escape · fields Options Strip: Leader=on · expect Text Notes +1` | green: pressed 'Text' on Annotate's Text panel (through its fold): the tool 'Text' stands \| fields: Leader=on reads yes \| picks: (3000,0) mm at px (703.8,427.0) on the plan view \| (3000,-1500) mm at px (703.8,454.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: 1 delivered to QLineEdit (taken); 2 delivered to QLineEdit (taken); 0 delivered to QLineEdit (taken); / delivered to QLineEdit (taken); 1 delivered to QLineEdit (taken); 2 delivered to QLineEdit (taken); 0 delivered to QLineEdit (taken); / delivered to QLineEdit (taken); 1 delivered to QLineEdit (taken); 2 delivered to QLineEdit (taken); 0 delivered to QLineEdit (taken); Space delivered to QLineEdit (taken); F delivered to QLineEdit (taken); I delivered to QLineEdit (taken); R delivered to QLineEdit (taken); E delivered to QLineEdit (taken); Space delivered to QLineEdit (taken); R delivered to QLineEdit (taken); A delivered to QLineEdit (taken); T delivered to QLineEdit (taken); E delivered to QLineEdit (taken); D delivered to QLineEdit (taken); Space delivered to QLineEdit (taken); W delivered to QLineEdit (taken); A delivered to QLineEdit (taken); L delivered to QLineEdit (taken); L delivered to QLineEdit (taken); Return (tool Text -> tool Text, the edit field took it and closed); Escape (tool Text -> no tool) Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Text Notes 1,Walls 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 5055. Run a 100 mm sewer pipe along the corridor wall and tag it.

- Starts from: a new Hydraulic project
- Ends with: a corridor wall and a 100 mm pipe 6 m long on Level 1, with a pipe tag
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=\"Level 1\"",
  "op:add pipe from=(0,500) to=(6000,500) level=\"Level 1\" diameter=100 elevation=2400"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level="Level 1"` | green: op:add wall made=wall-d9ca0e173826ca93 changed= ms=6 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(0,500) to=(6000,500) level="Level 1" diameter=100 elevation=2400` | green: op:add pipe made=pipe-3b34f6cba457a206,system-7b95261f35f1beaf changed= ms=4 Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Tag by Category · picks (3000,500) · keys Escape Escape · fields — · expect Tags +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Tag by Category · picks (3000,500) · keys Escape Escape · fields — · expect Tags +1` | green: pressed 'Tag by Category' on Annotate's Tag panel (through its fold): the tool 'Tag by Category' stands \| picks: (3000,500) mm at px (703.8,417.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Tag by Category -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Tags +1": Tags 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 1,Pipes Tags 1,Piping Systems 1,Tags 1,Walls 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 5056. Add terracotta roof tile and a charcoal Colorbond sheet for the roof, with the tile repeat set to 330 mm.

- Starts from: a new Architectural project
- Ends with: file materials Roof Tile Terracotta and Roof Sheet Charcoal, the tile with a 330 mm repeat and the sheet with a colour and a metallic finish
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material library=roof_tile_terracotta name=\"Roof Tile Terracotta\"",
  "op:set material name=\"Roof Tile Terracotta\" key=texture_size value=330",
  "op:add material library=box_profile name=\"Roof Sheet Charcoal\"",
  "op:set material name=\"Roof Sheet Charcoal\" key=render_colour value=#3B3F44",
  "op:set material name=\"Roof Sheet Charcoal\" key=metallic value=0.4",
  "op:set material name=\"Roof Sheet Charcoal\" key=roughness value=0.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material library=roof_tile_terracotta name="Roof Tile Terracotta"` | green: op:add material made="Roof Tile Terracotta" changed= ms=250 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Roof Tile Terracotta" key=texture_size value=330` | green: op:set material made= changed="Roof Tile Terracotta" ms=23 Check "every count unchanged": the counts: no count changed |
| `op:add material library=box_profile name="Roof Sheet Charcoal"` | green: op:add material made="Roof Sheet Charcoal" changed= ms=90 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Roof Sheet Charcoal" key=render_colour value=#3B3F44` | green: op:set material made= changed="Roof Sheet Charcoal" ms=50 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Roof Sheet Charcoal" key=metallic value=0.4` | green: op:set material made= changed="Roof Sheet Charcoal" ms=693 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Roof Sheet Charcoal" key=roughness value=0.5` | green: op:set material made= changed="Roof Sheet Charcoal" ms=27 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5057. Add the pipe materials for the hydraulic model: grey PVC and copper, with the thermal values on the copper.

- Starts from: a new Hydraulic project
- Ends with: file materials PVC Pipe Grey and Copper Pipe, the copper from the copper set with density and heat conductivity
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material name=\"PVC Pipe Grey\"",
  "op:set material name=\"PVC Pipe Grey\" key=render_colour value=#9A9EA3",
  "op:set material name=\"PVC Pipe Grey\" key=roughness value=0.4",
  "op:set material name=\"PVC Pipe Grey\" key=manufacturer value=\"Vinidex\"",
  "op:add material library=copper name=\"Copper Pipe\"",
  "op:set material name=\"Copper Pipe\" key=density value=8960",
  "op:set material name=\"Copper Pipe\" key=heat_conductivity value=385"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material name="PVC Pipe Grey"` | green: op:add material made="PVC Pipe Grey" changed= ms=221 Check "every count unchanged": the counts: no count changed |
| `op:set material name="PVC Pipe Grey" key=render_colour value=#9A9EA3` | green: op:set material made= changed="PVC Pipe Grey" ms=28 Check "every count unchanged": the counts: no count changed |
| `op:set material name="PVC Pipe Grey" key=roughness value=0.4` | green: op:set material made= changed="PVC Pipe Grey" ms=35 Check "every count unchanged": the counts: no count changed |
| `op:set material name="PVC Pipe Grey" key=manufacturer value="Vinidex"` | green: op:set material made= changed="PVC Pipe Grey" ms=22 Check "every count unchanged": the counts: no count changed |
| `op:add material library=copper name="Copper Pipe"` | green: op:add material made="Copper Pipe" changed= ms=63 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Copper Pipe" key=density value=8960` | green: op:set material made= changed="Copper Pipe" ms=29 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Copper Pipe" key=heat_conductivity value=385` | green: op:set material made= changed="Copper Pipe" ms=186 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 5058. Add a hot-dip galvanised finish for the cable trays and a copper material for the conductors.

- Starts from: a new Electrical project
- Ends with: file materials Cable Tray Galvanised and Conductor Copper with colours, roughness and descriptions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material library=steel_galvanised name=\"Cable Tray Galvanised\"",
  "op:set material name=\"Cable Tray Galvanised\" key=description value=\"Hot-dip galvanised ladder tray\"",
  "op:set material name=\"Cable Tray Galvanised\" key=roughness value=0.55",
  "op:add material name=\"Conductor Copper\"",
  "op:set material name=\"Conductor Copper\" key=render_colour value=#B87333",
  "op:set material name=\"Conductor Copper\" key=metallic value=0.95",
  "op:set material name=\"Conductor Copper\" key=description value=\"Stranded copper conductor\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add material library=steel_galvanised name="Cable Tray Galvanised"` | green: op:add material made="Cable Tray Galvanised" changed= ms=310 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Cable Tray Galvanised" key=description value="Hot-dip galvanised ladder tray"` | green: op:set material made= changed="Cable Tray Galvanised" ms=24 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Cable Tray Galvanised" key=roughness value=0.55` | green: op:set material made= changed="Cable Tray Galvanised" ms=22 Check "every count unchanged": the counts: no count changed |
| `op:add material name="Conductor Copper"` | green: op:add material made="Conductor Copper" changed= ms=62 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Conductor Copper" key=render_colour value=#B87333` | green: op:set material made= changed="Conductor Copper" ms=71 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Conductor Copper" key=metallic value=0.95` | green: op:set material made= changed="Conductor Copper" ms=25 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Conductor Copper" key=description value="Stranded copper conductor"` | green: op:set material made= changed="Conductor Copper" ms=16 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 5059. Add the intumescent paint we spec on steelwork for a 90 minute rating, with its colour, supplier and cost.

- Starts from: a new Fire Protection project
- Ends with: a file material Intumescent Coating 90 with a pale grey colour, a supplier, a cost and a description naming the rating
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material name=\"Intumescent Coating 90\"",
  "op:set material name=\"Intumescent Coating 90\" key=render_colour value=#E4E6E8",
  "op:set material name=\"Intumescent Coating 90\" key=glow value=0.25",
  "op:set material name=\"Intumescent Coating 90\" key=manufacturer value=\"Sherwin Fire Protection\"",
  "op:set material name=\"Intumescent Coating 90\" key=cost value=62",
  "op:set material name=\"Intumescent Coating 90\" key=description value=\"Water-based intumescent, 90 minute FRL, 1.9 mm DFT\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add material name="Intumescent Coating 90"` | green: op:add material made="Intumescent Coating 90" changed= ms=54 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Intumescent Coating 90" key=render_colour value=#E4E6E8` | green: op:set material made= changed="Intumescent Coating 90" ms=31 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Intumescent Coating 90" key=glow value=0.25` | green: op:set material made= changed="Intumescent Coating 90" ms=29 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Intumescent Coating 90" key=manufacturer value="Sherwin Fire Protection"` | green: op:set material made= changed="Intumescent Coating 90" ms=20 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Intumescent Coating 90" key=cost value=62` | green: op:set material made= changed="Intumescent Coating 90" ms=768 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Intumescent Coating 90" key=description value="Water-based intumescent, 90 minute FRL, 1.9 mm DFT"` | green: op:set material made= changed="Intumescent Coating 90" ms=24 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 5060. Add three concrete finishes for the structural model: smooth, board-formed and rough, with the strength noted on each.

- Starts from: a new Structural project
- Ends with: file materials Concrete Smooth, Concrete Board Formed and Concrete Rough from three texture sets, each with a keynote and a strength
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add material library=concrete_smooth name=\"Concrete Smooth\"",
  "op:set material name=\"Concrete Smooth\" key=compressive_strength value=40",
  "op:add material library=concrete_board_formed name=\"Concrete Board Formed\"",
  "op:set material name=\"Concrete Board Formed\" key=texture_size value=2400",
  "op:set material name=\"Concrete Board Formed\" key=compressive_strength value=32",
  "op:add material library=concrete_rough name=\"Concrete Rough\"",
  "op:set material name=\"Concrete Rough\" key=compressive_strength value=25",
  "op:set material name=\"Concrete Rough\" key=material_keynote value=03310"
]}
```

| Line | UNION answered |
|---|---|
| `op:add material library=concrete_smooth name="Concrete Smooth"` | green: op:add material made="Concrete Smooth" changed= ms=207 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete Smooth" key=compressive_strength value=40` | green: op:set material made= changed="Concrete Smooth" ms=23 Check "every count unchanged": the counts: no count changed |
| `op:add material library=concrete_board_formed name="Concrete Board Formed"` | green: op:add material made="Concrete Board Formed" changed= ms=53 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete Board Formed" key=texture_size value=2400` | green: op:set material made= changed="Concrete Board Formed" ms=30 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete Board Formed" key=compressive_strength value=32` | green: op:set material made= changed="Concrete Board Formed" ms=28 Check "every count unchanged": the counts: no count changed |
| `op:add material library=concrete_rough name="Concrete Rough"` | green: op:add material made="Concrete Rough" changed= ms=64 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete Rough" key=compressive_strength value=25` | green: op:set material made= changed="Concrete Rough" ms=32 Check "every count unchanged": the counts: no count changed |
| `op:set material name="Concrete Rough" key=material_keynote value=03310` | green: op:set material made= changed="Concrete Rough" ms=31 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5061. I drew one detail line too many in the lintel detail. Take the last one back, then bring it back again.

- Starts from: a new Architectural project
- Ends with: a drafting view "Lintel Check" with two detail lines standing after the undo and redo
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Lintel Check\" scale=1:10",
  "op:add detail line points=(0,0) (900,0) view=\"Lintel Check\" style=\"Wide Lines\"",
  "op:add detail line points=(0,-90) (900,-90) view=\"Lintel Check\" style=\"Wide Lines\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Lintel Check" scale=1:10` | green: op:add drafting view made=f953a28dcd214d3593d4182253828a89 changed= ms=48 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (900,0) view="Lintel Check" style="Wide Lines"` | green: op:add detail line made=detail-a6000e1310154456 changed= ms=120 Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,-90) (900,-90) view="Lintel Check" style="Wide Lines"` | green: op:add detail line made=detail-791d3a676164493d changed= ms=12 Check "Lines +1": Lines 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect Lines -1",
  "qa:Redo · picks — · keys — · fields — · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect Lines -1` | green: QToolButton pressed; a command ran Check "Lines -1": Lines 2 -> 1 (-1, expected -1) |
| `qa:Redo · picks — · keys — · fields — · expect Lines +1` | green: QToolButton pressed; a command ran Check "Lines +1": Lines 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Lines 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5062. Draw the kitchen bench section at 1:10: a 33 mm stone top, the cabinet carcase, a kickboard and the splashback.

- Starts from: a new Architectural project
- Ends with: a 1:10 drafting view "Kitchen Bench Detail" with the cabinet, top, kickboard, splashback tiles, a hatch, two notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Kitchen Bench Detail\" scale=1:10",
  "op:add detail line points=(0,100) (600,100) (600,820) (0,820) (0,100) view=\"Kitchen Bench Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(30,0) (30,100) (570,100) (570,0) (30,0) view=\"Kitchen Bench Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-20,820) (640,820) (640,853) (-20,853) (-20,820) view=\"Kitchen Bench Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(0,853) (0,1400) (20,1400) (20,853) view=\"Kitchen Bench Detail\" style=\"Wide Lines\"",
  "op:add filled region boundary=(-20,820) (640,820) (640,853) (-20,853) view=\"Kitchen Bench Detail\" pattern=\"Solid fill\"",
  "op:add text at=(900,900) view=\"Kitchen Bench Detail\" text=\"33 ENGINEERED STONE BENCHTOP\" leader_to=(640,840)",
  "op:add text at=(900,1200) view=\"Kitchen Bench Detail\" text=\"TILED SPLASHBACK TO 600 ABOVE BENCH\" leader_to=(20,1200)",
  "op:add dimension from=(30,0) to=(30,100) view=\"Kitchen Bench Detail\" offset=-150",
  "op:add dimension from=(0,820) to=(0,100) view=\"Kitchen Bench Detail\" offset=-150"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Kitchen Bench Detail" scale=1:10` | green: op:add drafting view made=35aa736dec384419bd24f4e0615c11b6 changed= ms=47 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,100) (600,100) (600,820) (0,820) (0,100) view="Kitchen Bench Detail" style="Wide Lines"` | green: op:add detail line made=detail-41926cb723744143,detail-5760be26f107483b,detail-a5d247a5e64d447b,detail-39b66c28ef384169 changed= ms=29 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(30,0) (30,100) (570,100) (570,0) (30,0) view="Kitchen Bench Detail" style="Wide Lines"` | green: op:add detail line made=detail-85acb263c98a48f8,detail-fd23cb6144a3488e,detail-360c5d845c3e4121,detail-5c91d64c2e604c1c changed= ms=5 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-20,820) (640,820) (640,853) (-20,853) (-20,820) view="Kitchen Bench Detail" style="Wide Lines"` | green: op:add detail line made=detail-bec5915afaaf4e83,detail-418428e229f84469,detail-ea07d5ab9ab74b11,detail-6f3aee34088b44f2 changed= ms=51 Check "Lines +4": Lines 8 -> 12 (+4, expected +4) |
| `op:add detail line points=(0,853) (0,1400) (20,1400) (20,853) view="Kitchen Bench Detail" style="Wide Lines"` | green: op:add detail line made=detail-dff9a63cd85140e8,detail-61d7735a7b4146b6,detail-d011b8d1ce8e40d2 changed= ms=4 Check "Lines +3": Lines 12 -> 15 (+3, expected +3) |
| `op:add filled region boundary=(-20,820) (640,820) (640,853) (-20,853) view="Kitchen Bench Detail" pattern="Solid fill"` | green: op:add filled region made=region-e37958e777f045b0 changed= ms=8 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add text at=(900,900) view="Kitchen Bench Detail" text="33 ENGINEERED STONE BENCHTOP" leader_to=(640,840)` | green: op:add text made=text-69c52c263f0c4c75 changed= ms=14 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(900,1200) view="Kitchen Bench Detail" text="TILED SPLASHBACK TO 600 ABOVE BENCH" leader_to=(20,1200)` | green: op:add text made=text-c81b0cce913d4fa9 changed= ms=42 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(30,0) to=(30,100) view="Kitchen Bench Detail" offset=-150` | green: op:add dimension made=dim-fc47ac947ff94faa changed= ms=415 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(0,820) to=(0,100) view="Kitchen Bench Detail" offset=-150` | green: op:add dimension made=dim-8ffefc5fd0eb434d changed= ms=8 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Filled Regions 1,Levels 3,Lines 15,Text Notes 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 5063. Detail a saw-cut control joint in a 150 mm ground slab at 1:5, with the cut depth, sealant and mesh position noted.

- Starts from: a new Structural project
- Ends with: a 1:5 drafting view "Control Joint Detail" with the slab outline, the sawcut, a sealant strip, a mesh line, a hatch, two notes and a depth dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Control Joint Detail\" scale=1:5",
  "op:add detail line points=(-300,0) (-6,0) (-6,-45) (6,-45) (6,0) (300,0) (300,-150) (-300,-150) (-300,0) view=\"Control Joint Detail\" style=\"Wide Lines\"",
  "op:add filled region boundary=(-300,0) (-6,0) (-6,-45) (6,-45) (6,0) (300,0) (300,-150) (-300,-150) view=\"Control Joint Detail\" pattern=\"Diagonal crosshatch\"",
  "op:add detail line points=(-300,-100) (300,-100) view=\"Control Joint Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(-6,-20) (6,-20) view=\"Control Joint Detail\" style=\"Medium Lines\"",
  "op:add text at=(450,100) view=\"Control Joint Detail\" text=\"SAWCUT 5 WIDE x 45 DEEP, SEALED\" leader_to=(6,-30)",
  "op:add text at=(450,-220) view=\"Control Joint Detail\" text=\"SL82 MESH, 50 FROM BOTTOM\" leader_to=(200,-100)",
  "op:add dimension from=(-6,0) to=(-6,-45) view=\"Control Joint Detail\" offset=-50"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Control Joint Detail" scale=1:5` | green: op:add drafting view made=77c03cfc430a47eba4161c36000fddf7 changed= ms=440 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-300,0) (-6,0) (-6,-45) (6,-45) (6,0) (300,0) (300,-150) (-300,-150) (-300,0) view="Control Joint Detail" style="Wide Lines"` | green: op:add detail line made=detail-67d304d0f1c9416f,detail-4d102025d064477c,detail-823734e2dcb44913,detail-7d50e00aa2e34904,detail-df03f75c1bf049a8,detail-908680c97ec7491b,detail-8643d55f441144bf,detail-795780ce60ed49d3 changed= ms=7 Check "Lines +8": Lines 0 -> 8 (+8, expected +8) |
| `op:add filled region boundary=(-300,0) (-6,0) (-6,-45) (6,-45) (6,0) (300,0) (300,-150) (-300,-150) view="Control Joint Detail" pattern="Diagonal crosshatch"` | green: op:add filled region made=region-2afb2ae1d32f470b changed= ms=9 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(-300,-100) (300,-100) view="Control Joint Detail" style="Medium Lines"` | green: op:add detail line made=detail-7d5d06f0033642ae changed= ms=3 Check "Lines +1": Lines 8 -> 9 (+1, expected +1) |
| `op:add detail line points=(-6,-20) (6,-20) view="Control Joint Detail" style="Medium Lines"` | green: op:add detail line made=detail-a5e8a5b617dd4a1a changed= ms=28 Check "Lines +1": Lines 9 -> 10 (+1, expected +1) |
| `op:add text at=(450,100) view="Control Joint Detail" text="SAWCUT 5 WIDE x 45 DEEP, SEALED" leader_to=(6,-30)` | green: op:add text made=text-c82b2b0df6764ac4 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(450,-220) view="Control Joint Detail" text="SL82 MESH, 50 FROM BOTTOM" leader_to=(200,-100)` | green: op:add text made=text-e092296e141b47da changed= ms=4 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-6,0) to=(-6,-45) view="Control Joint Detail" offset=-50` | green: op:add dimension made=dim-a77c0aeddb3940d6 changed= ms=73 note=offset -50: the dimension line stands 50 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Filled Regions 1,Levels 2,Lines 10,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 5064. Draw the pipe clip fixing a 50 mm pipe to a concrete soffit at 1:5, with the anchor and the clip spacing noted.

- Starts from: a new Hydraulic project
- Ends with: a 1:5 drafting view "Pipe Clip Detail" with the soffit, a pipe circle, a clip strap, an anchor, notes and a diameter dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Pipe Clip Detail; Scale=1:5 · expect view: Drafting View +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Pipe Clip Detail; Scale=1:5 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 66 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Pipe Clip Detail reads 'Pipe Clip Detail'; Scale=1:5 reads '1:5' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add detail line points=(-200,0) (200,0) (200,150) (-200,150) (-200,0) view=\"Pipe Clip Detail\" style=\"Wide Lines\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add detail line points=(-200,0) (200,0) (200,150) (-200,150) (-200,0) view="Pipe Clip Detail" style="Wide Lines"` | green: op:add detail line made=detail-aad1d580ff0044c8,detail-6dd0345d9c104ac5,detail-c599888cf68a463b,detail-5a9e917696b546ea changed= ms=9 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Detail Line · picks (0,-45) (25,-45) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Detail Line · picks (0,-45) (25,-45) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (0,-45) mm at px (648.0,470.2) on the Drafting View 'Pipe Clip Detail' view \| (25,-45) mm at px (672.0,470.2) on the Drafting View 'Pipe Clip Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 4 -> 5 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add detail line points=(-35,-35) (-35,-8) (-25,0) (25,0) (35,-8) (35,-35) view=\"Pipe Clip Detail\" style=\"Medium Lines\"",
  "op:add detail line points=(-30,0) (-30,120) (-24,120) (-24,0) view=\"Pipe Clip Detail\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add detail line points=(-35,-35) (-35,-8) (-25,0) (25,0) (35,-8) (35,-35) view="Pipe Clip Detail" style="Medium Lines"` | green: op:add detail line made=detail-a74f819b9ca7446b,detail-621f07f278df480d,detail-39b6fdf6c05a4118,detail-260476d3c83c4300,detail-532b3a955cb1424c changed= ms=185 Check "Lines +5": Lines 5 -> 10 (+5, expected +5) |
| `op:add detail line points=(-30,0) (-30,120) (-24,120) (-24,0) view="Pipe Clip Detail"` | green: op:add detail line made=detail-869d9d36f3e24d12,detail-3a26451024ed426c,detail-627d1438624b484e changed= ms=44 Check "Lines +3": Lines 10 -> 13 (+3, expected +3) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Diameter · picks (25,-45) (120,-100) · keys Escape Escape · fields — · expect Dimensions +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Diameter · picks (25,-45) (120,-100) · keys Escape Escape · fields — · expect Dimensions +1` | green: pressed 'Diameter' on Annotate's Dimension panel: the tool 'Diameter' stands \| picks: (25,-45) mm at px (672.0,470.2) on the Drafting View 'Pipe Clip Detail' view \| (120,-100) mm at px (763.2,523.0) on the Drafting View 'Pipe Clip Detail' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Diameter -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add text at=(300,80) view=\"Pipe Clip Detail\" text=\"M6 DROP-IN ANCHOR\" leader_to=(-24,80)",
  "op:add text at=(300,-120) view=\"Pipe Clip Detail\" text=\"CLIPS AT 1200 MAXIMUM CENTRES\" leader_to=(35,-25)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add text at=(300,80) view="Pipe Clip Detail" text="M6 DROP-IN ANCHOR" leader_to=(-24,80)` | green: op:add text made=text-25cab6c9b3e145b2 changed= ms=146 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(300,-120) view="Pipe Clip Detail" text="CLIPS AT 1200 MAXIMUM CENTRES" leader_to=(35,-25)` | green: op:add text made=text-72b484a4ca4f4490 changed= ms=13 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Levels 2,Lines 13,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5065. Detail a duct passing through a fire wall at 1:10 with a fire damper in the wall, the retaining angle and the packing.

- Starts from: a new Mechanical project
- Ends with: a 1:10 drafting view "Fire Damper Detail" with the wall, duct, damper sleeve, angles, packing batt, notes and a dimension
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Fire Damper Detail\" scale=1:10",
  "op:add detail line points=(0,-600) (190,-600) (190,-200) (0,-200) (0,-600) view=\"Fire Damper Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(0,200) (190,200) (190,600) (0,600) (0,200) view=\"Fire Damper Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-500,-200) (700,-200) (700,200) (-500,200) (-500,-200) view=\"Fire Damper Detail\" style=\"Wide Lines\"",
  "op:add detail line points=(-40,-215) (230,-215) (230,215) (-40,215) (-40,-215) view=\"Fire Damper Detail\" style=\"Medium Lines\"",
  "op:add insulation from=(-30,-208) to=(220,-208) view=\"Fire Damper Detail\" width=15",
  "op:add text at=(900,0) view=\"Fire Damper Detail\" text=\"FIRE DAMPER IN SLEEVE, 120 MIN\" leader_to=(95,0)",
  "op:add text at=(900,350) view=\"Fire Damper Detail\" text=\"MINERAL WOOL PACKING BOTH SIDES\" leader_to=(190,330)",
  "op:add dimension from=(-500,-200) to=(-500,200) view=\"Fire Damper Detail\" offset=150"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Fire Damper Detail" scale=1:10` | green: op:add drafting view made=8e4753789f854bbbbdc8bbe6aa36a69e changed= ms=10 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,-600) (190,-600) (190,-200) (0,-200) (0,-600) view="Fire Damper Detail" style="Wide Lines"` | green: op:add detail line made=detail-08b6615e4b2f43d6,detail-98422fccf9eb4f69,detail-15c3271d404a400e,detail-a97063580b014cbf changed= ms=20 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(0,200) (190,200) (190,600) (0,600) (0,200) view="Fire Damper Detail" style="Wide Lines"` | green: op:add detail line made=detail-456b0756ef6a4edd,detail-87ff2bf3d44446d6,detail-4df68982ce25400d,detail-ac0b48e80b3b4dae changed= ms=5 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(-500,-200) (700,-200) (700,200) (-500,200) (-500,-200) view="Fire Damper Detail" style="Wide Lines"` | green: op:add detail line made=detail-5f59c3f1bbc64058,detail-5ebe3ff1b2a2412c,detail-1fd3cf830cca4412,detail-aa94fd4629d144f4 changed= ms=151 Check "Lines +4": Lines 8 -> 12 (+4, expected +4) |
| `op:add detail line points=(-40,-215) (230,-215) (230,215) (-40,215) (-40,-215) view="Fire Damper Detail" style="Medium Lines"` | green: op:add detail line made=detail-f62c93c2954c467d,detail-12861a077be44279,detail-80111ce9939743c6,detail-eb8ea8a76b714758 changed= ms=3 Check "Lines +4": Lines 12 -> 16 (+4, expected +4) |
| `op:add insulation from=(-30,-208) to=(220,-208) view="Fire Damper Detail" width=15` | green: op:add insulation made=insul-4ada9a403ba62037 changed= ms=3 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) |
| `op:add text at=(900,0) view="Fire Damper Detail" text="FIRE DAMPER IN SLEEVE, 120 MIN" leader_to=(95,0)` | green: op:add text made=text-8b5195c442fc47cc changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(900,350) view="Fire Damper Detail" text="MINERAL WOOL PACKING BOTH SIDES" leader_to=(190,330)` | green: op:add text made=text-8b7c8d19c4f24e64 changed= ms=3 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-500,-200) to=(-500,200) view="Fire Damper Detail" offset=150` | green: op:add dimension made=dim-449f64bffc84428e changed= ms=207 note=offset 150: the dimension line stands 150 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Detail Items 1,Dimensions 1,Levels 2,Lines 16,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5066. Draw the plan of a stepped duct transition in a drafting view and put a chain dimension along its three legs.

- Starts from: a new Mechanical project
- Ends with: a 1:20 drafting view "Duct Transition Plan" with three joined duct legs drawn as lines, a dimension chain along them, a diameter note and a title
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Duct Transition Plan\" scale=1:20",
  "op:add detail line points=(0,0) (1200,0) view=\"Duct Transition Plan\" style=\"Wide Lines\"",
  "op:add detail line points=(1200,0) (2200,0) view=\"Duct Transition Plan\" style=\"Wide Lines\"",
  "op:add detail line points=(2200,0) (3000,0) view=\"Duct Transition Plan\" style=\"Wide Lines\"",
  "op:add dimension chain points=(0,0) (1200,0) (2200,0) (3000,0) view=\"Duct Transition Plan\" offset=-300",
  "op:add text at=(0,400) view=\"Duct Transition Plan\" text=\"600 x 300 TO 400 x 300 TO 300 DIA\"",
  "op:add text at=(0,-700) view=\"Duct Transition Plan\" text=\"DUCT TRANSITION PLAN 1:20\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Duct Transition Plan" scale=1:20` | green: op:add drafting view made=5a6187ff232b46ba81b9e46ce9243802 changed= ms=12 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (1200,0) view="Duct Transition Plan" style="Wide Lines"` | green: op:add detail line made=detail-c5ce47f8bbdc4a5f changed= ms=3 Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(1200,0) (2200,0) view="Duct Transition Plan" style="Wide Lines"` | green: op:add detail line made=detail-16ef92fbb327470f changed= ms=3 Check "Lines +1": Lines 1 -> 2 (+1, expected +1) |
| `op:add detail line points=(2200,0) (3000,0) view="Duct Transition Plan" style="Wide Lines"` | green: op:add detail line made=detail-6856937dc7f54d17 changed= ms=3 Check "Lines +1": Lines 2 -> 3 (+1, expected +1) |
| `op:add dimension chain points=(0,0) (1200,0) (2200,0) (3000,0) view="Duct Transition Plan" offset=-300` | green: op:add dimension chain made=dimstr-2ff6a2b578234332 changed= ms=28 note=segments 1200, 1000, 800; offset -300: the dimension line stands 300 mm to the right of the direction from the first point to the last (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,400) view="Duct Transition Plan" text="600 x 300 TO 400 x 300 TO 300 DIA"` | green: op:add text made=text-23e18ea44b264871 changed= ms=7 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-700) view="Duct Transition Plan" text="DUCT TRANSITION PLAN 1:20"` | green: op:add text made=text-d571d4291d5a4956 changed= ms=6 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Levels 2,Lines 3,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

## 5067. Draw a 20 mm conduit and a socket box in a stud wall at 1:5 with the stud, the lining and the box depth.

- Starts from: a new Electrical project
- Ends with: a 1:5 drafting view "Conduit In Stud Wall" with studs, linings, a conduit circle, a socket box, notes and two dimensions
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Conduit In Stud Wall; Scale=1:5 · expect view: Drafting View +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Conduit In Stud Wall; Scale=1:5 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 129 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Conduit In Stud Wall reads 'Conduit In Stud Wall'; Scale=1:5 reads '1:5' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add detail line points=(0,0) (70,0) (70,300) (0,300) (0,0) view=\"Conduit In Stud Wall\" style=\"Wide Lines\"",
  "op:add detail line points=(-13,0) (0,0) (0,300) (-13,300) (-13,0) view=\"Conduit In Stud Wall\" style=\"Wide Lines\"",
  "op:add detail line points=(70,0) (83,0) (83,300) (70,300) view=\"Conduit In Stud Wall\" style=\"Wide Lines\"",
  "op:add detail line points=(-13,100) (-13,180) (-45,180) (-45,100) (-13,100) view=\"Conduit In Stud Wall\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add detail line points=(0,0) (70,0) (70,300) (0,300) (0,0) view="Conduit In Stud Wall" style="Wide Lines"` | green: op:add detail line made=detail-c495d7b3506e49cb,detail-2f3139da697d425b,detail-8f641e82d73742d2,detail-818c8af812ee4b4d changed= ms=8 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add detail line points=(-13,0) (0,0) (0,300) (-13,300) (-13,0) view="Conduit In Stud Wall" style="Wide Lines"` | green: op:add detail line made=detail-7bf46f2cba2e4a2b,detail-e2b62edf02534180,detail-49c01b799e2d4426,detail-7ef82f544db244ab changed= ms=75 Check "Lines +4": Lines 4 -> 8 (+4, expected +4) |
| `op:add detail line points=(70,0) (83,0) (83,300) (70,300) view="Conduit In Stud Wall" style="Wide Lines"` | green: op:add detail line made=detail-68b534b0e6f54daa,detail-633523acbd8741d0,detail-add9dab54e52465d changed= ms=114 Check "Lines +3": Lines 8 -> 11 (+3, expected +3) |
| `op:add detail line points=(-13,100) (-13,180) (-45,180) (-45,100) (-13,100) view="Conduit In Stud Wall"` | green: op:add detail line made=detail-060a5a1d6bbb4b33,detail-1d143e5cdfeb4c22,detail-cf322fd2910a448e,detail-70c2bad542e5476f changed= ms=6 Check "Lines +4": Lines 11 -> 15 (+4, expected +4) |

```json
steps_run {"steps":[
  "ribbon:Annotate:Detail Line · picks (35,90) (45,90) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Annotate:Detail Line · picks (35,90) (45,90) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Detail Line' on Annotate's Detail panel (through its fold): the tool 'Detail Line' stands \| fields: Draw=Circle set \| picks: (35,90) mm at px (681.6,340.6) on the Drafting View 'Conduit In Stud Wall' view \| (45,90) mm at px (691.2,340.6) on the Drafting View 'Conduit In Stud Wall' view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Detail Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 15 -> 16 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add text at=(300,230) view=\"Conduit In Stud Wall\" text=\"20 mm CONDUIT IN STUD CAVITY\" leader_to=(35,100)",
  "op:add text at=(-300,260) view=\"Conduit In Stud Wall\" text=\"SINGLE SOCKET BOX 32 DEEP\" leader_to=(-45,150)",
  "op:add dimension from=(-45,100) to=(-45,180) view=\"Conduit In Stud Wall\" offset=-60",
  "op:add dimension from=(-45,100) to=(-13,100) view=\"Conduit In Stud Wall\" offset=-40"
]}
```

| Line | UNION answered |
|---|---|
| `op:add text at=(300,230) view="Conduit In Stud Wall" text="20 mm CONDUIT IN STUD CAVITY" leader_to=(35,100)` | green: op:add text made=text-384d90ad0c1d4aec changed= ms=9 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(-300,260) view="Conduit In Stud Wall" text="SINGLE SOCKET BOX 32 DEEP" leader_to=(-45,150)` | green: op:add text made=text-8ad987a7abcd455a changed= ms=8 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(-45,100) to=(-45,180) view="Conduit In Stud Wall" offset=-60` | green: op:add dimension made=dim-6f1316e8ea644c02 changed= ms=26 note=offset -60: the dimension line stands 60 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(-45,100) to=(-13,100) view="Conduit In Stud Wall" offset=-40` | green: op:add dimension made=dim-09abe6a39f7a410d changed= ms=16 note=offset -40: the dimension line stands 40 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |

### The result

The model holds: Dimensions 2,Levels 2,Lines 16,Text Notes 2,mark: Elevation 4,view: 3D View 1,view: Drafting View 1,view: Elevation 4,view: Floor Plan 3.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
