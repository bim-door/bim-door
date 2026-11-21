# UNION examples: Setting out and structure

64 drafting jobs, each the request in plain words, the exact calls an AI sends to UNION, and UNION's answer to each, played green on UNION 1.0.0-beta.2.

## 1001. Set up the levels for a four-storey steel office, 3.6 m floor to floor, with the roof at 14.4 m.

- Starts from: a new Structural project
- Ends with: levels Level 1 to Level 4 at 0, 3600, 7200 and 10800 and a Roof level at 14400, with one steel column standing from Level 1 to the roof
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=3600",
  "op:add level elevation=7200 name=\"Level 3\"",
  "op:add level elevation=10800 name=\"Level 4\"",
  "op:add level elevation=14400 name=\"Roof\"",
  "op:add column at=(0,0) level=\"Level 1\" top=Roof type=310UC158"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=3600` | green: op:set made= changed="Level 2" ms=23 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=7200 name="Level 3"` | green: op:add level made="level-Level 3" changed= ms=52 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add level elevation=10800 name="Level 4"` | green: op:add level made="level-Level 4" changed= ms=9 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add level elevation=14400 name="Roof"` | green: op:add level made=level-Roof changed= ms=8 Check "Levels +1": Levels 4 -> 5 (+1, expected +1) |
| `op:add column at=(0,0) level="Level 1" top=Roof type=310UC158` | green: op:add column made=column-11a38e63252f663a changed= ms=4 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 5,Structural Columns 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1002. Rename the two template levels Ground Floor and First Floor and put the first floor at 4200 mm.

- Starts from: a new Structural project
- Ends with: the levels named Ground Floor and First Floor, the first floor at 4200 mm, with a column and a beam placed on the new names
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 1\" key=Name value=\"Ground Floor\"",
  "op:set id=\"Level 2\" key=Elevation value=4200",
  "op:set id=\"Level 2\" key=Name value=\"First Floor\"",
  "op:add column at=(0,0) level=\"Ground Floor\" top=\"First Floor\" type=250UC89.5",
  "op:add beam from=(0,0) to=(6000,0) level=\"First Floor\" type=360UB50.7"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 1" key=Name value="Ground Floor"` | green: op:set made= changed="Level 1" ms=518 Check "every count unchanged": the counts: no count changed |
| `op:set id="Level 2" key=Elevation value=4200` | green: op:set made= changed="Level 2" ms=4 Check "every count unchanged": the counts: no count changed |
| `op:set id="Level 2" key=Name value="First Floor"` | green: op:set made= changed="Level 2" ms=7 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level="Ground Floor" top="First Floor" type=250UC89.5` | green: op:add column made=column-86859f543372f17d changed= ms=9 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,0) to=(6000,0) level="First Floor" type=360UB50.7` | green: op:add beam made=beam-f6ade2a5add715a8 changed= ms=10 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 1,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1003. Add a basement level 3 m below ground for a car park and stand four concrete columns in it.

- Starts from: a new Structural project
- Ends with: a Basement level at -3000 with four 400 x 400 columns running up to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=-3000 name=\"Basement\"",
  "op:add column at=(0,0) level=\"Basement\" top=\"Level 1\" type=\"400 x 400\"",
  "op:add column at=(8100,0) level=\"Basement\" top=\"Level 1\" type=\"400 x 400\"",
  "op:add column at=(8100,7500) level=\"Basement\" top=\"Level 1\" type=\"400 x 400\"",
  "op:add column at=(0,7500) level=\"Basement\" top=\"Level 1\" type=\"400 x 400\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=-3000 name="Basement"` | green: op:add level made=level-Basement changed= ms=74 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,0) level="Basement" top="Level 1" type="400 x 400"` | green: op:add column made=column-71bc714924fecae2 changed= ms=8 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(8100,0) level="Basement" top="Level 1" type="400 x 400"` | green: op:add column made=column-db56267998275042 changed= ms=4 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(8100,7500) level="Basement" top="Level 1" type="400 x 400"` | green: op:add column made=column-9acaadd936353853 changed= ms=3 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,7500) level="Basement" top="Level 1" type="400 x 400"` | green: op:add column made=column-b909fe4f4291c9a6 changed= ms=4 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1004. Make the ground floor double height by raising Level 2 to 6000 mm; the columns must follow.

- Starts from: a new Structural project
- Ends with: Level 2 at 6000 mm with two columns that reach it and a beam on it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=310UC137",
  "op:add column at=(7500,0) level=\"Level 1\" top=\"Level 2\" type=310UC137",
  "op:set id=\"Level 2\" key=Elevation value=6000",
  "op:add beam from=(0,0) to=(7500,0) level=\"Level 2\" type=530UB82.0"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=310UC137` | green: op:add column made=column-50dbd1f83d337b18 changed= ms=18 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(7500,0) level="Level 1" top="Level 2" type=310UC137` | green: op:add column made=column-5d8e8f7cc3df5bc6 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:set id="Level 2" key=Elevation value=6000` | green: op:set made= changed="Level 2",column-50dbd1f83d337b18,column-5d8e8f7cc3df5bc6 ms=7 Check "every count unchanged": the counts: no count changed |
| `op:add beam from=(0,0) to=(7500,0) level="Level 2" type=530UB82.0` | green: op:add beam made=beam-f3ae7bd0682f92fe changed= ms=5 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1005. Copy Level 2 up three times at 3.4 m to make the typical floors of a tower.

- Starts from: a new Structural project
- Ends with: Level 2 at 3400 mm and three copies above it at 6800, 10200 and 13600 mm
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=3400",
  "op:copy id=\"Level 2\" by=(0,0,3400)",
  "op:copy id=\"Level 2\" by=(0,0,6800)",
  "op:copy id=\"Level 2\" by=(0,0,10200)"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=3400` | green: op:set made= changed="Level 2" ms=14 Check "every count unchanged": the counts: no count changed |
| `op:copy id="Level 2" by=(0,0,3400)` | green: op:copy made="level-Level 3" changed= ms=14 note=Level 3 placed at 6800 mm; Floor Plan made Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:copy id="Level 2" by=(0,0,6800)` | green: op:copy made="level-Level 4" changed= ms=13 note=Level 4 placed at 10200 mm; Floor Plan made Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:copy id="Level 2" by=(0,0,10200)` | green: op:copy made="level-Level 5" changed= ms=9 note=Level 5 placed at 13600 mm; Floor Plan made Check "Levels +1": Levels 4 -> 5 (+1, expected +1) |

### The result

The model holds: Levels 5,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 4,view: Structural Plan 2.

## 1006. Add a plant level, delete it, then bring it back with Undo and take it away again with Redo.

- Starts from: a new Structural project
- Ends with: the Plant level deleted again after an Undo and a Redo
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=4500 name=\"Plant\"",
  "op:delete id=\"level-Plant\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=4500 name="Plant"` | green: op:add level made=level-Plant changed= ms=71 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:delete id="level-Plant"` | green: op:delete made= changed=level-Plant ms=13 Check "Levels -1": Levels 3 -> 2 (-1, expected -1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect Levels +1",
  "qa:Redo · picks — · keys — · fields — · expect Levels -1"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect Levels +1` | green: QToolButton pressed; a command ran Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `qa:Redo · picks — · keys — · fields — · expect Levels -1` | green: QToolButton pressed; a command ran Check "Levels -1": Levels 3 -> 2 (-1, expected -1) |

### The result

The model holds: Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1007. Put a mezzanine platform at 2.7 m inside a 7 m high warehouse: a 9 x 6 m deck on four columns with edge beams.

- Starts from: a new Structural project
- Ends with: the warehouse height at 7000 mm, a Mezzanine level at 2700 mm, four columns up to it and four edge beams on it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=7000",
  "op:add level elevation=2700 name=\"Mezzanine\"",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Mezzanine\" type=250UC72.9",
  "op:add column at=(9000,0) level=\"Level 1\" top=\"Mezzanine\" type=250UC72.9",
  "op:add column at=(9000,6000) level=\"Level 1\" top=\"Mezzanine\" type=250UC72.9",
  "op:add column at=(0,6000) level=\"Level 1\" top=\"Mezzanine\" type=250UC72.9",
  "op:add beam from=(0,0) to=(9000,0) level=\"Mezzanine\" type=310UB32.0",
  "op:add beam from=(9000,0) to=(9000,6000) level=\"Mezzanine\" type=310UB32.0",
  "op:add beam from=(9000,6000) to=(0,6000) level=\"Mezzanine\" type=310UB32.0",
  "op:add beam from=(0,6000) to=(0,0) level=\"Mezzanine\" type=310UB32.0"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=7000` | green: op:set made= changed="Level 2" ms=333 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=2700 name="Mezzanine"` | green: op:add level made=level-Mezzanine changed= ms=6 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,0) level="Level 1" top="Mezzanine" type=250UC72.9` | green: op:add column made=column-39ac1d39894f6865 changed= ms=8 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(9000,0) level="Level 1" top="Mezzanine" type=250UC72.9` | green: op:add column made=column-41ea05c0e2175dc4 changed= ms=2 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(9000,6000) level="Level 1" top="Mezzanine" type=250UC72.9` | green: op:add column made=column-1c4702bfb708d3a4 changed= ms=2 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 1" top="Mezzanine" type=250UC72.9` | green: op:add column made=column-37089c224a591315 changed= ms=4 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add beam from=(0,0) to=(9000,0) level="Mezzanine" type=310UB32.0` | green: op:add beam made=beam-38cd4f4764611a94 changed= ms=6 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(9000,0) to=(9000,6000) level="Mezzanine" type=310UB32.0` | green: op:add beam made=beam-6d3fbdcc98ed332e changed= ms=4 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add beam from=(9000,6000) to=(0,6000) level="Mezzanine" type=310UB32.0` | green: op:add beam made=beam-715291d17c818f8c changed= ms=5 Check "Structural Framing +1": Structural Framing 2 -> 3 (+1, expected +1) |
| `op:add beam from=(0,6000) to=(0,0) level="Mezzanine" type=310UB32.0` | green: op:add beam made=beam-cd849a4b830a022d changed= ms=6 Check "Structural Framing +1": Structural Framing 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 4,Structural Framing 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1008. Name the levels L00 Ground, L01 First and L02 Second to match the client's drawing numbers, then run a column up through all three.

- Starts from: a new Structural project
- Ends with: levels L00 Ground at 0, L01 First at 3600 and L02 Second at 7200 with one column from L00 to L02
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 1\" key=Name value=\"L00 Ground\"",
  "op:set id=\"Level 2\" key=Elevation value=3600",
  "op:set id=\"Level 2\" key=Name value=\"L01 First\"",
  "op:add level elevation=7200 name=\"L02 Second\"",
  "op:add column at=(0,0) level=\"L00 Ground\" top=\"L02 Second\" type=200UC59.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 1" key=Name value="L00 Ground"` | green: op:set made= changed="Level 1" ms=602 Check "every count unchanged": the counts: no count changed |
| `op:set id="Level 2" key=Elevation value=3600` | green: op:set made= changed="Level 2" ms=2 Check "every count unchanged": the counts: no count changed |
| `op:set id="Level 2" key=Name value="L01 First"` | green: op:set made= changed="Level 2" ms=4 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=7200 name="L02 Second"` | green: op:add level made="level-L02 Second" changed= ms=32 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,0) level="L00 Ground" top="L02 Second" type=200UC59.5` | green: op:add column made=column-1044b0816c2e72ec changed= ms=5 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1009. The site is at RL 12.5: move Ground, Level 1 and the Roof up to 12500, 15900 and 19300 and run a steel column through them.

- Starts from: a new Architectural project
- Ends with: Ground at 12500, Level 1 at 15900, Roof at 19300 and one 250UC89.5 column from Ground to the Roof
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=level-Roof key=Elevation value=19300",
  "op:set id=\"level-Level 1\" key=Elevation value=15900",
  "op:set id=level-Ground key=Elevation value=12500",
  "op:add column at=(0,0) level=Ground top=Roof type=250UC89.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id=level-Roof key=Elevation value=19300` | green: op:set made= changed=level-Roof ms=661 Check "every count unchanged": the counts: no count changed |
| `op:set id="level-Level 1" key=Elevation value=15900` | green: op:set made= changed="level-Level 1" ms=2 Check "every count unchanged": the counts: no count changed |
| `op:set id=level-Ground key=Elevation value=12500` | green: op:set made= changed=level-Ground ms=2 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level=Ground top=Roof type=250UC89.5` | green: op:add column made=column-eabbe46ac5bb55d1 changed= ms=7 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1010. Add a second floor to the house frame at 6800 mm and lift the roof to 10200 mm.

- Starts from: a new Architectural project
- Ends with: Level 1 at 3400, a new Level 2 at 6800, the roof at 10200, a column to Level 2 and a column from Level 2 to the roof
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"level-Level 1\" key=Elevation value=3400",
  "op:add level elevation=6800 name=\"Level 2\"",
  "op:set id=level-Roof key=Elevation value=10200",
  "op:add column at=(0,0) level=Ground top=\"Level 2\" type=200UC59.5",
  "op:add column at=(6000,0) level=\"Level 2\" top=Roof type=200UC59.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="level-Level 1" key=Elevation value=3400` | green: op:set made= changed="level-Level 1" ms=17 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=6800 name="Level 2"` | green: op:add level made="level-Level 2" changed= ms=5 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:set id=level-Roof key=Elevation value=10200` | green: op:set made= changed=level-Roof ms=2 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level=Ground top="Level 2" type=200UC59.5` | green: op:add column made=column-ac6d20cb65167b61 changed= ms=9 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 2" top=Roof type=200UC59.5` | green: op:add column made=column-b3dea08d3f097421 changed= ms=5 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 4,Structural Columns 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1011. Set out a square column grid, three bays each way at 8 m, lettered across and numbered up, with a column at every crossing.

- Starts from: a new Structural project
- Ends with: grids A to C one way and 1 to 3 the other at 8 m centres and nine columns at the crossings
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,18000) name=A",
  "op:array id=grid-A count=3 step=(8000,0,0)",
  "op:add grid from=(-2000,0) to=(18000,0) name=1",
  "op:array id=grid-1 count=3 step=(0,8000,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,18000) name=A` | green: op:add grid made=grid-A changed= ms=73 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=3 step=(8000,0,0)` | green: op:array made=grid-A-a6fd9408f2f65bb9,grid-A-f5d2c9bf05a2cc50 changed= ms=4 Check "Grids +2": Grids 1 -> 3 (+2, expected +2) |
| `op:add grid from=(-2000,0) to=(18000,0) name=1` | green: op:add grid made=grid-1 changed= ms=3 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:array id=grid-1 count=3 step=(0,8000,0)` | green: op:array made=grid-1-75e239f9ed99e13f,grid-1-cf63790b16afa130 changed= ms=3 Check "Grids +2": Grids 4 -> 6 (+2, expected +2) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (17000,17000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +9"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (17000,17000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +9` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (17000,17000) mm at px (964.4,110.6) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +9": Structural Columns 0 -> 9 (+9, expected +9) |

### The result

The model holds: Grids 6,Levels 2,Structural Columns 9,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1012. The building sits skew to the boundary: set out a 7.5 x 6 m grid and swing the whole grid 30 degrees, then put columns on the crossings.

- Starts from: a new Structural project
- Ends with: four grid lines swung 30 degrees about the origin and four columns at their crossings
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:add grid from=(7500,-2000) to=(7500,8000) name=B",
  "op:add grid from=(-2000,0) to=(9500,0) name=1",
  "op:add grid from=(-2000,6000) to=(9500,6000) name=2",
  "op:rotate id=grid-A,grid-B,grid-1,grid-2 about=(0,0) angle=30"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=566 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(7500,-2000) to=(7500,8000) name=B` | green: op:add grid made=grid-B changed= ms=3 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(-2000,0) to=(9500,0) name=1` | green: op:add grid made=grid-1 changed= ms=4 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add grid from=(-2000,6000) to=(9500,6000) name=2` | green: op:add grid made=grid-2 changed= ms=4 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:rotate id=grid-A,grid-B,grid-1,grid-2 about=(0,0) angle=30` | green: op:rotate made= changed=grid-A,grid-B,grid-1,grid-2 ms=54 Check "moved": 4 element(s) moved: grid-1  -> ; grid-2  -> ; grid-A  -> |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-4500,-1500) (8500,10500) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-4500,-1500) (8500,10500) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +4` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-4500,-1500) mm at px (564.3,454.9) on the plan view \| (8500,10500) mm at px (806.2,231.6) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +4": Structural Columns 0 -> 4 (+4, expected +4) |

### The result

The model holds: Grids 4,Levels 2,Structural Columns 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1013. Set out a fan-shaped grid for an auditorium: five lines splayed 10 degrees apart from the stage point, cut by one cross line, with a column at each crossing.

- Starts from: a new Structural project
- Ends with: five splayed grid lines A to E, a cross line 1 at x = 15000 and five columns where they cross
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,0) to=(28191,-10261) name=A",
  "op:add grid from=(0,0) to=(29544,-5209) name=B",
  "op:add grid from=(0,0) to=(30000,0) name=C",
  "op:add grid from=(0,0) to=(29544,5209) name=D",
  "op:add grid from=(0,0) to=(28191,10261) name=E",
  "op:add grid from=(15000,-9000) to=(15000,9000) name=1"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,0) to=(28191,-10261) name=A` | green: op:add grid made=grid-A changed= ms=589 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(0,0) to=(29544,-5209) name=B` | green: op:add grid made=grid-B changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(0,0) to=(30000,0) name=C` | green: op:add grid made=grid-C changed= ms=30 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add grid from=(0,0) to=(29544,5209) name=D` | green: op:add grid made=grid-D changed= ms=4 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:add grid from=(0,0) to=(28191,10261) name=E` | green: op:add grid made=grid-E changed= ms=3 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |
| `op:add grid from=(15000,-9000) to=(15000,9000) name=1` | green: op:add grid made=grid-1 changed= ms=4 Check "Grids +1": Grids 5 -> 6 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (14000,-9000) (16000,9000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +5"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (14000,-9000) (16000,9000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +5` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (14000,-9000) mm at px (837.8,594.5) on the plan view \| (16000,9000) mm at px (875.0,259.5) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +5": Structural Columns 0 -> 5 (+5, expected +5) |

### The result

The model holds: Grids 6,Levels 2,Structural Columns 5,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1014. Set out the plant room grid with uneven bays of 6.0, 7.5, 9.0, 7.5 and 6.0 m and two rows 12 m apart, with a column at every crossing.

- Starts from: a new Structural project
- Ends with: six grid lines A to F at 0, 6000, 13500, 22500, 30000 and 36000, two cross lines and twelve columns
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,14000) name=A",
  "op:add grid from=(6000,-2000) to=(6000,14000) name=B",
  "op:add grid from=(13500,-2000) to=(13500,14000) name=C",
  "op:add grid from=(22500,-2000) to=(22500,14000) name=D",
  "op:add grid from=(30000,-2000) to=(30000,14000) name=E",
  "op:add grid from=(36000,-2000) to=(36000,14000) name=F",
  "op:add grid from=(-2000,0) to=(38000,0) name=1",
  "op:add grid from=(-2000,12000) to=(38000,12000) name=2"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,14000) name=A` | green: op:add grid made=grid-A changed= ms=75 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(6000,-2000) to=(6000,14000) name=B` | green: op:add grid made=grid-B changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(13500,-2000) to=(13500,14000) name=C` | green: op:add grid made=grid-C changed= ms=3 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add grid from=(22500,-2000) to=(22500,14000) name=D` | green: op:add grid made=grid-D changed= ms=53 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:add grid from=(30000,-2000) to=(30000,14000) name=E` | green: op:add grid made=grid-E changed= ms=3 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |
| `op:add grid from=(36000,-2000) to=(36000,14000) name=F` | green: op:add grid made=grid-F changed= ms=67 Check "Grids +1": Grids 5 -> 6 (+1, expected +1) |
| `op:add grid from=(-2000,0) to=(38000,0) name=1` | green: op:add grid made=grid-1 changed= ms=3 Check "Grids +1": Grids 6 -> 7 (+1, expected +1) |
| `op:add grid from=(-2000,12000) to=(38000,12000) name=2` | green: op:add grid made=grid-2 changed= ms=3 Check "Grids +1": Grids 7 -> 8 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (37000,13000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +12"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (37000,13000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +12` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-1000,-1000) mm at px (611.6,445.6) on the plan view \| (37000,13000) lay outside the view: panned to bring it to px (648.0,445.0); (37000,13000) mm at px (648.0,445.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +12": Structural Columns 0 -> 12 (+12, expected +12) |

### The result

The model holds: Grids 8,Levels 2,Structural Columns 12,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1015. The client calls the gridlines X, Y and Z instead of A, B and C: rename them and shift all three 250 mm east.

- Starts from: a new Structural project
- Ends with: three grid lines renamed X, Y and Z and moved 250 mm east
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,10000) name=A",
  "op:add grid from=(6000,-2000) to=(6000,10000) name=B",
  "op:add grid from=(12000,-2000) to=(12000,10000) name=C",
  "op:set id=grid-A key=Name value=X",
  "op:set id=grid-B key=Name value=Y",
  "op:set id=grid-C key=Name value=Z",
  "op:move id=grid-A,grid-B,grid-C by=(250,0,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,10000) name=A` | green: op:add grid made=grid-A changed= ms=73 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(6000,-2000) to=(6000,10000) name=B` | green: op:add grid made=grid-B changed= ms=44 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(12000,-2000) to=(12000,10000) name=C` | green: op:add grid made=grid-C changed= ms=3 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:set id=grid-A key=Name value=X` | green: op:set made= changed=grid-A ms=9 Check "every count unchanged": the counts: no count changed |
| `op:set id=grid-B key=Name value=Y` | green: op:set made= changed=grid-B ms=3 Check "every count unchanged": the counts: no count changed |
| `op:set id=grid-C key=Name value=Z` | green: op:set made= changed=grid-C ms=2 Check "every count unchanged": the counts: no count changed |
| `op:move id=grid-A,grid-B,grid-C by=(250,0,0)` | green: op:move made= changed=grid-A,grid-B,grid-C ms=8 Check "moved": 3 element(s) moved: grid-A  -> ; grid-B  -> ; grid-C  -> |

### The result

The model holds: Grids 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1016. Shift gridline B 500 mm east to clear the stair core, then undo it and do it again.

- Starts from: a new Structural project
- Ends with: gridline B moved 500 mm east after an Undo and a Redo
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,10000) name=A",
  "op:add grid from=(6000,-2000) to=(6000,10000) name=B",
  "op:add grid from=(12000,-2000) to=(12000,10000) name=C",
  "op:move id=grid-B by=(500,0,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,10000) name=A` | green: op:add grid made=grid-A changed= ms=522 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(6000,-2000) to=(6000,10000) name=B` | green: op:add grid made=grid-B changed= ms=3 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(12000,-2000) to=(12000,10000) name=C` | green: op:add grid made=grid-C changed= ms=8 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:move id=grid-B by=(500,0,0)` | green: op:move made= changed=grid-B ms=350 Check "moved": 1 element(s) moved: grid-B  -> |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect back",
  "qa:Redo · picks — · keys — · fields — · expect moved"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect back` | green: QToolButton pressed; a command ran Check "back": the document is again what the snapshot 2 before the step's start held (1 element(s) differ from the step's start) |
| `qa:Redo · picks — · keys — · fields — · expect moved` | green: QToolButton pressed; a command ran Check "moved": 1 element(s) moved: grid-B  -> |

### The result

The model holds: Grids 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1017. Extend the grid east by copying gridline A six metres and then twelve metres.

- Starts from: a new Structural project
- Ends with: gridline A and two copies of it 6 m and 12 m to the east
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,12000) name=A",
  "op:copy id=grid-A by=(6000,0,0)",
  "op:copy id=grid-A by=(12000,0,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,12000) name=A` | green: op:add grid made=grid-A changed= ms=78 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:copy id=grid-A by=(6000,0,0)` | green: op:copy made=grid-A-2e0803fadd9865a2 changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:copy id=grid-A by=(12000,0,0)` | green: op:copy made=grid-A-1a4ec08c0b4a3952 changed= ms=4 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |

### The result

The model holds: Grids 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1018. The building is symmetrical about a centre line at 12 m: draw the west half of the grid, mirror it east and add the centre line.

- Starts from: a new Structural project
- Ends with: gridlines A and B, their mirror images at 18 m and 24 m and a centre line CL at 12 m
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,12000) name=A",
  "op:add grid from=(6000,-2000) to=(6000,12000) name=B",
  "op:mirror id=grid-A,grid-B axis=(12000,-2000) (12000,12000) copy=yes",
  "op:add grid from=(12000,-2000) to=(12000,12000) name=CL"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,12000) name=A` | green: op:add grid made=grid-A changed= ms=561 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(6000,-2000) to=(6000,12000) name=B` | green: op:add grid made=grid-B changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:mirror id=grid-A,grid-B axis=(12000,-2000) (12000,12000) copy=yes` | green: op:mirror made=grid-A-284865f099432cdc,grid-B-f0c20987777683f4 changed= ms=12 Check "Grids +2": Grids 2 -> 4 (+2, expected +2) |
| `op:add grid from=(12000,-2000) to=(12000,12000) name=CL` | green: op:add grid made=grid-CL changed= ms=4 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |

### The result

The model holds: Grids 5,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1019. Set out a radial grid for a circular tank farm: one line 20 m long, copied round the centre every 15 degrees to 60 degrees.

- Starts from: a new Structural project
- Ends with: the first radial line and four copies of it at 15, 30, 45 and 60 degrees about the origin
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,0) to=(20000,0) name=R",
  "op:rotate id=grid-R about=(0,0) angle=15 copy=yes",
  "op:rotate id=grid-R about=(0,0) angle=30 copy=yes",
  "op:rotate id=grid-R about=(0,0) angle=45 copy=yes",
  "op:rotate id=grid-R about=(0,0) angle=60 copy=yes"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,0) to=(20000,0) name=R` | green: op:add grid made=grid-R changed= ms=69 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:rotate id=grid-R about=(0,0) angle=15 copy=yes` | green: op:rotate made=grid-R-5764f6aed80a7f47 changed= ms=8 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:rotate id=grid-R about=(0,0) angle=30 copy=yes` | green: op:rotate made=grid-R-056e0e8cfdb9fb64 changed= ms=5 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:rotate id=grid-R about=(0,0) angle=45 copy=yes` | green: op:rotate made=grid-R-7c8d5982ac69944b changed= ms=10 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:rotate id=grid-R about=(0,0) angle=60 copy=yes` | green: op:rotate made=grid-R-8ae9c35907377c7e changed= ms=7 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |

### The result

The model holds: Grids 5,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1020. Take gridline C out of a four-line grid, change my mind with Undo, then take it out again with Redo.

- Starts from: a new Structural project
- Ends with: gridline C deleted, leaving A, B and D
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,10000) name=A",
  "op:add grid from=(7000,-2000) to=(7000,10000) name=B",
  "op:add grid from=(14000,-2000) to=(14000,10000) name=C",
  "op:add grid from=(21000,-2000) to=(21000,10000) name=D",
  "op:delete id=grid-C"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,10000) name=A` | green: op:add grid made=grid-A changed= ms=51 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(7000,-2000) to=(7000,10000) name=B` | green: op:add grid made=grid-B changed= ms=3 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(14000,-2000) to=(14000,10000) name=C` | green: op:add grid made=grid-C changed= ms=3 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add grid from=(21000,-2000) to=(21000,10000) name=D` | green: op:add grid made=grid-D changed= ms=4 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:delete id=grid-C` | green: op:delete made= changed=grid-C ms=511 Check "Grids -1": Grids 4 -> 3 (-1, expected -1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect Grids +1",
  "qa:Redo · picks — · keys — · fields — · expect Grids -1"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect Grids +1` | green: QToolButton pressed; a command ran Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `qa:Redo · picks — · keys — · fields — · expect Grids -1` | green: QToolButton pressed; a command ran Check "Grids -1": Grids 4 -> 3 (-1, expected -1) |

### The result

The model holds: Grids 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1021. Click in two grid lines each way for a 6 x 6 m bay and put columns where they cross.

- Starts from: a new Structural project
- Ends with: four grid lines drawn with the Grid tool and four columns at their crossings
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Setout:Grid · picks (0,-2000) (0,8000) (6000,-2000) (6000,8000) · keys Escape Escape · fields — · expect Grids +2",
  "ribbon:Setout:Grid · picks (-2000,0) (8000,0) (-2000,6000) (8000,6000) · keys Escape Escape · fields — · expect Grids +2",
  "ribbon:Structure:Column · picks (-1000,-1000) (7000,7000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Setout:Grid · picks (0,-2000) (0,8000) (6000,-2000) (6000,8000) · keys Escape Escape · fields — · expect Grids +2` | green: pressed 'Grid' on Setout's Datum panel: the tool 'Grid' stands \| picks: (0,-2000) mm at px (648.0,464.2) on the plan view \| (0,8000) mm at px (648.0,278.1) on the plan view \| (6000,-2000) mm at px (759.7,464.2) on the plan view \| (6000,8000) mm at px (759.7,278.1) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Grid -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Grids +2": Grids 0 -> 2 (+2, expected +2) |
| `ribbon:Setout:Grid · picks (-2000,0) (8000,0) (-2000,6000) (8000,6000) · keys Escape Escape · fields — · expect Grids +2` | green: pressed 'Grid' on Setout's Datum panel: the tool 'Grid' stands \| picks: (-2000,0) mm at px (610.8,427.0) on the plan view \| (8000,0) mm at px (796.9,427.0) on the plan view \| (-2000,6000) mm at px (610.8,315.3) on the plan view \| (8000,6000) mm at px (796.9,315.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Grid -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Grids +2": Grids 2 -> 4 (+2, expected +2) |
| `ribbon:Structure:Column · picks (-1000,-1000) (7000,7000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +4` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (7000,7000) mm at px (778.3,296.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +4": Structural Columns 0 -> 4 (+4, expected +4) |

### The result

The model holds: Grids 4,Levels 2,Structural Columns 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1022. Place a 310UC158, a 250UC89.5 and a 200UC52.2 column along one line so the three sizes can be compared.

- Starts from: a new Structural project
- Ends with: three universal columns of different sizes 6 m apart, each from Level 1 to Level 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=310UC158",
  "op:add column at=(6000,0) level=\"Level 1\" top=\"Level 2\" type=250UC89.5",
  "op:add column at=(12000,0) level=\"Level 1\" top=\"Level 2\" type=200UC52.2"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=310UC158` | green: op:add column made=column-d3f3a97ea73a5a6d changed= ms=512 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1" top="Level 2" type=250UC89.5` | green: op:add column made=column-7c395d4c920139b9 changed= ms=232 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(12000,0) level="Level 1" top="Level 2" type=200UC52.2` | green: op:add column made=column-0142173510f52ffe changed= ms=31 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1023. Four 400 x 400 concrete columns at the corners of a 12 x 8 m plant room, 5 m high.

- Starts from: a new Structural project
- Ends with: Level 2 at 5000 mm and a 400 x 400 column at each corner of a 12 x 8 m rectangle
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=5000",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=\"400 x 400\"",
  "op:add column at=(12000,0) level=\"Level 1\" top=\"Level 2\" type=\"400 x 400\"",
  "op:add column at=(12000,8000) level=\"Level 1\" top=\"Level 2\" type=\"400 x 400\"",
  "op:add column at=(0,8000) level=\"Level 1\" top=\"Level 2\" type=\"400 x 400\""
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=5000` | green: op:set made= changed="Level 2" ms=18 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level="Level 1" top="Level 2" type="400 x 400"` | green: op:add column made=column-4a56037b91280ab9 changed= ms=11 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(12000,0) level="Level 1" top="Level 2" type="400 x 400"` | green: op:add column made=column-bd0eac912537133e changed= ms=4 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(12000,8000) level="Level 1" top="Level 2" type="400 x 400"` | green: op:add column made=column-803e29aafce81274 changed= ms=3 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,8000) level="Level 1" top="Level 2" type="400 x 400"` | green: op:add column made=column-9e0b3dc848742a14 changed= ms=3 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1024. Six 600 dia round columns for a car-park deck: two rows of three at 8.1 m, the rows 16.2 m apart.

- Starts from: a new Structural project
- Ends with: six round concrete columns in two rows of three, from Level 1 to Level 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=\"600 dia\"",
  "op:add column at=(8100,0) level=\"Level 1\" top=\"Level 2\" type=\"600 dia\"",
  "op:add column at=(16200,0) level=\"Level 1\" top=\"Level 2\" type=\"600 dia\"",
  "op:add column at=(0,16200) level=\"Level 1\" top=\"Level 2\" type=\"600 dia\"",
  "op:add column at=(8100,16200) level=\"Level 1\" top=\"Level 2\" type=\"600 dia\"",
  "op:add column at=(16200,16200) level=\"Level 1\" top=\"Level 2\" type=\"600 dia\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type="600 dia"` | green: op:add column made=column-567dfea1aca694b0 changed= ms=18 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(8100,0) level="Level 1" top="Level 2" type="600 dia"` | green: op:add column made=column-0da92a841ba2d911 changed= ms=5 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(16200,0) level="Level 1" top="Level 2" type="600 dia"` | green: op:add column made=column-819818b4633518f3 changed= ms=5 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,16200) level="Level 1" top="Level 2" type="600 dia"` | green: op:add column made=column-701faad993933d8b changed= ms=4 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add column at=(8100,16200) level="Level 1" top="Level 2" type="600 dia"` | green: op:add column made=column-bd217c3d84b582a0 changed= ms=6 Check "Structural Columns +1": Structural Columns 4 -> 5 (+1, expected +1) |
| `op:add column at=(16200,16200) level="Level 1" top="Level 2" type="600 dia"` | green: op:add column made=column-25330cff3c6cd72a changed= ms=5 Check "Structural Columns +1": Structural Columns 5 -> 6 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1025. Click in six columns along the south wall line, 4.5 m apart.

- Starts from: a new Structural project
- Ends with: six columns on a line at 4.5 m centres
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (0,0) (4500,0) (9000,0) (13500,0) (18000,0) (22500,0) · keys Escape Escape · fields — · expect Structural Columns +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (0,0) (4500,0) (9000,0) (13500,0) (18000,0) (22500,0) · keys Escape Escape · fields — · expect Structural Columns +6` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (4500,0) mm at px (731.7,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| (13500,0) mm at px (899.2,427.0) on the plan view \| (18000,0) mm at px (983.0,427.0) on the plan view \| (22500,0) mm at px (1066.7,427.0) on the plan view \| presses to the tool 6, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +6": Structural Columns 0 -> 6 (+6, expected +6) |

### The result

The model holds: Levels 2,Structural Columns 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1026. Run four 300 dia columns up through two storeys of 3.3 m, from Level 1 to a new Level 3.

- Starts from: a new Structural project
- Ends with: Level 2 at 3300, Level 3 at 6600 and four 300 dia columns each two storeys tall
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=3300",
  "op:add level elevation=6600 name=\"Level 3\"",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 3\" type=\"300 dia\"",
  "op:add column at=(6000,0) level=\"Level 1\" top=\"Level 3\" type=\"300 dia\"",
  "op:add column at=(6000,6000) level=\"Level 1\" top=\"Level 3\" type=\"300 dia\"",
  "op:add column at=(0,6000) level=\"Level 1\" top=\"Level 3\" type=\"300 dia\""
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=3300` | green: op:set made= changed="Level 2" ms=79 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=6600 name="Level 3"` | green: op:add level made="level-Level 3" changed= ms=37 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,0) level="Level 1" top="Level 3" type="300 dia"` | green: op:add column made=column-1834e4073d016329 changed= ms=7 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1" top="Level 3" type="300 dia"` | green: op:add column made=column-ad0e9b22e54ee558 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(6000,6000) level="Level 1" top="Level 3" type="300 dia"` | green: op:add column made=column-86f1d669d32d161a changed= ms=3 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 1" top="Level 3" type="300 dia"` | green: op:add column made=column-a1d654a695a1b76a changed= ms=3 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1027. Four 323.9 x 9.5 tube posts, 4.8 m high, for a 6 x 6 m entrance canopy.

- Starts from: a new Structural project
- Ends with: Level 2 at 4800 mm and four circular hollow section posts at the corners of a 6 m square
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=4800",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=323.9x9.5CHS",
  "op:add column at=(6000,0) level=\"Level 1\" top=\"Level 2\" type=323.9x9.5CHS",
  "op:add column at=(6000,6000) level=\"Level 1\" top=\"Level 2\" type=323.9x9.5CHS",
  "op:add column at=(0,6000) level=\"Level 1\" top=\"Level 2\" type=323.9x9.5CHS"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=4800` | green: op:set made= changed="Level 2" ms=432 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=323.9x9.5CHS` | green: op:add column made=column-e38df498478750b5 changed= ms=51 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1" top="Level 2" type=323.9x9.5CHS` | green: op:add column made=column-e56fee042eb4aa8b changed= ms=4 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(6000,6000) level="Level 1" top="Level 2" type=323.9x9.5CHS` | green: op:add column made=column-4feb31628f02845c changed= ms=3 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 1" top="Level 2" type=323.9x9.5CHS` | green: op:add column made=column-71277f332e9f4d3d changed= ms=4 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1028. Draw one column and array it five times at 7.2 m along the frontage.

- Starts from: a new Structural project
- Ends with: a row of five 250UC89.5 columns 7.2 m apart
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" type=250UC89.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" type=250UC89.5` | green: op:add column made=column-f9571acf977a83f5 changed= ms=17 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (0,0) · keys — · fields — · expect column selected",
  "ribbon:Modify:Array · picks (0,0) (7200,0) · keys Return · fields Options Strip: Number=5; Group And Associate=no · expect Structural Columns +4"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (0,0) · keys — · fields — · expect column selected` | green: select: (0,0) mm at px (648.0,427.0) on the plan view; picked 'column-f9571acf977a83f5'; selected 0 -> 1 [column-f9571acf977a83f5] \| picks: the plan band pressed these 1 pick(s) as its own process Check "column selected": 1 selected (column-f9571acf977a83f5) (words not read: 'column') |
| `ribbon:Modify:Array · picks (0,0) (7200,0) · keys Return · fields Options Strip: Number=5; Group And Associate=no · expect Structural Columns +4` | green: pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands \| fields: Number=5 reads '5.00'; Group And Associate=no reads no \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (7200,0) mm at px (782.0,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Return (tool Array -> tool Array) Check "Structural Columns +4": Structural Columns 1 -> 5 (+4, expected +4) |

### The result

The model holds: Levels 2,Structural Columns 5,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1029. Draw one 8 m secondary beam on the first floor and array it five times at 3 m centres.

- Starts from: a new Structural project
- Ends with: the first floor at 3600 mm with five 250UB31.4 beams 3 m apart
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 1\" key=Elevation value=3600",
  "op:add beam from=(0,0) to=(0,8000) level=\"Level 1\" type=250UB31.4"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 1" key=Elevation value=3600` | green: op:set made= changed="Level 1" ms=94 Check "every count unchanged": the counts: no count changed |
| `op:add beam from=(0,0) to=(0,8000) level="Level 1" type=250UB31.4` | green: op:add beam made=beam-bcb4a13acb3db0ba changed= ms=11 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (0,4000) · keys — · fields — · expect beam selected",
  "ribbon:Modify:Array · picks (0,4000) (3000,4000) · keys Return · fields Options Strip: Number=5; Group And Associate=no · expect Structural Framing +4"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (0,4000) · keys — · fields — · expect beam selected` | green: select: (0,4000) mm at px (648.0,352.6) on the plan view; picked 'beam-bcb4a13acb3db0ba'; selected 0 -> 1 [beam-bcb4a13acb3db0ba] \| picks: the plan band pressed these 1 pick(s) as its own process Check "beam selected": 1 selected (beam-bcb4a13acb3db0ba) (words not read: 'beam') |
| `ribbon:Modify:Array · picks (0,4000) (3000,4000) · keys Return · fields Options Strip: Number=5; Group And Associate=no · expect Structural Framing +4` | green: pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands \| fields: Number=5 reads '5.00'; Group And Associate=no reads no \| picks: (0,4000) mm at px (648.0,352.6) on the plan view \| (3000,4000) mm at px (703.8,352.6) on the plan view \| presses to the tool 2, selection unchanged \| keys: Return (tool Array -> tool Array) Check "Structural Framing +4": Structural Framing 1 -> 5 (+4, expected +4) |

### The result

The model holds: Levels 2,Structural Framing 5,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1030. Frame a four-storey steel building 9 x 6 m: four columns full height and a ring of beams at each floor.

- Starts from: a new Structural project
- Ends with: levels at 0, 3600, 7200 and 10800, four 310UC158 columns up to Level 4 and twelve 360UB50.7 beams on Levels 2 to 4
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=3600",
  "op:add level elevation=7200 name=\"Level 3\"",
  "op:add level elevation=10800 name=\"Level 4\"",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 4\" type=310UC158",
  "op:add column at=(9000,0) level=\"Level 1\" top=\"Level 4\" type=310UC158",
  "op:add column at=(9000,6000) level=\"Level 1\" top=\"Level 4\" type=310UC158",
  "op:add column at=(0,6000) level=\"Level 1\" top=\"Level 4\" type=310UC158"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=3600` | green: op:set made= changed="Level 2" ms=27 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=7200 name="Level 3"` | green: op:add level made="level-Level 3" changed= ms=52 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add level elevation=10800 name="Level 4"` | green: op:add level made="level-Level 4" changed= ms=10 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add column at=(0,0) level="Level 1" top="Level 4" type=310UC158` | green: op:add column made=column-8a2779d07c29a08c changed= ms=5 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(9000,0) level="Level 1" top="Level 4" type=310UC158` | green: op:add column made=column-276a8cf42df4f85a changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(9000,6000) level="Level 1" top="Level 4" type=310UC158` | green: op:add column made=column-540e58d42b2bbb1a changed= ms=4 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 1" top="Level 4" type=310UC158` | green: op:add column made=column-c22e4971134c1858 changed= ms=3 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Beam · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Level 2 · expect Structural Framing +4",
  "ribbon:Structure:Beam · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Level 3 · expect Structural Framing +4",
  "ribbon:Structure:Beam · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Level 4 · expect Structural Framing +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Beam · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Level 2 · expect Structural Framing +4` | green: pressed 'Beam' on Structure's Framing panel: the tool 'Beam' stands \| fields: Chain=yes reads yes; Placement Plane=Level 2 reads 'Level 2' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| (9000,6000) mm at px (815.5,315.3) on the plan view \| (0,6000) mm at px (648.0,315.3) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Beam -> tool Beam, 'Beam' still stands (the key went to union_shell::Viewport)); Escape (tool Beam -> no tool) Check "Structural Framing +4": Structural Framing 0 -> 4 (+4, expected +4) |
| `ribbon:Structure:Beam · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Level 3 · expect Structural Framing +4` | green: pressed 'Beam' on Structure's Framing panel: the tool 'Beam' stands \| fields: Chain=yes reads yes; Placement Plane=Level 3 reads 'Level 3' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| (9000,6000) mm at px (815.5,315.3) on the plan view \| (0,6000) mm at px (648.0,315.3) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Beam -> tool Beam, 'Beam' still stands (the key went to union_shell::Viewport)); Escape (tool Beam -> no tool) Check "Structural Framing +4": Structural Framing 4 -> 8 (+4, expected +4) |
| `ribbon:Structure:Beam · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Level 4 · expect Structural Framing +4` | green: pressed 'Beam' on Structure's Framing panel: the tool 'Beam' stands \| fields: Chain=yes reads yes; Placement Plane=Level 4 reads 'Level 4' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (9000,0) mm at px (815.5,427.0) on the plan view \| (9000,6000) mm at px (815.5,315.3) on the plan view \| (0,6000) mm at px (648.0,315.3) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Beam -> tool Beam, 'Beam' still stands (the key went to union_shell::Viewport)); Escape (tool Beam -> no tool) Check "Structural Framing +4": Structural Framing 8 -> 12 (+4, expected +4) |

### The result

The model holds: Levels 4,Structural Columns 4,Structural Framing 12,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1031. Span a 530UB82.0 beam 8.4 m between two columns at the first floor, 4.2 m up.

- Starts from: a new Structural project
- Ends with: Level 2 at 4200 mm, two 310UC118 columns 8.4 m apart and a 530UB82.0 beam between their tops
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=4200",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=310UC118",
  "op:add column at=(8400,0) level=\"Level 1\" top=\"Level 2\" type=310UC118",
  "op:add beam from=(0,0) to=(8400,0) level=\"Level 2\" type=530UB82.0"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=4200` | green: op:set made= changed="Level 2" ms=12 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=310UC118` | green: op:add column made=column-5a446bdd4ec4f736 changed= ms=10 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(8400,0) level="Level 1" top="Level 2" type=310UC118` | green: op:add column made=column-4ae5ed372e6d1541 changed= ms=4 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,0) to=(8400,0) level="Level 2" type=530UB82.0` | green: op:add beam made=beam-917020b7a3d6e350 changed= ms=9 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1032. Click a ring of beams round a 12 x 9 m bay at the first floor, 3.6 m up.

- Starts from: a new Structural project
- Ends with: Level 2 at 3600 mm and four chained beams round a 12 x 9 m rectangle on it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=3600"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=3600` | green: op:set made= changed="Level 2" ms=103 Check "every count unchanged": the counts: no count changed |

```json
steps_run {"steps":[
  "ribbon:Structure:Beam · picks (0,0) (12000,0) (12000,9000) (0,9000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Level 2 · expect Structural Framing +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Beam · picks (0,0) (12000,0) (12000,9000) (0,9000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Level 2 · expect Structural Framing +4` | green: pressed 'Beam' on Structure's Framing panel: the tool 'Beam' stands \| fields: Chain=yes reads yes; Placement Plane=Level 2 reads 'Level 2' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (12000,0) mm at px (871.3,427.0) on the plan view \| (12000,9000) mm at px (871.3,259.5) on the plan view \| (0,9000) mm at px (648.0,259.5) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Beam -> tool Beam, 'Beam' still stands (the key went to union_shell::Viewport)); Escape (tool Beam -> no tool) Check "Structural Framing +4": Structural Framing 0 -> 4 (+4, expected +4) |

### The result

The model holds: Levels 2,Structural Framing 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1033. Lay out a floor bay 12 x 9 m: two 610UB125 girders 12 m apart and three 360UB50.7 joists at 3 m centres between them.

- Starts from: a new Structural project
- Ends with: two girders along the 9 m sides and three joists across the bay on Level 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=3600",
  "op:add beam from=(0,0) to=(0,9000) level=\"Level 2\" type=610UB125",
  "op:add beam from=(12000,0) to=(12000,9000) level=\"Level 2\" type=610UB125",
  "op:add beam from=(0,1500) to=(12000,1500) level=\"Level 2\" type=360UB50.7",
  "op:add beam from=(0,4500) to=(12000,4500) level=\"Level 2\" type=360UB50.7",
  "op:add beam from=(0,7500) to=(12000,7500) level=\"Level 2\" type=360UB50.7"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=3600` | green: op:set made= changed="Level 2" ms=14 Check "every count unchanged": the counts: no count changed |
| `op:add beam from=(0,0) to=(0,9000) level="Level 2" type=610UB125` | green: op:add beam made=beam-af808b05cdd92520 changed= ms=5 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(12000,0) to=(12000,9000) level="Level 2" type=610UB125` | green: op:add beam made=beam-f43f3c8b6295d675 changed= ms=6 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,1500) to=(12000,1500) level="Level 2" type=360UB50.7` | green: op:add beam made=beam-b8e8011b0bfe4d67 changed= ms=34 Check "Structural Framing +1": Structural Framing 2 -> 3 (+1, expected +1) |
| `op:add beam from=(0,4500) to=(12000,4500) level="Level 2" type=360UB50.7` | green: op:add beam made=beam-0d024659f522e3cb changed= ms=6 Check "Structural Framing +1": Structural Framing 3 -> 4 (+1, expected +1) |
| `op:add beam from=(0,7500) to=(12000,7500) level="Level 2" type=360UB50.7` | green: op:add beam made=beam-d44ef238fb7f8aa5 changed= ms=6 Check "Structural Framing +1": Structural Framing 4 -> 5 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Framing 5,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1034. Brace one 6 m bay with a cross of two 168.3 x 6.4 tubes between the columns, ground to first floor.

- Starts from: a new Structural project
- Ends with: two columns 6 m apart and two crossing braces from Level 1 to Level 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=200UC59.5",
  "op:add column at=(6000,0) level=\"Level 1\" top=\"Level 2\" type=200UC59.5",
  "op:add brace from=(0,0) to=(6000,0) level=\"Level 1\" top=\"Level 2\" type=168.3x6.4CHS",
  "op:add brace from=(6000,0) to=(0,0) level=\"Level 1\" top=\"Level 2\" type=168.3x6.4CHS"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=200UC59.5` | green: op:add column made=column-e1359c5578d25a01 changed= ms=573 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1" top="Level 2" type=200UC59.5` | green: op:add column made=column-13ca3f4b662cbf9f changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add brace from=(0,0) to=(6000,0) level="Level 1" top="Level 2" type=168.3x6.4CHS` | green: op:add brace made=brace-d28a360cc4e4ad78 changed= ms=8 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add brace from=(6000,0) to=(0,0) level="Level 1" top="Level 2" type=168.3x6.4CHS` | green: op:add brace made=brace-a09b5b3d76f3135e changed= ms=5 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1035. Put chevron bracing in a 6 m bay: two braces meeting at the middle of the first-floor beam.

- Starts from: a new Structural project
- Ends with: two columns, a first-floor beam and two braces rising from the column bases to the beam's midpoint
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=250UC72.9",
  "op:add column at=(6000,0) level=\"Level 1\" top=\"Level 2\" type=250UC72.9",
  "op:add beam from=(0,0) to=(6000,0) level=\"Level 2\" type=310UB40.4",
  "op:add brace from=(0,0) to=(3000,0) level=\"Level 1\" top=\"Level 2\" type=139.7x3.5CHS",
  "op:add brace from=(6000,0) to=(3000,0) level=\"Level 1\" top=\"Level 2\" type=139.7x3.5CHS"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=250UC72.9` | green: op:add column made=column-41e72ea8d6eca9b3 changed= ms=17 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1" top="Level 2" type=250UC72.9` | green: op:add column made=column-43f69d189b1b65b0 changed= ms=4 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,0) to=(6000,0) level="Level 2" type=310UB40.4` | green: op:add beam made=beam-e2cabbba9940ed63 changed= ms=8 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add brace from=(0,0) to=(3000,0) level="Level 1" top="Level 2" type=139.7x3.5CHS` | green: op:add brace made=brace-55534a1ca12cd551 changed= ms=6 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add brace from=(6000,0) to=(3000,0) level="Level 1" top="Level 2" type=139.7x3.5CHS` | green: op:add brace made=brace-c94475dd63fdecbc changed= ms=6 Check "Structural Framing +1": Structural Framing 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1036. Set out one portal frame: 30 m span, 6 m to the eaves, ridge at 7.5 m, 310UC96.8 columns and 530UB82.0 rafters.

- Starts from: a new Structural project
- Ends with: Level 2 at 6000 mm, two eaves columns 30 m apart and two rafters rising to a ridge at 7500 mm
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=6000",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=310UC96.8",
  "op:add column at=(30000,0) level=\"Level 1\" top=\"Level 2\" type=310UC96.8",
  "op:add brace from=(0,0) to=(15000,0) level=\"Level 1\" top=\"Level 1\" start_offset=6000 end_offset=7500 type=530UB82.0",
  "op:add brace from=(30000,0) to=(15000,0) level=\"Level 1\" top=\"Level 1\" start_offset=6000 end_offset=7500 type=530UB82.0"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=6000` | green: op:set made= changed="Level 2" ms=18 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=310UC96.8` | green: op:add column made=column-59db47c6866fa20d changed= ms=40 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(30000,0) level="Level 1" top="Level 2" type=310UC96.8` | green: op:add column made=column-a265900c5a7799ff changed= ms=4 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add brace from=(0,0) to=(15000,0) level="Level 1" top="Level 1" start_offset=6000 end_offset=7500 type=530UB82.0` | green: op:add brace made=brace-d2d8aa8164b977cc changed= ms=7 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add brace from=(30000,0) to=(15000,0) level="Level 1" top="Level 1" start_offset=6000 end_offset=7500 type=530UB82.0` | green: op:add brace made=brace-92457c46d33e98a3 changed= ms=10 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1037. Set out a portal-frame shed: five frames 7.5 m apart, 24 m span, columns at every frame and an eaves beam down each side.

- Starts from: a new Structural project
- Ends with: two column lines 24 m apart, five frame lines 7.5 m apart, ten columns and two eaves beams of 30 m
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=6000",
  "op:add grid from=(0,-2000) to=(0,32000) name=A",
  "op:add grid from=(24000,-2000) to=(24000,32000) name=B",
  "op:add grid from=(-2000,0) to=(26000,0) name=1",
  "op:array id=grid-1 count=5 step=(0,7500,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=6000` | green: op:set made= changed="Level 2" ms=93 Check "every count unchanged": the counts: no count changed |
| `op:add grid from=(0,-2000) to=(0,32000) name=A` | green: op:add grid made=grid-A changed= ms=47 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(24000,-2000) to=(24000,32000) name=B` | green: op:add grid made=grid-B changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(-2000,0) to=(26000,0) name=1` | green: op:add grid made=grid-1 changed= ms=5 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:array id=grid-1 count=5 step=(0,7500,0)` | green: op:array made=grid-1-b50b0834ed2f6011,grid-1-08ac5858ccc883dd,grid-1-549cd847e32ffdf3,grid-1-42fb313282b51b31 changed= ms=6 Check "Grids +4": Grids 3 -> 7 (+4, expected +4) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (25000,31000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +10"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (25000,31000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +10` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (25000,31000) lay outside the view: panned to bring it to px (972.0,445.0); (25000,31000) mm at px (972.0,445.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +10": Structural Columns 0 -> 10 (+10, expected +10) |

```json
ops_run {"lines":[
  "op:add beam from=(0,0) to=(0,30000) level=\"Level 2\" type=250UB37.3",
  "op:add beam from=(24000,0) to=(24000,30000) level=\"Level 2\" type=250UB37.3"
]}
```

| Line | UNION answered |
|---|---|
| `op:add beam from=(0,0) to=(0,30000) level="Level 2" type=250UB37.3` | green: op:add beam made=beam-a36036ed77237122 changed= ms=9 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(24000,0) to=(24000,30000) level="Level 2" type=250UB37.3` | green: op:add beam made=beam-25130a7861c4d0aa changed= ms=5 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |

### The result

The model holds: Grids 7,Levels 2,Structural Columns 10,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1038. Brace a lift core over three storeys in a zigzag, 3.6 m storeys and a 6 m bay.

- Starts from: a new Structural project
- Ends with: levels at 0, 3600, 7200 and 10800, two columns to Level 4 and one brace in each storey, zigzagging up
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=3600",
  "op:add level elevation=7200 name=\"Level 3\"",
  "op:add level elevation=10800 name=\"Level 4\"",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 4\" type=250UC89.5",
  "op:add column at=(6000,0) level=\"Level 1\" top=\"Level 4\" type=250UC89.5",
  "op:add brace from=(0,0) to=(6000,0) level=\"Level 1\" top=\"Level 2\" type=114.3x3.6CHS",
  "op:add brace from=(6000,0) to=(0,0) level=\"Level 2\" top=\"Level 3\" type=114.3x3.6CHS",
  "op:add brace from=(0,0) to=(6000,0) level=\"Level 3\" top=\"Level 4\" type=114.3x3.6CHS"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=3600` | green: op:set made= changed="Level 2" ms=588 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=7200 name="Level 3"` | green: op:add level made="level-Level 3" changed= ms=71 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add level elevation=10800 name="Level 4"` | green: op:add level made="level-Level 4" changed= ms=10 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add column at=(0,0) level="Level 1" top="Level 4" type=250UC89.5` | green: op:add column made=column-759ada5fd512fac6 changed= ms=8 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1" top="Level 4" type=250UC89.5` | green: op:add column made=column-872dcdff906d9d35 changed= ms=9 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add brace from=(0,0) to=(6000,0) level="Level 1" top="Level 2" type=114.3x3.6CHS` | green: op:add brace made=brace-f8bd4ae1e1a53810 changed= ms=9 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add brace from=(6000,0) to=(0,0) level="Level 2" top="Level 3" type=114.3x3.6CHS` | green: op:add brace made=brace-77c1f157013d7d2b changed= ms=10 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add brace from=(0,0) to=(6000,0) level="Level 3" top="Level 4" type=114.3x3.6CHS` | green: op:add brace made=brace-395bfc015ec27014 changed= ms=10 Check "Structural Framing +1": Structural Framing 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 4,Structural Columns 2,Structural Framing 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1039. Cantilever three 460UB74.6 canopy beams 3 m out from a column line along the front of the building.

- Starts from: a new Structural project
- Ends with: three columns 4 m apart on one line and three beams projecting 3 m from their tops at Level 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=310UC118",
  "op:add column at=(0,4000) level=\"Level 1\" top=\"Level 2\" type=310UC118",
  "op:add column at=(0,8000) level=\"Level 1\" top=\"Level 2\" type=310UC118",
  "op:add beam from=(0,0) to=(-3000,0) level=\"Level 2\" type=460UB74.6",
  "op:add beam from=(0,4000) to=(-3000,4000) level=\"Level 2\" type=460UB74.6",
  "op:add beam from=(0,8000) to=(-3000,8000) level=\"Level 2\" type=460UB74.6"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=310UC118` | green: op:add column made=column-776f82ce3e3c183c changed= ms=29 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(0,4000) level="Level 1" top="Level 2" type=310UC118` | green: op:add column made=column-93a18f48b91b5409 changed= ms=5 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(0,8000) level="Level 1" top="Level 2" type=310UC118` | green: op:add column made=column-b2966ca857e6bafe changed= ms=4 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add beam from=(0,0) to=(-3000,0) level="Level 2" type=460UB74.6` | green: op:add beam made=beam-02a8998a5a3979de changed= ms=90 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,4000) to=(-3000,4000) level="Level 2" type=460UB74.6` | green: op:add beam made=beam-4c2e8adf5d9563da changed= ms=6 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,8000) to=(-3000,8000) level="Level 2" type=460UB74.6` | green: op:add beam made=beam-b83ca377c545684e changed= ms=5 Check "Structural Framing +1": Structural Framing 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 3,Structural Framing 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1040. Carry the tower columns on a 12 m transfer beam: a 1200WB278 welded beam on two 500WC440 columns over the podium.

- Starts from: a new Structural project
- Ends with: Level 2 at 5400 mm, two welded columns 12 m apart and a 1200WB278 beam across their tops
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=5400",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=500WC440",
  "op:add column at=(12000,0) level=\"Level 1\" top=\"Level 2\" type=500WC440",
  "op:add beam from=(0,0) to=(12000,0) level=\"Level 2\" type=1200WB278"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=5400` | green: op:set made= changed="Level 2" ms=19 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=500WC440` | green: op:add column made=column-6b3edcd597af1358 changed= ms=13 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(12000,0) level="Level 1" top="Level 2" type=500WC440` | green: op:add column made=column-ffb59b60faccbcbb changed= ms=6 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,0) to=(12000,0) level="Level 2" type=1200WB278` | green: op:add beam made=beam-9dbc9fb562ed0e6b changed= ms=15 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1041. Stiffen the roof plane of a 6 x 6 m bay with two crossing diagonal braces at eaves level.

- Starts from: a new Structural project
- Ends with: four eaves beams round a 6 m square and two flat diagonal braces across it at Level 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add beam from=(0,0) to=(6000,0) level=\"Level 2\" type=250UB25.7",
  "op:add beam from=(6000,0) to=(6000,6000) level=\"Level 2\" type=250UB25.7",
  "op:add beam from=(6000,6000) to=(0,6000) level=\"Level 2\" type=250UB25.7",
  "op:add beam from=(0,6000) to=(0,0) level=\"Level 2\" type=250UB25.7",
  "op:add brace from=(0,0) to=(6000,6000) level=\"Level 2\" top=\"Level 2\" type=48.3x2.9CHS",
  "op:add brace from=(6000,0) to=(0,6000) level=\"Level 2\" top=\"Level 2\" type=48.3x2.9CHS"
]}
```

| Line | UNION answered |
|---|---|
| `op:add beam from=(0,0) to=(6000,0) level="Level 2" type=250UB25.7` | green: op:add beam made=beam-f173412710d888ac changed= ms=42 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(6000,0) to=(6000,6000) level="Level 2" type=250UB25.7` | green: op:add beam made=beam-afe76254c3135ea3 changed= ms=7 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add beam from=(6000,6000) to=(0,6000) level="Level 2" type=250UB25.7` | green: op:add beam made=beam-05ae552a007336a7 changed= ms=6 Check "Structural Framing +1": Structural Framing 2 -> 3 (+1, expected +1) |
| `op:add beam from=(0,6000) to=(0,0) level="Level 2" type=250UB25.7` | green: op:add beam made=beam-c23c6a5399e7dc3b changed= ms=5 Check "Structural Framing +1": Structural Framing 3 -> 4 (+1, expected +1) |
| `op:add brace from=(0,0) to=(6000,6000) level="Level 2" top="Level 2" type=48.3x2.9CHS` | green: op:add brace made=brace-46d07673731b09ba changed= ms=7 Check "Structural Framing +1": Structural Framing 4 -> 5 (+1, expected +1) |
| `op:add brace from=(6000,0) to=(0,6000) level="Level 2" top="Level 2" type=48.3x2.9CHS` | green: op:add brace made=brace-8921914220ccae3e changed= ms=10 Check "Structural Framing +1": Structural Framing 5 -> 6 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Framing 6,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1042. Set out the column grid for a warehouse: six 9 m bays along its length, three 10 m bays across, a column at every crossing.

- Starts from: a new Structural project
- Ends with: seven gridlines at 9 m and four at 10 m with twenty-eight columns at the crossings
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,40000) name=A",
  "op:array id=grid-A count=7 step=(9000,0,0)",
  "op:add grid from=(-2000,0) to=(56000,0) name=1",
  "op:array id=grid-1 count=4 step=(0,10000,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,40000) name=A` | green: op:add grid made=grid-A changed= ms=74 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=7 step=(9000,0,0)` | green: op:array made=grid-A-03ba2dac1b8d5bb6,grid-A-22c4cc55bfe71326,grid-A-24d9cce585c464a7,grid-A-cb7a0c9d1b925ba7,grid-A-c030f2dba61d5ded,grid-A-22991361b3e5e9ac changed= ms=6 Check "Grids +6": Grids 1 -> 7 (+6, expected +6) |
| `op:add grid from=(-2000,0) to=(56000,0) name=1` | green: op:add grid made=grid-1 changed= ms=3 Check "Grids +1": Grids 7 -> 8 (+1, expected +1) |
| `op:array id=grid-1 count=4 step=(0,10000,0)` | green: op:array made=grid-1-858554c9b6672c3f,grid-1-5b82c4c2f65bcea0,grid-1-ffc7514ba06de70c changed= ms=3014 Check "Grids +3": Grids 8 -> 11 (+3, expected +3) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect nothing selected",
  "ribbon:Structure:Column · picks (-1000,-1000) (55000,31000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +28"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran Check "nothing selected": 0 selected |
| `ribbon:Structure:Column · picks (-1000,-1000) (55000,31000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +28` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-1000,-1000) mm at px (409.0,563.8) on the plan view \| (55000,31000) mm at px (1124.4,155.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +28": Structural Columns 0 -> 28 (+28, expected +28) |

### The result

The model holds: Grids 11,Levels 2,Structural Columns 28,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1043. Lay out the column grid of a car-park deck: four bays of 8.1 m and two rows of columns 16.2 m apart.

- Starts from: a new Structural project
- Ends with: five column lines at 8.1 m, two rows 16.2 m apart and ten columns
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,18200) name=A",
  "op:array id=grid-A count=5 step=(8100,0,0)",
  "op:add grid from=(-2000,0) to=(34400,0) name=1",
  "op:add grid from=(-2000,16200) to=(34400,16200) name=2"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,18200) name=A` | green: op:add grid made=grid-A changed= ms=74 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=5 step=(8100,0,0)` | green: op:array made=grid-A-f7f90ab9add271f3,grid-A-096de265b2b858b3,grid-A-4e37bac410c2d577,grid-A-f29a79cc0efcc183 changed= ms=7 Check "Grids +4": Grids 1 -> 5 (+4, expected +4) |
| `op:add grid from=(-2000,0) to=(34400,0) name=1` | green: op:add grid made=grid-1 changed= ms=8 Check "Grids +1": Grids 5 -> 6 (+1, expected +1) |
| `op:add grid from=(-2000,16200) to=(34400,16200) name=2` | green: op:add grid made=grid-2 changed= ms=4 Check "Grids +1": Grids 6 -> 7 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (33400,17200) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +10"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (33400,17200) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +10` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (33400,17200) mm at px (1269.6,106.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +10": Structural Columns 0 -> 10 (+10, expected +10) |

### The result

The model holds: Grids 7,Levels 2,Structural Columns 10,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1044. Add a basement car park 3.2 m down and put its columns on a 8.1 x 16.2 m grid, up to the ground floor.

- Starts from: a new Structural project
- Ends with: a Basement level at -3200, four gridlines at 8.1 m, two rows 16.2 m apart and eight columns from the Basement up
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=-3200 name=\"Basement\"",
  "op:add grid from=(0,-2000) to=(0,18200) name=A",
  "op:array id=grid-A count=4 step=(8100,0,0)",
  "op:add grid from=(-2000,0) to=(26300,0) name=1",
  "op:array id=grid-1 count=2 step=(0,16200,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=-3200 name="Basement"` | green: op:add level made=level-Basement changed= ms=116 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add grid from=(0,-2000) to=(0,18200) name=A` | green: op:add grid made=grid-A changed= ms=97 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=4 step=(8100,0,0)` | green: op:array made=grid-A-ac4ca5edd054202d,grid-A-08130d38c71e86f9,grid-A-f7837e7ccaf688ac changed= ms=8 Check "Grids +3": Grids 1 -> 4 (+3, expected +3) |
| `op:add grid from=(-2000,0) to=(26300,0) name=1` | green: op:add grid made=grid-1 changed= ms=4 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |
| `op:array id=grid-1 count=2 step=(0,16200,0)` | green: op:array made=grid-1-f890f04df61d9a0d changed= ms=7 Check "Grids +1": Grids 5 -> 6 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (25300,17200) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Basement · expect Structural Columns +8"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (25300,17200) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Basement · expect Structural Columns +8` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes; Level=Basement reads 'Basement' \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (25300,17200) mm at px (1118.8,106.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +8": Structural Columns 0 -> 8 (+8, expected +8) |

### The result

The model holds: Grids 6,Levels 3,Structural Columns 8,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1045. Set out a mezzanine at 3 m on its own grid, three lines 7.5 m apart by two lines 6 m apart, with a beam along each grid line.

- Starts from: a new Structural project
- Ends with: a Mezzanine level at 3000 mm, a 3 x 2 grid, six columns up to the mezzanine and five beams on it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=3000 name=\"Mezzanine\"",
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:array id=grid-A count=3 step=(7500,0,0)",
  "op:add grid from=(-2000,0) to=(17000,0) name=1",
  "op:array id=grid-1 count=2 step=(0,6000,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=3000 name="Mezzanine"` | green: op:add level made=level-Mezzanine changed= ms=13 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=77 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=3 step=(7500,0,0)` | green: op:array made=grid-A-5b380abe4fe66b5f,grid-A-d73a505e8c27e0a4 changed= ms=7 Check "Grids +2": Grids 1 -> 3 (+2, expected +2) |
| `op:add grid from=(-2000,0) to=(17000,0) name=1` | green: op:add grid made=grid-1 changed= ms=9 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:array id=grid-1 count=2 step=(0,6000,0)` | green: op:array made=grid-1-9d394e4a6efc196e changed= ms=5 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (16000,7000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (16000,7000) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +6` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (16000,7000) mm at px (945.8,296.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +6": Structural Columns 0 -> 6 (+6, expected +6) |

```json
ops_run {"lines":[
  "op:add beam from=(0,0) to=(15000,0) level=\"Mezzanine\" type=310UB32.0",
  "op:add beam from=(0,6000) to=(15000,6000) level=\"Mezzanine\" type=310UB32.0",
  "op:add beam from=(0,0) to=(0,6000) level=\"Mezzanine\" type=250UB25.7",
  "op:add beam from=(7500,0) to=(7500,6000) level=\"Mezzanine\" type=250UB25.7",
  "op:add beam from=(15000,0) to=(15000,6000) level=\"Mezzanine\" type=250UB25.7"
]}
```

| Line | UNION answered |
|---|---|
| `op:add beam from=(0,0) to=(15000,0) level="Mezzanine" type=310UB32.0` | green: op:add beam made=beam-e82d29e2b892893f changed= ms=10 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,6000) to=(15000,6000) level="Mezzanine" type=310UB32.0` | green: op:add beam made=beam-3c5184ecd0786b99 changed= ms=6 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,0) to=(0,6000) level="Mezzanine" type=250UB25.7` | green: op:add beam made=beam-efebcea5ab5b9d80 changed= ms=13 Check "Structural Framing +1": Structural Framing 2 -> 3 (+1, expected +1) |
| `op:add beam from=(7500,0) to=(7500,6000) level="Mezzanine" type=250UB25.7` | green: op:add beam made=beam-ae40b084a1dbf2c1 changed= ms=8 Check "Structural Framing +1": Structural Framing 3 -> 4 (+1, expected +1) |
| `op:add beam from=(15000,0) to=(15000,6000) level="Mezzanine" type=250UB25.7` | green: op:add beam made=beam-e7c46f205c3a01be changed= ms=6 Check "Structural Framing +1": Structural Framing 4 -> 5 (+1, expected +1) |

### The result

The model holds: Grids 5,Levels 3,Structural Columns 6,Structural Framing 5,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1047. Stack the columns of a two-deck car park: decks at 2.9 m and 5.8 m, eight columns on each deck, on a 8.1 x 16.2 m grid.

- Starts from: a new Structural project
- Ends with: levels at 0, 2900 and 5800, a 4 x 2 grid and eight columns standing on Level 1 and eight on Level 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=2900",
  "op:add level elevation=5800 name=\"Level 3\"",
  "op:add grid from=(0,-2000) to=(0,18200) name=A",
  "op:array id=grid-A count=4 step=(8100,0,0)",
  "op:add grid from=(-2000,0) to=(26300,0) name=1",
  "op:array id=grid-1 count=2 step=(0,16200,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=2900` | green: op:set made= changed="Level 2" ms=335 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=5800 name="Level 3"` | green: op:add level made="level-Level 3" changed= ms=108 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add grid from=(0,-2000) to=(0,18200) name=A` | green: op:add grid made=grid-A changed= ms=150 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=4 step=(8100,0,0)` | green: op:array made=grid-A-47d0153e35935f79,grid-A-564e8786db9a0457,grid-A-d236d27db0d655d2 changed= ms=7 Check "Grids +3": Grids 1 -> 4 (+3, expected +3) |
| `op:add grid from=(-2000,0) to=(26300,0) name=1` | green: op:add grid made=grid-1 changed= ms=5 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |
| `op:array id=grid-1 count=2 step=(0,16200,0)` | green: op:array made=grid-1-b8332cebdf4ae6b2 changed= ms=5 Check "Grids +1": Grids 5 -> 6 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (25300,17200) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Level 1 · expect Structural Columns +8",
  "ribbon:Structure:Column · picks (-1000,-1000) (25300,17200) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Level 2 · expect Structural Columns +8"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (25300,17200) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Level 1 · expect Structural Columns +8` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes; Level=Level 1 reads 'Level 1' \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (25300,17200) mm at px (1118.8,106.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +8": Structural Columns 0 -> 8 (+8, expected +8) |
| `ribbon:Structure:Column · picks (-1000,-1000) (25300,17200) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Level 2 · expect Structural Columns +8` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes; Level=Level 2 reads 'Level 2' \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (25300,17200) mm at px (1118.8,106.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +8": Structural Columns 8 -> 16 (+8, expected +8) |

### The result

The model holds: Grids 6,Levels 3,Structural Columns 16,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1048. Build a five-storey steel frame at 3.8 m storeys by copying Level 2 up, then run four corner columns to the top.

- Starts from: a new Structural project
- Ends with: levels at 0, 3800, 7600, 11400 and 15200 and four 310UC158 columns from Level 1 to Level 5
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=3800",
  "op:copy id=\"Level 2\" by=(0,0,3800)",
  "op:copy id=\"Level 2\" by=(0,0,7600)",
  "op:copy id=\"Level 2\" by=(0,0,11400)",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 5\" type=310UC158",
  "op:add column at=(9000,0) level=\"Level 1\" top=\"Level 5\" type=310UC158",
  "op:add column at=(9000,7500) level=\"Level 1\" top=\"Level 5\" type=310UC158",
  "op:add column at=(0,7500) level=\"Level 1\" top=\"Level 5\" type=310UC158"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=3800` | green: op:set made= changed="Level 2" ms=29 Check "every count unchanged": the counts: no count changed |
| `op:copy id="Level 2" by=(0,0,3800)` | green: op:copy made="level-Level 3" changed= ms=22 note=Level 3 placed at 7600 mm; Floor Plan made Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:copy id="Level 2" by=(0,0,7600)` | green: op:copy made="level-Level 4" changed= ms=16 note=Level 4 placed at 11400 mm; Floor Plan made Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:copy id="Level 2" by=(0,0,11400)` | green: op:copy made="level-Level 5" changed= ms=14 note=Level 5 placed at 15200 mm; Floor Plan made Check "Levels +1": Levels 4 -> 5 (+1, expected +1) |
| `op:add column at=(0,0) level="Level 1" top="Level 5" type=310UC158` | green: op:add column made=column-b0b879319b308e1a changed= ms=6 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(9000,0) level="Level 1" top="Level 5" type=310UC158` | green: op:add column made=column-27ffc72bec65fe92 changed= ms=5 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(9000,7500) level="Level 1" top="Level 5" type=310UC158` | green: op:add column made=column-75428c1b0b2ea3db changed= ms=8 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,7500) level="Level 1" top="Level 5" type=310UC158` | green: op:add column made=column-c52355a574489d5e changed= ms=7 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 5,Structural Columns 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 4,view: Structural Plan 2.

## 1049. The slab is being raised 600 mm for flood protection: lift Level 1 to 600, then span a beam across the two columns that stand on it.

- Starts from: a new Structural project
- Ends with: two columns on Level 1, Level 1 raised to 600 mm and a beam on Level 2 over them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=250UC89.5",
  "op:add column at=(6000,0) level=\"Level 1\" top=\"Level 2\" type=250UC89.5",
  "op:set id=\"Level 1\" key=Elevation value=600",
  "op:add beam from=(0,0) to=(6000,0) level=\"Level 2\" type=360UB50.7"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=250UC89.5` | green: op:add column made=column-b553a0bbbc03fef7 changed= ms=83 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1" top="Level 2" type=250UC89.5` | green: op:add column made=column-f552335f4fbc02c0 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:set id="Level 1" key=Elevation value=600` | green: op:set made= changed="Level 1",column-b553a0bbbc03fef7,column-f552335f4fbc02c0 ms=14 Check "every count unchanged": the counts: no count changed |
| `op:add beam from=(0,0) to=(6000,0) level="Level 2" type=360UB50.7` | green: op:add beam made=beam-60154c3ad54395ad changed= ms=9 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1050. Rename gridlines A to D as P1 to P4 to match the client's pier numbers.

- Starts from: a new Structural project
- Ends with: four gridlines at 7 m named P1, P2, P3 and P4
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,10000) name=A",
  "op:add grid from=(7000,-2000) to=(7000,10000) name=B",
  "op:add grid from=(14000,-2000) to=(14000,10000) name=C",
  "op:add grid from=(21000,-2000) to=(21000,10000) name=D",
  "op:set id=grid-A key=Name value=P1",
  "op:set id=grid-B key=Name value=P2",
  "op:set id=grid-C key=Name value=P3",
  "op:set id=grid-D key=Name value=P4"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,10000) name=A` | green: op:add grid made=grid-A changed= ms=103 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(7000,-2000) to=(7000,10000) name=B` | green: op:add grid made=grid-B changed= ms=5 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(14000,-2000) to=(14000,10000) name=C` | green: op:add grid made=grid-C changed= ms=4 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add grid from=(21000,-2000) to=(21000,10000) name=D` | green: op:add grid made=grid-D changed= ms=5 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:set id=grid-A key=Name value=P1` | green: op:set made= changed=grid-A ms=7 Check "every count unchanged": the counts: no count changed |
| `op:set id=grid-B key=Name value=P2` | green: op:set made= changed=grid-B ms=4 Check "every count unchanged": the counts: no count changed |
| `op:set id=grid-C key=Name value=P3` | green: op:set made= changed=grid-C ms=3 Check "every count unchanged": the counts: no count changed |
| `op:set id=grid-D key=Name value=P4` | green: op:set made= changed=grid-D ms=104 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Grids 4,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1051. Fit the grid to an angled boundary: pull gridline A 400 mm west and swing gridline B 5 degrees about its foot.

- Starts from: a new Structural project
- Ends with: gridline A moved 400 mm west and gridline B rotated 5 degrees about (6000,0)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,12000) name=A",
  "op:add grid from=(6000,-2000) to=(6000,12000) name=B",
  "op:move id=grid-A by=(-400,0,0)",
  "op:rotate id=grid-B about=(6000,0) angle=5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,12000) name=A` | green: op:add grid made=grid-A changed= ms=88 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(6000,-2000) to=(6000,12000) name=B` | green: op:add grid made=grid-B changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:move id=grid-A by=(-400,0,0)` | green: op:move made= changed=grid-A ms=30 Check "moved": 1 element(s) moved: grid-A  -> |
| `op:rotate id=grid-B about=(6000,0) angle=5` | green: op:rotate made= changed=grid-B ms=5 Check "moved": 1 element(s) moved: grid-B  -> |

### The result

The model holds: Grids 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1052. Add a half level at 1.5 m for a split-level house and carry a column up from Ground to it, then on to Level 1.

- Starts from: a new Architectural project
- Ends with: a Split Level at 1500 mm, Level 1 at 3200 mm and two stacked columns Ground to Split Level to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=1500 name=\"Split Level\"",
  "op:set id=\"level-Level 1\" key=Elevation value=3200",
  "op:add column at=(0,0) level=Ground top=\"Split Level\" type=200UC46.2",
  "op:add column at=(0,0) level=\"Split Level\" top=\"Level 1\" type=200UC46.2"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=1500 name="Split Level"` | green: op:add level made="level-Split Level" changed= ms=16 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:set id="level-Level 1" key=Elevation value=3200` | green: op:set made= changed="level-Level 1" ms=8 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level=Ground top="Split Level" type=200UC46.2` | green: op:add column made=column-22ff130f0da6950a changed= ms=10 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(0,0) level="Split Level" top="Level 1" type=200UC46.2` | green: op:add column made=column-0f9969d12e5ca820 changed= ms=4 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 4,Structural Columns 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1053. Put a 3 x 2 grid at 6 m on the house plan and a column at every crossing on the ground floor.

- Starts from: a new Architectural project
- Ends with: three gridlines and two cross lines at 6 m and six columns from Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:array id=grid-A count=3 step=(6000,0,0)",
  "op:add grid from=(-2000,0) to=(14000,0) name=1",
  "op:array id=grid-1 count=2 step=(0,6000,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=57 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=3 step=(6000,0,0)` | green: op:array made=grid-A-db975bb695c99021,grid-A-6ffa0c915a288036 changed= ms=6 Check "Grids +2": Grids 1 -> 3 (+2, expected +2) |
| `op:add grid from=(-2000,0) to=(14000,0) name=1` | green: op:add grid made=grid-1 changed= ms=4 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:array id=grid-1 count=2 step=(0,6000,0)` | green: op:array made=grid-1-299b4e408adfde15 changed= ms=4 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (13000,7000) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Ground · expect Structural Columns +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (13000,7000) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Ground · expect Structural Columns +6` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes; Level=Ground reads 'Ground' \| picks: (-1000,-1000) mm at px (579.9,456.3) on the plan view \| (13000,7000) mm at px (990.6,221.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +6": Structural Columns 0 -> 6 (+6, expected +6) |

### The result

The model holds: Grids 5,Levels 3,Structural Columns 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1054. Carry the upper floor over a 9 m open-plan ground floor on a 610UB125 steel beam and two 310UC158 columns.

- Starts from: a new Architectural project
- Ends with: two columns 9 m apart from Ground to Level 1 and a 610UB125 beam on Level 1 between them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=Ground top=\"Level 1\" type=310UC158",
  "op:add column at=(9000,0) level=Ground top=\"Level 1\" type=310UC158",
  "op:add beam from=(0,0) to=(9000,0) level=\"Level 1\" type=610UB125"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level=Ground top="Level 1" type=310UC158` | green: op:add column made=column-6c99e962e5da66b7 changed= ms=17 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(9000,0) level=Ground top="Level 1" type=310UC158` | green: op:add column made=column-806017a211dc74d4 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,0) to=(9000,0) level="Level 1" type=610UB125` | green: op:add beam made=beam-83f83869f626e363 changed= ms=4 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 2,Structural Framing 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1055. Brace a 3 m wide lift shaft with two 150UC37.2 columns and a cross of 100UC14.8 braces from Ground to Level 1.

- Starts from: a new Architectural project
- Ends with: two columns 3 m apart and two crossing braces between Ground and Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=Ground top=\"Level 1\" type=150UC37.2",
  "op:add column at=(3000,0) level=Ground top=\"Level 1\" type=150UC37.2",
  "op:add brace from=(0,0) to=(3000,0) level=Ground top=\"Level 1\" type=100UC14.8",
  "op:add brace from=(3000,0) to=(0,0) level=Ground top=\"Level 1\" type=100UC14.8"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level=Ground top="Level 1" type=150UC37.2` | green: op:add column made=column-f7f308f7bb3a2465 changed= ms=17 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(3000,0) level=Ground top="Level 1" type=150UC37.2` | green: op:add column made=column-894fffeb941283c3 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add brace from=(0,0) to=(3000,0) level=Ground top="Level 1" type=100UC14.8` | green: op:add brace made=brace-2cd7df14c06f6924 changed= ms=7 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add brace from=(3000,0) to=(0,0) level=Ground top="Level 1" type=100UC14.8` | green: op:add brace made=brace-b169f489a34e0709 changed= ms=5 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 2,Structural Framing 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1056. Frame the roof of a 12 x 8 m building in steel: four columns Ground to the Roof, a ring beam by clicks and one purlin across the middle.

- Starts from: a new Architectural project
- Ends with: four 250UC72.9 columns, four chained roof beams and one 4 m centre beam at the Roof level
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=Ground top=Roof type=250UC72.9",
  "op:add column at=(12000,0) level=Ground top=Roof type=250UC72.9",
  "op:add column at=(12000,8000) level=Ground top=Roof type=250UC72.9",
  "op:add column at=(0,8000) level=Ground top=Roof type=250UC72.9"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level=Ground top=Roof type=250UC72.9` | green: op:add column made=column-24482f966a4bceb1 changed= ms=13 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(12000,0) level=Ground top=Roof type=250UC72.9` | green: op:add column made=column-28db6ebd0fd1dc36 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(12000,8000) level=Ground top=Roof type=250UC72.9` | green: op:add column made=column-b8c28fc3e344449c changed= ms=4 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,8000) level=Ground top=Roof type=250UC72.9` | green: op:add column made=column-71904449fff45af0 changed= ms=3 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Beam · picks (0,0) (12000,0) (12000,8000) (0,8000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Roof · expect Structural Framing +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Beam · picks (0,0) (12000,0) (12000,8000) (0,8000) (0,0) · keys Escape Escape · fields Options Strip: Chain=yes; Placement Plane=Roof · expect Structural Framing +4` | green: pressed 'Beam' on Structure's Framing panel: the tool 'Beam' stands \| fields: Chain=yes reads yes; Placement Plane=Roof reads 'Roof' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (12000,0) mm at px (1000.0,427.0) on the plan view \| (12000,8000) mm at px (1000.0,192.3) on the plan view \| (0,8000) mm at px (648.0,192.3) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Beam -> tool Beam, 'Beam' still stands (the key went to union_shell::Viewport)); Escape (tool Beam -> no tool) Check "Structural Framing +4": Structural Framing 0 -> 4 (+4, expected +4) |

```json
ops_run {"lines":[
  "op:add beam from=(0,4000) to=(12000,4000) level=Roof type=200UB22.3"
]}
```

| Line | UNION answered |
|---|---|
| `op:add beam from=(0,4000) to=(12000,4000) level=Roof type=200UB22.3` | green: op:add beam made=beam-d632c090e55a0e42 changed= ms=5 Check "Structural Framing +1": Structural Framing 4 -> 5 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 4,Structural Framing 5,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1057. Draw one 250UC89.5 column and array it into a colonnade of eight at 3.6 m along the front of the building.

- Starts from: a new Architectural project
- Ends with: a row of eight 250UC89.5 columns 3.6 m apart from Ground to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(6000,-3000) level=Ground top=\"Level 1\" type=250UC89.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(6000,-3000) level=Ground top="Level 1" type=250UC89.5` | green: op:add column made=column-d261c52de6e969e1 changed= ms=19 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (6000,-3000) · keys — · fields — · expect column selected",
  "ribbon:Modify:Array · picks (6000,-3000) (9600,-3000) · keys Return · fields Options Strip: Number=8; Group And Associate=no · expect Structural Columns +7"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (6000,-3000) · keys — · fields — · expect column selected` | green: select: (6000,-3000) mm at px (824.0,515.0) on the plan view; picked 'column-d261c52de6e969e1'; selected 0 -> 1 [column-d261c52de6e969e1] \| picks: the plan band pressed these 1 pick(s) as its own process Check "column selected": 1 selected (column-d261c52de6e969e1) (words not read: 'column') |
| `ribbon:Modify:Array · picks (6000,-3000) (9600,-3000) · keys Return · fields Options Strip: Number=8; Group And Associate=no · expect Structural Columns +7` | green: pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands \| fields: Number=8 reads '8.00'; Group And Associate=no reads no \| picks: (6000,-3000) mm at px (824.0,515.0) on the plan view \| (9600,-3000) mm at px (929.6,515.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Return (tool Array -> tool Array) Check "Structural Columns +7": Structural Columns 1 -> 8 (+7, expected +7) |

### The result

The model holds: Levels 3,Structural Columns 8,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1058. Add a plant deck level 2.4 m above the roof and frame it: two columns up from the roof and a beam across them.

- Starts from: a new Architectural project
- Ends with: a Plant level at 8400 mm, two columns from the Roof to Plant and a beam on Plant
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=8400 name=\"Plant\"",
  "op:add column at=(0,0) level=Roof top=\"Plant\" type=150UC30.0",
  "op:add column at=(4000,0) level=Roof top=\"Plant\" type=150UC30.0",
  "op:add beam from=(0,0) to=(4000,0) level=\"Plant\" type=250UB25.7"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=8400 name="Plant"` | green: op:add level made=level-Plant changed= ms=19 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add column at=(0,0) level=Roof top="Plant" type=150UC30.0` | green: op:add column made=column-79b050bb83867043 changed= ms=5 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(4000,0) level=Roof top="Plant" type=150UC30.0` | green: op:add column made=column-ff29442ecac9b0c5 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,0) to=(4000,0) level="Plant" type=250UB25.7` | green: op:add beam made=beam-a47080bddea35eb3 changed= ms=123 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 4,Structural Columns 2,Structural Framing 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1059. Add Level 3 at 7200 mm with its own structural framing plan and put a beam on it.

- Starts from: a new Structural project
- Ends with: Level 3 at 7200 mm, a Level 3 Framing Plan view and one beam on Level 3
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=7200 name=\"Level 3\"",
  "op:add view kind=structural level=\"Level 3\" name=\"Level 3 Framing Plan\"",
  "op:add beam from=(0,0) to=(7200,0) level=\"Level 3\" type=310UB40.4"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=7200 name="Level 3"` | green: op:add level made="level-Level 3" changed= ms=81 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:add view kind=structural level="Level 3" name="Level 3 Framing Plan"` | green: op:add view made=826a52100f52452d8cada04e68191e3e changed= ms=8 Check "view: Structural Plan +1": view: Structural Plan 2 -> 3 (+1, expected +1) |
| `op:add beam from=(0,0) to=(7200,0) level="Level 3" type=310UB40.4` | green: op:add beam made=beam-67a527a837a011f6 changed= ms=4 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 3.

## 1060. Prop a wall column with a 3 m raking brace rising 3 m from the slab.

- Starts from: a new Structural project
- Ends with: a 200UC52.2 column and a 139.7 x 3.5 tube brace rising from the slab level at (3000,0) to 3000 mm up the column
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=200UC52.2",
  "op:add brace from=(3000,0) to=(0,0) level=\"Level 1\" top=\"Level 1\" start_offset=0 end_offset=3000 type=139.7x3.5CHS"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=200UC52.2` | green: op:add column made=column-3e6f24b44bf0ddc5 changed= ms=19 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add brace from=(3000,0) to=(0,0) level="Level 1" top="Level 1" start_offset=0 end_offset=3000 type=139.7x3.5CHS` | green: op:add brace made=brace-8af5693ef602f16c changed= ms=7 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 1,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1061. Click in a new level at 4.5 m with the Level tool, then stand a column from Level 1 up to Level 2.

- Starts from: a new Structural project
- Ends with: a third level at 4500 mm drawn with the Level tool and a column from Level 1 to Level 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Setout:Level · picks (-3000,0) (20000,0) · keys Escape Escape · fields Options Strip: Offset=4500 · expect Levels +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Setout:Level · picks (-3000,0) (20000,0) · keys Escape Escape · fields Options Strip: Offset=4500 · expect Levels +1` | green: pressed 'Level' on Setout's Datum panel: the tool 'Level' stands \| fields: Offset=4500 reads '4500 mm' \| picks: (-3000,0) mm at px (592.2,427.0) on the plan view \| (20000,0) mm at px (1020.2,427.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Level -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=250UC72.9"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1" top="Level 2" type=250UC72.9` | green: op:add column made=column-fd23069bb4b83b7b changed= ms=6 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 2,view: Structural Plan 2.

## 1062. Copy Level 2 up 4.2 m for the hospital's plant floor, call the copy Plant Floor and run a column up to it.

- Starts from: a new Structural project
- Ends with: Level 2 at 4200 mm, a copied level at 8400 mm renamed Plant Floor and a column from Level 1 up to it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"Level 2\" key=Elevation value=4200",
  "op:copy id=\"Level 2\" by=(0,0,4200)",
  "op:set id=\"level-Level 3\" key=Name value=\"Plant Floor\"",
  "op:add column at=(0,0) level=\"Level 1\" top=\"Plant Floor\" type=310UC137"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="Level 2" key=Elevation value=4200` | green: op:set made= changed="Level 2" ms=16 Check "every count unchanged": the counts: no count changed |
| `op:copy id="Level 2" by=(0,0,4200)` | green: op:copy made="level-Level 3" changed= ms=11 note=Level 3 placed at 8400 mm; Floor Plan made Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:set id="level-Level 3" key=Name value="Plant Floor"` | green: op:set made= changed="level-Level 3" ms=3 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level="Level 1" top="Plant Floor" type=310UC137` | green: op:add column made=column-562c4f78e720d303 changed= ms=7 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Structural Columns 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 2,view: Structural Plan 2.

## 1063. Two grid lines cross at 45 degrees on a corner site: draw one, copy it round 45 degrees and put a column where they cross.

- Starts from: a new Architectural project
- Ends with: two 10 m grid lines crossing at the origin at 45 degrees and one 250UC72.9 column at their crossing
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(-5000,0) to=(5000,0) name=A",
  "op:rotate id=grid-A about=(0,0) angle=45 copy=yes"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(-5000,0) to=(5000,0) name=A` | green: op:add grid made=grid-A changed= ms=44 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:rotate id=grid-A about=(0,0) angle=45 copy=yes` | green: op:rotate made=grid-A-57fe1877ad052be8 changed= ms=40 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (1000,1000) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Ground · expect Structural Columns +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (1000,1000) · keys Escape Escape · fields Options Strip: At Grids=yes; Level=Ground · expect Structural Columns +1` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes; Level=Ground reads 'Ground' \| picks: (-1000,-1000) mm at px (618.7,456.3) on the plan view \| (1000,1000) mm at px (677.3,397.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

### The result

The model holds: Grids 2,Levels 3,Structural Columns 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 1066. Put columns at every crossing of a 2 x 2 grid, take the whole lot back with Undo, then bring it back with Redo.

- Starts from: a new Structural project
- Ends with: four columns at the crossings of a 7.2 m grid after an Undo and a Redo
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,9200) name=A",
  "op:array id=grid-A count=2 step=(7200,0,0)",
  "op:add grid from=(-2000,0) to=(9200,0) name=1",
  "op:array id=grid-1 count=2 step=(0,7200,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,9200) name=A` | green: op:add grid made=grid-A changed= ms=113 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=2 step=(7200,0,0)` | green: op:array made=grid-A-21fd5cddec8f1a2d changed= ms=5 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(-2000,0) to=(9200,0) name=1` | green: op:add grid made=grid-1 changed= ms=4 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:array id=grid-1 count=2 step=(0,7200,0)` | green: op:array made=grid-1-ccc1805d32d89bd2 changed= ms=7 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Structure:Column · picks (-1000,-1000) (8200,8200) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +4",
  "qa:Undo · picks — · keys — · fields — · expect Structural Columns -4",
  "qa:Redo · picks — · keys — · fields — · expect Structural Columns +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Column · picks (-1000,-1000) (8200,8200) · keys Escape Escape · fields Options Strip: At Grids=yes · expect Structural Columns +4` | green: pressed 'Column' on Structure's Structure panel: the tool 'Column' stands \| fields: At Grids=yes reads yes \| picks: (-1000,-1000) mm at px (629.4,445.6) on the plan view \| (8200,8200) mm at px (800.6,274.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +4": Structural Columns 0 -> 4 (+4, expected +4) |
| `qa:Undo · picks — · keys — · fields — · expect Structural Columns -4` | green: QToolButton pressed; a command ran Check "Structural Columns -4": Structural Columns 4 -> 0 (-4, expected -4) |
| `qa:Redo · picks — · keys — · fields — · expect Structural Columns +4` | green: QToolButton pressed; a command ran Check "Structural Columns +4": Structural Columns 0 -> 4 (+4, expected +4) |

### The result

The model holds: Grids 4,Levels 2,Structural Columns 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 1067. The building steps down: add a Low Roof level at 5400 mm, lift the main Roof to 7200 mm and carry a column to each.

- Starts from: a new Architectural project
- Ends with: a Low Roof at 5400 mm, the Roof at 7200 mm, one column to the Low Roof and one to the Roof
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=5400 name=\"Low Roof\"",
  "op:set id=level-Roof key=Elevation value=7200",
  "op:add column at=(0,0) level=Ground top=\"Low Roof\" type=200UC46.2",
  "op:add column at=(8000,0) level=Ground top=Roof type=200UC46.2"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=5400 name="Low Roof"` | green: op:add level made="level-Low Roof" changed= ms=17 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:set id=level-Roof key=Elevation value=7200` | green: op:set made= changed=level-Roof ms=7 Check "every count unchanged": the counts: no count changed |
| `op:add column at=(0,0) level=Ground top="Low Roof" type=200UC46.2` | green: op:add column made=column-defe20bf8cd7150c changed= ms=8 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(8000,0) level=Ground top=Roof type=200UC46.2` | green: op:add column made=column-2a7982897b5c6c9b changed= ms=43 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 4,Structural Columns 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
