# UNION examples: Change, modify and freeform

72 drafting jobs, each the request in plain words, the exact calls an AI sends to UNION, and UNION's answer to each, played green on UNION 1.0.0-beta.2.

## 6001. Move the partition wall 1.5 m to the north.

- Starts from: a new Architectural project
- Ends with: one 6 m partition wall on Ground, standing 1500 mm north of where it was drawn
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,3000) to=(18000,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,3000) to=(18000,3000) level=Ground` | green: op:add wall made=wall-7f373cb7f8d305df changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Move · picks (15000,3000) (15000,4500) · keys Escape Escape · fields — · expect moved",
  "plan:select · picks (15000,4500) · keys — · fields — · expect 1 selected",
  "plan:deselect · picks — · keys — · fields — · expect nothing selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (1088.0,339.0) on the plan view; picked 'wall-7f373cb7f8d305df'; selected 0 -> 1 [wall-7f373cb7f8d305df] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-7f373cb7f8d305df) (expected exactly 1) |
| `ribbon:Modify:Move · picks (15000,3000) (15000,4500) · keys Escape Escape · fields — · expect moved` | green: pressed 'Move' on Modify's Modify panel (through its fold): the tool 'Move' stands \| picks: (15000,3000) mm at px (1021.7,339.0) on the plan view \| (15000,4500) mm at px (1021.7,295.0) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: wall-7f373cb7f8d305df  -> |
| `plan:select · picks (15000,4500) · keys — · fields — · expect 1 selected` | green: select: (15000,4500) mm at px (1021.7,295.0) on the plan view; picked 'wall-7f373cb7f8d305df'; selected 0 -> 1 [wall-7f373cb7f8d305df] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-7f373cb7f8d305df) (expected exactly 1) |
| `plan:deselect · picks — · keys — · fields — · expect nothing selected` | green: deselect: cleared as a press on nothing clears; selected 1 -> 0 [] Check "nothing selected": 0 selected |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6002. Copy this 6 m wall 3.6 m north to make the other side of the corridor.

- Starts from: a new Architectural project
- Ends with: two parallel 6 m walls on Ground, 3600 mm apart
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(18000,2000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(18000,2000) level=Ground` | green: op:add wall made=wall-2407adde0045f1c5 changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Copy · picks (15000,2000) (15000,5600) · keys Escape Escape · fields — · expect Walls +1",
  "plan:select · picks (15000,5600) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected` | green: select: (15000,2000) mm at px (1088.0,368.3) on the plan view; picked 'wall-2407adde0045f1c5'; selected 0 -> 1 [wall-2407adde0045f1c5] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-2407adde0045f1c5) (expected exactly 1) |
| `ribbon:Modify:Copy · picks (15000,2000) (15000,5600) · keys Escape Escape · fields — · expect Walls +1` | green: pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands \| picks: (15000,2000) mm at px (1021.7,368.3) on the plan view \| (15000,5600) mm at px (1021.7,262.7) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `plan:select · picks (15000,5600) · keys — · fields — · expect 1 selected` | green: select: (15000,5600) mm at px (1021.7,262.7) on the plan view; picked 'wall-2407adde0045f1c5-3110aa92ebb42796'; selected 0 -> 1 [wall-2407adde0045f1c5-3110aa92ebb42796] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-2407adde0045f1c5-3110aa92ebb42796) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6003. Turn the 5 m wall a quarter turn about its centre so it runs north to south.

- Starts from: a new Architectural project
- Ends with: one 5 m wall on Ground running north to south through (14500,3000)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,3000) to=(17000,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,3000) to=(17000,3000) level=Ground` | green: op:add wall made=wall-384c5ae08194a29e changed= ms=13 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (14500,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Rotate · picks (14500,3000) (17000,3000) (14500,5500) · keys Escape Escape · fields — · expect moved",
  "plan:select · picks (14500,4500) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (14500,3000) · keys — · fields — · expect 1 selected` | green: select: (14500,3000) mm at px (1073.4,339.0) on the plan view; picked 'wall-384c5ae08194a29e'; selected 0 -> 1 [wall-384c5ae08194a29e] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-384c5ae08194a29e) (expected exactly 1) |
| `ribbon:Modify:Rotate · picks (14500,3000) (17000,3000) (14500,5500) · keys Escape Escape · fields — · expect moved` | green: pressed 'Rotate' on Modify's Modify panel (through its fold): the tool 'Rotate' stands \| picks: (14500,3000) mm at px (1021.7,339.0) on the plan view \| (17000,3000) mm at px (1095.0,339.0) on the plan view \| (14500,5500) mm at px (1021.7,265.7) on the plan view \| presses to the tool 3 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: wall-384c5ae08194a29e  -> |
| `plan:select · picks (14500,4500) · keys — · fields — · expect 1 selected` | green: select: (14500,4500) mm at px (1021.7,295.0) on the plan view; picked 'wall-384c5ae08194a29e'; selected 0 -> 1 [wall-384c5ae08194a29e] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-384c5ae08194a29e) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6004. Mirror the 4 m entrance wall across a centre line at y = 5000 so the lobby is symmetrical.

- Starts from: a new Architectural project
- Ends with: the entrance wall on Ground and its mirror image 6000 mm north of it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(16000,2000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(16000,2000) level=Ground` | green: op:add wall made=wall-8968c45306529baf changed= ms=16 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (14000,2000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Mirror › Draw Axis · picks (10500,5000) (20000,5000) · keys Escape Escape · fields — · expect Walls +1",
  "plan:select · picks (14000,8000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (14000,2000) · keys — · fields — · expect 1 selected` | green: select: (14000,2000) mm at px (1058.7,368.3) on the plan view; picked 'wall-8968c45306529baf'; selected 0 -> 1 [wall-8968c45306529baf] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-8968c45306529baf) (expected exactly 1) |
| `ribbon:Modify:Mirror › Draw Axis · picks (10500,5000) (20000,5000) · keys Escape Escape · fields — · expect Walls +1` | green: pressed 'Mirror › Draw Axis' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Draw Axis'; the press stood 221 ms (the menu stood at 46 ms; its row ran 162 ms; it made 0 child widgets native)): the tool 'Mirror › Draw Axis' stands \| picks: (10500,5000) mm at px (919.0,280.3) on the plan view \| (20000,5000) mm at px (1197.7,280.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `plan:select · picks (14000,8000) · keys — · fields — · expect 1 selected` | green: select: (14000,8000) mm at px (1021.7,192.3) on the plan view; picked 'wall-8968c45306529baf-130169a93baec661'; selected 0 -> 1 [wall-8968c45306529baf-130169a93baec661] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-8968c45306529baf-130169a93baec661) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6005. Mirror the north wing wall across the corridor wall.

- Starts from: a new Architectural project
- Ends with: the 9 m corridor wall, the 4 m wing wall to its north and a mirrored wing wall to its south
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(11000,5000) to=(20000,5000) level=Ground",
  "op:add wall from=(14000,6000) to=(14000,10000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(11000,5000) to=(20000,5000) level=Ground` | green: op:add wall made=wall-de682533ab9965c3 changed= ms=11 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(14000,6000) to=(14000,10000) level=Ground` | green: op:add wall made=wall-f9a5c86d76d997a4 changed= ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (14000,9000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Mirror › Pick Axis · picks (18000,5000) · keys Escape Escape · fields — · expect Walls +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (14000,1000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (14000,9000) · keys — · fields — · expect 1 selected` | green: select: (14000,9000) mm at px (963.0,163.0) on the plan view; picked 'wall-f9a5c86d76d997a4'; selected 0 -> 1 [wall-f9a5c86d76d997a4] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-f9a5c86d76d997a4) (expected exactly 1) |
| `ribbon:Modify:Mirror › Pick Axis · picks (18000,5000) · keys Escape Escape · fields — · expect Walls +1` | green: pressed 'Mirror › Pick Axis' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Pick Axis'; the press stood 361 ms (the menu stood at 22 ms; its row ran 338 ms; it made 0 child widgets native)): the tool 'Mirror › Pick Axis' stands \| picks: (18000,5000) mm at px (1080.4,280.3) on the plan view \| presses to the tool 1 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (14000,1000) · keys — · fields — · expect 1 selected` | green: select: (14000,1000) mm at px (963.0,397.7) on the plan view; picked 'wall-f9a5c86d76d997a4-6973a8b7aa629f4d'; selected 0 -> 1 [wall-f9a5c86d76d997a4-6973a8b7aa629f4d] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-f9a5c86d76d997a4-6973a8b7aa629f4d) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6006. Array this 3 m wall four times at 2 m centres for the cubicle partitions.

- Starts from: a new Architectural project
- Ends with: four 3 m walls on Ground at 2000 mm centres, the last one at x = 18000
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(12000,5000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(12000,5000) level=Ground` | green: op:add wall made=wall-08c51e8158be8b03 changed= ms=47 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (12000,3500) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Array · picks (12000,3500) (14000,3500) · keys Escape Escape · fields Options Strip: Number=4 · expect Walls +3",
  "plan:select · picks (18000,3500) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (12000,3500) · keys — · fields — · expect 1 selected` | green: select: (12000,3500) mm at px (1000.0,324.3) on the plan view; picked 'wall-08c51e8158be8b03'; selected 0 -> 1 [wall-08c51e8158be8b03] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-08c51e8158be8b03) (expected exactly 1) |
| `ribbon:Modify:Array · picks (12000,3500) (14000,3500) · keys Escape Escape · fields Options Strip: Number=4 · expect Walls +3` | green: pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands \| fields: Number=4 reads '4.00' \| picks: (12000,3500) mm at px (1000.0,324.3) on the plan view \| (14000,3500) mm at px (1058.7,324.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Array -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Walls +3": Walls 1 -> 4 (+3, expected +3) |
| `plan:select · picks (18000,3500) · keys — · fields — · expect 1 selected` | green: select: (18000,3500) mm at px (1176.0,324.3) on the plan view; picked 'wall-08c51e8158be8b03-cf56b99b5d381784'; selected 0 -> 1 [wall-08c51e8158be8b03-cf56b99b5d381784] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-08c51e8158be8b03-cf56b99b5d381784) (expected exactly 1) |

### The result

The model holds: Levels 3,Model Groups 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6007. Delete the store wall, then undo it, then redo it.

- Starts from: a new Architectural project
- Ends with: the store wall deleted again after an undo and a redo
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,4000) to=(18000,4000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,4000) to=(18000,4000) level=Ground` | green: op:add wall made=wall-ac2e290852e4771a changed= ms=43 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (15000,4000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Walls -1",
  "qa:Undo · picks — · keys — · fields — · expect Walls +1",
  "qa:Redo · picks — · keys — · fields — · expect Walls -1"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (15000,4000) · keys — · fields — · expect 1 selected` | green: select: (15000,4000) mm at px (1088.0,309.7) on the plan view; picked 'wall-ac2e290852e4771a'; selected 0 -> 1 [wall-ac2e290852e4771a] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-ac2e290852e4771a) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Walls -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Walls -1": Walls 1 -> 0 (-1, expected -1) |
| `qa:Undo · picks — · keys — · fields — · expect Walls +1` | green: QToolButton pressed; a command ran Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `qa:Redo · picks — · keys — · fields — · expect Walls -1` | green: QToolButton pressed; a command ran Check "Walls -1": Walls 1 -> 0 (-1, expected -1) |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6008. Delete the south and north walls together, then take it back.

- Starts from: a new Architectural project
- Ends with: all three walls back on Ground after the undo
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(18000,2000) level=Ground",
  "op:add wall from=(12000,5000) to=(18000,5000) level=Ground",
  "op:add wall from=(12000,8000) to=(18000,8000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(18000,2000) level=Ground` | green: op:add wall made=wall-444f557083a326e1 changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,5000) to=(18000,5000) level=Ground` | green: op:add wall made=wall-0723ef96b31a5311 changed= ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(18000,8000) level=Ground` | green: op:add wall made=wall-b4fe34b87db862fa changed= ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (15000,8000) · keys — · fields — · expect 2 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Walls -2",
  "qa:Undo · picks — · keys — · fields — · expect Walls +2"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected` | green: select: (15000,2000) mm at px (1088.0,368.3) on the plan view; picked 'wall-444f557083a326e1'; selected 0 -> 1 [wall-444f557083a326e1] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-444f557083a326e1) (expected exactly 1) |
| `plan:select add · picks (15000,8000) · keys — · fields — · expect 2 selected` | green: select add: (15000,8000) mm at px (1021.7,192.3) on the plan view; picked 'wall-b4fe34b87db862fa'; selected 1 -> 2 [wall-444f557083a326e1,wall-b4fe34b87db862fa] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (wall-444f557083a326e1, wall-b4fe34b87db862fa) (expected exactly 2) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Walls -2` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Walls -2": Walls 3 -> 1 (-2, expected -2) |
| `qa:Undo · picks — · keys — · fields — · expect Walls +2` | green: QToolButton pressed; a command ran Check "Walls +2": Walls 1 -> 3 (+2, expected +2) |

### The result

The model holds: Levels 3,Walls 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6009. Select the whole 6 x 4 m meeting room with a window and move it 3 m north.

- Starts from: a new Architectural project
- Ends with: four walls of a 6 x 4 m room on Ground, 3000 mm north of where they were drawn
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(18000,2000) level=Ground",
  "op:add wall from=(18000,2000) to=(18000,6000) level=Ground",
  "op:add wall from=(18000,6000) to=(12000,6000) level=Ground",
  "op:add wall from=(12000,6000) to=(12000,2000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(18000,2000) level=Ground` | green: op:add wall made=wall-0d5d6b6f561355c1 changed= ms=15 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(18000,2000) to=(18000,6000) level=Ground` | green: op:add wall made=wall-5e345744dfa75521 changed=wall-0d5d6b6f561355c1 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(18000,6000) to=(12000,6000) level=Ground` | green: op:add wall made=wall-0e9165775a5c8ae3 changed=wall-5e345744dfa75521 ms=5 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(12000,6000) to=(12000,2000) level=Ground` | green: op:add wall made=wall-7f716431589735e4 changed=wall-0d5d6b6f561355c1,wall-0e9165775a5c8ae3 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:marquee · picks (11000,7000) (19000,1000) · keys — · fields — · expect 4 selected",
  "ribbon:Modify:Move · picks (15000,2000) (15000,5000) · keys Escape Escape · fields — · expect moved",
  "plan:marquee · picks (11000,10000) (19000,4000) · keys — · fields — · expect 4 selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:marquee · picks (11000,7000) (19000,1000) · keys — · fields — · expect 4 selected` | green: marquee: window (left to right); drag px (902.9,221.7) -> (1137.6,397.7) on the plan view; selected 0 -> 4 [wall-0d5d6b6f561355c1,wall-0e9165775a5c8ae3,wall-5e345744dfa75521,wall-7f716431589735e4] \| picks: the plan band pressed these 2 pick(s) as its own process Check "4 selected": 4 selected (wall-0d5d6b6f561355c1, wall-0e9165775a5c8ae3, wall-5e345744dfa75521, ...) (expected exactly 4) |
| `ribbon:Modify:Move · picks (15000,2000) (15000,5000) · keys Escape Escape · fields — · expect moved` | green: pressed 'Move' on Modify's Modify panel (through its fold): the tool 'Move' stands \| picks: (15000,2000) mm at px (1020.2,368.3) on the plan view \| (15000,5000) mm at px (1020.2,280.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 4 element(s) moved: wall-0d5d6b6f561355c1  -> ; wall-0e9165775a5c8ae3  -> ; wall-5e345744dfa75521  -> |
| `plan:marquee · picks (11000,10000) (19000,4000) · keys — · fields — · expect 4 selected` | green: marquee: window (left to right); drag px (902.9,133.7) -> (1137.6,309.7) on the plan view; selected 0 -> 4 [wall-0d5d6b6f561355c1,wall-0e9165775a5c8ae3,wall-5e345744dfa75521,wall-7f716431589735e4] \| picks: the plan band pressed these 2 pick(s) as its own process Check "4 selected": 4 selected (wall-0d5d6b6f561355c1, wall-0e9165775a5c8ae3, wall-5e345744dfa75521, ...) (expected exactly 4) |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6010. Pick the three corridor walls one after another, then clear the selection.

- Starts from: a new Architectural project
- Ends with: three parallel walls on Ground and nothing selected
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(18000,2000) level=Ground",
  "op:add wall from=(12000,5000) to=(18000,5000) level=Ground",
  "op:add wall from=(12000,8000) to=(18000,8000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(18000,2000) level=Ground` | green: op:add wall made=wall-f695e07ba9094e42 changed= ms=20 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,5000) to=(18000,5000) level=Ground` | green: op:add wall made=wall-ade01de9c1d2e2ea changed= ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(18000,8000) level=Ground` | green: op:add wall made=wall-e2ad3a83d70267c8 changed= ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (15000,5000) · keys — · fields — · expect 2 selected",
  "plan:select add · picks (15000,8000) · keys — · fields — · expect 3 selected",
  "plan:deselect · picks — · keys — · fields — · expect nothing selected",
  "plan:select · picks (15000,5000) · keys — · fields — · expect 1 selected",
  "plan:deselect · picks — · keys — · fields — · expect nothing selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected` | green: select: (15000,2000) mm at px (1021.7,368.3) on the plan view; picked 'wall-f695e07ba9094e42'; selected 0 -> 1 [wall-f695e07ba9094e42] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-f695e07ba9094e42) (expected exactly 1) |
| `plan:select add · picks (15000,5000) · keys — · fields — · expect 2 selected` | green: select add: (15000,5000) mm at px (1021.7,280.3) on the plan view; picked 'wall-ade01de9c1d2e2ea'; selected 1 -> 2 [wall-f695e07ba9094e42,wall-ade01de9c1d2e2ea] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (wall-f695e07ba9094e42, wall-ade01de9c1d2e2ea) (expected exactly 2) |
| `plan:select add · picks (15000,8000) · keys — · fields — · expect 3 selected` | green: select add: (15000,8000) mm at px (1021.7,192.3) on the plan view; picked 'wall-e2ad3a83d70267c8'; selected 2 -> 3 [wall-f695e07ba9094e42,wall-ade01de9c1d2e2ea,wall-e2ad3a83d70267c8] \| picks: the plan band pressed these 1 pick(s) as its own process Check "3 selected": 3 selected (wall-f695e07ba9094e42, wall-ade01de9c1d2e2ea, wall-e2ad3a83d70267c8) (expected exactly 3) |
| `plan:deselect · picks — · keys — · fields — · expect nothing selected` | green: deselect: cleared as a press on nothing clears; selected 3 -> 0 [] Check "nothing selected": 0 selected |
| `plan:select · picks (15000,5000) · keys — · fields — · expect 1 selected` | green: select: (15000,5000) mm at px (1021.7,280.3) on the plan view; picked 'wall-ade01de9c1d2e2ea'; selected 0 -> 1 [wall-ade01de9c1d2e2ea] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-ade01de9c1d2e2ea) (expected exactly 1) |
| `plan:deselect · picks — · keys — · fields — · expect nothing selected` | green: deselect: cleared as a press on nothing clears; selected 1 -> 0 [] Check "nothing selected": 0 selected |

### The result

The model holds: Levels 3,Walls 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6011. Touch the south and middle walls with a crossing box and delete them, keeping the north wall.

- Starts from: a new Architectural project
- Ends with: only the north wall on Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(18000,2000) level=Ground",
  "op:add wall from=(12000,5000) to=(18000,5000) level=Ground",
  "op:add wall from=(12000,8000) to=(18000,8000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(18000,2000) level=Ground` | green: op:add wall made=wall-0b83f0d81c5d79cc changed= ms=14 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,5000) to=(18000,5000) level=Ground` | green: op:add wall made=wall-519e0a39b3c96851 changed= ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(18000,8000) level=Ground` | green: op:add wall made=wall-40b5dc1be645db2d changed= ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:marquee · picks (19000,6000) (16000,1000) · keys — · fields — · expect 2 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Walls -2",
  "plan:select · picks (15000,8000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:marquee · picks (19000,6000) (16000,1000) · keys — · fields — · expect 2 selected` | green: marquee: crossing (right to left); drag px (1139.0,251.0) -> (1051.0,397.7) on the plan view; selected 0 -> 2 [wall-0b83f0d81c5d79cc,wall-519e0a39b3c96851] \| picks: the plan band pressed these 2 pick(s) as its own process Check "2 selected": 2 selected (wall-0b83f0d81c5d79cc, wall-519e0a39b3c96851) (expected exactly 2) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Walls -2` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Walls -2": Walls 3 -> 1 (-2, expected -2) |
| `plan:select · picks (15000,8000) · keys — · fields — · expect 1 selected` | green: select: (15000,8000) mm at px (1021.7,192.3) on the plan view; picked 'wall-40b5dc1be645db2d'; selected 0 -> 1 [wall-40b5dc1be645db2d] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-40b5dc1be645db2d) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6012. Drag the 5 m service wall 3 m north with the pointer.

- Starts from: a new Architectural project
- Ends with: one 5 m wall on Ground, 3000 mm north of where it was drawn
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,3000) to=(17000,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,3000) to=(17000,3000) level=Ground` | green: op:add wall made=wall-ad7029a9ce550e03 changed= ms=11 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "plan:select · picks (14500,3000) · keys — · fields — · expect 1 selected",
  "plan:drag · picks (14500,3000) (14500,6000) · keys — · fields — · expect moved",
  "plan:select · picks (14500,6000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `plan:select · picks (14500,3000) · keys — · fields — · expect 1 selected` | green: select: (14500,3000) mm at px (1073.4,339.0) on the plan view; picked 'wall-ad7029a9ce550e03'; selected 0 -> 1 [wall-ad7029a9ce550e03] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-ad7029a9ce550e03) (expected exactly 1) |
| `plan:drag · picks (14500,3000) (14500,6000) · keys — · fields — · expect moved` | green: drag: drag px (1021.7,339.0) -> (1021.7,251.0) on the plan view; selected 1 -> 1 [wall-ad7029a9ce550e03] \| picks: the plan band pressed these 2 pick(s) as its own process Check "moved": 1 element(s) moved: wall-ad7029a9ce550e03  -> |
| `plan:select · picks (14500,6000) · keys — · fields — · expect 1 selected` | green: select: (14500,6000) mm at px (1021.7,251.0) on the plan view; picked 'wall-ad7029a9ce550e03'; selected 1 -> 1 [wall-ad7029a9ce550e03] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-ad7029a9ce550e03) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6013. Give the party wall the mark W-01 and a comment saying it is the wall to unit 2.

- Starts from: a new Architectural project
- Ends with: one 6 m wall on Ground with Mark W-01 and a comment
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,7000) to=(18000,7000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,7000) to=(18000,7000) level=Ground` | green: op:add wall made=wall-d96c81ece7d14c64 changed= ms=32 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (15000,7000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Mark=W-01; Comments=Party wall to unit 2 · expect 1 selected",
  "plan:deselect · picks — · keys — · fields — · expect nothing selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (15000,7000) · keys — · fields — · expect 1 selected` | green: select: (15000,7000) mm at px (1021.7,221.7) on the plan view; picked 'wall-d96c81ece7d14c64'; selected 0 -> 1 [wall-d96c81ece7d14c64] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-d96c81ece7d14c64) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Mark=W-01; Comments=Party wall to unit 2 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Mark=W-01 committed ok, reads 'W-01'; Attributes [Common] Comments=Party wall to unit 2 committed ok, reads 'Party wall to unit 2' Check "1 selected": 1 selected (wall-d96c81ece7d14c64) (expected exactly 1) |
| `plan:deselect · picks — · keys — · fields — · expect nothing selected` | green: deselect: cleared as a press on nothing clears; selected 1 -> 0 [] Check "nothing selected": 0 selected |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6014. Make the plant room wall 4.2 m high and start it 150 mm up on a plinth.

- Starts from: a new Architectural project
- Ends with: one 6 m wall on Ground, Unconnected Height 4200 and Base Offset 150
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,4000) to=(18000,4000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,4000) to=(18000,4000) level=Ground` | green: op:add wall made=wall-28d3d4ee52ef56b8 changed= ms=17 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (15000,4000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Unconnected Height=4200; Base Offset=150 · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Placement Line=Core Centerline; Room Bounding=no · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (15000,4000) · keys — · fields — · expect 1 selected` | green: select: (15000,4000) mm at px (1021.7,309.7) on the plan view; picked 'wall-28d3d4ee52ef56b8'; selected 0 -> 1 [wall-28d3d4ee52ef56b8] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-28d3d4ee52ef56b8) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Unconnected Height=4200; Base Offset=150 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Unconnected Height=4200 committed ok, reads '4200 mm'; Attributes [Common] Base Offset=150 committed ok, reads '150 mm' Check "1 selected": 1 selected (wall-28d3d4ee52ef56b8) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Placement Line=Core Centerline; Room Bounding=no · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Placement Line=Core Centerline committed ok, reads 'Core Centerline'; Attributes [Common] Room Bounding=no committed ok, reads 'False' Check "1 selected": 1 selected (wall-28d3d4ee52ef56b8) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6015. Put a door in the south wall, mark it D01 and slide it 2.5 m along the wall.

- Starts from: a new Architectural project
- Ends with: one 6 m wall on Ground with a door marked D01 standing 2500 mm further east
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(18000,2000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(18000,2000) level=Ground` | green: op:add wall made=wall-67a6ed5d5a58be47 changed= ms=14 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Architecture:Door · picks (13500,2000) · keys Escape Escape · fields — · expect Doors +1",
  "plan:select · picks (13500,2000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Mark=D01 · expect 1 selected",
  "ribbon:Modify:Move · picks (13500,2000) (16000,2000) · keys Escape Escape · fields — · expect moved",
  "plan:deselect · picks — · keys — · fields — · expect nothing selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Architecture:Door · picks (13500,2000) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (13500,2000) mm at px (977.7,368.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `plan:select · picks (13500,2000) · keys — · fields — · expect 1 selected` | green: select: (13500,2000) mm at px (977.7,368.3) on the plan view; picked 'door-8e04465334f53336'; selected 0 -> 1 [door-8e04465334f53336] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (door-8e04465334f53336) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Mark=D01 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Doors] Mark=D01 committed ok, reads 'D01' Check "1 selected": 1 selected (door-8e04465334f53336) (expected exactly 1) |
| `ribbon:Modify:Move · picks (13500,2000) (16000,2000) · keys Escape Escape · fields — · expect moved` | green: pressed 'Move' on Modify's Modify panel (through its fold): the tool 'Move' stands \| picks: (13500,2000) mm at px (977.7,368.3) on the plan view \| (16000,2000) mm at px (1051.0,368.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 2 element(s) moved: door-8e04465334f53336  -> ; opening-58363ba3568c7d5a  -> |
| `plan:deselect · picks — · keys — · fields — · expect nothing selected` | green: deselect: cleared as a press on nothing clears; selected 0 -> 0 [] Check "nothing selected": 0 selected |

### The result

The model holds: Doors 1,Levels 3,Openings 1,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6016. Put a window in the north wall and copy it 3 m along for the second bay.

- Starts from: a new Architectural project
- Ends with: one 8 m wall on Ground with two windows 3000 mm apart
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,6000) to=(20000,6000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,6000) to=(20000,6000) level=Ground` | green: op:add wall made=wall-493610cbffae80a6 changed= ms=24 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Structure:Opening:Window · picks (14000,6000) · keys Escape Escape · fields — · expect Windows +1",
  "plan:select · picks (14000,6000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Copy · picks (14000,6000) (17000,6000) · keys Escape Escape · fields — · expect Windows +1",
  "plan:select · picks (17000,6000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Structure:Opening:Window · picks (14000,6000) · keys Escape Escape · fields — · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands (the walk names Structure; the tile stands on Architecture) \| picks: (14000,6000) mm at px (963.0,251.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `plan:select · picks (14000,6000) · keys — · fields — · expect 1 selected` | green: select: (14000,6000) mm at px (963.0,251.0) on the plan view; picked 'window-1feca44f2112ac20'; selected 0 -> 1 [window-1feca44f2112ac20] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (window-1feca44f2112ac20) (expected exactly 1) |
| `ribbon:Modify:Copy · picks (14000,6000) (17000,6000) · keys Escape Escape · fields — · expect Windows +1` | green: pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands \| picks: (14000,6000) mm at px (963.0,251.0) on the plan view \| (17000,6000) mm at px (1051.0,251.0) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |
| `plan:select · picks (17000,6000) · keys — · fields — · expect 1 selected` | green: select: (17000,6000) mm at px (1051.0,251.0) on the plan view; picked 'window-1feca44f2112ac20-e16f3f07b26e240d'; selected 0 -> 1 [window-1feca44f2112ac20-e16f3f07b26e240d] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (window-1feca44f2112ac20-e16f3f07b26e240d) (expected exactly 1) |

### The result

The model holds: Levels 3,Openings 2,Walls 1,Windows 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6017. Drop the base of column C1 300 mm below the slab and lift its top 300 mm.

- Starts from: a new Structural project
- Ends with: one column at (14000,3000) with Mark C1, Base Offset -300 and Top Offset 300
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(14000,3000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(14000,3000) level="Level 1"` | green: op:add column made=column-db2de5a82d552c43 changed= ms=16 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (14000,3000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Mark=C1; Base Offset=-300; Top Offset=300 · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (14000,3000) · keys — · fields — · expect 1 selected` | green: select: (14000,3000) mm at px (908.5,371.2) on the plan view; picked 'column-db2de5a82d552c43'; selected 0 -> 1 [column-db2de5a82d552c43] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (column-db2de5a82d552c43) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Mark=C1; Base Offset=-300; Top Offset=300 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Mark=C1 committed ok, no undo step made, reads 'C1'; Attributes [Common] Base Offset=-300 committed ok, reads '-300 mm'; Attributes [Common] Top Offset=300 committed ok, reads '300 mm' Check "1 selected": 1 selected (column-db2de5a82d552c43) (expected exactly 1) |

### The result

The model holds: Levels 2,Structural Columns 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6018. Slope the 6 m edge beam so its far end is 600 mm lower than its near end.

- Starts from: a new Structural project
- Ends with: one 6 m beam on Level 1 with Start Level Offset 0, End Level Offset -600 and Mark B-12
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add beam from=(12000,3000) to=(18000,3000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add beam from=(12000,3000) to=(18000,3000) level="Level 1"` | green: op:add beam made=beam-3841f6e8894d88fc changed= ms=15 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Mark=B-12; Start Level Offset=0; End Level Offset=-600 · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (927.2,371.2) on the plan view; picked 'beam-3841f6e8894d88fc'; selected 0 -> 1 [beam-3841f6e8894d88fc] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (beam-3841f6e8894d88fc) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Mark=B-12; Start Level Offset=0; End Level Offset=-600 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Mark=B-12 committed ok, reads 'B-12'; Attributes [Common] Start Level Offset=0 committed ok, no undo step made, reads '0 mm'; Attributes [Common] End Level Offset=-600 committed ok, reads '-600 mm' Check "1 selected": 1 selected (beam-3841f6e8894d88fc) (expected exactly 1) |

### The result

The model holds: Levels 2,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6019. Repeat this column five times at 3 m centres along the grid line.

- Starts from: a new Structural project
- Ends with: five columns on Level 1 at 3000 mm centres from x = 12000 to x = 24000
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(12000,3000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(12000,3000) level="Level 1"` | green: op:add column made=column-17a3caaf87f31b81 changed= ms=433 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (12000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Array · picks (12000,3000) (15000,3000) · keys Escape Escape · fields Options Strip: Number=5 · expect Structural Columns +4",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (24000,3000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (12000,3000) · keys — · fields — · expect 1 selected` | green: select: (12000,3000) mm at px (871.3,371.2) on the plan view; picked 'column-17a3caaf87f31b81'; selected 0 -> 1 [column-17a3caaf87f31b81] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (column-17a3caaf87f31b81) (expected exactly 1) |
| `ribbon:Modify:Array · picks (12000,3000) (15000,3000) · keys Escape Escape · fields Options Strip: Number=5 · expect Structural Columns +4` | green: pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands \| fields: Number=5 reads '5.00' \| picks: (12000,3000) mm at px (871.3,371.2) on the plan view \| (15000,3000) mm at px (927.2,371.2) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Array -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +4": Structural Columns 1 -> 5 (+4, expected +4) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (24000,3000) · keys — · fields — · expect 1 selected` | green: select: (24000,3000) mm at px (1067.6,371.2) on the plan view; picked 'column-17a3caaf87f31b81-e05507a54de4b926'; selected 0 -> 1 [column-17a3caaf87f31b81-e05507a54de4b926] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (column-17a3caaf87f31b81-e05507a54de4b926) (expected exactly 1) |

### The result

The model holds: Levels 2,Model Groups 1,Structural Columns 5,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6020. Mirror the column and its beam across the centre line at y = 6000.

- Starts from: a new Structural project
- Ends with: a column and a 6 m beam on Level 1 and their mirror image 6000 mm north
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(12000,3000) level=\"Level 1\"",
  "op:add beam from=(12000,3000) to=(18000,3000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(12000,3000) level="Level 1"` | green: op:add column made=column-f29cac7b5688de83 changed= ms=52 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add beam from=(12000,3000) to=(18000,3000) level="Level 1"` | green: op:add beam made=beam-df1615f85dd8785f changed= ms=2 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:marquee · picks (11000,4500) (19500,1500) · keys — · fields — · expect 2 selected",
  "ribbon:Modify:Mirror › Draw Axis · picks (10000,6000) (20000,6000) · keys Escape Escape · fields — · expect Structural Columns +1; Structural Framing +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (12000,9000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:marquee · picks (11000,4500) (19500,1500) · keys — · fields — · expect 2 selected` | green: marquee: window (left to right); drag px (852.7,343.3) -> (1010.9,399.1) on the plan view; selected 0 -> 2 [beam-df1615f85dd8785f,column-f29cac7b5688de83] \| picks: the plan band pressed these 2 pick(s) as its own process Check "2 selected": 2 selected (beam-df1615f85dd8785f, column-f29cac7b5688de83) (expected exactly 2) |
| `ribbon:Modify:Mirror › Draw Axis · picks (10000,6000) (20000,6000) · keys Escape Escape · fields — · expect Structural Columns +1; Structural Framing +1` | green: pressed 'Mirror › Draw Axis' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Draw Axis'; the press stood 57 ms (the menu stood at 30 ms; its row ran 12 ms; it made 0 child widgets native)): the tool 'Mirror › Draw Axis' stands \| picks: (10000,6000) mm at px (834.1,315.3) on the plan view \| (20000,6000) mm at px (1020.2,315.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Structural Columns +1; Structural Framing +1": Structural Columns 1 -> 2 (+1, expected +1); [green] Structural Framing 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (12000,9000) · keys — · fields — · expect 1 selected` | green: select: (12000,9000) mm at px (871.3,259.5) on the plan view; picked 'column-f29cac7b5688de83-e2dac8571a37dad9'; selected 0 -> 1 [column-f29cac7b5688de83-e2dac8571a37dad9] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (column-f29cac7b5688de83-e2dac8571a37dad9) (expected exactly 1) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6021. Delete the corner column, bring it back with undo, then delete it again with redo.

- Starts from: a new Structural project
- Ends with: the corner column deleted after an undo and a redo
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(12000,3000) level=\"Level 1\"",
  "op:add column at=(18000,3000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(12000,3000) level="Level 1"` | green: op:add column made=column-2721c0ff66935f64 changed= ms=509 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(18000,3000) level="Level 1"` | green: op:add column made=column-214f1d0103fa2451 changed= ms=49 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (12000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Structural Columns -1",
  "qa:Undo · picks — · keys — · fields — · expect Structural Columns +1",
  "qa:Redo · picks — · keys — · fields — · expect Structural Columns -1"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (12000,3000) · keys — · fields — · expect 1 selected` | green: select: (12000,3000) mm at px (871.3,371.2) on the plan view; picked 'column-2721c0ff66935f64'; selected 0 -> 1 [column-2721c0ff66935f64] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (column-2721c0ff66935f64) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Structural Columns -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Structural Columns -1": Structural Columns 2 -> 1 (-1, expected -1) |
| `qa:Undo · picks — · keys — · fields — · expect Structural Columns +1` | green: QToolButton pressed; a command ran Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `qa:Redo · picks — · keys — · fields — · expect Structural Columns -1` | green: QToolButton pressed; a command ran Check "Structural Columns -1": Structural Columns 2 -> 1 (-1, expected -1) |

### The result

The model holds: Levels 2,Structural Columns 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6022. Raise Level 1 to 3600, lift the roof level to 7200 and call it Level 2, then add a Parapet level at 10800.

- Starts from: a new Architectural project
- Ends with: levels Ground at 0, Level 1 at 3600, Level 2 at 7200 and Parapet at 10800
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:set id=\"level-Level 1\" key=Elevation value=3600",
  "op:set id=level-Roof key=Elevation value=7200",
  "op:set id=level-Roof key=Name value=\"Level 2\"",
  "op:add level elevation=10800 name=Parapet"
]}
```

| Line | UNION answered |
|---|---|
| `op:set id="level-Level 1" key=Elevation value=3600` | green: op:set made= changed="level-Level 1" ms=15 Check "moved": 1 element(s) moved: level-Level 1  -> |
| `op:set id=level-Roof key=Elevation value=7200` | green: op:set made= changed=level-Roof ms=4 Check "moved": 1 element(s) moved: level-Roof  -> |
| `op:set id=level-Roof key=Name value="Level 2"` | green: op:set made= changed=level-Roof ms=5 Check "every count unchanged": the counts: no count changed |
| `op:add level elevation=10800 name=Parapet` | green: op:add level made=level-Parapet changed= ms=52 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6023. Add a mezzanine level at 1500, copy it up 3 m for the plant deck, then undo the copy.

- Starts from: a new Architectural project
- Ends with: the template levels and a Mezzanine level at 1500, the copied plant deck taken back
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=1500 name=Mezzanine",
  "op:copy id=level-Mezzanine by=(0,0,3000)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=1500 name=Mezzanine` | green: op:add level made=level-Mezzanine changed= ms=539 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:copy id=level-Mezzanine by=(0,0,3000)` | green: op:copy made="level-Level 2" changed= ms=8 note=Level 2 placed at 4500 mm; Floor Plan made Check "Levels +1": Levels 4 -> 5 (+1, expected +1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect Levels -1",
  "qa:Redo · picks — · keys — · fields — · expect Levels +1",
  "qa:Undo · picks — · keys — · fields — · expect Levels -1"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect Levels -1` | green: QToolButton pressed; a command ran Check "Levels -1": Levels 5 -> 4 (-1, expected -1) |
| `qa:Redo · picks — · keys — · fields — · expect Levels +1` | green: QToolButton pressed; a command ran Check "Levels +1": Levels 4 -> 5 (+1, expected +1) |
| `qa:Undo · picks — · keys — · fields — · expect Levels -1` | green: QToolButton pressed; a command ran Check "Levels -1": Levels 5 -> 4 (-1, expected -1) |

### The result

The model holds: Levels 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6024. Add the plant level at 9000, delete it, then undo and redo the delete.

- Starts from: a new Architectural project
- Ends with: the template levels without the plant level
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=9000 name=Plant",
  "op:delete id=level-Plant"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=9000 name=Plant` | green: op:add level made=level-Plant changed= ms=20 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:delete id=level-Plant` | green: op:delete made= changed=level-Plant ms=24 Check "Levels -1": Levels 4 -> 3 (-1, expected -1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect Levels +1",
  "qa:Redo · picks — · keys — · fields — · expect Levels -1"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect Levels +1` | green: QToolButton pressed; a command ran Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `qa:Redo · picks — · keys — · fields — · expect Levels -1` | green: QToolButton pressed; a command ran Check "Levels -1": Levels 4 -> 3 (-1, expected -1) |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6025. Set out a column grid: five lines running north to south at 6 m centres and three running east to west at 6 m centres.

- Starts from: a new Structural project
- Ends with: five vertical and three horizontal grid lines
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,14000) name=A",
  "op:array id=grid-A count=5 step=(6000,0,0)",
  "op:add grid from=(-2000,0) to=(26000,0) name=1",
  "op:array id=grid-1 count=3 step=(0,6000,0)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,14000) name=A` | green: op:add grid made=grid-A changed= ms=440 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:array id=grid-A count=5 step=(6000,0,0)` | green: op:array made=grid-A-b59d0a568eff6c8a,grid-A-6411884da632786d,grid-A-d1485b4430d7fb03,grid-A-2e078dcdbf570e12 changed= ms=6 Check "Grids +4": Grids 1 -> 5 (+4, expected +4) |
| `op:add grid from=(-2000,0) to=(26000,0) name=1` | green: op:add grid made=grid-1 changed= ms=4 Check "Grids +1": Grids 5 -> 6 (+1, expected +1) |
| `op:array id=grid-1 count=3 step=(0,6000,0)` | green: op:array made=grid-1-3de82ffbb6cbc7cd,grid-1-4557e0c800820545 changed= ms=4 Check "Grids +2": Grids 6 -> 8 (+2, expected +2) |

### The result

The model holds: Grids 8,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6026. Move grid A 500 mm east, copy it 8 m for the second line, rename the original to Z, then delete it and take the delete back.

- Starts from: a new Structural project
- Ends with: two grid lines, Z at x = 500 and its copy at x = 8500
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,14000) name=A",
  "op:move id=grid-A by=(500,0,0)",
  "op:copy id=grid-A by=(8000,0,0)",
  "op:set id=grid-A key=Name value=Z",
  "op:delete id=grid-A"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,14000) name=A` | green: op:add grid made=grid-A changed= ms=545 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:move id=grid-A by=(500,0,0)` | green: op:move made= changed=grid-A ms=58 Check "moved": 1 element(s) moved: grid-A  -> |
| `op:copy id=grid-A by=(8000,0,0)` | green: op:copy made=grid-A-ca404e1d07fe4b14 changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:set id=grid-A key=Name value=Z` | green: op:set made= changed=grid-A ms=7 Check "every count unchanged": the counts: no count changed |
| `op:delete id=grid-A` | green: op:delete made= changed=grid-A ms=1842 Check "Grids -1": Grids 2 -> 1 (-1, expected -1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect Grids +1"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect Grids +1` | green: QToolButton pressed; a command ran Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |

### The result

The model holds: Grids 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6027. Add a Level 3 at 9000, lift it to 9300 and rename it Roof Slab.

- Starts from: a new Structural project
- Ends with: the template levels plus Level 3 renamed Roof Slab at 9300
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=9000 name=\"Level 3\"",
  "op:set id=\"level-Level 3\" key=Elevation value=9300",
  "op:set id=\"level-Level 3\" key=Name value=\"Roof Slab\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=9000 name="Level 3"` | green: op:add level made="level-Level 3" changed= ms=830 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) |
| `op:set id="level-Level 3" key=Elevation value=9300` | green: op:set made= changed="level-Level 3" ms=9 Check "moved": 1 element(s) moved: level-Level 3  -> |
| `op:set id="level-Level 3" key=Name value="Roof Slab"` | green: op:set made= changed="level-Level 3" ms=3 Check "every count unchanged": the counts: no count changed |

### The result

The model holds: Levels 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6028. Copy the 6 m supply duct 3 m north for the second room and mark it SA-2.

- Starts from: a new Mechanical project
- Ends with: two 400 x 300 supply ducts on Level 1, the copy marked SA-2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(12000,3000) to=(18000,3000) level=\"Level 1\" width=400 height=300"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(12000,3000) to=(18000,3000) level="Level 1" width=400 height=300` | green: op:add duct made=duct-28f5365e0dea1307,system-551907840a7b621a changed= ms=5 Check "Ducts +1": Ducts 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Copy · picks (15000,3000) (15000,6000) · keys Escape Escape · fields — · expect Ducts +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,6000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Mark=SA-2 · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (927.2,371.2) on the plan view; picked 'duct-28f5365e0dea1307'; selected 0 -> 1 [duct-28f5365e0dea1307] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (duct-28f5365e0dea1307) (expected exactly 1) |
| `ribbon:Modify:Copy · picks (15000,3000) (15000,6000) · keys Escape Escape · fields — · expect Ducts +1` | green: pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands \| picks: (15000,3000) mm at px (927.2,371.2) on the plan view \| (15000,6000) mm at px (927.2,315.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Ducts +1": Ducts 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,6000) · keys — · fields — · expect 1 selected` | green: select: (15000,6000) mm at px (927.2,315.3) on the plan view; picked 'duct-28f5365e0dea1307-d2c02a0fab8d397a'; selected 0 -> 1 [duct-28f5365e0dea1307-d2c02a0fab8d397a] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (duct-28f5365e0dea1307-d2c02a0fab8d397a) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Mark=SA-2 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Mark=SA-2 committed ok, reads 'SA-2' Check "1 selected": 1 selected (duct-28f5365e0dea1307-d2c02a0fab8d397a) (expected exactly 1) |

### The result

The model holds: Duct Systems 1,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6029. Turn the 5 m return duct a quarter turn about its centre, then delete the 2 m stub.

- Starts from: a new Mechanical project
- Ends with: one 5 m return duct on Level 1 running north to south
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(12000,3000) to=(17000,3000) level=\"Level 1\" width=500 height=300",
  "op:add duct from=(12000,8000) to=(14000,8000) level=\"Level 1\" width=300 height=200"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(12000,3000) to=(17000,3000) level="Level 1" width=500 height=300` | green: op:add duct made=duct-244e236c26437a7b,system-c05b25430422ecea changed= ms=671 Check "Ducts +1": Ducts 0 -> 1 (+1, expected +1) |
| `op:add duct from=(12000,8000) to=(14000,8000) level="Level 1" width=300 height=200` | green: op:add duct made=duct-ea2086afa091154a,system-e2075c2ae43a6a06 changed= ms=3 Check "Ducts +1": Ducts 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (14500,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Rotate · picks (14500,3000) (17000,3000) (14500,5500) · keys Escape Escape · fields — · expect moved",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (13000,8000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Ducts -1"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (14500,3000) · keys — · fields — · expect 1 selected` | green: select: (14500,3000) mm at px (917.9,371.2) on the plan view; picked 'duct-244e236c26437a7b'; selected 0 -> 1 [duct-244e236c26437a7b] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (duct-244e236c26437a7b) (expected exactly 1) |
| `ribbon:Modify:Rotate · picks (14500,3000) (17000,3000) (14500,5500) · keys Escape Escape · fields — · expect moved` | green: pressed 'Rotate' on Modify's Modify panel (through its fold): the tool 'Rotate' stands \| picks: (14500,3000) mm at px (917.9,371.2) on the plan view \| (17000,3000) mm at px (964.4,371.2) on the plan view \| (14500,5500) mm at px (917.9,324.6) on the plan view \| presses to the tool 3 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: duct-244e236c26437a7b (12000, 3000) -> (14500, 500) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (13000,8000) · keys — · fields — · expect 1 selected` | green: select: (13000,8000) mm at px (889.9,278.1) on the plan view; picked 'duct-ea2086afa091154a'; selected 0 -> 1 [duct-ea2086afa091154a] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (duct-ea2086afa091154a) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Ducts -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Ducts -1": Ducts 2 -> 1 (-1, expected -1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6030. Repeat the 6 m cold water branch four times at 2.5 m centres for the four bathrooms.

- Starts from: a new Hydraulic project
- Ends with: four 100 mm pipes on Level 1 at 2500 mm centres
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(12000,2000) to=(18000,2000) level=\"Level 1\" diameter=100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(12000,2000) to=(18000,2000) level="Level 1" diameter=100` | green: op:add pipe made=pipe-0ec47cf8ec22aa81,system-1dc0d6242bb386f0 changed= ms=13 Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Array · picks (15000,2000) (15000,4500) · keys Escape Escape · fields Options Strip: Number=4 · expect Pipes +3",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,9500) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected` | green: select: (15000,2000) mm at px (927.2,389.8) on the plan view; picked 'pipe-0ec47cf8ec22aa81'; selected 0 -> 1 [pipe-0ec47cf8ec22aa81] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-0ec47cf8ec22aa81) (expected exactly 1) |
| `ribbon:Modify:Array · picks (15000,2000) (15000,4500) · keys Escape Escape · fields Options Strip: Number=4 · expect Pipes +3` | green: pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands \| fields: Number=4 reads '4.00' \| picks: (15000,2000) mm at px (927.2,389.8) on the plan view \| (15000,4500) mm at px (927.2,343.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Array -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Pipes +3": Pipes 1 -> 4 (+3, expected +3) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,9500) · keys — · fields — · expect 1 selected` | green: select: (15000,9500) mm at px (927.2,250.2) on the plan view; picked 'pipe-0ec47cf8ec22aa81-e89de491773c8269'; selected 0 -> 1 [pipe-0ec47cf8ec22aa81-e89de491773c8269] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-0ec47cf8ec22aa81-e89de491773c8269) (expected exactly 1) |

### The result

The model holds: Levels 2,Model Groups 1,Pipes 4,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6031. Mirror the 100 mm sprinkler branch to the other side of the 8 m main.

- Starts from: a new Fire Protection project
- Ends with: an 8 m 100 mm main, a 5 m 50 mm branch north of it and a mirrored branch south of it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(12000,3000) to=(20000,3000) level=\"Level 1\" diameter=100",
  "op:add pipe from=(16000,3000) to=(16000,8000) level=\"Level 1\" diameter=50"
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(12000,3000) to=(20000,3000) level="Level 1" diameter=100` | green: op:add pipe made=pipe-6ea0280cfa0168be,system-ba5da344e2a1187a changed= ms=5 Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |
| `op:add pipe from=(16000,3000) to=(16000,8000) level="Level 1" diameter=50` | green: op:add pipe made=pipe-f681c9b1f402c7bc,fitting-c9166715e374deee,pipe-6c3def6f6730eb1f changed=system-ba5da344e2a1187a,pipe-6ea0280cfa0168be ms=4 Check "Pipes +2; Pipe Fittings +1": Pipes 1 -> 3 (+2, expected +2); [green] Pipe Fittings 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (16000,6500) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Mirror › Pick Axis · picks (19000,3000) · keys Escape Escape · fields — · expect Pipes +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (16000,500) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (16000,6500) · keys — · fields — · expect 1 selected` | green: select: (16000,6500) mm at px (945.8,306.0) on the plan view; picked 'pipe-f681c9b1f402c7bc'; selected 0 -> 1 [pipe-f681c9b1f402c7bc] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-f681c9b1f402c7bc) (expected exactly 1) |
| `ribbon:Modify:Mirror › Pick Axis · picks (19000,3000) · keys Escape Escape · fields — · expect Pipes +1` | green: pressed 'Mirror › Pick Axis' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Pick Axis'; the press stood 368 ms (the menu stood at 26 ms; its row ran 341 ms; it made 0 child widgets native)): the tool 'Mirror › Pick Axis' stands \| picks: (19000,3000) mm at px (1001.6,371.2) on the plan view \| presses to the tool 1 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Pipes +1": Pipes 3 -> 4 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (16000,500) · keys — · fields — · expect 1 selected` | green: select: (16000,500) mm at px (945.8,417.7) on the plan view; picked 'pipe-f681c9b1f402c7bc-75c7f0a7a7931adf'; selected 0 -> 1 [pipe-f681c9b1f402c7bc-75c7f0a7a7931adf] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-f681c9b1f402c7bc-75c7f0a7a7931adf) (expected exactly 1) |

### The result

The model holds: Levels 2,Pipe Fittings 1,Pipes 4,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6032. Offset the 6 m main 1.2 m north to run the parallel return.

- Starts from: a new Fire Protection project
- Ends with: two parallel 6 m 80 mm pipes on Level 1, 1200 mm apart
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(12000,3000) to=(18000,3000) level=\"Level 1\" diameter=80"
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(12000,3000) to=(18000,3000) level="Level 1" diameter=80` | green: op:add pipe made=pipe-a6696ca972502ba4,system-426ff9a39d8ac5ff changed= ms=8 Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Offset · picks (15000,3000) (15000,4200) · keys Escape Escape · fields Options Strip: Offset value=1200; Copy=yes · expect Pipes +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,4200) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (927.2,371.2) on the plan view; picked 'pipe-a6696ca972502ba4'; selected 0 -> 1 [pipe-a6696ca972502ba4] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-a6696ca972502ba4) (expected exactly 1) |
| `ribbon:Modify:Offset · picks (15000,3000) (15000,4200) · keys Escape Escape · fields Options Strip: Offset value=1200; Copy=yes · expect Pipes +1` | green: pressed 'Offset' on Modify's Modify panel (through its fold): the tool 'Offset' stands \| fields: Offset value=1200 reads '1200 mm'; Copy=yes reads yes \| picks: (15000,3000) mm at px (927.2,371.2) on the plan view \| (15000,4200) mm at px (927.2,348.8) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Offset -> tool Offset, 'Offset' still stands (the key went to union_shell::Viewport)); Escape (tool Offset -> no tool) Check "Pipes +1": Pipes 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,4200) · keys — · fields — · expect 1 selected` | green: select: (15000,4200) mm at px (927.2,348.8) on the plan view; picked 'pipe-a6696ca972502ba4-e235c490c94ff16e'; selected 1 -> 1 [pipe-a6696ca972502ba4-e235c490c94ff16e] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-a6696ca972502ba4-e235c490c94ff16e) (expected exactly 1) |

### The result

The model holds: Levels 2,Pipes 2,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6033. Repeat the distribution board four times at 2.5 m centres along the plant wall.

- Starts from: a new Electrical project
- Ends with: four pieces of equipment on Level 1 at 2500 mm centres from x = 12000
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add equipment at=(12000,5000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add equipment at=(12000,5000) level="Level 1"` | green: op:add equipment made=equipment-9e5d84f851e316a5 changed= ms=6 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (12000,5000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Array · picks (12000,5000) (14500,5000) · keys Escape Escape · fields Options Strip: Number=4 · expect Mechanical Equipment +3",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (19500,5000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (12000,5000) · keys — · fields — · expect 1 selected` | green: select: (12000,5000) mm at px (871.3,333.9) on the plan view; picked 'equipment-9e5d84f851e316a5'; selected 0 -> 1 [equipment-9e5d84f851e316a5] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (equipment-9e5d84f851e316a5) (expected exactly 1) |
| `ribbon:Modify:Array · picks (12000,5000) (14500,5000) · keys Escape Escape · fields Options Strip: Number=4 · expect Mechanical Equipment +3` | green: pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands \| fields: Number=4 reads '4.00' \| picks: (12000,5000) mm at px (871.3,333.9) on the plan view \| (14500,5000) mm at px (917.9,333.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Array -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Mechanical Equipment +3": Mechanical Equipment 1 -> 4 (+3, expected +3) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (19500,5000) · keys — · fields — · expect 1 selected` | green: select: (19500,5000) mm at px (1010.9,333.9) on the plan view; picked 'equipment-9e5d84f851e316a5-f1de7c1ee7e390a8'; selected 0 -> 1 [equipment-9e5d84f851e316a5-f1de7c1ee7e390a8] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (equipment-9e5d84f851e316a5-f1de7c1ee7e390a8) (expected exactly 1) |

### The result

The model holds: Levels 2,Mechanical Equipment 4,Model Groups 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6034. Copy distribution board DB-1 3 m east and mark the copy DB-2.

- Starts from: a new Electrical project
- Ends with: two boards on Level 1 marked DB-1 and DB-2, 3000 mm apart
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add equipment at=(14000,5000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add equipment at=(14000,5000) level="Level 1"` | green: op:add equipment made=equipment-4da506743ee0c9dd changed= ms=6 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (14000,5000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Mark=DB-1 · expect 1 selected",
  "ribbon:Modify:Copy · picks (14000,5000) (17000,5000) · keys Escape Escape · fields — · expect Mechanical Equipment +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (17000,5000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Mark=DB-2 · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (14000,5000) · keys — · fields — · expect 1 selected` | green: select: (14000,5000) mm at px (908.5,333.9) on the plan view; picked 'equipment-4da506743ee0c9dd'; selected 0 -> 1 [equipment-4da506743ee0c9dd] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (equipment-4da506743ee0c9dd) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Mark=DB-1 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Mark=DB-1 committed ok, reads 'DB-1' Check "1 selected": 1 selected (equipment-4da506743ee0c9dd) (expected exactly 1) |
| `ribbon:Modify:Copy · picks (14000,5000) (17000,5000) · keys Escape Escape · fields — · expect Mechanical Equipment +1` | green: pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands \| picks: (14000,5000) mm at px (908.5,333.9) on the plan view \| (17000,5000) mm at px (964.4,333.9) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Mechanical Equipment +1": Mechanical Equipment 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (17000,5000) · keys — · fields — · expect 1 selected` | green: select: (17000,5000) mm at px (964.4,333.9) on the plan view; picked 'equipment-4da506743ee0c9dd-e5b94c5178f7b38b'; selected 0 -> 1 [equipment-4da506743ee0c9dd-e5b94c5178f7b38b] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (equipment-4da506743ee0c9dd-e5b94c5178f7b38b) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Mark=DB-2 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Mark=DB-2 committed ok, reads 'DB-2' Check "1 selected": 1 selected (equipment-4da506743ee0c9dd-e5b94c5178f7b38b) (expected exactly 1) |

### The result

The model holds: Levels 2,Mechanical Equipment 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6035. The east wall sits 300 mm out of line with the west wall: align it to the west wall's line.

- Starts from: a new Architectural project
- Ends with: two walls on Ground now standing on the same line at y = 5000
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,5000) to=(15500,5000) level=Ground",
  "op:add wall from=(16000,5300) to=(20000,5300) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,5000) to=(15500,5000) level=Ground` | green: op:add wall made=wall-2e3cef0df808a5d4 changed= ms=469 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(16000,5300) to=(20000,5300) level=Ground` | green: op:add wall made=wall-52f0b887159be0d1 changed= ms=15 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Modify:Align · picks (13500,5000) (18000,5300) · keys Escape Escape · fields — · expect moved",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (18000,5000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Modify:Align · picks (13500,5000) (18000,5300) · keys Escape Escape · fields — · expect moved` | green: pressed 'Align' on Modify's Modify panel (through its fold): the tool 'Align' stands \| picks: (13500,5000) mm at px (948.4,280.3) on the plan view \| (18000,5300) mm at px (1080.4,271.5) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Align -> tool Align, 'Align' still stands (the key went to union_shell::Viewport)); Escape (tool Align -> no tool) Check "moved": 1 element(s) moved: wall-52f0b887159be0d1  -> |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (18000,5000) · keys — · fields — · expect 1 selected` | green: select: (18000,5000) mm at px (1080.4,280.3) on the plan view; picked 'wall-52f0b887159be0d1'; selected 0 -> 1 [wall-52f0b887159be0d1] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-52f0b887159be0d1) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6036. Trim the south wall and the east wall to meet in a clean corner.

- Starts from: a new Architectural project
- Ends with: two walls on Ground meeting at a corner at (20000,2000)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(17000,2000) level=Ground",
  "op:add wall from=(20000,3000) to=(20000,8000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(17000,2000) level=Ground` | green: op:add wall made=wall-da030496a987719b changed= ms=355 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(20000,3000) to=(20000,8000) level=Ground` | green: op:add wall made=wall-12e11bf6334a1a3a changed= ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Modify:Trim/Extend › Trim/Extend to Corner · picks (14000,2000) (20000,6000) · keys Escape Escape · fields — · expect moved",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (18500,2000) · keys — · fields — · expect 1 selected",
  "plan:select · picks (20000,2500) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Modify:Trim/Extend › Trim/Extend to Corner · picks (14000,2000) (20000,6000) · keys Escape Escape · fields — · expect moved` | green: pressed 'Trim/Extend › Trim/Extend to Corner' on Modify's Edit panel (through its fold) (through its parent 'Trim/Extend''s arrow, the row 'Trim/Extend to Corner'; the press stood 747 ms (the menu stood at 64 ms; its row ran 680 ms; it made 0 child widgets native)): the tool 'Trim/Extend › Trim/Extend to Corner' stands \| picks: (14000,2000) mm at px (961.6,368.3) on the plan view \| (20000,6000) mm at px (1137.6,251.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Trim/Extend › Trim/Extend to Corner -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "moved": 2 element(s) moved: wall-12e11bf6334a1a3a  -> ; wall-da030496a987719b  -> |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (18500,2000) · keys — · fields — · expect 1 selected` | green: select: (18500,2000) mm at px (1093.6,368.3) on the plan view; picked 'wall-da030496a987719b'; selected 0 -> 1 [wall-da030496a987719b] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-da030496a987719b) (expected exactly 1) |
| `plan:select · picks (20000,2500) · keys — · fields — · expect 1 selected` | green: select: (20000,2500) mm at px (1137.6,353.7) on the plan view; picked 'wall-12e11bf6334a1a3a'; selected 1 -> 1 [wall-12e11bf6334a1a3a] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-12e11bf6334a1a3a) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6037. Extend the 5 m partition east until it meets the boundary wall.

- Starts from: a new Architectural project
- Ends with: a boundary wall at x = 20000 and a partition on Ground reaching it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(20000,2000) to=(20000,8000) level=Ground",
  "op:add wall from=(12000,5000) to=(17000,5000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(20000,2000) to=(20000,8000) level=Ground` | green: op:add wall made=wall-a104f01cd621b89d changed= ms=643 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,5000) to=(17000,5000) level=Ground` | green: op:add wall made=wall-70e9fb64c304e824 changed= ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Modify:Trim/Extend › Trim/Extend Single Element · picks (20000,3000) (14000,5000) · keys Escape Escape · fields — · expect moved",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (18500,5000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Modify:Trim/Extend › Trim/Extend Single Element · picks (20000,3000) (14000,5000) · keys Escape Escape · fields — · expect moved` | green: pressed 'Trim/Extend › Trim/Extend Single Element' on Modify's Edit panel (through its fold) (through its parent 'Trim/Extend''s arrow, the row 'Trim/Extend Single Element'; the press stood 449 ms (the menu stood at 85 ms; its row ran 331 ms; it made 0 child widgets native)): the tool 'Trim/Extend › Trim/Extend Single Element' stands \| picks: (20000,3000) mm at px (1137.6,339.0) on the plan view \| (14000,5000) mm at px (961.6,280.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Trim/Extend › Trim/Extend Single Element -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: wall-70e9fb64c304e824  -> |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (18500,5000) · keys — · fields — · expect 1 selected` | green: select: (18500,5000) mm at px (1093.6,280.3) on the plan view; picked 'wall-70e9fb64c304e824'; selected 0 -> 1 [wall-70e9fb64c304e824] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-70e9fb64c304e824) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6038. Split the 8 m wall at its middle and delete the east half.

- Starts from: a new Architectural project
- Ends with: one 4 m wall on Ground, from (12000,4000) to (16000,4000)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,4000) to=(20000,4000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,4000) to=(20000,4000) level=Ground` | green: op:add wall made=wall-176d8fe68125bf68 changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Modify:Split · picks (16000,4000) · keys Escape Escape · fields — · expect Walls +1",
  "plan:select · picks (18000,4000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Walls -1"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Modify:Split · picks (16000,4000) · keys Escape Escape · fields — · expect Walls +1` | green: pressed 'Split' on Modify's Edit panel (through its fold): the command 'Split' ran; status 'Click an element to break it there' \| picks: (16000,4000) mm at px (1021.7,309.7) on the plan view \| presses to the tool 1 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `plan:select · picks (18000,4000) · keys — · fields — · expect 1 selected` | green: select: (18000,4000) mm at px (1080.4,309.7) on the plan view; picked 'wall-176d8fe68125bf68-2bb494b8c584227e'; selected 0 -> 1 [wall-176d8fe68125bf68-2bb494b8c584227e] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-176d8fe68125bf68-2bb494b8c584227e) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Walls -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Walls -1": Walls 2 -> 1 (-1, expected -1) |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6039. Break the 8 m wall in two with a gap at the movement joint.

- Starts from: a new Architectural project
- Ends with: two walls on Ground with a gap between them at x = 16000
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,6000) to=(20000,6000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,6000) to=(20000,6000) level=Ground` | green: op:add wall made=wall-451c66882b36b927 changed= ms=16 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Modify:Split › Split with Gap · picks (16000,6000) · keys Escape Escape · fields — · expect Walls +1",
  "plan:select · picks (14000,6000) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (18000,6000) · keys — · fields — · expect 2 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Modify:Split › Split with Gap · picks (16000,6000) · keys Escape Escape · fields — · expect Walls +1` | green: pressed 'Split › Split with Gap' on Modify's Edit panel (through its fold) (through its parent 'Split''s arrow, the row 'Split with Gap'; the press stood 73 ms (the menu stood at 36 ms; its row ran 13 ms; it made 0 child widgets native)): the command 'Split › Split with Gap' ran; status 'Click an element to break it with a gap' \| picks: (16000,6000) mm at px (1021.7,251.0) on the plan view \| presses to the tool 1 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `plan:select · picks (14000,6000) · keys — · fields — · expect 1 selected` | green: select: (14000,6000) mm at px (963.0,251.0) on the plan view; picked 'wall-451c66882b36b927'; selected 0 -> 1 [wall-451c66882b36b927] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-451c66882b36b927) (expected exactly 1) |
| `plan:select add · picks (18000,6000) · keys — · fields — · expect 2 selected` | green: select add: (18000,6000) mm at px (1080.4,251.0) on the plan view; picked 'wall-451c66882b36b927-a97c3e650ac27354'; selected 1 -> 2 [wall-451c66882b36b927,wall-451c66882b36b927-a97c3e650ac27354] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (wall-451c66882b36b927, wall-451c66882b36b927-a97c3e650ac27354) (expected exactly 2) |

### The result

The model holds: Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6040. Offset the 8 m facade wall 1.5 m inward to start the inner leaf.

- Starts from: a new Architectural project
- Ends with: two parallel 8 m walls on Ground, 1500 mm apart
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(20000,2000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(20000,2000) level=Ground` | green: op:add wall made=wall-35c90b86b78aa990 changed= ms=11 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (16000,2000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Offset · picks (16000,2000) (16000,3500) · keys Escape Escape · fields Options Strip: Offset value=1500; Copy=yes · expect Walls +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (16000,3500) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (16000,2000) · keys — · fields — · expect 1 selected` | green: select: (16000,2000) mm at px (1021.7,368.3) on the plan view; picked 'wall-35c90b86b78aa990'; selected 0 -> 1 [wall-35c90b86b78aa990] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-35c90b86b78aa990) (expected exactly 1) |
| `ribbon:Modify:Offset · picks (16000,2000) (16000,3500) · keys Escape Escape · fields Options Strip: Offset value=1500; Copy=yes · expect Walls +1` | green: pressed 'Offset' on Modify's Modify panel (through its fold): the tool 'Offset' stands \| fields: Offset value=1500 reads '1500 mm'; Copy=yes reads yes \| picks: (16000,2000) mm at px (1021.7,368.3) on the plan view \| (16000,3500) mm at px (1021.7,324.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Offset -> tool Offset, 'Offset' still stands (the key went to union_shell::Viewport)); Escape (tool Offset -> no tool) Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (16000,3500) · keys — · fields — · expect 1 selected` | green: select: (16000,3500) mm at px (1021.7,324.3) on the plan view; picked 'wall-35c90b86b78aa990-791310995d92e100'; selected 1 -> 1 [wall-35c90b86b78aa990-791310995d92e100] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-35c90b86b78aa990-791310995d92e100) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6041. Pin the surveyed boundary wall so nobody moves it, then unpin it and move it 500 mm.

- Starts from: a new Architectural project
- Ends with: one 6 m boundary wall on Ground, moved 500 mm north after its pin was released
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,3000) to=(18000,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,3000) to=(18000,3000) level=Ground` | green: op:add wall made=wall-38612be5176ef8e2 changed= ms=13 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Pin · picks — · keys — · fields — · expect status: Pinned 1 element",
  "ribbon:Modify:Move · picks (15000,3000) (15000,3500) · keys Escape Escape · fields — · expect refuses: element pinned",
  "ribbon:Modify:Unpin · picks (15000,3000) · keys Escape Escape · fields — · expect status: Unpinned 1 element",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Move · picks (15000,3000) (15000,3500) · keys Escape Escape · fields — · expect moved"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (1021.7,339.0) on the plan view; picked 'wall-38612be5176ef8e2'; selected 0 -> 1 [wall-38612be5176ef8e2] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-38612be5176ef8e2) (expected exactly 1) |
| `ribbon:Modify:Pin · picks — · keys — · fields — · expect status: Pinned 1 element` | green: pressed 'Pin' on Modify's Edit panel (through its fold): the command 'Pin' ran; status 'Pinned 1 element' Check "status: Pinned 1 element": status 'Pinned 1 element' read; now 'Pinned 1 element', since the step began 'Click to select, Tab for alternates, Ctrl adds, Shift removes / Pinned 1 element' |
| `ribbon:Modify:Move · picks (15000,3000) (15000,3500) · keys Escape Escape · fields — · expect refuses: element pinned` | green: pressed 'Move' on Modify's Modify panel (through its fold): the tool 'Move' stands \| picks: (15000,3000) mm at px (1021.7,339.0) on the plan view \| (15000,3500) mm at px (1021.7,324.3) on the plan view \| presses to the tool 2, selection unchanged \| a refusal was spoken: cannot proceed: element pinned \| keys: Escape (tool Move -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "refuses: element pinned": refusal 'element pinned' read; the status bar read ' / Click a base point / Click a destination point / Click a base point / cannot proceed: element pinned', message boxes '', dialog error lines '', stage words '(15000,3000) mm at px (1021.7,339.0) on the plan view \| (15000,3500) mm at px (1021.7,324.3) on the plan view \| presses to the tool 2, selection unchanged \| a refusal was spoken: cannot proceed: element pinned \| Escape (tool Move -> no tool); Escape (no tool -> no tool, nothing standing to end)', band words '', refusal record '' |
| `ribbon:Modify:Unpin · picks (15000,3000) · keys Escape Escape · fields — · expect status: Unpinned 1 element` | green: pressed 'Unpin' on Modify's Edit panel (through its fold): the tool 'Unpin' stands \| picks: (15000,3000) mm at px (1021.7,339.0) on the plan view \| presses to the tool 1 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "status: Unpinned 1 element": status 'Unpinned 1 element' read; now 'Unpinned 1 element', since the step began 'Click the element to unpin / Unpinned 1 element' |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (1021.7,339.0) on the plan view; picked 'wall-38612be5176ef8e2'; selected 0 -> 1 [wall-38612be5176ef8e2] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-38612be5176ef8e2) (expected exactly 1) |
| `ribbon:Modify:Move · picks (15000,3000) (15000,3500) · keys Escape Escape · fields — · expect moved` | green: pressed 'Move' on Modify's Modify panel (through its fold): the tool 'Move' stands \| picks: (15000,3000) mm at px (1021.7,339.0) on the plan view \| (15000,3500) mm at px (1021.7,324.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: wall-38612be5176ef8e2  -> |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6042. Draw a spline model line through four points for the garden path edge, then copy it 3 m north for the other edge.

- Starts from: a new Architectural project
- Ends with: two spline model lines on Ground 3000 mm apart
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Setout:Model Line · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) · keys Return Escape Escape · fields Options Strip: Draw=Spline · expect Lines +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Copy · picks (14000,3500) (14000,6500) · keys Escape Escape · fields — · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Setout:Model Line · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) · keys Return Escape Escape · fields Options Strip: Draw=Spline · expect Lines +1` | green: pressed 'Model Line' on Setout's Reference panel: the tool 'Model Line' stands \| fields: Draw=Spline set \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (14000,3500) mm at px (1058.7,324.3) on the plan view \| (16000,1500) mm at px (1117.4,383.0) on the plan view \| (18000,3000) mm at px (1176.0,339.0) on the plan view \| presses to the tool 4, selection unchanged \| keys: Return (tool Model Line -> tool Model Line); Escape (tool Model Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected` | green: select: (14000,3500) mm at px (992.4,324.3) on the plan view; picked 'modelline-dc7e578b352d7fb6'; selected 0 -> 1 [modelline-dc7e578b352d7fb6] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (modelline-dc7e578b352d7fb6) (expected exactly 1) |
| `ribbon:Modify:Copy · picks (14000,3500) (14000,6500) · keys Escape Escape · fields — · expect Lines +1` | green: pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands \| picks: (14000,3500) mm at px (992.4,324.3) on the plan view \| (14000,6500) mm at px (992.4,236.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Lines 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6043. Draw the 6 x 4 m pavilion footprint as a rectangle of model lines.

- Starts from: a new Architectural project
- Ends with: four model lines on Ground forming a 6 x 4 m rectangle
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Setout:Model Line · picks (12000,2000) (18000,6000) · keys Escape Escape · fields Options Strip: Draw=Rectangle · expect Lines +4"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Setout:Model Line · picks (12000,2000) (18000,6000) · keys Escape Escape · fields Options Strip: Draw=Rectangle · expect Lines +4` | green: pressed 'Model Line' on Setout's Reference panel: the tool 'Model Line' stands \| fields: Draw=Rectangle set \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (18000,6000) mm at px (1176.0,251.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Model Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |

### The result

The model holds: Levels 3,Lines 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6044. Draw the fountain as a model line circle of 2.5 m radius.

- Starts from: a new Architectural project
- Ends with: one circular model line on Ground centred at (15000,5000)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Setout:Model Line · picks (15000,5000) (17500,5000) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Setout:Model Line · picks (15000,5000) (17500,5000) · keys Escape Escape · fields Options Strip: Draw=Circle · expect Lines +1` | green: pressed 'Model Line' on Setout's Reference panel: the tool 'Model Line' stands \| fields: Draw=Circle set \| picks: (15000,5000) mm at px (1088.0,280.3) on the plan view \| (17500,5000) mm at px (1161.4,280.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Model Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Lines 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6045. Draw the L-shaped setting-out line as three connected model lines.

- Starts from: a new Architectural project
- Ends with: three connected model lines on Ground from (12000,2000) through (15000,2000) and (15000,5000) to (12000,5000)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Setout:Model Line · picks (12000,2000) (15000,2000) (15000,5000) (12000,5000) · keys Escape Escape · fields Options Strip: Draw=Line · expect Lines +3"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Setout:Model Line · picks (12000,2000) (15000,2000) (15000,5000) (12000,5000) · keys Escape Escape · fields Options Strip: Draw=Line · expect Lines +3` | green: pressed 'Model Line' on Setout's Reference panel: the tool 'Model Line' stands \| fields: Draw=Line set \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (15000,2000) mm at px (1088.0,368.3) on the plan view \| (15000,5000) mm at px (1088.0,280.3) on the plan view \| (12000,5000) mm at px (1000.0,280.3) on the plan view \| presses to the tool 4, selection unchanged \| keys: Escape (tool Model Line -> tool Model Line, 'Model Line' still stands (the key went to union_shell::Viewport)); Escape (tool Model Line -> no tool) Check "Lines +3": Lines 0 -> 3 (+3, expected +3) |

### The result

The model holds: Levels 3,Lines 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6046. Draw the curved bench back as a model line arc, 6 m chord with a 2.5 m rise.

- Starts from: a new Architectural project
- Ends with: one arc model line on Ground from (12000,2000) to (18000,2000) passing through (15000,4500)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Setout:Model Line · picks (12000,2000) (18000,2000) (15000,4500) · keys Escape Escape · fields Options Strip: Draw=Start-End-Radius Arc · expect Lines +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Setout:Model Line · picks (12000,2000) (18000,2000) (15000,4500) · keys Escape Escape · fields Options Strip: Draw=Start-End-Radius Arc · expect Lines +1` | green: pressed 'Model Line' on Setout's Reference panel: the tool 'Model Line' stands \| fields: Draw=Start-End-Radius Arc set \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (18000,2000) mm at px (1176.0,368.3) on the plan view \| (15000,4500) mm at px (1088.0,295.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Model Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lines +1": Lines 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Lines 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6048. Draw a faceted degree 1 curve through five points for the folded-plate edge.

- Starts from: a new Architectural project
- Ends with: one degree 1 freeform curve through five points on Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,2000) (14000,4500) (16000,2000) (18000,4500) (20000,2000) · keys Return Escape Escape · fields Options Strip: Degree=1; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (16000,2000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,2000) (14000,4500) (16000,2000) (18000,4500) (20000,2000) · keys Return Escape Escape · fields Options Strip: Degree=1; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=1 reads '1'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (14000,4500) mm at px (1058.7,295.0) on the plan view \| (16000,2000) mm at px (1117.4,368.3) on the plan view \| (18000,4500) mm at px (1176.0,295.0) on the plan view \| (20000,2000) mm at px (1234.7,368.3) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (16000,2000) · keys — · fields — · expect 1 selected` | green: select: (16000,2000) mm at px (1021.7,368.3) on the plan view; picked 'e10203b799a077cdf55db1074ca97be9'; selected 0 -> 1 [e10203b799a077cdf55db1074ca97be9] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (e10203b799a077cdf55db1074ca97be9) (expected exactly 1) |

### The result

The model holds: Freeform Curve 1,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6049. Draw the fascia line as a degree 2 curve driven by control points rather than passing through them.

- Starts from: a new Architectural project
- Ends with: one degree 2 freeform curve on Ground defined by five control points
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,3000) (14000,5500) (16000,3000) (18000,5500) (20000,3000) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=no; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (12000,3000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,3000) (14000,5500) (16000,3000) (18000,5500) (20000,3000) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=no; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=2 reads '2'; Interpolate=no reads no; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (12000,3000) mm at px (1000.0,339.0) on the plan view \| (14000,5500) mm at px (1058.7,265.7) on the plan view \| (16000,3000) mm at px (1117.4,339.0) on the plan view \| (18000,5500) mm at px (1176.0,265.7) on the plan view \| (20000,3000) mm at px (1234.7,339.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (12000,3000) · keys — · fields — · expect 1 selected` | green: select: (12000,3000) mm at px (904.4,339.0) on the plan view; picked 'a3aa51de32a210b6e16d512d42491880'; selected 0 -> 1 [a3aa51de32a210b6e16d512d42491880] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (a3aa51de32a210b6e16d512d42491880) (expected exactly 1) |

### The result

The model holds: Freeform Curve 1,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6050. Draw the balustrade top-rail curve on Level 1, 500 mm above the floor.

- Starts from: a new Architectural project
- Ends with: one freeform curve at Level 1 with an offset of 500
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,2500) (18000,4000) (20000,3000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Level 1; Offset=500 · expect Freeform Curve +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,2500) (18000,4000) (20000,3000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Level 1; Offset=500 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Level 1 reads 'Level 1'; Offset=500 reads '500 mm' \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (14000,3500) mm at px (1058.7,324.3) on the plan view \| (16000,2500) mm at px (1117.4,353.7) on the plan view \| (18000,4000) mm at px (1176.0,309.7) on the plan view \| (20000,3000) mm at px (1234.7,339.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |

### The result

The model holds: Freeform Curve 1,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6051. Loft a canopy surface between the front edge curve and the raised back edge curve.

- Starts from: a new Architectural project
- Ends with: two freeform curves on Ground and one lofted Form between them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) (20000,2000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,6000) (14000,7500) (16000,5500) (18000,7000) (20000,6000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=900 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (14000,7500) · keys — · fields — · expect 2 selected",
  "ribbon:Massing \u0026 Site:Loft · picks — · keys Return · fields — · expect Form +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) (20000,2000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (14000,3500) mm at px (1058.7,324.3) on the plan view \| (16000,1500) mm at px (1117.4,383.0) on the plan view \| (18000,3000) mm at px (1176.0,339.0) on the plan view \| (20000,2000) mm at px (1234.7,368.3) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `ribbon:Massing & Site:Freeform Curve · picks (12000,6000) (14000,7500) (16000,5500) (18000,7000) (20000,6000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=900 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=900 reads '900 mm' \| picks: (12000,6000) mm at px (1000.0,251.0) on the plan view \| (14000,7500) mm at px (1058.7,207.0) on the plan view \| (16000,5500) mm at px (1117.4,265.7) on the plan view \| (18000,7000) mm at px (1176.0,221.7) on the plan view \| (20000,6000) mm at px (1234.7,251.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected` | green: select: (14000,3500) mm at px (963.0,324.3) on the plan view; picked 'd99b42079a457cefe9e8de8b8ab4a7de'; selected 0 -> 1 [d99b42079a457cefe9e8de8b8ab4a7de] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (d99b42079a457cefe9e8de8b8ab4a7de) (expected exactly 1) |
| `plan:select add · picks (14000,7500) · keys — · fields — · expect 2 selected` | green: select add: (14000,7500) mm at px (963.0,207.0) on the plan view; picked 'b5f56dd0aa182ac4f0832a8abf5d8029'; selected 1 -> 2 [d99b42079a457cefe9e8de8b8ab4a7de,b5f56dd0aa182ac4f0832a8abf5d8029] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (d99b42079a457cefe9e8de8b8ab4a7de, b5f56dd0aa182ac4f0832a8abf5d8029) (expected exactly 2) |
| `ribbon:Massing & Site:Loft · picks — · keys Return · fields — · expect Form +1` | green: pressed 'Loft' on Massing & Site's Form panel: the command 'Loft' ran; status '1 selected' \| keys: Return (no tool -> tool Loft, nothing standing to end) Check "Form +1": Form 0 -> 1 (+1, expected +1) |

### The result

The model holds: Form 1,Freeform Curve 2,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6052. Loft the shell through three section curves and divide it into hexagonal panels.

- Starts from: a new Architectural project
- Ends with: three freeform curves, one lofted Form and its curtain panels
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,0) (14000,1500) (16000,-1000) (18000,800) (20000,0) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,4000) (14000,5500) (16000,3500) (18000,5200) (20000,4000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=500 · expect Freeform Curve +1",
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,8000) (14000,9000) (16000,7500) (18000,9200) (20000,8000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=1000 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (14000,1500) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (14000,5500) · keys — · fields — · expect 2 selected",
  "plan:select add · picks (14000,9000) · keys — · fields — · expect 3 selected",
  "ribbon:Massing \u0026 Site:Loft · picks — · keys Return · fields — · expect Form +1",
  "ribbon:Massing \u0026 Site:form-panels · picks — · keys Return Escape Escape · fields Options Strip: Pattern=hex · expect Curtain Panels +240"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,0) (14000,1500) (16000,-1000) (18000,800) (20000,0) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (12000,0) mm at px (1000.0,427.0) on the plan view \| (14000,1500) mm at px (1058.7,383.0) on the plan view \| (16000,-1000) mm at px (1117.4,456.3) on the plan view \| (18000,800) mm at px (1176.0,403.5) on the plan view \| (20000,0) mm at px (1234.7,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `ribbon:Massing & Site:Freeform Curve · picks (12000,4000) (14000,5500) (16000,3500) (18000,5200) (20000,4000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=500 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=500 reads '500 mm' \| picks: (12000,4000) mm at px (1000.0,309.7) on the plan view \| (14000,5500) mm at px (1058.7,265.7) on the plan view \| (16000,3500) mm at px (1117.4,324.3) on the plan view \| (18000,5200) mm at px (1176.0,274.5) on the plan view \| (20000,4000) mm at px (1234.7,309.7) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 1 -> 2 (+1, expected +1) |
| `ribbon:Massing & Site:Freeform Curve · picks (12000,8000) (14000,9000) (16000,7500) (18000,9200) (20000,8000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=1000 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=1000 reads '1000 mm' \| picks: (12000,8000) mm at px (1000.0,192.3) on the plan view \| (14000,9000) mm at px (1058.7,163.0) on the plan view \| (16000,7500) mm at px (1117.4,207.0) on the plan view \| (18000,9200) mm at px (1176.0,157.1) on the plan view \| (20000,8000) mm at px (1234.7,192.3) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 2 -> 3 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (14000,1500) · keys — · fields — · expect 1 selected` | green: select: (14000,1500) mm at px (963.0,383.0) on the plan view; picked 'c23ec2e6cf5853bac7fcbb388db8b071'; selected 0 -> 1 [c23ec2e6cf5853bac7fcbb388db8b071] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (c23ec2e6cf5853bac7fcbb388db8b071) (expected exactly 1) |
| `plan:select add · picks (14000,5500) · keys — · fields — · expect 2 selected` | green: select add: (14000,5500) mm at px (963.0,265.7) on the plan view; picked '967a13ebb586c0e74ea59f70395e922b'; selected 1 -> 2 [c23ec2e6cf5853bac7fcbb388db8b071,967a13ebb586c0e74ea59f70395e922b] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (c23ec2e6cf5853bac7fcbb388db8b071, 967a13ebb586c0e74ea59f70395e922b) (expected exactly 2) |
| `plan:select add · picks (14000,9000) · keys — · fields — · expect 3 selected` | green: select add: (14000,9000) mm at px (963.0,163.0) on the plan view; picked '05959d7815f6ad7c8f7c02b453454694'; selected 2 -> 3 [c23ec2e6cf5853bac7fcbb388db8b071,967a13ebb586c0e74ea59f70395e922b,05959d7815f6ad7c8f7c02b453454694] \| picks: the plan band pressed these 1 pick(s) as its own process Check "3 selected": 3 selected (c23ec2e6cf5853bac7fcbb388db8b071, 967a13ebb586c0e74ea59f70395e922b, 05959d7815f6ad7c8f7c02b453454694) (expected exactly 3) |
| `ribbon:Massing & Site:Loft · picks — · keys Return · fields — · expect Form +1` | green: pressed 'Loft' on Massing & Site's Form panel: the command 'Loft' ran; status '1 selected' \| keys: Return (no tool -> tool Loft, nothing standing to end) Check "Form +1": Form 0 -> 1 (+1, expected +1) |
| `ribbon:Massing & Site:form-panels · picks — · keys Return Escape Escape · fields Options Strip: Pattern=hex · expect Curtain Panels +240` | green: pressed 'form-panels' on Massing & Site's Form panel: the command 'form-panels' ran \| fields: Pattern=hex reads 'hex' \| keys: Return (tool Form Panels -> tool Form Panels); Escape (tool Form Panels -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Curtain Panels +240": Curtain Panels 0 -> 240 (+240, expected +240) |

### The result

The model holds: Curtain Panels 240,Form 1,Freeform Curve 3,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6053. Revolve the profile curve 360 degrees about a vertical axis to make the column vase.

- Starts from: a new Architectural project
- Ends with: one freeform profile curve and one revolved Form on Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,6000) (13500,7000) (12800,7800) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (13500,7000) · keys — · fields — · expect 1 selected",
  "ribbon:Massing \u0026 Site:Revolve · picks (15000,5500) (15000,8000) · keys Return Escape Escape · fields Options Strip: Angle=360 · expect Form +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,6000) (13500,7000) (12800,7800) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=2 reads '2'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (12000,6000) mm at px (1000.0,251.0) on the plan view \| (13500,7000) mm at px (1044.0,221.7) on the plan view \| (12800,7800) mm at px (1023.5,198.2) on the plan view \| presses to the tool 3, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (13500,7000) · keys — · fields — · expect 1 selected` | green: select: (13500,7000) mm at px (1043.6,221.7) on the plan view; picked '0272243ada61d87b37060908c8e549ed'; selected 0 -> 1 [0272243ada61d87b37060908c8e549ed] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (0272243ada61d87b37060908c8e549ed) (expected exactly 1) |
| `ribbon:Massing & Site:Revolve · picks (15000,5500) (15000,8000) · keys Return Escape Escape · fields Options Strip: Angle=360 · expect Form +1` | green: pressed 'Revolve' on Massing & Site's Form panel: the tool 'Revolve' stands \| fields: Angle=360 reads '360.00 °' \| picks: (15000,5500) mm at px (1087.6,265.7) on the plan view \| (15000,8000) mm at px (1087.6,192.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Return (no tool -> tool Revolve, nothing standing to end); Escape (tool Revolve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Form +1": Form 0 -> 1 (+1, expected +1) |

### The result

The model holds: Form 1,Freeform Curve 1,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6054. Revolve the profile 180 degrees to make the half-round apse surface.

- Starts from: a new Architectural project
- Ends with: one freeform profile curve and one half-turn revolved Form on Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,6000) (13500,7000) (12800,7800) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (13500,7000) · keys — · fields — · expect 1 selected",
  "ribbon:Massing \u0026 Site:Revolve · picks (15000,5500) (15000,8000) · keys Return Escape Escape · fields Options Strip: Angle=180 · expect Form +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,6000) (13500,7000) (12800,7800) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=2 reads '2'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (12000,6000) mm at px (1000.0,251.0) on the plan view \| (13500,7000) mm at px (1044.0,221.7) on the plan view \| (12800,7800) mm at px (1023.5,198.2) on the plan view \| presses to the tool 3, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (13500,7000) · keys — · fields — · expect 1 selected` | green: select: (13500,7000) mm at px (1043.6,221.7) on the plan view; picked '5f35e5a9d68589f234221f24d1fca254'; selected 0 -> 1 [5f35e5a9d68589f234221f24d1fca254] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (5f35e5a9d68589f234221f24d1fca254) (expected exactly 1) |
| `ribbon:Massing & Site:Revolve · picks (15000,5500) (15000,8000) · keys Return Escape Escape · fields Options Strip: Angle=180 · expect Form +1` | green: pressed 'Revolve' on Massing & Site's Form panel: the tool 'Revolve' stands \| fields: Angle=180 reads '180.00 °' \| picks: (15000,5500) mm at px (1087.6,265.7) on the plan view \| (15000,8000) mm at px (1087.6,192.3) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Return (no tool -> tool Revolve, nothing standing to end); Escape (tool Revolve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Form +1": Form 0 -> 1 (+1, expected +1) |

### The result

The model holds: Form 1,Freeform Curve 1,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6055. Sweep the small section curve along the rail curve to model the curved handrail.

- Starts from: a new Architectural project
- Ends with: a rail curve, a section curve and one swept Form on Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (17000,6000) (19000,7500) (21000,6000) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (17000,5000) (17500,5500) (17000,6000) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (19000,7500) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (17500,5500) · keys — · fields — · expect 2 selected",
  "ribbon:Massing \u0026 Site:Sweep · picks — · keys Return · fields — · expect Form +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (17000,6000) (19000,7500) (21000,6000) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=2 reads '2'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (17000,6000) mm at px (1146.7,251.0) on the plan view \| (19000,7500) mm at px (1205.4,207.0) on the plan view \| (21000,6000) mm at px (1264.0,251.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `ribbon:Massing & Site:Freeform Curve · picks (17000,5000) (17500,5500) (17000,6000) · keys Return Escape Escape · fields Options Strip: Degree=2; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=2 reads '2'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (17000,5000) mm at px (1146.7,280.3) on the plan view \| (17500,5500) mm at px (1161.4,265.7) on the plan view \| (17000,6000) mm at px (1146.7,251.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (19000,7500) · keys — · fields — · expect 1 selected` | green: select: (19000,7500) mm at px (1095.0,207.0) on the plan view; picked '9953dbd5f72bb98dc1a09ee3aa242686'; selected 0 -> 1 [9953dbd5f72bb98dc1a09ee3aa242686] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (9953dbd5f72bb98dc1a09ee3aa242686) (expected exactly 1) |
| `plan:select add · picks (17500,5500) · keys — · fields — · expect 2 selected` | green: select add: (17500,5500) mm at px (1051.0,265.7) on the plan view; picked 'e12335412f3fba30629b643f8774887c'; selected 1 -> 2 [9953dbd5f72bb98dc1a09ee3aa242686,e12335412f3fba30629b643f8774887c] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (9953dbd5f72bb98dc1a09ee3aa242686, e12335412f3fba30629b643f8774887c) (expected exactly 2) |
| `ribbon:Massing & Site:Sweep · picks — · keys Return · fields — · expect Form +1` | green: pressed 'Sweep' on Massing & Site's Form panel: the command 'Sweep' ran; status '1 selected' \| keys: Return (no tool -> tool Sweep, nothing standing to end) Check "Form +1": Form 0 -> 1 (+1, expected +1) |

### The result

The model holds: Form 1,Freeform Curve 2,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6056. Put a 1 m wide spiral stair in the corner of the atrium, Ground up to Level 1.

- Starts from: a new Architectural project
- Ends with: one spiral stair centred at (15000,5000), 1000 mm wide, rising from Ground to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:draw-stair · picks (15000,5000) (16200,5000) · keys Return Escape Escape · fields Options Strip: Shape=spiral; Width=1000; Inner Radius=200; Sweep=360; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:draw-stair · picks (15000,5000) (16200,5000) · keys Return Escape Escape · fields Options Strip: Shape=spiral; Width=1000; Inner Radius=200; Sweep=360; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1` | green: pressed 'draw-stair' on Architecture's Circulation panel: the tool 'draw-stair' stands \| fields: Shape=spiral reads 'Spiral'; Width=1000 reads '1000 mm'; Inner Radius=200 reads '200 mm'; Sweep=360 reads '360.00 °'; Level=Ground reads 'Ground'; Multistorey Top Level=Level 1 reads 'Level 1' \| picks: (15000,5000) mm at px (1088.0,280.3) on the plan view \| (16200,5000) mm at px (1123.2,280.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Return (tool draw-stair -> tool draw-stair); Escape (tool draw-stair -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Stairs 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6057. Draw a 1.2 m wide spiral stair turning left through three quarters of a turn to the mezzanine at Level 1.

- Starts from: a new Architectural project
- Ends with: one left-turning spiral stair, 1200 mm wide, sweeping 270 degrees from Ground to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:draw-stair · picks (16000,6000) (17500,6000) · keys Return Escape Escape · fields Options Strip: Shape=spiral; Turn=left; Width=1200; Inner Radius=300; Sweep=270; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:draw-stair · picks (16000,6000) (17500,6000) · keys Return Escape Escape · fields Options Strip: Shape=spiral; Turn=left; Width=1200; Inner Radius=300; Sweep=270; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1` | green: pressed 'draw-stair' on Architecture's Circulation panel: the tool 'draw-stair' stands \| fields: Shape=spiral reads 'Spiral'; Turn=left reads 'left'; Width=1200 reads '1200 mm'; Inner Radius=300 reads '300 mm'; Sweep=270 reads '270.00 °'; Level=Ground reads 'Ground'; Multistorey Top Level=Level 1 reads 'Level 1' \| picks: (16000,6000) mm at px (1117.4,251.0) on the plan view \| (17500,6000) mm at px (1161.4,251.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Return (tool draw-stair -> tool draw-stair); Escape (tool draw-stair -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Stairs 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6058. Loft a roof shell through two curves on Level 1 for the stadium canopy study.

- Starts from: a new Structural project
- Ends with: two freeform curves on Level 1 and one lofted Form between them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) (20000,2000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Level 1; Offset=0 · expect Freeform Curve +1",
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,6000) (14000,7500) (16000,5500) (18000,7000) (20000,6000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Level 1; Offset=900 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (14000,7500) · keys — · fields — · expect 2 selected",
  "ribbon:Massing \u0026 Site:Loft · picks — · keys Return · fields — · expect Form +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) (20000,2000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Level 1; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Level 1 reads 'Level 1'; Offset=0 reads '0 mm' \| picks: (12000,2000) mm at px (871.3,389.8) on the plan view \| (14000,3500) mm at px (908.5,361.9) on the plan view \| (16000,1500) mm at px (945.8,399.1) on the plan view \| (18000,3000) mm at px (983.0,371.2) on the plan view \| (20000,2000) mm at px (1020.2,389.8) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `ribbon:Massing & Site:Freeform Curve · picks (12000,6000) (14000,7500) (16000,5500) (18000,7000) (20000,6000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Level 1; Offset=900 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Level 1 reads 'Level 1'; Offset=900 reads '900 mm' \| picks: (12000,6000) mm at px (871.3,315.3) on the plan view \| (14000,7500) mm at px (908.5,287.4) on the plan view \| (16000,5500) mm at px (945.8,324.6) on the plan view \| (18000,7000) mm at px (983.0,296.7) on the plan view \| (20000,6000) mm at px (1020.2,315.3) on the plan view \| presses to the tool 5, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected` | green: select: (14000,3500) mm at px (908.5,361.9) on the plan view; picked '796289d2c2b5ef36530e6e2528464270'; selected 0 -> 1 [796289d2c2b5ef36530e6e2528464270] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (796289d2c2b5ef36530e6e2528464270) (expected exactly 1) |
| `plan:select add · picks (14000,7500) · keys — · fields — · expect 2 selected` | green: select add: (14000,7500) mm at px (908.5,287.4) on the plan view; picked 'e506585899a1dd4a8c6f6d3b79d42493'; selected 1 -> 2 [796289d2c2b5ef36530e6e2528464270,e506585899a1dd4a8c6f6d3b79d42493] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (796289d2c2b5ef36530e6e2528464270, e506585899a1dd4a8c6f6d3b79d42493) (expected exactly 2) |
| `ribbon:Massing & Site:Loft · picks — · keys Return · fields — · expect Form +1` | green: pressed 'Loft' on Massing & Site's Form panel: the command 'Loft' ran; status '1 selected' \| keys: Return (no tool -> tool Loft, nothing standing to end) Check "Form +1": Form 0 -> 1 (+1, expected +1) |

### The result

The model holds: Form 1,Freeform Curve 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6062. Loft the two curves, take the loft back with undo, then put it back with redo.

- Starts from: a new Architectural project
- Ends with: two freeform curves and one lofted Form between them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,6000) (14000,7500) (16000,5500) (18000,7000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=1200 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (14000,7500) · keys — · fields — · expect 2 selected",
  "ribbon:Massing \u0026 Site:Loft · picks — · keys Return · fields — · expect Form +1",
  "qa:Undo · picks — · keys — · fields — · expect Form -1",
  "qa:Redo · picks — · keys — · fields — · expect Form +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (14000,3500) mm at px (1058.7,324.3) on the plan view \| (16000,1500) mm at px (1117.4,383.0) on the plan view \| (18000,3000) mm at px (1176.0,339.0) on the plan view \| presses to the tool 4, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `ribbon:Massing & Site:Freeform Curve · picks (12000,6000) (14000,7500) (16000,5500) (18000,7000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=1200 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=1200 reads '1200 mm' \| picks: (12000,6000) mm at px (1000.0,251.0) on the plan view \| (14000,7500) mm at px (1058.7,207.0) on the plan view \| (16000,5500) mm at px (1117.4,265.7) on the plan view \| (18000,7000) mm at px (1176.0,221.7) on the plan view \| presses to the tool 4, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 1 -> 2 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected` | green: select: (14000,3500) mm at px (992.4,324.3) on the plan view; picked '263500b2d3890c0dded14702e8de3d73'; selected 0 -> 1 [263500b2d3890c0dded14702e8de3d73] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (263500b2d3890c0dded14702e8de3d73) (expected exactly 1) |
| `plan:select add · picks (14000,7500) · keys — · fields — · expect 2 selected` | green: select add: (14000,7500) mm at px (992.4,207.0) on the plan view; picked '739994e5d0a22d71da973f07170b4478'; selected 1 -> 2 [263500b2d3890c0dded14702e8de3d73,739994e5d0a22d71da973f07170b4478] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (263500b2d3890c0dded14702e8de3d73, 739994e5d0a22d71da973f07170b4478) (expected exactly 2) |
| `ribbon:Massing & Site:Loft · picks — · keys Return · fields — · expect Form +1` | green: pressed 'Loft' on Massing & Site's Form panel: the command 'Loft' ran; status '1 selected' \| keys: Return (no tool -> tool Loft, nothing standing to end) Check "Form +1": Form 0 -> 1 (+1, expected +1) |
| `qa:Undo · picks — · keys — · fields — · expect Form -1` | green: QToolButton pressed; a command ran Check "Form -1": Form 1 -> 0 (-1, expected -1) |
| `qa:Redo · picks — · keys — · fields — · expect Form +1` | green: QToolButton pressed; a command ran Check "Form +1": Form 0 -> 1 (+1, expected +1) |

### The result

The model holds: Form 1,Freeform Curve 2,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6063. Draw a trial curve, decide against it and delete it.

- Starts from: a new Architectural project
- Ends with: no freeform curves in the model
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Massing \u0026 Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Freeform Curve -1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Massing & Site:Freeform Curve · picks (12000,2000) (14000,3500) (16000,1500) (18000,3000) · keys Return Escape Escape · fields Options Strip: Degree=3; Interpolate=yes; Level=Ground; Offset=0 · expect Freeform Curve +1` | green: pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands \| fields: Degree=3 reads '3'; Interpolate=yes reads yes; Level=Ground reads 'Ground'; Offset=0 reads '0 mm' \| picks: (12000,2000) mm at px (1000.0,368.3) on the plan view \| (14000,3500) mm at px (1058.7,324.3) on the plan view \| (16000,1500) mm at px (1117.4,383.0) on the plan view \| (18000,3000) mm at px (1176.0,339.0) on the plan view \| presses to the tool 4, selection unchanged \| keys: Return (tool Freeform Curve -> tool Freeform Curve); Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Freeform Curve +1": Freeform Curve 0 -> 1 (+1, expected +1) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (14000,3500) · keys — · fields — · expect 1 selected` | green: select: (14000,3500) mm at px (992.4,324.3) on the plan view; picked 'dedd5b9222aa33ac33d9265a1c7d97e6'; selected 0 -> 1 [dedd5b9222aa33ac33d9265a1c7d97e6] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (dedd5b9222aa33ac33d9265a1c7d97e6) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Freeform Curve -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Freeform Curve -1": Freeform Curve 1 -> 0 (-1, expected -1) |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6064. Upsize the cold water riser to 150 mm and mark it CW-1.

- Starts from: a new Hydraulic project
- Ends with: one 6 m pipe on Level 1 with Diameter 150 and Mark CW-1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(12000,3000) to=(18000,3000) level=\"Level 1\" diameter=100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(12000,3000) to=(18000,3000) level="Level 1" diameter=100` | green: op:add pipe made=pipe-72cff5f4860ea081,system-191bebc4f0f778cc changed= ms=7 Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Diameter=150; Mark=CW-1 · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (927.2,371.2) on the plan view; picked 'pipe-72cff5f4860ea081'; selected 0 -> 1 [pipe-72cff5f4860ea081] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-72cff5f4860ea081) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Diameter=150; Mark=CW-1 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Diameter=150 committed ok, reads '150 mm'; Attributes [Common] Mark=CW-1 committed ok, reads 'CW-1' Check "1 selected": 1 selected (pipe-72cff5f4860ea081) (expected exactly 1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6065. Resize the main supply duct to 600 x 400 and mark it SA-1.

- Starts from: a new Mechanical project
- Ends with: one 6 m duct on Level 1 with Width 600, Height 400 and Mark SA-1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add duct from=(12000,3000) to=(18000,3000) level=\"Level 1\" width=400 height=300"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(12000,3000) to=(18000,3000) level="Level 1" width=400 height=300` | green: op:add duct made=duct-4a963753a480a4c9,system-baf404fb958cc9b2 changed= ms=6 Check "Ducts +1": Ducts 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Width=600; Height=400; Mark=SA-1 · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (927.2,371.2) on the plan view; picked 'duct-4a963753a480a4c9'; selected 0 -> 1 [duct-4a963753a480a4c9] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (duct-4a963753a480a4c9) (expected exactly 1) |
| `dock:Properties · picks — · keys — · fields Attributes: Width=600; Height=400; Mark=SA-1 · expect 1 selected` | green: Properties stands and raised \| fields: Attributes [Common] Width=600 committed ok, reads '600 mm'; Attributes [Common] Height=400 committed ok, reads '400 mm'; Attributes [Common] Mark=SA-1 committed ok, reads 'SA-1' Check "1 selected": 1 selected (duct-4a963753a480a4c9) (expected exactly 1) |

### The result

The model holds: Duct Systems 1,Ducts 1,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6066. Repeat the 8 m beam four times at 3 m centres for the floor framing.

- Starts from: a new Structural project
- Ends with: four 8 m beams on Level 1 at 3000 mm centres
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add beam from=(12000,2000) to=(20000,2000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add beam from=(12000,2000) to=(20000,2000) level="Level 1"` | green: op:add beam made=beam-46f186e50689b1d1 changed= ms=18 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (16000,2000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Array · picks (16000,2000) (16000,5000) · keys Escape Escape · fields Options Strip: Number=4 · expect Structural Framing +3",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (16000,11000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (16000,2000) · keys — · fields — · expect 1 selected` | green: select: (16000,2000) mm at px (945.8,389.8) on the plan view; picked 'beam-46f186e50689b1d1'; selected 0 -> 1 [beam-46f186e50689b1d1] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (beam-46f186e50689b1d1) (expected exactly 1) |
| `ribbon:Modify:Array · picks (16000,2000) (16000,5000) · keys Escape Escape · fields Options Strip: Number=4 · expect Structural Framing +3` | green: pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands \| fields: Number=4 reads '4.00' \| picks: (16000,2000) mm at px (945.8,389.8) on the plan view \| (16000,5000) mm at px (945.8,333.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Array -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Structural Framing +3": Structural Framing 1 -> 4 (+3, expected +3) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (16000,11000) · keys — · fields — · expect 1 selected` | green: select: (16000,11000) mm at px (945.8,222.3) on the plan view; picked 'beam-46f186e50689b1d1-e2fdec90c26cfdf5'; selected 0 -> 1 [beam-46f186e50689b1d1-e2fdec90c26cfdf5] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (beam-46f186e50689b1d1-e2fdec90c26cfdf5) (expected exactly 1) |

### The result

The model holds: Levels 2,Model Groups 1,Structural Framing 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6067. Select one bay of the frame, two columns and the beam between them, and move it 2 m north.

- Starts from: a new Structural project
- Ends with: two columns and a beam on Level 1 standing 2000 mm further north
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(12000,3000) level=\"Level 1\"",
  "op:add column at=(18000,3000) level=\"Level 1\"",
  "op:add beam from=(12000,3000) to=(18000,3000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(12000,3000) level="Level 1"` | green: op:add column made=column-856f6dca44f36c22 changed= ms=564 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(18000,3000) level="Level 1"` | green: op:add column made=column-94432542aa8b559e changed= ms=5 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add beam from=(12000,3000) to=(18000,3000) level="Level 1"` | green: op:add beam made=beam-94c84cf57bffadc9 changed= ms=8 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:marquee · picks (11000,4500) (19000,1500) · keys — · fields — · expect 3 selected",
  "ribbon:Modify:Move · picks (15000,3000) (15000,5000) · keys Escape Escape · fields — · expect moved",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:marquee · picks (11000,6500) (19000,3500) · keys — · fields — · expect 3 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:marquee · picks (11000,4500) (19000,1500) · keys — · fields — · expect 3 selected` | green: marquee: window (left to right); drag px (852.7,343.3) -> (1001.6,399.1) on the plan view; selected 0 -> 3 [beam-94c84cf57bffadc9,column-856f6dca44f36c22,column-94432542aa8b559e] \| picks: the plan band pressed these 2 pick(s) as its own process Check "3 selected": 3 selected (beam-94c84cf57bffadc9, column-856f6dca44f36c22, column-94432542aa8b559e) (expected exactly 3) |
| `ribbon:Modify:Move · picks (15000,3000) (15000,5000) · keys Escape Escape · fields — · expect moved` | green: pressed 'Move' on Modify's Modify panel (through its fold): the tool 'Move' stands \| picks: (15000,3000) mm at px (927.2,371.2) on the plan view \| (15000,5000) mm at px (927.2,333.9) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 3 element(s) moved: beam-94c84cf57bffadc9 (12000, 3000) -> (12000, 5000); column-856f6dca44f36c22 (12000, 3000) -> (12000, 5000); column-94432542aa8b559e (18000, 3000) -> (18000, 5000) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:marquee · picks (11000,6500) (19000,3500) · keys — · fields — · expect 3 selected` | green: marquee: window (left to right); drag px (852.7,306.0) -> (1001.6,361.9) on the plan view; selected 0 -> 3 [beam-94c84cf57bffadc9,column-856f6dca44f36c22,column-94432542aa8b559e] \| picks: the plan band pressed these 2 pick(s) as its own process Check "3 selected": 3 selected (beam-94c84cf57bffadc9, column-856f6dca44f36c22, column-94432542aa8b559e) (expected exactly 3) |

### The result

The model holds: Levels 2,Structural Columns 2,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6068. Move, copy and turn the wall, take the three changes back one by one, then redo the first.

- Starts from: a new Architectural project
- Ends with: the wall moved 1500 mm north, with the copy and the turn undone
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,3000) to=(18000,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,3000) to=(18000,3000) level=Ground` | green: op:add wall made=wall-c8ccb609d5476f1b changed= ms=370 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Move · picks (15000,3000) (15000,4500) · keys Escape Escape · fields — · expect moved",
  "plan:select · picks (15000,4500) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Copy · picks (15000,4500) (15000,7500) · keys Escape Escape · fields — · expect Walls +1",
  "plan:select · picks (15000,7500) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Rotate · picks (15000,7500) (18000,7500) (15000,10500) · keys Escape Escape · fields — · expect moved",
  "qa:Undo · picks — · keys — · fields — · expect moved",
  "qa:Undo · picks — · keys — · fields — · expect Walls -1",
  "qa:Undo · picks — · keys — · fields — · expect moved",
  "qa:Redo · picks — · keys — · fields — · expect moved"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (1021.7,339.0) on the plan view; picked 'wall-c8ccb609d5476f1b'; selected 0 -> 1 [wall-c8ccb609d5476f1b] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-c8ccb609d5476f1b) (expected exactly 1) |
| `ribbon:Modify:Move · picks (15000,3000) (15000,4500) · keys Escape Escape · fields — · expect moved` | green: pressed 'Move' on Modify's Modify panel (through its fold): the tool 'Move' stands \| picks: (15000,3000) mm at px (1021.7,339.0) on the plan view \| (15000,4500) mm at px (1021.7,295.0) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: wall-c8ccb609d5476f1b  -> |
| `plan:select · picks (15000,4500) · keys — · fields — · expect 1 selected` | green: select: (15000,4500) mm at px (1021.7,295.0) on the plan view; picked 'wall-c8ccb609d5476f1b'; selected 0 -> 1 [wall-c8ccb609d5476f1b] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-c8ccb609d5476f1b) (expected exactly 1) |
| `ribbon:Modify:Copy · picks (15000,4500) (15000,7500) · keys Escape Escape · fields — · expect Walls +1` | green: pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands \| picks: (15000,4500) mm at px (1021.7,295.0) on the plan view \| (15000,7500) mm at px (1021.7,207.0) on the plan view \| presses to the tool 2 (the tool ended on the press), selection changed \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `plan:select · picks (15000,7500) · keys — · fields — · expect 1 selected` | green: select: (15000,7500) mm at px (1021.7,207.0) on the plan view; picked 'wall-c8ccb609d5476f1b-dfb749cd05c999f6'; selected 0 -> 1 [wall-c8ccb609d5476f1b-dfb749cd05c999f6] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-c8ccb609d5476f1b-dfb749cd05c999f6) (expected exactly 1) |
| `ribbon:Modify:Rotate · picks (15000,7500) (18000,7500) (15000,10500) · keys Escape Escape · fields — · expect moved` | green: pressed 'Rotate' on Modify's Modify panel (through its fold): the tool 'Rotate' stands \| picks: (15000,7500) mm at px (1021.7,207.0) on the plan view \| (18000,7500) mm at px (1109.7,207.0) on the plan view \| (15000,10500) mm at px (1021.7,119.0) on the plan view \| presses to the tool 3 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: wall-c8ccb609d5476f1b-dfb749cd05c999f6  -> |
| `qa:Undo · picks — · keys — · fields — · expect moved` | green: QToolButton pressed; a command ran Check "moved": 1 element(s) moved: wall-c8ccb609d5476f1b-dfb749cd05c999f6  -> |
| `qa:Undo · picks — · keys — · fields — · expect Walls -1` | green: QToolButton pressed; a command ran Check "Walls -1": Walls 2 -> 1 (-1, expected -1) |
| `qa:Undo · picks — · keys — · fields — · expect moved` | green: QToolButton pressed; a command ran Check "moved": 1 element(s) moved: wall-c8ccb609d5476f1b  -> |
| `qa:Redo · picks — · keys — · fields — · expect moved` | green: QToolButton pressed; a command ran Check "moved": 1 element(s) moved: wall-c8ccb609d5476f1b  -> |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6069. Delete the door from the north wall, then undo the delete to bring it back.

- Starts from: a new Architectural project
- Ends with: one 6 m wall on Ground with its door back in place
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,6000) to=(18000,6000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,6000) to=(18000,6000) level=Ground` | green: op:add wall made=wall-df5fa52f9f34118a changed= ms=389 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Architecture:Door · picks (15000,6000) · keys Escape Escape · fields — · expect Doors +1",
  "plan:select · picks (15000,6000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Doors -1",
  "qa:Undo · picks — · keys — · fields — · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Architecture:Door · picks (15000,6000) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (15000,6000) mm at px (1021.7,251.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `plan:select · picks (15000,6000) · keys — · fields — · expect 1 selected` | green: select: (15000,6000) mm at px (1021.7,251.0) on the plan view; picked 'door-0a53835c3e3d4020'; selected 0 -> 1 [door-0a53835c3e3d4020] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (door-0a53835c3e3d4020) (expected exactly 1) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Doors -1` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Doors -1": Doors 1 -> 0 (-1, expected -1) |
| `qa:Undo · picks — · keys — · fields — · expect Doors +1` | green: QToolButton pressed; a command ran Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |

### The result

The model holds: Doors 1,Levels 3,Openings 1,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6070. Select the three stair-core walls together and write the fire rating in all their comments.

- Starts from: a new Architectural project
- Ends with: three stair-core walls on Ground, each with the comment FRL 120/120/120
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(18000,2000) level=Ground",
  "op:add wall from=(18000,2000) to=(18000,8000) level=Ground",
  "op:add wall from=(18000,8000) to=(12000,8000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(18000,2000) level=Ground` | green: op:add wall made=wall-11a5307bc84d5502 changed= ms=407 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(18000,2000) to=(18000,8000) level=Ground` | green: op:add wall made=wall-dda88235306a73c1 changed=wall-11a5307bc84d5502 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(18000,8000) to=(12000,8000) level=Ground` | green: op:add wall made=wall-47b9159766c8204d changed=wall-dda88235306a73c1 ms=50 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected",
  "plan:select add · picks (18000,5000) · keys — · fields — · expect 2 selected",
  "plan:select add · picks (15000,8000) · keys — · fields — · expect 3 selected",
  "dock:Properties · picks — · keys — · fields Attributes: Comments=FRL 120/120/120 · expect 3 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (15000,2000) · keys — · fields — · expect 1 selected` | green: select: (15000,2000) mm at px (1020.2,368.3) on the plan view; picked 'wall-11a5307bc84d5502'; selected 0 -> 1 [wall-11a5307bc84d5502] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-11a5307bc84d5502) (expected exactly 1) |
| `plan:select add · picks (18000,5000) · keys — · fields — · expect 2 selected` | green: select add: (18000,5000) mm at px (1108.2,280.3) on the plan view; picked 'wall-dda88235306a73c1'; selected 1 -> 2 [wall-11a5307bc84d5502,wall-dda88235306a73c1] \| picks: the plan band pressed these 1 pick(s) as its own process Check "2 selected": 2 selected (wall-11a5307bc84d5502, wall-dda88235306a73c1) (expected exactly 2) |
| `plan:select add · picks (15000,8000) · keys — · fields — · expect 3 selected` | green: select add: (15000,8000) mm at px (1020.2,192.3) on the plan view; picked 'wall-47b9159766c8204d'; selected 2 -> 3 [wall-11a5307bc84d5502,wall-dda88235306a73c1,wall-47b9159766c8204d] \| picks: the plan band pressed these 1 pick(s) as its own process Check "3 selected": 3 selected (wall-11a5307bc84d5502, wall-dda88235306a73c1, wall-47b9159766c8204d) (expected exactly 3) |
| `dock:Properties · picks — · keys — · fields Attributes: Comments=FRL 120/120/120 · expect 3 selected` | green: Properties stands and raised \| fields: Attributes [Common] Comments=FRL 120/120/120 committed ok, reads 'FRL 120/120/120' Check "3 selected": 3 selected (wall-11a5307bc84d5502, wall-dda88235306a73c1, wall-47b9159766c8204d) (expected exactly 3) |

### The result

The model holds: Levels 3,Walls 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6071. Turn the 6 m roof beam a quarter turn about its centre to run it north to south.

- Starts from: a new Structural project
- Ends with: one 6 m beam on Level 1 running north to south through (15000,3000)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add beam from=(12000,3000) to=(18000,3000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add beam from=(12000,3000) to=(18000,3000) level="Level 1"` | green: op:add beam made=beam-55be4adaa2ce361d changed= ms=65 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Rotate · picks (15000,3000) (18000,3000) (15000,6000) · keys Escape Escape · fields — · expect moved",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,5000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (927.2,371.2) on the plan view; picked 'beam-55be4adaa2ce361d'; selected 0 -> 1 [beam-55be4adaa2ce361d] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (beam-55be4adaa2ce361d) (expected exactly 1) |
| `ribbon:Modify:Rotate · picks (15000,3000) (18000,3000) (15000,6000) · keys Escape Escape · fields — · expect moved` | green: pressed 'Rotate' on Modify's Modify panel (through its fold): the tool 'Rotate' stands \| picks: (15000,3000) mm at px (927.2,371.2) on the plan view \| (18000,3000) mm at px (983.0,371.2) on the plan view \| (15000,6000) mm at px (927.2,315.3) on the plan view \| presses to the tool 3 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: beam-55be4adaa2ce361d (12000, 3000) -> (15000, 0) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,5000) · keys — · fields — · expect 1 selected` | green: select: (15000,5000) mm at px (927.2,333.9) on the plan view; picked 'beam-55be4adaa2ce361d'; selected 0 -> 1 [beam-55be4adaa2ce361d] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (beam-55be4adaa2ce361d) (expected exactly 1) |

### The result

The model holds: Levels 2,Structural Framing 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6072. Drag the 6 m waste pipe 2 m north to clear the beam below.

- Starts from: a new Hydraulic project
- Ends with: one 6 m 100 mm pipe on Level 1, 2000 mm north of where it was drawn
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add pipe from=(12000,3000) to=(18000,3000) level=\"Level 1\" diameter=100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(12000,3000) to=(18000,3000) level="Level 1" diameter=100` | green: op:add pipe made=pipe-7f500dc5a66dc527,system-198f33755d873374 changed= ms=6 Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "plan:drag · picks (15000,3000) (15000,5000) · keys — · fields — · expect moved",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:select · picks (15000,5000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (927.2,371.2) on the plan view; picked 'pipe-7f500dc5a66dc527'; selected 0 -> 1 [pipe-7f500dc5a66dc527] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-7f500dc5a66dc527) (expected exactly 1) |
| `plan:drag · picks (15000,3000) (15000,5000) · keys — · fields — · expect moved` | green: drag: drag px (927.2,371.2) -> (927.2,333.9) on the plan view; selected 1 -> 1 [pipe-7f500dc5a66dc527] \| picks: the plan band pressed these 2 pick(s) as its own process Check "moved": 1 element(s) moved: pipe-7f500dc5a66dc527 (15, 300) -> (15, 300) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:select · picks (15000,5000) · keys — · fields — · expect 1 selected` | green: select: (15000,5000) mm at px (927.2,333.9) on the plan view; picked 'pipe-7f500dc5a66dc527'; selected 1 -> 1 [pipe-7f500dc5a66dc527] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (pipe-7f500dc5a66dc527) (expected exactly 1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 6073. Select the two walls of the L-shaped wing with a window and mirror them across the line at x = 16000.

- Starts from: a new Architectural project
- Ends with: the two wing walls on Ground and their mirror image east of x = 16000
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,2000) to=(15000,2000) level=Ground",
  "op:add wall from=(12000,2000) to=(12000,7000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,2000) to=(15000,2000) level=Ground` | green: op:add wall made=wall-2be8d932a78eb28f changed= ms=565 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,2000) to=(12000,7000) level=Ground` | green: op:add wall made=wall-b5cf2d758a3ec1d1 changed=wall-2be8d932a78eb28f ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:marquee · picks (11000,8000) (15500,1000) · keys — · fields — · expect 2 selected",
  "ribbon:Modify:Mirror › Draw Axis · picks (16000,1000) (16000,9000) · keys Escape Escape · fields — · expect Walls +2",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (20000,4500) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:marquee · picks (11000,8000) (15500,1000) · keys — · fields — · expect 2 selected` | green: marquee: window (left to right); drag px (948.4,192.3) -> (1080.4,397.7) on the plan view; selected 0 -> 2 [wall-2be8d932a78eb28f,wall-b5cf2d758a3ec1d1] \| picks: the plan band pressed these 2 pick(s) as its own process Check "2 selected": 2 selected (wall-2be8d932a78eb28f, wall-b5cf2d758a3ec1d1) (expected exactly 2) |
| `ribbon:Modify:Mirror › Draw Axis · picks (16000,1000) (16000,9000) · keys Escape Escape · fields — · expect Walls +2` | green: pressed 'Mirror › Draw Axis' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Draw Axis'; the press stood 254 ms (the menu stood at 10 ms; its row ran 234 ms; it made 0 child widgets native)): the tool 'Mirror › Draw Axis' stands \| picks: (16000,1000) mm at px (1095.0,397.7) on the plan view \| (16000,9000) mm at px (1095.0,163.0) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "Walls +2": Walls 2 -> 4 (+2, expected +2) |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (20000,4500) · keys — · fields — · expect 1 selected` | green: select: (20000,4500) mm at px (1137.6,295.0) on the plan view; picked 'wall-b5cf2d758a3ec1d1-073a404690990868'; selected 0 -> 1 [wall-b5cf2d758a3ec1d1-073a404690990868] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-b5cf2d758a3ec1d1-073a404690990868) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6074. Window-select the whole east bay of the frame, delete it, then undo the delete.

- Starts from: a new Structural project
- Ends with: both bays of the frame standing again after the undo
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(12000,3000) level=\"Level 1\"",
  "op:add column at=(18000,3000) level=\"Level 1\"",
  "op:add column at=(24000,3000) level=\"Level 1\"",
  "op:add beam from=(12000,3000) to=(18000,3000) level=\"Level 1\"",
  "op:add beam from=(18000,3000) to=(24000,3000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(12000,3000) level="Level 1"` | green: op:add column made=column-b8b59f6499925f6e changed= ms=19 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(18000,3000) level="Level 1"` | green: op:add column made=column-c8d88fbeef228680 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(24000,3000) level="Level 1"` | green: op:add column made=column-d0d299e0d7587533 changed= ms=3 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add beam from=(12000,3000) to=(18000,3000) level="Level 1"` | green: op:add beam made=beam-370695b8258d8ad4 changed= ms=4 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(18000,3000) to=(24000,3000) level="Level 1"` | green: op:add beam made=beam-29d0782a10a22b57 changed= ms=36 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active",
  "plan:marquee · picks (17500,4500) (25000,1500) · keys — · fields — · expect 3 selected",
  "ribbon:Modify:Delete · picks — · keys — · fields — · expect Structural Columns -2",
  "qa:Undo · picks — · keys — · fields — · expect Structural Columns +2"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Level 1 active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Level 1 active": the active view is 'Level 1' (expected 'Level 1') |
| `plan:marquee · picks (17500,4500) (25000,1500) · keys — · fields — · expect 3 selected` | green: marquee: window (left to right); drag px (946.6,343.3) -> (1086.2,399.1) on the plan view; selected 0 -> 3 [beam-29d0782a10a22b57,column-c8d88fbeef228680,column-d0d299e0d7587533] \| picks: the plan band pressed these 2 pick(s) as its own process Check "3 selected": 3 selected (beam-29d0782a10a22b57, column-c8d88fbeef228680, column-d0d299e0d7587533) (expected exactly 3) |
| `ribbon:Modify:Delete · picks — · keys — · fields — · expect Structural Columns -2` | green: pressed 'Delete' on Modify's Edit panel (through its fold): the command 'Delete' ran Check "Structural Columns -2": Structural Columns 3 -> 1 (-2, expected -2) |
| `qa:Undo · picks — · keys — · fields — · expect Structural Columns +2` | green: QToolButton pressed; a command ran Check "Structural Columns +2": Structural Columns 1 -> 3 (+2, expected +2) |

### The result

The model holds: Levels 2,Structural Columns 3,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 6075. Scale the 6 m boundary wall up from its west end to 9 m.

- Starts from: a new Architectural project
- Ends with: one wall on Ground from (12000,3000) to (21000,3000)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(12000,3000) to=(18000,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(12000,3000) to=(18000,3000) level=Ground` | green: op:add wall made=wall-c29995782f75cfc7 changed= ms=17 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected",
  "ribbon:Modify:Scale · picks (12000,3000) (18000,3000) (21000,3000) · keys Escape Escape · fields — · expect moved",
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "plan:select · picks (20000,3000) · keys — · fields — · expect 1 selected"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (15000,3000) · keys — · fields — · expect 1 selected` | green: select: (15000,3000) mm at px (1021.7,339.0) on the plan view; picked 'wall-c29995782f75cfc7'; selected 0 -> 1 [wall-c29995782f75cfc7] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-c29995782f75cfc7) (expected exactly 1) |
| `ribbon:Modify:Scale · picks (12000,3000) (18000,3000) (21000,3000) · keys Escape Escape · fields — · expect moved` | green: pressed 'Scale' on Modify's Modify panel (through its fold): the tool 'Scale' stands \| picks: (12000,3000) mm at px (933.7,339.0) on the plan view \| (18000,3000) mm at px (1109.7,339.0) on the plan view \| (21000,3000) mm at px (1197.7,339.0) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Scale -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: wall-c29995782f75cfc7  -> |
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `plan:select · picks (20000,3000) · keys — · fields — · expect 1 selected` | green: select: (20000,3000) mm at px (1124.4,339.0) on the plan view; picked 'wall-c29995782f75cfc7'; selected 0 -> 1 [wall-c29995782f75cfc7] \| picks: the plan band pressed these 1 pick(s) as its own process Check "1 selected": 1 selected (wall-c29995782f75cfc7) (expected exactly 1) |

### The result

The model holds: Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 6076. Join the slab to the wall that stands on it so the slab edge follows the wall.

- Starts from: a new Architectural project
- Ends with: one floor and one wall on Ground, joined
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add floor boundary=(12000,2000),(20000,2000),(20000,7000),(12000,7000) level=Ground",
  "op:add wall from=(12000,6000) to=(20000,6000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(12000,2000),(20000,2000),(20000,7000),(12000,7000) level=Ground` | green: op:add floor made=floor-8fbb86c81b9c2b8e changed= ms=11 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,6000) to=(20000,6000) level=Ground` | green: op:add wall made=wall-74c253294aafb1cb changed= ms=3 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active",
  "ribbon:Modify:Join › Join Geometry · picks (14000,2000) (14000,6000) · keys Escape Escape · fields — · expect moved"
]}
```

| Line | UNION answered |
|---|---|
| `chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect view Ground active` | green: PlanNavBarZoomToFit pressed; a command ran Check "view Ground active": the active view is 'Ground' (expected 'Ground') |
| `ribbon:Modify:Join › Join Geometry · picks (14000,2000) (14000,6000) · keys Escape Escape · fields — · expect moved` | green: pressed 'Join › Join Geometry' on Modify's Geometry panel (through its fold) (through its parent 'Join''s arrow, the row 'Join Geometry'; the press stood 333 ms (the menu stood at 17 ms; its row ran 315 ms; it made 0 child widgets native)): the tool 'Join › Join Geometry' stands \| picks: (14000,2000) mm at px (963.0,368.3) on the plan view \| (14000,6000) mm at px (963.0,251.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Join › Join Geometry -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "moved": 1 element(s) moved: wall-74c253294aafb1cb  -> |

### The result

The model holds: Floors 1,Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
