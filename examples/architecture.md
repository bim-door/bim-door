# UNION examples: Architecture

71 drafting jobs, each the request in plain words, the exact calls an AI sends to UNION, and UNION's answer to each, played green on UNION 1.0.0-beta.2.

## 2001. Draw a 6 m blockwork boundary wall, 1800 high, with a 3 m return at each end.

- Starts from: a new Architectural project
- Ends with: three blockwork walls 1800 high on Ground: a 6 m run with a 3 m return at each end
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground type=\"Block 190 Core-filled\" height=1800",
  "op:add wall from=(6000,0) to=(6000,3000) level=Ground type=\"Block 190 Core-filled\" height=1800",
  "op:add wall from=(0,0) to=(0,3000) level=Ground type=\"Block 190 Core-filled\" height=1800"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground type="Block 190 Core-filled" height=1800` | green: op:add wall made=wall-5171bd3098e1f341 changed= ms=21 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,3000) level=Ground type="Block 190 Core-filled" height=1800` | green: op:add wall made=wall-b55e56108c5343d2 changed=wall-5171bd3098e1f341 ms=7 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(0,0) to=(0,3000) level=Ground type="Block 190 Core-filled" height=1800` | green: op:add wall made=wall-6c5b388247422660 changed=wall-5171bd3098e1f341 ms=7 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2002. Set out a 6 x 4 m site office on Ground: four walls and a slab.

- Starts from: a new Architectural project
- Ends with: four walls and a concrete slab with tile finish on Ground, 6 x 4 m
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0) (6000,0) (6000,4000) (0,4000) level=Ground type=\"Concrete Slab 200 + Tile\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-2313ed525eab9400 changed= ms=441 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-a1fb734cd609e1cc changed=wall-2313ed525eab9400 ms=5 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-7b95b98699b8780e changed=wall-a1fb734cd609e1cc ms=5 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-2ff611c843ddc4fa changed=wall-7b95b98699b8780e,wall-2313ed525eab9400 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (6000,0) (6000,4000) (0,4000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-b0cc1e2fe4688b48 changed= ms=9 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2003. Click out the walls of a 5 x 4 m store room corner to corner, close the loop and hang a door.

- Starts from: a new Architectural project
- Ends with: four walls closed on Ground with a door in the south wall, 5 x 4 m
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:Wall · picks (0,0) (5000,0) (5000,4000) (0,4000) (0,0) · keys Escape Escape · fields — · expect Walls +4",
  "ribbon:Architecture:Door · picks (1500,0) · keys Escape Escape · fields — · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Wall · picks (0,0) (5000,0) (5000,4000) (0,4000) (0,0) · keys Escape Escape · fields — · expect Walls +4` | green: pressed 'Wall: Architectural' on Architecture's Build panel: the command 'Wall: Architectural' ran; status 'Click to start the wall' ('Wall' is the word of Architecture's Build panel button 'Wall: Architectural') \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (5000,0) mm at px (794.7,427.0) on the plan view \| (5000,4000) mm at px (794.7,309.7) on the plan view \| (0,4000) mm at px (648.0,309.7) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +4": Walls 0 -> 4 (+4, expected +4) |
| `ribbon:Architecture:Door · picks (1500,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (1500,0) mm at px (692.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |

### The result

The model holds: Doors 1,Levels 3,Openings 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2004. Draw an 8 x 5 m plant room from two corners, then put a double door in the south wall and a window in the north.

- Starts from: a new Architectural project
- Ends with: an 8 x 5 m rectangle of four walls on Ground with a double door in the south wall and a window in the north wall
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:Wall · picks (0,0) (8000,5000) · keys Escape Escape · fields Options Strip: Draw=Rectangle · expect Walls +4",
  "ribbon:Architecture:Door · picks (2500,0) · keys Escape Escape · fields Options Strip: Width=1800 · expect Doors +1",
  "ribbon:Architecture:Window · picks (5500,5000) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Wall · picks (0,0) (8000,5000) · keys Escape Escape · fields Options Strip: Draw=Rectangle · expect Walls +4` | green: pressed 'Wall: Architectural' on Architecture's Build panel: the command 'Wall: Architectural' ran; status 'Click to start the wall' ('Wall' is the word of Architecture's Build panel button 'Wall: Architectural') \| fields: Draw=Rectangle set \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,5000) mm at px (882.7,280.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Walls +4": Walls 0 -> 4 (+4, expected +4) |
| `ribbon:Architecture:Door · picks (2500,0) · keys Escape Escape · fields Options Strip: Width=1800 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=1800 reads '1800 mm' \| picks: (2500,0) mm at px (721.3,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (5500,5000) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm' \| picks: (5500,5000) mm at px (809.3,280.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |

### The result

The model holds: Doors 1,Levels 3,Openings 2,Walls 4,Windows 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2005. Draw a 10 x 6 m house outline in brick veneer with a 110 stud partition down the middle.

- Starts from: a new Architectural project
- Ends with: four brick veneer external walls and one interior stud partition on Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(10000,0) to=(10000,6000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(10000,6000) to=(0,6000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(0,6000) to=(0,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(5000,0) to=(5000,6000) level=Ground type=\"Interior Stud 110\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-d502ceac74bbe749 changed= ms=22 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,6000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-1025d38ed80f67af changed=wall-d502ceac74bbe749 ms=6 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,6000) to=(0,6000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-da2b099e74000771 changed=wall-1025d38ed80f67af ms=6 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-ffa27c3191924711 changed=wall-d502ceac74bbe749,wall-da2b099e74000771 ms=8 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(5000,0) to=(5000,6000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-a92b27c163092f3a changed= ms=9 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 5,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2006. Draw three walls on Ground: a 2400 screen wall, a wall that runs up to Level 1, and a 3600 high wall.

- Starts from: a new Architectural project
- Ends with: three walls on Ground standing 2400, 3000 (to Level 1) and 3600 high
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(4000,0) level=Ground height=2400",
  "op:add wall from=(0,3000) to=(4000,3000) level=Ground top=\"Level 1\"",
  "op:add wall from=(0,6000) to=(4000,6000) level=Ground height=3600 type=\"Concrete 200 + Render\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(4000,0) level=Ground height=2400` | green: op:add wall made=wall-788a086f61b791fc changed= ms=538 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(0,3000) to=(4000,3000) level=Ground top="Level 1"` | green: op:add wall made=wall-d9ae2d83aa85bff8 changed= ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(4000,6000) level=Ground height=3600 type="Concrete 200 + Render"` | green: op:add wall made=wall-7ec6519c1fbcad9a changed= ms=9 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2007. Draw a curved feature wall, 6 m chord with a 2 m rise, and a straight return wall at each end.

- Starts from: a new Architectural project
- Ends with: one curved wall through three points with a 3 m straight return at each end on Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:Wall · picks (0,0) (6000,0) (3000,2000) · keys Escape Escape · fields Options Strip: Draw=Start-End-Radius Arc · expect Walls +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Wall · picks (0,0) (6000,0) (3000,2000) · keys Escape Escape · fields Options Strip: Draw=Start-End-Radius Arc · expect Walls +1` | green: pressed 'Wall: Architectural' on Architecture's Build panel: the command 'Wall: Architectural' ran; status 'Click to start the wall' ('Wall' is the word of Architecture's Build panel button 'Wall: Architectural') \| fields: Draw=Start-End-Radius Arc set \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (6000,0) mm at px (824.0,427.0) on the plan view \| (3000,2000) mm at px (736.0,368.3) on the plan view \| presses to the tool 3, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(0,-3000) level=Ground",
  "op:add wall from=(6000,0) to=(6000,-3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(0,-3000) level=Ground` | green: op:add wall made=wall-fa4918f4c7a8e2a4 changed=wall-a5e08124666912f4 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,-3000) level=Ground` | green: op:add wall made=wall-89da4238483a0c1a changed=wall-a5e08124666912f4 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2008. Add a curved blockwork garden wall, 8 m between its ends, passing through a point 2.5 m out.

- Starts from: a new Architectural project
- Ends with: one curved blockwork wall 1200 high on Ground and a straight wall of the same type closing its ends
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) through=(4000,-2500) level=Ground type=\"Block 190 Core-filled\" height=1200",
  "op:add wall from=(8000,0) to=(0,0) level=Ground type=\"Block 190 Core-filled\" height=1200"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) through=(4000,-2500) level=Ground type="Block 190 Core-filled" height=1200` | green: op:add wall made=wall-b0924aa461235d38 changed= ms=532 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(0,0) level=Ground type="Block 190 Core-filled" height=1200` | green: op:add wall made=wall-ba9c57d4a119d6c8 changed=wall-b0924aa461235d38 ms=7 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2009. Draw a hexagonal garden pavilion 4 m across the corners, with a slab and a pitched roof.

- Starts from: a new Architectural project
- Ends with: six walls in a hexagon, a slab and a roof over them on Ground and Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:Wall · picks (6000,4000) (8000,4000) · keys Escape Escape · fields Options Strip: Draw=Inscribed Polygon; Sides=6 · expect Walls +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Wall · picks (6000,4000) (8000,4000) · keys Escape Escape · fields Options Strip: Draw=Inscribed Polygon; Sides=6 · expect Walls +6` | green: pressed 'Wall: Architectural' on Architecture's Build panel: the command 'Wall: Architectural' ran; status 'Click to start the wall' ('Wall' is the word of Architecture's Build panel button 'Wall: Architectural') \| fields: Draw=Inscribed Polygon set; Sides=6 reads '6.00' \| picks: (6000,4000) mm at px (824.0,309.7) on the plan view \| (8000,4000) mm at px (882.7,309.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Walls +6": Walls 0 -> 6 (+6, expected +6) |

```json
ops_run {"lines":[
  "op:add floor boundary=(8000,4000) (7000,5732) (5000,5732) (4000,4000) (5000,2268) (7000,2268) level=Ground",
  "op:add roof boundary=(8000,4000) (7000,5732) (5000,5732) (4000,4000) (5000,2268) (7000,2268) level=\"Level 1\" slope=20"
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(8000,4000) (7000,5732) (5000,5732) (4000,4000) (5000,2268) (7000,2268) level=Ground` | green: op:add floor made=floor-43f8e9f1e93f47e4 changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add roof boundary=(8000,4000) (7000,5732) (5000,5732) (4000,4000) (5000,2268) (7000,2268) level="Level 1" slope=20` | green: op:add roof made=roof-1bcb13777f1255e3 changed= ms=3 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Roofs 1,Walls 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2010. Draw the walls of an L-shaped house, 12 x 8 m overall with a 6 x 4 m corner cut out, and slab it.

- Starts from: a new Architectural project
- Ends with: six closed walls forming an L on Ground with a floor slab inside them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:Wall · picks (0,0) (12000,0) (12000,4000) (6000,4000) (6000,8000) (0,8000) (0,0) · keys Escape Escape · fields — · expect Walls +6"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Wall · picks (0,0) (12000,0) (12000,4000) (6000,4000) (6000,8000) (0,8000) (0,0) · keys Escape Escape · fields — · expect Walls +6` | green: pressed 'Wall: Architectural' on Architecture's Build panel: the command 'Wall: Architectural' ran; status 'Click to start the wall' ('Wall' is the word of Architecture's Build panel button 'Wall: Architectural') \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (12000,0) mm at px (1000.0,427.0) on the plan view \| (12000,4000) mm at px (1000.0,309.7) on the plan view \| (6000,4000) mm at px (824.0,309.7) on the plan view \| (6000,8000) mm at px (824.0,192.3) on the plan view \| (0,8000) mm at px (648.0,192.3) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 7, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +6": Walls 0 -> 6 (+6, expected +6) |

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0) (12000,0) (12000,4000) (6000,4000) (6000,8000) (0,8000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0) (12000,0) (12000,4000) (6000,4000) (6000,8000) (0,8000) level=Ground` | green: op:add floor made=floor-5048783422c2fc4e changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Walls 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2011. Pour a 15 x 10 m warehouse slab and stand precast walls round it.

- Starts from: a new Architectural project
- Ends with: a 15 x 10 m waffle pod slab with four precast walls round it on Ground
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0) (15000,0) (15000,10000) (0,10000) level=Ground type=\"Waffle Pod Slab 225\"",
  "op:add wall from=(0,0) to=(15000,0) level=Ground height=5400 type=\"Precast 150 + Lining\"",
  "op:add wall from=(15000,0) to=(15000,10000) level=Ground height=5400 type=\"Precast 150 + Lining\"",
  "op:add wall from=(15000,10000) to=(0,10000) level=Ground height=5400 type=\"Precast 150 + Lining\"",
  "op:add wall from=(0,10000) to=(0,0) level=Ground height=5400 type=\"Precast 150 + Lining\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0) (15000,0) (15000,10000) (0,10000) level=Ground type="Waffle Pod Slab 225"` | green: op:add floor made=floor-e54838eacf6a9514 changed= ms=499 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add wall from=(0,0) to=(15000,0) level=Ground height=5400 type="Precast 150 + Lining"` | green: op:add wall made=wall-3209d0d0c16acbcc changed= ms=9 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(15000,0) to=(15000,10000) level=Ground height=5400 type="Precast 150 + Lining"` | green: op:add wall made=wall-55f2d97c10c88994 changed=wall-3209d0d0c16acbcc ms=5 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(15000,10000) to=(0,10000) level=Ground height=5400 type="Precast 150 + Lining"` | green: op:add wall made=wall-a19c2fa44765f964 changed=wall-55f2d97c10c88994 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,10000) to=(0,0) level=Ground height=5400 type="Precast 150 + Lining"` | green: op:add wall made=wall-e76126b178501bbd changed=wall-a19c2fa44765f964,wall-3209d0d0c16acbcc ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2012. Sketch a floor slab over the walls of a 7 x 5 m classroom.

- Starts from: a new Architectural project
- Ends with: four walls on Ground and a floor sketched over them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(7000,0) level=Ground",
  "op:add wall from=(7000,0) to=(7000,5000) level=Ground",
  "op:add wall from=(7000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(7000,0) level=Ground` | green: op:add wall made=wall-53ed5520ba5a2473 changed= ms=13 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(7000,0) to=(7000,5000) level=Ground` | green: op:add wall made=wall-6a8c83d13ce226cb changed=wall-53ed5520ba5a2473 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(7000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-1e46e6b026fe5ef5 changed=wall-6a8c83d13ce226cb ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-f3dc908c1a79973c changed=wall-1e46e6b026fe5ef5,wall-53ed5520ba5a2473 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Floor: Architectural · picks (0,0) (7000,0) (7000,5000) (0,5000) (0,0) · keys — · fields — · expect nothing selected",
  "contextual:Finish · picks — · keys — · fields — · expect Floors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Floor: Architectural · picks (0,0) (7000,0) (7000,5000) (0,5000) (0,0) · keys — · fields — · expect nothing selected` | green: pressed 'Floor: Architectural' on Architecture's Build panel: the command 'Floor: Architectural' ran; status 'Sketch the floor boundary, then Finish' \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (7000,0) mm at px (853.3,427.0) on the plan view \| (7000,5000) mm at px (853.3,280.3) on the plan view \| (0,5000) mm at px (648.0,280.3) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged Check "nothing selected": 0 selected |
| `contextual:Finish · picks — · keys — · fields — · expect Floors +1` | green: contextual 'Finish' on 'Modify \| Create Floor Boundary': pressed 'Finish' on Modify \| Create Floor Boundary's Mode panel: the command 'Finish' ran Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2013. Lay a tiled wet-area slab in the 3 x 3 m bathroom and a carpet slab in the 5 x 3 m bedroom next to it.

- Starts from: a new Architectural project
- Ends with: walls round an 8 x 3 m block split by a stud partition, with a tiled wet-area slab in the bathroom and a carpet slab in the bedroom
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,3000) level=Ground",
  "op:add wall from=(8000,3000) to=(0,3000) level=Ground",
  "op:add wall from=(0,3000) to=(0,0) level=Ground",
  "op:add wall from=(5000,0) to=(5000,3000) level=Ground type=\"Interior Stud 110\"",
  "op:add floor boundary=(0,0) (5000,0) (5000,3000) (0,3000) level=Ground type=\"Slab Carpet 200\"",
  "op:add floor boundary=(5000,0) (8000,0) (8000,3000) (5000,3000) level=Ground type=\"Slab Tiled Wet Area 200\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-defb781f9540feda changed= ms=16 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,3000) level=Ground` | green: op:add wall made=wall-b0adca5c9b23f411 changed=wall-defb781f9540feda ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,3000) to=(0,3000) level=Ground` | green: op:add wall made=wall-c333b9ca689418e5 changed=wall-b0adca5c9b23f411 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,3000) to=(0,0) level=Ground` | green: op:add wall made=wall-9ef77ca6aacc727a changed=wall-c333b9ca689418e5,wall-defb781f9540feda ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(5000,0) to=(5000,3000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-bb61af9d53cf216e changed= ms=10 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add floor boundary=(0,0) (5000,0) (5000,3000) (0,3000) level=Ground type="Slab Carpet 200"` | green: op:add floor made=floor-9010f46aa603bb08 changed= ms=7 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add floor boundary=(5000,0) (8000,0) (8000,3000) (5000,3000) level=Ground type="Slab Tiled Wet Area 200"` | green: op:add floor made=floor-cf263a555bde73a6 changed= ms=7 Check "Floors +1": Floors 1 -> 2 (+1, expected +1) |

### The result

The model holds: Floors 2,Levels 3,Walls 5,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2014. Build the ground floor of an 8 x 6 m house with its slab, then add a timber first floor and the walls of the upper level.

- Starts from: a new Architectural project
- Ends with: four walls and a slab on Ground, a timber joist floor on Level 1 and four more walls on Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0) (8000,0) (8000,6000) (0,6000) level=Ground type=\"Concrete Slab 200 + Tile\"",
  "op:add floor boundary=(0,0) (8000,0) (8000,6000) (0,6000) level=\"Level 1\" type=\"Timber Joist and Ply 240\"",
  "op:add wall from=(0,0) to=(8000,0) level=\"Level 1\" top=Roof",
  "op:add wall from=(8000,0) to=(8000,6000) level=\"Level 1\" top=Roof",
  "op:add wall from=(8000,6000) to=(0,6000) level=\"Level 1\" top=Roof",
  "op:add wall from=(0,6000) to=(0,0) level=\"Level 1\" top=Roof"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-e3be8aff31978bea changed= ms=16 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-baf91485e82b6e71 changed=wall-e3be8aff31978bea ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-ea8cd938547b256d changed=wall-baf91485e82b6e71 ms=33 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-c7e1a9609f47aa39 changed=wall-e3be8aff31978bea,wall-ea8cd938547b256d ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (8000,0) (8000,6000) (0,6000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-9550df1b66dd766d changed= ms=43 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add floor boundary=(0,0) (8000,0) (8000,6000) (0,6000) level="Level 1" type="Timber Joist and Ply 240"` | green: op:add floor made=floor-1b9539033792c968 changed= ms=7 Check "Floors +1": Floors 1 -> 2 (+1, expected +1) |
| `op:add wall from=(0,0) to=(8000,0) level="Level 1" top=Roof` | green: op:add wall made=wall-b3382114c4b3eb7e changed= ms=2 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level="Level 1" top=Roof` | green: op:add wall made=wall-e20d715e3d0594d9 changed=wall-b3382114c4b3eb7e ms=3 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level="Level 1" top=Roof` | green: op:add wall made=wall-55d64dbb91e23550 changed=wall-e20d715e3d0594d9 ms=4 Check "Walls +1": Walls 6 -> 7 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level="Level 1" top=Roof` | green: op:add wall made=wall-4196b034da416259 changed=wall-b3382114c4b3eb7e,wall-55d64dbb91e23550 ms=3 Check "Walls +1": Walls 7 -> 8 (+1, expected +1) |

### The result

The model holds: Floors 2,Levels 3,Walls 8,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2015. Put a 2700 high ceiling in the 6 x 4 m office by clicking inside its walls.

- Starts from: a new Architectural project
- Ends with: four walls on Ground with a ceiling 2700 above Ground filling the room
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add ceiling at=(3000,2000) level=Ground height=2700"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-02ea1dae594c3655 changed= ms=14 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-c8a1bb5a1e2088fd changed=wall-02ea1dae594c3655 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-8d821082a0fcf113 changed=wall-c8a1bb5a1e2088fd ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-35e7c6f170664fc1 changed=wall-02ea1dae594c3655,wall-8d821082a0fcf113 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add ceiling at=(3000,2000) level=Ground height=2700` | green: op:add ceiling made=ceiling-bd3843f96b73fbb6 changed= ms=6 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Ceilings 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2016. Draw a plasterboard-on-grid ceiling over a 12 m long, 1800 wide corridor at 2400.

- Starts from: a new Architectural project
- Ends with: two corridor walls and a plasterboard on grid ceiling 2400 above Ground between them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground",
  "op:add wall from=(0,1800) to=(12000,1800) level=Ground",
  "op:add ceiling boundary=(0,0) (12000,0) (12000,1800) (0,1800) level=Ground height=2400 type=\"Plasterboard on Grid\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground` | green: op:add wall made=wall-a6289c27499267fc changed= ms=14 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(0,1800) to=(12000,1800) level=Ground` | green: op:add wall made=wall-c323faaa23e71f15 changed= ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add ceiling boundary=(0,0) (12000,0) (12000,1800) (0,1800) level=Ground height=2400 type="Plasterboard on Grid"` | green: op:add ceiling made=ceiling-8bc6675b8bcdc965 changed= ms=6 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Ceilings 1,Levels 3,Walls 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2017. Ceiling the reception at 2700 and the meeting room at 2400 with a 600 x 600 grid, by clicking in each room.

- Starts from: a new Architectural project
- Ends with: two rooms side by side on Ground, one with a 2700 ceiling and one with a 2400 ceiling on a 600 x 600 grid
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground",
  "op:add wall from=(9000,0) to=(9000,4000) level=Ground",
  "op:add wall from=(9000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add wall from=(5000,0) to=(5000,4000) level=Ground type=\"Interior Stud 110\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground` | green: op:add wall made=wall-fce1291e31e7c920 changed= ms=471 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,4000) level=Ground` | green: op:add wall made=wall-4186196150f1ba6f changed=wall-fce1291e31e7c920 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-51f82cb0828e9523 changed=wall-4186196150f1ba6f ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-e4b5ce4295cecbd4 changed=wall-51f82cb0828e9523,wall-fce1291e31e7c920 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(5000,0) to=(5000,4000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-541ce1ef48f7f9f6 changed= ms=8 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:draw-ceiling · picks (2500,2000) · keys Escape Escape · fields Options Strip: Height Offset From Level=2700 · expect Ceilings +1",
  "ribbon:Architecture:draw-ceiling · picks (7000,2000) · keys Escape Escape · fields Options Strip: Height Offset From Level=2400; Grid=600x600 · expect Ceilings +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:draw-ceiling · picks (2500,2000) · keys Escape Escape · fields Options Strip: Height Offset From Level=2700 · expect Ceilings +1` | green: pressed 'draw-ceiling' on Architecture's Build panel: the tool 'draw-ceiling' stands \| fields: Height Offset From Level=2700 reads '2700 mm' \| picks: (2500,2000) mm at px (721.3,368.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool draw-ceiling -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:draw-ceiling · picks (7000,2000) · keys Escape Escape · fields Options Strip: Height Offset From Level=2400; Grid=600x600 · expect Ceilings +1` | green: pressed 'draw-ceiling' on Architecture's Build panel: the tool 'draw-ceiling' stands \| fields: Height Offset From Level=2400 reads '2400 mm'; Grid=600x600 reads '600x600' \| picks: (7000,2000) mm at px (853.3,368.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool draw-ceiling -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ceilings +1": Ceilings 1 -> 2 (+1, expected +1) |

### The result

The model holds: Ceilings 2,Levels 3,Walls 5,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2018. Put an insulated metal deck flat roof over a 10 x 6 m store.

- Starts from: a new Architectural project
- Ends with: four walls on Ground with a flat metal deck insulated roof at Level 1 over them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground",
  "op:add wall from=(10000,0) to=(10000,6000) level=Ground",
  "op:add wall from=(10000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add roof boundary=(0,0) (10000,0) (10000,6000) (0,6000) level=\"Level 1\" slope=0 type=\"Metal Deck Insulated 100\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground` | green: op:add wall made=wall-23c47f43db9a3b91 changed= ms=20 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,6000) level=Ground` | green: op:add wall made=wall-efd49cda68e8a566 changed=wall-23c47f43db9a3b91 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-6c4e3c6caffc96ef changed=wall-efd49cda68e8a566 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-e8083c059c0a99f1 changed=wall-6c4e3c6caffc96ef,wall-23c47f43db9a3b91 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add roof boundary=(0,0) (10000,0) (10000,6000) (0,6000) level="Level 1" slope=0 type="Metal Deck Insulated 100"` | green: op:add roof made=roof-5d3199363cea12e2 changed= ms=6 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2019. Roof the brick house with a 25 degree hip roof in concrete tiles on battens.

- Starts from: a new Architectural project
- Ends with: four brick veneer walls on Ground with a 25 degree concrete tile hip roof over them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(12000,0) to=(12000,8000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(12000,8000) to=(0,8000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(0,8000) to=(0,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add roof boundary=(-400,-400) (12400,-400) (12400,8400) (-400,8400) level=\"Level 1\" slope=25 type=\"Concrete Tile Battens 140\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-e7630dd1d241a237 changed= ms=20 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,8000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-c72d1f82ef31f3f4 changed=wall-e7630dd1d241a237 ms=5 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(0,8000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-f33fb3409ef1739d changed=wall-c72d1f82ef31f3f4 ms=5 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-72c4b5812250d770 changed=wall-f33fb3409ef1739d,wall-e7630dd1d241a237 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add roof boundary=(-400,-400) (12400,-400) (12400,8400) (-400,8400) level="Level 1" slope=25 type="Concrete Tile Battens 140"` | green: op:add roof made=roof-e59080fcc9112355 changed= ms=6 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2020. Roof the 8 x 5 m cottage with a gable roof: slope the long sides, leave the gable ends upright, 400 overhang, sitting on the wall tops.

- Starts from: a new Architectural project
- Ends with: four walls 2700 high on Ground, an Eaves level at 2500, and a gable roof picked from the walls on it with a 400 overhang, sloping over the long walls
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground height=2700",
  "op:add wall from=(8000,0) to=(8000,5000) level=Ground height=2700",
  "op:add wall from=(8000,5000) to=(0,5000) level=Ground height=2700",
  "op:add wall from=(0,5000) to=(0,0) level=Ground height=2700",
  "op:add level elevation=2500 name=\"Eaves\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground height=2700` | green: op:add wall made=wall-f3f37c75a20237fc changed= ms=288 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,5000) level=Ground height=2700` | green: op:add wall made=wall-90dc51f439416237 changed=wall-f3f37c75a20237fc ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,5000) to=(0,5000) level=Ground height=2700` | green: op:add wall made=wall-ae2d8801bf9a0b96 changed=wall-90dc51f439416237 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground height=2700` | green: op:add wall made=wall-5b74a63fc837af4c changed=wall-ae2d8801bf9a0b96,wall-f3f37c75a20237fc ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add level elevation=2500 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=2 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed",
  "ribbon:Architecture:Roof · picks (4000,0) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=400 · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (8000,2500) · keys — · fields Options Strip: Defines Slope=no · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (4000,5000) · keys — · fields Options Strip: Defines Slope=yes · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (0,2500) · keys Return · fields Options Strip: Defines Slope=no · expect Roofs +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed` | green: pressed 'Plan Views › Floor Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Floor Plan'; the press stood 521 ms (the menu stood at 343 ms; its row ran 178 ms; the window's first paint at 178 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1092 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player \| inside the modal 'New Plan' \| fields: table 'Levels' row 'Eaves' pressed, reads New 'yes' \| keys: Return (no tool, dialog 'New Plan' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window; 'Plan Views › Floor Plan' opens no dialog (its door is an action), so the step's Return went to the viewport |
| `ribbon:Architecture:Roof · picks (4000,0) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=400 · expect nothing selected` | green: pressed 'Roof' on Architecture's Build panel: the tool 'Roof' stands \| fields: Draw=Pick Walls set; Defines Slope=yes reads yes; Overhang=400 reads '400 mm' \| picks: (4000,0) mm at px (765.3,427.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (8000,2500) · keys — · fields Options Strip: Defines Slope=no · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=no reads no \| picks: (8000,2500) mm at px (882.7,353.7) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (4000,5000) · keys — · fields Options Strip: Defines Slope=yes · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=yes reads yes \| picks: (4000,5000) mm at px (765.3,280.3) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (0,2500) · keys Return · fields Options Strip: Defines Slope=no · expect Roofs +1` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=no reads no \| picks: (0,2500) mm at px (648.0,353.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Return (tool Roof -> no tool) Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 4,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2021. Give the 6 x 4 m studio a single-pitch roof that falls to the south wall, drawn on an eaves plan.

- Starts from: a new Architectural project
- Ends with: four walls 2700 high on Ground, an Eaves level at 2500, and a single-pitch roof picked from the walls, sloping only over the south wall
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground height=2700",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground height=2700",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground height=2700",
  "op:add wall from=(0,4000) to=(0,0) level=Ground height=2700",
  "op:add level elevation=2500 name=\"Eaves\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground height=2700` | green: op:add wall made=wall-01967019e899e486 changed= ms=99 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground height=2700` | green: op:add wall made=wall-020fa0e0c23ed3fa changed=wall-01967019e899e486 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground height=2700` | green: op:add wall made=wall-fa5e374c8ecbaf48 changed=wall-020fa0e0c23ed3fa ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground height=2700` | green: op:add wall made=wall-ac086e69adaa6578 changed=wall-fa5e374c8ecbaf48,wall-01967019e899e486 ms=230 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add level elevation=2500 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=2 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed",
  "ribbon:Architecture:Roof · picks (3000,0) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=300 · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (6000,2000) · keys — · fields Options Strip: Defines Slope=no · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (3000,4000) · keys — · fields Options Strip: Defines Slope=no · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (0,2000) · keys Return · fields Options Strip: Defines Slope=no · expect Roofs +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed` | green: pressed 'Plan Views › Floor Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Floor Plan'; the press stood 443 ms (the menu stood at 380 ms; its row ran 63 ms; the window's first paint at 63 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1287 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player \| inside the modal 'New Plan' \| fields: table 'Levels' row 'Eaves' pressed, reads New 'yes' \| keys: Return (no tool, dialog 'New Plan' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window; 'Plan Views › Floor Plan' opens no dialog (its door is an action), so the step's Return went to the viewport |
| `ribbon:Architecture:Roof · picks (3000,0) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=300 · expect nothing selected` | green: pressed 'Roof' on Architecture's Build panel: the tool 'Roof' stands \| fields: Draw=Pick Walls set; Defines Slope=yes reads yes; Overhang=300 reads '300 mm' \| picks: (3000,0) mm at px (736.0,427.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (6000,2000) · keys — · fields Options Strip: Defines Slope=no · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=no reads no \| picks: (6000,2000) mm at px (824.0,368.3) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (3000,4000) · keys — · fields Options Strip: Defines Slope=no · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=no reads no \| picks: (3000,4000) mm at px (736.0,309.7) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (0,2000) · keys Return · fields Options Strip: Defines Slope=no · expect Roofs +1` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=no reads no \| picks: (0,2000) mm at px (648.0,368.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Return (tool Roof -> no tool) Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 4,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2022. Sketch the roof of the 9 x 6 m machinery shed from its outline on an eaves plan and finish it.

- Starts from: a new Architectural project
- Ends with: four walls 2700 high on Ground, an Eaves level at 2700 and a roof sketched over their outline at 9 x 6 m
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground height=2700",
  "op:add wall from=(9000,0) to=(9000,6000) level=Ground height=2700",
  "op:add wall from=(9000,6000) to=(0,6000) level=Ground height=2700",
  "op:add wall from=(0,6000) to=(0,0) level=Ground height=2700",
  "op:add level elevation=2700 name=\"Eaves\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground height=2700` | green: op:add wall made=wall-1f11bd99169d79aa changed= ms=18 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level=Ground height=2700` | green: op:add wall made=wall-8d6759a124a64586 changed=wall-1f11bd99169d79aa ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level=Ground height=2700` | green: op:add wall made=wall-ea615d70002c82f0 changed=wall-8d6759a124a64586 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground height=2700` | green: op:add wall made=wall-b9cbf24fc7bac771 changed=wall-ea615d70002c82f0,wall-1f11bd99169d79aa ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add level elevation=2700 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=2 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed",
  "ribbon:Architecture:Roof · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys — · fields — · expect nothing selected",
  "contextual:Finish · picks — · keys — · fields — · expect Roofs +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed` | green: pressed 'Plan Views › Floor Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Floor Plan'; the press stood 590 ms (the menu stood at 372 ms; its row ran 218 ms; the window's first paint at 218 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1308 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player \| inside the modal 'New Plan' \| fields: table 'Levels' row 'Eaves' pressed, reads New 'yes' \| keys: Return (no tool, dialog 'New Plan' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window; 'Plan Views › Floor Plan' opens no dialog (its door is an action), so the step's Return went to the viewport |
| `ribbon:Architecture:Roof · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys — · fields — · expect nothing selected` | green: pressed 'Roof' on Architecture's Build panel: the tool 'Roof' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (9000,0) mm at px (912.0,427.0) on the plan view \| (9000,6000) mm at px (912.0,251.0) on the plan view \| (0,6000) mm at px (648.0,251.0) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged Check "nothing selected": 0 selected |
| `contextual:Finish · picks — · keys — · fields — · expect Roofs +1` | green: contextual 'Finish' on 'Modify \| Create Roof Footprint': pressed 'Finish' on Modify \| Create Roof Footprint's Mode panel: the command 'Finish' ran Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 4,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2023. Roof the 8 x 5 m community room flat with an extensive green roof, 300 overhang, and run a fascia round all four edges.

- Starts from: a new Architectural project
- Ends with: four walls 2700 high on Ground, a flat extensive green roof on an Eaves level at 2700 and a fascia on each of its four edges
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground height=2700",
  "op:add wall from=(8000,0) to=(8000,5000) level=Ground height=2700",
  "op:add wall from=(8000,5000) to=(0,5000) level=Ground height=2700",
  "op:add wall from=(0,5000) to=(0,0) level=Ground height=2700",
  "op:add level elevation=2700 name=\"Eaves\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground height=2700` | green: op:add wall made=wall-8cb18da2cbdaf899 changed= ms=16 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,5000) level=Ground height=2700` | green: op:add wall made=wall-46e3214e5bdd6534 changed=wall-8cb18da2cbdaf899 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,5000) to=(0,5000) level=Ground height=2700` | green: op:add wall made=wall-57c6bd6ef6b03ed5 changed=wall-46e3214e5bdd6534 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground height=2700` | green: op:add wall made=wall-996396c6dc1f585a changed=wall-57c6bd6ef6b03ed5,wall-8cb18da2cbdaf899 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add level elevation=2700 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=6 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed` | green: pressed 'Plan Views › Floor Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Floor Plan'; the press stood 591 ms (the menu stood at 372 ms; its row ran 219 ms; the window's first paint at 219 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1224 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player \| inside the modal 'New Plan' \| fields: table 'Levels' row 'Eaves' pressed, reads New 'yes' \| keys: Return (no tool, dialog 'New Plan' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window; 'Plan Views › Floor Plan' opens no dialog (its door is an action), so the step's Return went to the viewport |

```json
ops_run {"lines":[
  "op:add roof boundary=(-300,-300) (8300,-300) (8300,5300) (-300,5300) level=Eaves slope=0 type=\"Green Extensive 150\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add roof boundary=(-300,-300) (8300,-300) (8300,5300) (-300,5300) level=Eaves slope=0 type="Green Extensive 150"` | green: op:add roof made=roof-a4f652d18169383b changed= ms=5 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Roof: Fascia · picks (4000,-300) · keys Escape Escape · fields — · expect Fascias +1",
  "ribbon:Architecture:Roof: Fascia · picks (8300,2500) · keys Escape Escape · fields — · expect Fascias +1",
  "ribbon:Architecture:Roof: Fascia · picks (4000,5300) · keys Escape Escape · fields — · expect Fascias +1",
  "ribbon:Architecture:Roof: Fascia · picks (-300,2500) · keys Escape Escape · fields — · expect Fascias +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Roof: Fascia · picks (4000,-300) · keys Escape Escape · fields — · expect Fascias +1` | green: pressed 'Roof: Fascia' on Architecture's Build panel: the tool 'Roof: Fascia' stands \| picks: (4000,-300) mm at px (765.3,435.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Roof: Fascia -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fascias +1": Fascias 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Roof: Fascia · picks (8300,2500) · keys Escape Escape · fields — · expect Fascias +1` | green: pressed 'Roof: Fascia' on Architecture's Build panel: the tool 'Roof: Fascia' stands \| picks: (8300,2500) mm at px (891.5,353.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Roof: Fascia -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fascias +1": Fascias 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Roof: Fascia · picks (4000,5300) · keys Escape Escape · fields — · expect Fascias +1` | green: pressed 'Roof: Fascia' on Architecture's Build panel: the tool 'Roof: Fascia' stands \| picks: (4000,5300) mm at px (765.3,271.5) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Roof: Fascia -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fascias +1": Fascias 2 -> 3 (+1, expected +1) |
| `ribbon:Architecture:Roof: Fascia · picks (-300,2500) · keys Escape Escape · fields — · expect Fascias +1` | green: pressed 'Roof: Fascia' on Architecture's Build panel: the tool 'Roof: Fascia' stands \| picks: (-300,2500) mm at px (639.2,353.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Roof: Fascia -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fascias +1": Fascias 3 -> 4 (+1, expected +1) |

### The result

The model holds: Fascias 4,Levels 4,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2024. Roof the 10 x 6 m house with a 30 degree hip roof and put a fascia and a gutter on its south eave.

- Starts from: a new Architectural project
- Ends with: four walls on Ground, a 30 degree hip roof on an Eaves level at 2700 with a 400 overhang, and a fascia and a gutter along its south eave
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground height=2700",
  "op:add wall from=(10000,0) to=(10000,6000) level=Ground height=2700",
  "op:add wall from=(10000,6000) to=(0,6000) level=Ground height=2700",
  "op:add wall from=(0,6000) to=(0,0) level=Ground height=2700",
  "op:add level elevation=2700 name=\"Eaves\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground height=2700` | green: op:add wall made=wall-b33d66566bb5c1a6 changed= ms=448 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,6000) level=Ground height=2700` | green: op:add wall made=wall-7447e4962ff4aa8e changed=wall-b33d66566bb5c1a6 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,6000) to=(0,6000) level=Ground height=2700` | green: op:add wall made=wall-fad5c5f979f92fd5 changed=wall-7447e4962ff4aa8e ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground height=2700` | green: op:add wall made=wall-8ebfa6d3e48bc309 changed=wall-fad5c5f979f92fd5,wall-b33d66566bb5c1a6 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add level elevation=2700 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=2 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed` | green: pressed 'Plan Views › Floor Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Floor Plan'; the press stood 461 ms (the menu stood at 348 ms; its row ran 113 ms; the window's first paint at 113 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1124 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player \| inside the modal 'New Plan' \| fields: table 'Levels' row 'Eaves' pressed, reads New 'yes' \| keys: Return (no tool, dialog 'New Plan' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window; 'Plan Views › Floor Plan' opens no dialog (its door is an action), so the step's Return went to the viewport |

```json
ops_run {"lines":[
  "op:add roof boundary=(-400,-400) (10400,-400) (10400,6400) (-400,6400) level=Eaves slope=30"
]}
```

| Line | UNION answered |
|---|---|
| `op:add roof boundary=(-400,-400) (10400,-400) (10400,6400) (-400,6400) level=Eaves slope=30` | green: op:add roof made=roof-9272a5327eecf8a8 changed= ms=2207 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Roof: Fascia · picks (5000,-400) · keys Escape Escape · fields — · expect Fascias +1",
  "ribbon:Architecture:Roof: Gutter · picks (5000,-400) · keys Escape Escape · fields — · expect Gutters +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Roof: Fascia · picks (5000,-400) · keys Escape Escape · fields — · expect Fascias +1` | green: pressed 'Roof: Fascia' on Architecture's Build panel: the tool 'Roof: Fascia' stands \| picks: (5000,-400) mm at px (794.7,438.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Roof: Fascia -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Fascias +1": Fascias 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Roof: Gutter · picks (5000,-400) · keys Escape Escape · fields — · expect Gutters +1` | green: pressed 'Roof: Gutter' on Architecture's Build panel: the tool 'Roof: Gutter' stands \| picks: (5000,-400) mm at px (794.7,438.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Roof: Gutter -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Gutters +1": Gutters 0 -> 1 (+1, expected +1) |

### The result

The model holds: Fascias 1,Gutters 1,Levels 4,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2025. Place a room named Office, number 101, inside the 6 x 4 m office and tag it.

- Starts from: a new Architectural project
- Ends with: four walls on Ground with one room named Office, number 101, and a room tag on it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add room at=(3000,2000) level=Ground name=\"Office\" number=101"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-19fd9f921b93e133 changed= ms=19 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-c5884a5d0c92ee9b changed=wall-19fd9f921b93e133 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-d25bce6eac85c680 changed=wall-c5884a5d0c92ee9b ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-43a0c57b1be1939d changed=wall-19fd9f921b93e133,wall-d25bce6eac85c680 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add room at=(3000,2000) level=Ground name="Office" number=101` | green: op:add room made=room-2624f855a4f566d8 changed= ms=19 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Room Tag · picks (3000,2000) · keys Escape Escape · fields — · expect Tags +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Room Tag · picks (3000,2000) · keys Escape Escape · fields — · expect Tags +1` | green: pressed 'Room Tag' on Architecture's Room & Area panel (through its fold): the tool 'Room Tag' stands \| picks: (3000,2000) mm at px (736.0,368.3) on the plan view \| presses to the tool 1, selection changed \| keys: Escape (tool Room Tag -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Tags +1": Tags 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Rooms 1,Rooms Tags 1,Tags 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2026. Divide a 12 x 5 m flat into a bedroom, a living room and a bathroom with stud partitions, and name and number each room.

- Starts from: a new Architectural project
- Ends with: a 12 x 5 m outline and two stud partitions on Ground with three rooms named Bedroom 1 (101), Living (102) and Bathroom (103)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground",
  "op:add wall from=(12000,0) to=(12000,5000) level=Ground",
  "op:add wall from=(12000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground",
  "op:add wall from=(4000,0) to=(4000,5000) level=Ground type=\"Interior Stud 110\"",
  "op:add wall from=(9000,0) to=(9000,5000) level=Ground type=\"Interior Stud 110\"",
  "op:add room at=(2000,2500) level=Ground name=\"Bedroom 1\" number=101",
  "op:add room at=(6500,2500) level=Ground name=\"Living\" number=102",
  "op:add room at=(10500,2500) level=Ground name=\"Bathroom\" number=103"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground` | green: op:add wall made=wall-d864077ddadce7c9 changed= ms=372 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,5000) level=Ground` | green: op:add wall made=wall-44ad54e42eb5f2e1 changed=wall-d864077ddadce7c9 ms=11 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-dbd4b809c1ef43fc changed=wall-44ad54e42eb5f2e1 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-5fc9873f4d57e2b0 changed=wall-dbd4b809c1ef43fc,wall-d864077ddadce7c9 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(4000,0) to=(4000,5000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-c4c30c3b9c9b7c87 changed= ms=31 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,5000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-8d7184de131d30c5 changed= ms=6 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add room at=(2000,2500) level=Ground name="Bedroom 1" number=101` | green: op:add room made=room-05bef86d9d5f26db changed= ms=118 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(6500,2500) level=Ground name="Living" number=102` | green: op:add room made=room-bd4051f0c3a8de4e changed= ms=22 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |
| `op:add room at=(10500,2500) level=Ground name="Bathroom" number=103` | green: op:add room made=room-69fc3d5ca905b780 changed= ms=19 Check "Rooms +1": Rooms 2 -> 3 (+1, expected +1) |

### The result

The model holds: Levels 3,Rooms 3,Walls 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2027. Put an entry door in the middle of the south wall of the 10 x 6 m cottage with a window either side of it.

- Starts from: a new Architectural project
- Ends with: four walls on Ground with an entry door at 5000 on the south wall and a window each side of it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground",
  "op:add wall from=(10000,0) to=(10000,6000) level=Ground",
  "op:add wall from=(10000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground` | green: op:add wall made=wall-221135cdff08827d changed= ms=13 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,6000) level=Ground` | green: op:add wall made=wall-d881eddb8a3ba74e changed=wall-221135cdff08827d ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-c49ceac0f6de2ec1 changed=wall-d881eddb8a3ba74e ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-d036bf532821099a changed=wall-221135cdff08827d,wall-c49ceac0f6de2ec1 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (5000,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Window · picks (2500,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Windows +1",
  "ribbon:Architecture:Window · picks (7500,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (5000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (5000,0) mm at px (794.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (2500,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1200 reads '1200 mm' \| picks: (2500,0) mm at px (721.3,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (7500,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1200 reads '1200 mm' \| picks: (7500,0) mm at px (868.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |

### The result

The model holds: Doors 1,Levels 3,Openings 3,Walls 4,Windows 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2028. Space four 1500 wide windows evenly along the 12 m north wall of the classroom, sills at 900.

- Starts from: a new Architectural project
- Ends with: a 12 x 5 m classroom outline on Ground with four 1500 wide windows along the north wall, sills at 900
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground",
  "op:add wall from=(12000,0) to=(12000,5000) level=Ground",
  "op:add wall from=(12000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground` | green: op:add wall made=wall-e85daf34eab7c4c5 changed= ms=147 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,5000) level=Ground` | green: op:add wall made=wall-a3bcff7ebf47a91a changed=wall-e85daf34eab7c4c5 ms=43 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-436ea9bee01f7038 changed=wall-a3bcff7ebf47a91a ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-6d38dc2c8f3c30fe changed=wall-e85daf34eab7c4c5,wall-436ea9bee01f7038 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Window · picks (1500,5000) · keys Escape Escape · fields Options Strip: Width=1500; Sill Height=900 · expect Windows +1",
  "ribbon:Architecture:Window · picks (4500,5000) · keys Escape Escape · fields Options Strip: Width=1500; Sill Height=900 · expect Windows +1",
  "ribbon:Architecture:Window · picks (7500,5000) · keys Escape Escape · fields Options Strip: Width=1500; Sill Height=900 · expect Windows +1",
  "ribbon:Architecture:Window · picks (10500,5000) · keys Escape Escape · fields Options Strip: Width=1500; Sill Height=900 · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Window · picks (1500,5000) · keys Escape Escape · fields Options Strip: Width=1500; Sill Height=900 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm'; Sill Height=900 reads '900 mm' \| picks: (1500,5000) mm at px (692.0,280.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (4500,5000) · keys Escape Escape · fields Options Strip: Width=1500; Sill Height=900 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm'; Sill Height=900 reads '900 mm' \| picks: (4500,5000) mm at px (780.0,280.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (7500,5000) · keys Escape Escape · fields Options Strip: Width=1500; Sill Height=900 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm'; Sill Height=900 reads '900 mm' \| picks: (7500,5000) mm at px (868.0,280.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 2 -> 3 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (10500,5000) · keys Escape Escape · fields Options Strip: Width=1500; Sill Height=900 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm'; Sill Height=900 reads '900 mm' \| picks: (10500,5000) mm at px (956.0,280.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Openings 4,Walls 4,Windows 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2029. Give the 14 x 8 m hall two 1200 exit doors on the south wall and a 1000 door on the east wall.

- Starts from: a new Architectural project
- Ends with: a 14 x 8 m hall outline on Ground with two 1200 doors in the south wall and a 1000 door in the east wall
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(14000,0) level=Ground",
  "op:add wall from=(14000,0) to=(14000,8000) level=Ground",
  "op:add wall from=(14000,8000) to=(0,8000) level=Ground",
  "op:add wall from=(0,8000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(14000,0) level=Ground` | green: op:add wall made=wall-01aab44b67fe3277 changed= ms=15 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(14000,0) to=(14000,8000) level=Ground` | green: op:add wall made=wall-47c021ec63057d8d changed=wall-01aab44b67fe3277 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(14000,8000) to=(0,8000) level=Ground` | green: op:add wall made=wall-b92c9cd9a278760d changed=wall-47c021ec63057d8d ms=83 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground` | green: op:add wall made=wall-39ee4575d80d35cc changed=wall-b92c9cd9a278760d,wall-01aab44b67fe3277 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (3000,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Doors +1",
  "ribbon:Architecture:Door · picks (11000,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Doors +1",
  "ribbon:Architecture:Door · picks (14000,4000) · keys Escape Escape · fields Options Strip: Width=1000 · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (3000,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=1200 reads '1200 mm' \| picks: (3000,0) mm at px (726.9,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (11000,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=1200 reads '1200 mm' \| picks: (11000,0) mm at px (961.6,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (14000,4000) · keys Escape Escape · fields Options Strip: Width=1000 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=1000 reads '1000 mm' \| picks: (14000,4000) mm at px (1049.6,309.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 2 -> 3 (+1, expected +1) |

### The result

The model holds: Doors 3,Levels 3,Openings 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2030. Cut a 2.5 m square lift shaft from Ground up to Level 1 inside concrete walls.

- Starts from: a new Architectural project
- Ends with: four concrete walls and a floor on Level 1 with a 2.5 m square shaft cut from Ground to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(2500,0) level=Ground type=\"Concrete 200 + Render\"",
  "op:add wall from=(2500,0) to=(2500,2500) level=Ground type=\"Concrete 200 + Render\"",
  "op:add wall from=(2500,2500) to=(0,2500) level=Ground type=\"Concrete 200 + Render\"",
  "op:add wall from=(0,2500) to=(0,0) level=Ground type=\"Concrete 200 + Render\"",
  "op:add floor boundary=(-2000,-2000) (4500,-2000) (4500,4500) (-2000,4500) level=\"Level 1\"",
  "op:add shaft boundary=(0,0) (2500,2500) level=Ground top=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(2500,0) level=Ground type="Concrete 200 + Render"` | green: op:add wall made=wall-0a1cf5355b151c04 changed= ms=1878 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(2500,0) to=(2500,2500) level=Ground type="Concrete 200 + Render"` | green: op:add wall made=wall-d357fd3e9c9c4898 changed=wall-0a1cf5355b151c04 ms=404 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(2500,2500) to=(0,2500) level=Ground type="Concrete 200 + Render"` | green: op:add wall made=wall-2d7e2bb0808d78f8 changed=wall-d357fd3e9c9c4898 ms=7 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,2500) to=(0,0) level=Ground type="Concrete 200 + Render"` | green: op:add wall made=wall-6d501f8b5886c252 changed=wall-0a1cf5355b151c04,wall-2d7e2bb0808d78f8 ms=8 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(-2000,-2000) (4500,-2000) (4500,4500) (-2000,4500) level="Level 1"` | green: op:add floor made=floor-8a547d7e2385bf4e changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add shaft boundary=(0,0) (2500,2500) level=Ground top="Level 1"` | green: op:add shaft made=shaft-fc6e20056ab95831 changed= ms=9 Check "Openings +1": Openings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Openings 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2031. Sketch a 1.2 x 0.8 m service riser opening through the first floor slab.

- Starts from: a new Architectural project
- Ends with: a first floor slab on Level 1 with a 1.2 x 0.8 m riser opening sketched through it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0) (6000,0) (6000,4000) (0,4000) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0) (6000,0) (6000,4000) (0,4000) level="Level 1"` | green: op:add floor made=floor-dbf30e3c5d9de93c changed= ms=11 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Shaft · picks (2000,1000) (3200,1800) · keys — · fields — · expect nothing selected",
  "contextual:Finish · picks — · keys — · fields — · expect Openings +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Shaft · picks (2000,1000) (3200,1800) · keys — · fields — · expect nothing selected` | green: pressed 'Shaft' on Architecture's Opening panel (through its fold): the tool 'Shaft' stands \| picks: (2000,1000) mm at px (706.7,397.7) on the plan view \| (3200,1800) mm at px (741.9,374.2) on the plan view \| presses to the tool 2, selection unchanged Check "nothing selected": 0 selected |
| `contextual:Finish · picks — · keys — · fields — · expect Openings +1` | green: contextual 'Finish' on 'Modify \| Shaft': pressed 'Finish' on Modify \| Shaft's Mode panel: the command 'Finish' ran; status 'Click one corner of the shaft footprint' Check "Openings +1": Openings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Openings 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2032. Run a 1200 wide straight stair from Ground up to Level 1 and put a handrail along each side.

- Starts from: a new Architectural project
- Ends with: one straight stair 1200 wide from Ground to Level 1 with a railing on each side of the run
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add stair from=(1000,1000) to=(5000,1000) level=Ground top=\"Level 1\" width=1200",
  "op:add railing points=(1000,300) (4760,300) level=Ground",
  "op:add railing points=(1000,1700) (4760,1700) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add stair from=(1000,1000) to=(5000,1000) level=Ground top="Level 1" width=1200` | green: op:add stair made=stair-f8a6e8e3b0d9d573 changed= ms=21 note=the run ends at its last riser (5760,1000) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) |
| `op:add railing points=(1000,300) (4760,300) level=Ground` | green: op:add railing made=railing-24dfca25c300fab6 changed= ms=4 Check "Railings +1": Railings 0 -> 1 (+1, expected +1) |
| `op:add railing points=(1000,1700) (4760,1700) level=Ground` | green: op:add railing made=railing-1d8d5782a02a9c1e changed= ms=3 Check "Railings +1": Railings 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Railings 2,Stairs 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2033. Add a 4 x 1.5 m balcony slab at Level 1 with a balustrade round its three free sides.

- Starts from: a new Architectural project
- Ends with: a 4 x 1.5 m balcony slab on Level 1 with a railing along its three free sides
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0) (4000,0) (4000,1500) (0,1500) level=\"Level 1\"",
  "op:add railing points=(0,0) (0,1500) (4000,1500) (4000,0) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0) (4000,0) (4000,1500) (0,1500) level="Level 1"` | green: op:add floor made=floor-9ea0c8f866d8c82b changed= ms=367 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add railing points=(0,0) (0,1500) (4000,1500) (4000,0) level="Level 1"` | green: op:add railing made=railing-af87615341603b75 changed= ms=6 Check "Railings +1": Railings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Railings 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2034. Glaze the 8 m front of the shop with an exterior glazing curtain wall and divide it with a vertical grid line.

- Starts from: a new Architectural project
- Ends with: one 8 m exterior glazing wall from Ground to Level 1 carrying a curtain grid line
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground top=\"Level 1\" type=\"Exterior Glazing\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground top="Level 1" type="Exterior Glazing"` | green: op:add wall made=wall-ebca3e8dbc853f4c,grid-f60f6edd6c9699ed,grid-7e3f7caac7095c59,grid-9d4cba6eaa967d18,grid-082959ac1295b55e,grid-b75625aacbccb891,grid-f885d16e0fc84e1a,panel-wall-ebca3e8dbc853f4c-0-0,panel-wall-ebca3e8dbc853f4c-0-1,panel-wall-ebca3e8dbc853f4c-1-0,panel-wall-ebca3e8dbc853f4c-1-1,panel-wall-ebca3e8dbc853f4c-2-0,panel-wall-ebca3e8dbc853f4c-2-1,panel-wall-ebca3e8dbc853f4c-3-0,panel-wall-ebca3e8dbc853f4c-3-1,panel-wall-ebca3e8dbc853f4c-4-0,panel-wall-ebca3e8dbc853f4c-4-1,panel-wall-ebca3e8dbc853f4c-5-0,panel-wall-ebca3e8dbc853f4c-5-1 changed= ms=28 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Curtain Grid · picks (4000,0) · keys Escape Escape · fields — · expect Curtain Grids +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Curtain Grid · picks (4000,0) · keys Escape Escape · fields — · expect Curtain Grids +1` | green: pressed 'Curtain Grid' on Architecture's Build panel: the tool 'Curtain Grid' stands \| picks: (4000,0) mm at px (765.3,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Curtain Grid -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Curtain Grids +1": Curtain Grids 6 -> 7 (+1, expected +1) |

### The result

The model holds: Curtain Grids 7,Curtain Panels 14,Curtain Walls 1,Levels 3,Walls 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2035. Put a 1000 wide spiral stair from Ground to Level 1 inside a 3.4 m square stairwell.

- Starts from: a new Architectural project
- Ends with: four walls round a 3.4 m square stairwell on Ground and one spiral stair 1000 wide from Ground up to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(3400,0) level=Ground",
  "op:add wall from=(3400,0) to=(3400,3400) level=Ground",
  "op:add wall from=(3400,3400) to=(0,3400) level=Ground",
  "op:add wall from=(0,3400) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(3400,0) level=Ground` | green: op:add wall made=wall-87501a785dde022a changed= ms=621 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(3400,0) to=(3400,3400) level=Ground` | green: op:add wall made=wall-96d35ba8b6552731 changed=wall-87501a785dde022a ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(3400,3400) to=(0,3400) level=Ground` | green: op:add wall made=wall-846eedbf5d0c9dee changed=wall-96d35ba8b6552731 ms=60 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,3400) to=(0,0) level=Ground` | green: op:add wall made=wall-df6888e8535382d2 changed=wall-87501a785dde022a,wall-846eedbf5d0c9dee ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:draw-stair · picks (1700,1700) (2900,1700) · keys Escape Escape · fields Options Strip: Shape=spiral; Width=1000; Inner Radius=200; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:draw-stair · picks (1700,1700) (2900,1700) · keys Escape Escape · fields Options Strip: Shape=spiral; Width=1000; Inner Radius=200; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1` | green: pressed 'draw-stair' on Architecture's Circulation panel: the tool 'draw-stair' stands \| fields: Shape=spiral reads 'Spiral'; Width=1000 reads '1000 mm'; Inner Radius=200 reads '200 mm'; Level=Ground reads 'Ground'; Multistorey Top Level=Level 1 reads 'Level 1' \| picks: (1700,1700) mm at px (697.9,377.1) on the plan view \| (2900,1700) mm at px (733.1,377.1) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool draw-stair -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Stairs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2036. Draw an L-shaped stair from Ground to Level 1 in the 3 x 5 m stair hall.

- Starts from: a new Architectural project
- Ends with: four walls round a 3 x 5 m stair hall on Ground and one L-shaped stair from Ground up to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(3000,0) level=Ground",
  "op:add wall from=(3000,0) to=(3000,5000) level=Ground",
  "op:add wall from=(3000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(3000,0) level=Ground` | green: op:add wall made=wall-bf832333299a4c85 changed= ms=609 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(3000,0) to=(3000,5000) level=Ground` | green: op:add wall made=wall-0db1bc0dfe95a17a changed=wall-bf832333299a4c85 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(3000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-03647f6ad02359c5 changed=wall-0db1bc0dfe95a17a ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-03d24b5a3ce62cfd changed=wall-bf832333299a4c85,wall-03647f6ad02359c5 ms=27 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:draw-stair · picks (800,500) (800,4500) · keys Escape Escape · fields Options Strip: Shape=L; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:draw-stair · picks (800,500) (800,4500) · keys Escape Escape · fields Options Strip: Shape=L; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1` | green: pressed 'draw-stair' on Architecture's Circulation panel: the tool 'draw-stair' stands \| fields: Shape=L reads 'L'; Level=Ground reads 'Ground'; Multistorey Top Level=Level 1 reads 'Level 1' \| picks: (800,500) mm at px (671.5,412.3) on the plan view \| (800,4500) mm at px (671.5,295.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool draw-stair -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Stairs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2037. Draw a U-shaped stair 1100 wide from Ground to Level 1 in the stair core of the walk-up.

- Starts from: a new Architectural project
- Ends with: four concrete walls round a stair core on Ground and one U-shaped stair 1100 wide from Ground up to Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(3000,0) level=Ground type=\"Concrete 200 + Render\"",
  "op:add wall from=(3000,0) to=(3000,5200) level=Ground type=\"Concrete 200 + Render\"",
  "op:add wall from=(3000,5200) to=(0,5200) level=Ground type=\"Concrete 200 + Render\"",
  "op:add wall from=(0,5200) to=(0,0) level=Ground type=\"Concrete 200 + Render\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(3000,0) level=Ground type="Concrete 200 + Render"` | green: op:add wall made=wall-4ee7289e191ac7f2 changed= ms=329 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(3000,0) to=(3000,5200) level=Ground type="Concrete 200 + Render"` | green: op:add wall made=wall-db526b2e1b7d209f changed=wall-4ee7289e191ac7f2 ms=51 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(3000,5200) to=(0,5200) level=Ground type="Concrete 200 + Render"` | green: op:add wall made=wall-198c06cbc4087ff6 changed=wall-db526b2e1b7d209f ms=438 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5200) to=(0,0) level=Ground type="Concrete 200 + Render"` | green: op:add wall made=wall-55cea2906133a20a changed=wall-198c06cbc4087ff6,wall-4ee7289e191ac7f2 ms=6 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:draw-stair · picks (700,500) (700,4500) · keys Escape Escape · fields Options Strip: Shape=U; Width=1100; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:draw-stair · picks (700,500) (700,4500) · keys Escape Escape · fields Options Strip: Shape=U; Width=1100; Level=Ground; Multistorey Top Level=Level 1 · expect Stairs +1` | green: pressed 'draw-stair' on Architecture's Circulation panel: the tool 'draw-stair' stands \| fields: Shape=U reads 'U'; Width=1100 reads '1100 mm'; Level=Ground reads 'Ground'; Multistorey Top Level=Level 1 reads 'Level 1' \| picks: (700,500) mm at px (668.5,412.3) on the plan view \| (700,4500) mm at px (668.5,295.0) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool draw-stair -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Stairs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2038. Draw a 10 m long, 1200 wide access ramp up from Ground and put a handrail along each side.

- Starts from: a new Architectural project
- Ends with: one straight ramp 1200 wide, 10 m long, rising from Ground, with a railing along each side
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:draw-ramp · picks (1000,1000) (11000,1000) · keys Escape Escape · fields Options Strip: base_level=Ground · expect Ramps +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:draw-ramp · picks (1000,1000) (11000,1000) · keys Escape Escape · fields Options Strip: base_level=Ground · expect Ramps +1` | green: pressed 'draw-ramp' on Architecture's Circulation panel: the tool 'draw-ramp' stands \| fields: base_level=Ground reads 'Ground' \| picks: (1000,1000) mm at px (677.3,397.7) on the plan view \| (11000,1000) mm at px (970.7,397.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool draw-ramp -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ramps +1": Ramps 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add railing points=(1000,300) (11000,300) level=Ground",
  "op:add railing points=(1000,1700) (11000,1700) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add railing points=(1000,300) (11000,300) level=Ground` | green: op:add railing made=railing-3c031b6c25b2aa16 changed= ms=41 Check "Railings +1": Railings 0 -> 1 (+1, expected +1) |
| `op:add railing points=(1000,1700) (11000,1700) level=Ground` | green: op:add railing made=railing-018c729a83abc434 changed= ms=15 Check "Railings +1": Railings 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Railings 2,Ramps 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2039. Cut a 3 x 1.5 m stair void in the first floor slab and put a railing round it.

- Starts from: a new Architectural project
- Ends with: a first floor slab on Level 1 with a 3 x 1.5 m void cut through it and a closed railing round the void
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0) (8000,0) (8000,5000) (0,5000) level=\"Level 1\" type=\"Timber Joist and Ply 240\"",
  "op:add shaft boundary=(2000,1500) (5000,3000) level=Ground top=\"Level 1\"",
  "op:add railing points=(2000,1500) (5000,1500) (5000,3000) (2000,3000) (2000,1500) level=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0) (8000,0) (8000,5000) (0,5000) level="Level 1" type="Timber Joist and Ply 240"` | green: op:add floor made=floor-ada2ed2765d539a7 changed= ms=548 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add shaft boundary=(2000,1500) (5000,3000) level=Ground top="Level 1"` | green: op:add shaft made=shaft-df966c4622911280 changed= ms=104 Check "Openings +1": Openings 0 -> 1 (+1, expected +1) |
| `op:add railing points=(2000,1500) (5000,1500) (5000,3000) (2000,3000) (2000,1500) level="Level 1"` | green: op:add railing made=railing-d10b42efdaa4bf2e changed= ms=5 Check "Railings +1": Railings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Openings 1,Railings 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2040. Split the 10 x 5 m open-plan office into a work area and a meeting area with a room separator line and name both rooms.

- Starts from: a new Architectural project
- Ends with: four walls on Ground, a room separator line at 5000, and two rooms named Work Area (101) and Meeting (102)
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground",
  "op:add wall from=(10000,0) to=(10000,5000) level=Ground",
  "op:add wall from=(10000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground` | green: op:add wall made=wall-5b6694a299aa466d changed= ms=11 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,5000) level=Ground` | green: op:add wall made=wall-fe35db352ff613fe changed=wall-5b6694a299aa466d ms=37 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-7b5f68a6d53c732d changed=wall-fe35db352ff613fe ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-6da462dae37d0741 changed=wall-7b5f68a6d53c732d,wall-5b6694a299aa466d ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Room Separator · picks (5000,0) (5000,5000) · keys Escape Escape · fields — · expect Room Separators +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Room Separator · picks (5000,0) (5000,5000) · keys Escape Escape · fields — · expect Room Separators +1` | green: pressed 'Room Separator' on Architecture's Room & Area panel (through its fold): the tool 'Room Separator' stands \| picks: (5000,0) mm at px (794.7,427.0) on the plan view \| (5000,5000) mm at px (794.7,280.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Room Separator -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Room Separators +1": Room Separators 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add room at=(2500,2500) level=Ground name=\"Work Area\" number=101",
  "op:add room at=(7500,2500) level=Ground name=\"Meeting\" number=102"
]}
```

| Line | UNION answered |
|---|---|
| `op:add room at=(2500,2500) level=Ground name="Work Area" number=101` | green: op:add room made=room-d84743580637deb7 changed= ms=19 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(7500,2500) level=Ground name="Meeting" number=102` | green: op:add room made=room-815c3fe3ef32f2e3 changed= ms=324 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |

### The result

The model holds: Levels 3,Room Separators 1,Rooms 2,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2041. Draw a small three-bedroom house, 12 x 9 m in brick veneer, with a slab, internal walls, a front door, windows, a hip roof and its rooms named.

- Starts from: a new Architectural project
- Ends with: a 12 x 9 m brick veneer house on Ground with a slab, two stud partitions, a front door, three windows, a hip roof and three rooms named Living, Bedroom 1 and Bedroom 2
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(12000,0) to=(12000,9000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(12000,9000) to=(0,9000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(0,9000) to=(0,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(6000,0) to=(6000,9000) level=Ground type=\"Interior Stud 110\"",
  "op:add wall from=(0,4500) to=(6000,4500) level=Ground type=\"Interior Stud 110\"",
  "op:add floor boundary=(0,0) (12000,0) (12000,9000) (0,9000) level=Ground type=\"Concrete Slab 200 + Tile\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-ba8064ed36a19496 changed= ms=17 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,9000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-62625c0b291ea683 changed=wall-ba8064ed36a19496 ms=5 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,9000) to=(0,9000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-497f9dcff4655678 changed=wall-62625c0b291ea683 ms=5 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,9000) to=(0,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-61cd905ae4ca872d changed=wall-ba8064ed36a19496,wall-497f9dcff4655678 ms=34 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,9000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-c8417d2200da7bf1 changed= ms=10 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(0,4500) to=(6000,4500) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-3ef37b42cfca5003 changed= ms=39 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add floor boundary=(0,0) (12000,0) (12000,9000) (0,9000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-cd14e55e39fa0c55 changed= ms=7 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (9000,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Window · picks (3000,0) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1",
  "ribbon:Architecture:Window · picks (3000,9000) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1",
  "ribbon:Architecture:Window · picks (9000,9000) · keys Escape Escape · fields Options Strip: Width=1800 · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (9000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (9000,0) mm at px (912.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (3000,0) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm' \| picks: (3000,0) mm at px (736.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (3000,9000) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm' \| picks: (3000,9000) mm at px (736.0,163.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (9000,9000) · keys Escape Escape · fields Options Strip: Width=1800 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1800 reads '1800 mm' \| picks: (9000,9000) mm at px (912.0,163.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 2 -> 3 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add roof boundary=(-450,-450) (12450,-450) (12450,9450) (-450,9450) level=\"Level 1\" slope=22 type=\"Terracotta Tile Battens 140\"",
  "op:add room at=(9000,4500) level=Ground name=\"Living\" number=101",
  "op:add room at=(3000,2250) level=Ground name=\"Bedroom 1\" number=102",
  "op:add room at=(3000,6750) level=Ground name=\"Bedroom 2\" number=103"
]}
```

| Line | UNION answered |
|---|---|
| `op:add roof boundary=(-450,-450) (12450,-450) (12450,9450) (-450,9450) level="Level 1" slope=22 type="Terracotta Tile Battens 140"` | green: op:add roof made=roof-a72b3a9db98d402f changed= ms=7 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |
| `op:add room at=(9000,4500) level=Ground name="Living" number=101` | green: op:add room made=room-700c44abaa5c55b0 changed= ms=289 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(3000,2250) level=Ground name="Bedroom 1" number=102` | green: op:add room made=room-f71e5c01602c6891 changed= ms=231 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |
| `op:add room at=(3000,6750) level=Ground name="Bedroom 2" number=103` | green: op:add room made=room-84059f1df8cc60b3 changed= ms=129 Check "Rooms +1": Rooms 2 -> 3 (+1, expected +1) |

### The result

The model holds: Doors 1,Floors 1,Levels 3,Openings 4,Roofs 1,Rooms 3,Walls 6,Windows 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2042. Fit out an 8 x 12 m shop unit: glazed shopfront, a stock room at the back with a door, a counter and a ceiling.

- Starts from: a new Architectural project
- Ends with: an 8 x 12 m shop unit on Ground with a storefront on the south side, a stock room behind a stud wall with a door, a low counter wall, a floor, a ceiling and two named rooms
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground top=\"Level 1\" type=Storefront",
  "op:add wall from=(8000,0) to=(8000,12000) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(8000,12000) to=(0,12000) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(0,12000) to=(0,0) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(0,9000) to=(8000,9000) level=Ground type=\"Interior Stud 110\"",
  "op:add wall from=(2500,4500) to=(5500,4500) level=Ground type=\"Interior Stud 110\" height=1000"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground top="Level 1" type=Storefront` | green: op:add wall made=wall-c6e46c3e7c6bd5c2,grid-577aa277e420b496,grid-b4648999f781b816,grid-2883a0ab938d7184,grid-abff6912943f0a3c,grid-928d9a07962a3b5d,grid-02f7dd5516ebff38,grid-d4be624ac9f0b680,grid-472f3226c3a3c4f1,grid-f5e20c66670efd2f,panel-wall-c6e46c3e7c6bd5c2-0-0,panel-wall-c6e46c3e7c6bd5c2-0-1,panel-wall-c6e46c3e7c6bd5c2-1-0,panel-wall-c6e46c3e7c6bd5c2-1-1,panel-wall-c6e46c3e7c6bd5c2-2-0,panel-wall-c6e46c3e7c6bd5c2-2-1,panel-wall-c6e46c3e7c6bd5c2-3-0,panel-wall-c6e46c3e7c6bd5c2-3-1,panel-wall-c6e46c3e7c6bd5c2-4-0,panel-wall-c6e46c3e7c6bd5c2-4-1,panel-wall-c6e46c3e7c6bd5c2-5-0,panel-wall-c6e46c3e7c6bd5c2-5-1,panel-wall-c6e46c3e7c6bd5c2-6-0,panel-wall-c6e46c3e7c6bd5c2-6-1,panel-wall-c6e46c3e7c6bd5c2-7-0,panel-wall-c6e46c3e7c6bd5c2-7-1,panel-wall-c6e46c3e7c6bd5c2-8-0,panel-wall-c6e46c3e7c6bd5c2-8-1 changed= ms=773 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,12000) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-afd4e6a1103eb53e changed=wall-c6e46c3e7c6bd5c2 ms=11 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,12000) to=(0,12000) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-f0b2553fa2b76f9c changed=wall-afd4e6a1103eb53e ms=9 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,12000) to=(0,0) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-c88127853539ee65 changed=wall-f0b2553fa2b76f9c,wall-c6e46c3e7c6bd5c2 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(0,9000) to=(8000,9000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-606563dc0a2df60e changed= ms=19 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(2500,4500) to=(5500,4500) level=Ground type="Interior Stud 110" height=1000` | green: op:add wall made=wall-dfc2dab04d3b925a changed= ms=113 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (6000,9000) · keys Escape Escape · fields — · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (6000,9000) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (6000,9000) mm at px (824.0,163.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0) (8000,0) (8000,12000) (0,12000) level=Ground type=\"Concrete Slab 200 + Tile\"",
  "op:add ceiling boundary=(0,0) (8000,0) (8000,9000) (0,9000) level=Ground height=2700 type=\"Suspended Tile 600 x 600\"",
  "op:add room at=(4000,2500) level=Ground name=\"Shop\" number=1",
  "op:add room at=(4000,10500) level=Ground name=\"Stock\" number=2"
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0) (8000,0) (8000,12000) (0,12000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-8f0008ad24601c65 changed= ms=9 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add ceiling boundary=(0,0) (8000,0) (8000,9000) (0,9000) level=Ground height=2700 type="Suspended Tile 600 x 600"` | green: op:add ceiling made=ceiling-b884cba544ba4a3d changed= ms=10 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `op:add room at=(4000,2500) level=Ground name="Shop" number=1` | green: op:add room made=room-49f646a00fb93055 changed= ms=178 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(4000,10500) level=Ground name="Stock" number=2` | green: op:add room made=room-b2cb00cd0b860db3 changed= ms=409 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |

### The result

The model holds: Ceilings 1,Curtain Grids 9,Curtain Panels 18,Curtain Walls 1,Doors 1,Floors 1,Levels 3,Openings 1,Rooms 2,Walls 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2043. Lay out a 9 x 3 m transportable site office with a slab, a door, two windows, a flat roof and its room.

- Starts from: a new Architectural project
- Ends with: a 9 x 3 m site office on Ground with four walls, a slab, a door, two windows, a flat metal deck roof and a room named Site Office
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground",
  "op:add wall from=(9000,0) to=(9000,3000) level=Ground",
  "op:add wall from=(9000,3000) to=(0,3000) level=Ground",
  "op:add wall from=(0,3000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0) (9000,0) (9000,3000) (0,3000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground` | green: op:add wall made=wall-bc522b0e9d506e6b changed= ms=351 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,3000) level=Ground` | green: op:add wall made=wall-6cb23d25522887d5 changed=wall-bc522b0e9d506e6b ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,3000) to=(0,3000) level=Ground` | green: op:add wall made=wall-3a5dd44cfefe04ea changed=wall-6cb23d25522887d5 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,3000) to=(0,0) level=Ground` | green: op:add wall made=wall-0164e19b45b71f8b changed=wall-3a5dd44cfefe04ea,wall-bc522b0e9d506e6b ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (9000,0) (9000,3000) (0,3000) level=Ground` | green: op:add floor made=floor-2c79d8f079817ccb changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (1200,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Window · picks (4000,0) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1",
  "ribbon:Architecture:Window · picks (7000,0) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (1200,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (1200,0) mm at px (683.2,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (4000,0) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm' \| picks: (4000,0) mm at px (765.3,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (7000,0) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm' \| picks: (7000,0) mm at px (853.3,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add roof boundary=(0,0) (9000,0) (9000,3000) (0,3000) level=\"Level 1\" slope=0 type=\"Metal Deck Insulated 75\"",
  "op:add room at=(4500,1500) level=Ground name=\"Site Office\" number=1"
]}
```

| Line | UNION answered |
|---|---|
| `op:add roof boundary=(0,0) (9000,0) (9000,3000) (0,3000) level="Level 1" slope=0 type="Metal Deck Insulated 75"` | green: op:add roof made=roof-2d629b3848296d4b changed= ms=7 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |
| `op:add room at=(4500,1500) level=Ground name="Site Office" number=1` | green: op:add room made=room-6029c8f0236a70ea changed= ms=13 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |

### The result

The model holds: Doors 1,Floors 1,Levels 3,Openings 3,Roofs 1,Rooms 1,Walls 4,Windows 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2044. Draw an 8 x 4 m ablution block with three toilet cubicles each with its own door, a tiled floor and a ceiling.

- Starts from: a new Architectural project
- Ends with: an 8 x 4 m ablution block on Ground with a wet-area slab, a cubicle wall line with three 800 doors, two cubicle dividers, an entry door and a ceiling
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground type=\"Block 190 Core-filled\" height=2700",
  "op:add wall from=(8000,0) to=(8000,4000) level=Ground type=\"Block 190 Core-filled\" height=2700",
  "op:add wall from=(8000,4000) to=(0,4000) level=Ground type=\"Block 190 Core-filled\" height=2700",
  "op:add wall from=(0,4000) to=(0,0) level=Ground type=\"Block 190 Core-filled\" height=2700",
  "op:add wall from=(0,1800) to=(6000,1800) level=Ground type=\"Interior Stud 110\" height=2100",
  "op:add wall from=(2000,0) to=(2000,1800) level=Ground type=\"Interior Stud 110\" height=2100",
  "op:add wall from=(4000,0) to=(4000,1800) level=Ground type=\"Interior Stud 110\" height=2100",
  "op:add floor boundary=(0,0) (8000,0) (8000,4000) (0,4000) level=Ground type=\"Slab Tiled Wet Area 200\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground type="Block 190 Core-filled" height=2700` | green: op:add wall made=wall-456a2c98591d15b6 changed= ms=16 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,4000) level=Ground type="Block 190 Core-filled" height=2700` | green: op:add wall made=wall-a1f06e1ceb0d01bb changed=wall-456a2c98591d15b6 ms=44 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,4000) to=(0,4000) level=Ground type="Block 190 Core-filled" height=2700` | green: op:add wall made=wall-d35d661344a7102d changed=wall-a1f06e1ceb0d01bb ms=5 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground type="Block 190 Core-filled" height=2700` | green: op:add wall made=wall-2171350ccab10a4e changed=wall-d35d661344a7102d,wall-456a2c98591d15b6 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(0,1800) to=(6000,1800) level=Ground type="Interior Stud 110" height=2100` | green: op:add wall made=wall-8dea127266736291 changed= ms=5 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(2000,0) to=(2000,1800) level=Ground type="Interior Stud 110" height=2100` | green: op:add wall made=wall-1004caca62cc2e25 changed= ms=5 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add wall from=(4000,0) to=(4000,1800) level=Ground type="Interior Stud 110" height=2100` | green: op:add wall made=wall-7266f2dcc84929f3 changed= ms=3 Check "Walls +1": Walls 6 -> 7 (+1, expected +1) |
| `op:add floor boundary=(0,0) (8000,0) (8000,4000) (0,4000) level=Ground type="Slab Tiled Wet Area 200"` | green: op:add floor made=floor-32a23b5f10c3a90a changed= ms=8 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (1000,1800) · keys Escape Escape · fields Options Strip: Width=800 · expect Doors +1",
  "ribbon:Architecture:Door · picks (3000,1800) · keys Escape Escape · fields Options Strip: Width=800 · expect Doors +1",
  "ribbon:Architecture:Door · picks (5000,1800) · keys Escape Escape · fields Options Strip: Width=800 · expect Doors +1",
  "ribbon:Architecture:Door · picks (8000,3000) · keys Escape Escape · fields — · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (1000,1800) · keys Escape Escape · fields Options Strip: Width=800 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=800 reads '800 mm' \| picks: (1000,1800) mm at px (677.3,374.2) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (3000,1800) · keys Escape Escape · fields Options Strip: Width=800 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=800 reads '800 mm' \| picks: (3000,1800) mm at px (736.0,374.2) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (5000,1800) · keys Escape Escape · fields Options Strip: Width=800 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=800 reads '800 mm' \| picks: (5000,1800) mm at px (794.7,374.2) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 2 -> 3 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (8000,3000) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (8000,3000) mm at px (882.7,339.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 3 -> 4 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add ceiling boundary=(0,0) (8000,0) (8000,4000) (0,4000) level=Ground height=2700 type=\"Plain Ceiling 13 mm\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add ceiling boundary=(0,0) (8000,0) (8000,4000) (0,4000) level=Ground height=2700 type="Plain Ceiling 13 mm"` | green: op:add ceiling made=ceiling-78e42c1171097ac5 changed= ms=3 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Ceilings 1,Doors 4,Floors 1,Levels 3,Openings 4,Walls 7,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2045. Draw a two-storey walk-up block, 10 x 7 m: ground and first floor walls, a slab and a timber first floor, a stair between the levels and a hip roof.

- Starts from: a new Architectural project
- Ends with: eight walls on two levels, a slab on Ground, a timber floor on Level 1, a straight stair from Ground to Level 1 and a hip roof at the top
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(10000,0) to=(10000,7000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(10000,7000) to=(0,7000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(0,7000) to=(0,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add floor boundary=(0,0) (10000,0) (10000,7000) (0,7000) level=Ground type=\"Concrete Slab 200 + Tile\"",
  "op:add floor boundary=(0,0) (10000,0) (10000,7000) (0,7000) level=\"Level 1\" type=\"Timber Joist and Ply 240\"",
  "op:add stair from=(1000,1000) to=(5000,1000) level=Ground top=\"Level 1\" width=1100",
  "op:add wall from=(0,0) to=(10000,0) level=\"Level 1\" top=Roof type=\"Brick Veneer 251\"",
  "op:add wall from=(10000,0) to=(10000,7000) level=\"Level 1\" top=Roof type=\"Brick Veneer 251\"",
  "op:add wall from=(10000,7000) to=(0,7000) level=\"Level 1\" top=Roof type=\"Brick Veneer 251\"",
  "op:add wall from=(0,7000) to=(0,0) level=\"Level 1\" top=Roof type=\"Brick Veneer 251\"",
  "op:add roof boundary=(-400,-400) (10400,-400) (10400,7400) (-400,7400) level=Roof slope=20 type=\"Concrete Tile Battens 140\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-bec20544ec128c38 changed= ms=432 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,7000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-e6a10f085d7650b6 changed=wall-bec20544ec128c38 ms=6 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,7000) to=(0,7000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-e5bfac34a5f87277 changed=wall-e6a10f085d7650b6 ms=6 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,7000) to=(0,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-50003cc818c1504e changed=wall-bec20544ec128c38,wall-e5bfac34a5f87277 ms=6 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (10000,0) (10000,7000) (0,7000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-0ca12d3ef40e7409 changed= ms=6 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add floor boundary=(0,0) (10000,0) (10000,7000) (0,7000) level="Level 1" type="Timber Joist and Ply 240"` | green: op:add floor made=floor-065acbcc472000e3 changed= ms=34 Check "Floors +1": Floors 1 -> 2 (+1, expected +1) |
| `op:add stair from=(1000,1000) to=(5000,1000) level=Ground top="Level 1" width=1100` | green: op:add stair made=stair-1d627a11765c5738 changed= ms=3 note=the run ends at its last riser (5760,1000) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) |
| `op:add wall from=(0,0) to=(10000,0) level="Level 1" top=Roof type="Brick Veneer 251"` | green: op:add wall made=wall-a5e565fd6a69e190 changed= ms=5 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,7000) level="Level 1" top=Roof type="Brick Veneer 251"` | green: op:add wall made=wall-e7ad513a2d9c36e6 changed=wall-a5e565fd6a69e190 ms=5 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add wall from=(10000,7000) to=(0,7000) level="Level 1" top=Roof type="Brick Veneer 251"` | green: op:add wall made=wall-5f8fa02143ca906d changed=wall-e7ad513a2d9c36e6 ms=5 Check "Walls +1": Walls 6 -> 7 (+1, expected +1) |
| `op:add wall from=(0,7000) to=(0,0) level="Level 1" top=Roof type="Brick Veneer 251"` | green: op:add wall made=wall-c0fc80821bcdf2eb changed=wall-a5e565fd6a69e190,wall-5f8fa02143ca906d ms=4 Check "Walls +1": Walls 7 -> 8 (+1, expected +1) |
| `op:add roof boundary=(-400,-400) (10400,-400) (10400,7400) (-400,7400) level=Roof slope=20 type="Concrete Tile Battens 140"` | green: op:add roof made=roof-eb82a560dd9d7959 changed= ms=5 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 2,Levels 3,Roofs 1,Stairs 1,Walls 8,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2046. Draw a 6 x 6 m double garage with a 4800 wide roller door in the south wall, a personal door in the east wall and a flat roof.

- Starts from: a new Architectural project
- Ends with: four blockwork walls on Ground with a slab, a 4800 wide roller door in the south wall, a 900 door in the east wall and a flat roof at Level 1
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(6000,0) to=(6000,6000) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(6000,6000) to=(0,6000) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(0,6000) to=(0,0) level=Ground type=\"Block 190 Core-filled\"",
  "op:add floor boundary=(0,0) (6000,0) (6000,6000) (0,6000) level=Ground type=\"Concrete Slab 200 + Tile\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-3aec02457697d482 changed= ms=15 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,6000) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-7d28da980549d95d changed=wall-3aec02457697d482 ms=5 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,6000) to=(0,6000) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-9b1ec48c4648cfab changed=wall-7d28da980549d95d ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-ee1c48231dd74062 changed=wall-9b1ec48c4648cfab,wall-3aec02457697d482 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (6000,0) (6000,6000) (0,6000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-b40080f0d4b7ab9f changed= ms=6 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (3000,0) · keys Escape Escape · fields Options Strip: Width=4800; Height=2100 · expect Doors +1",
  "ribbon:Architecture:Door · picks (6000,3000) · keys Escape Escape · fields Options Strip: Width=900; Height=2040 · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (3000,0) · keys Escape Escape · fields Options Strip: Width=4800; Height=2100 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=4800 reads '4800 mm'; Height=2100 reads '2100 mm' \| picks: (3000,0) mm at px (736.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (6000,3000) · keys Escape Escape · fields Options Strip: Width=900; Height=2040 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=900 reads '900 mm'; Height=2040 reads '2040 mm' \| picks: (6000,3000) mm at px (824.0,339.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add roof boundary=(0,0) (6000,0) (6000,6000) (0,6000) level=\"Level 1\" slope=0 type=\"Concrete Roof 250\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add roof boundary=(0,0) (6000,0) (6000,6000) (0,6000) level="Level 1" slope=0 type="Concrete Roof 250"` | green: op:add roof made=roof-b457b56267cdf040 changed= ms=6 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Doors 2,Floors 1,Levels 3,Openings 2,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2047. Draw a 4 x 3 m park kiosk in brick veneer with a serving window 1800 wide at 1000 sill, a side door and a low hip roof.

- Starts from: a new Architectural project
- Ends with: four brick veneer walls on Ground with a slab, a 1800 wide serving window with a 1000 sill, a side door and a 20 degree hip roof on an Eaves level
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(4000,0) level=Ground height=2700 type=\"Brick Veneer 251\"",
  "op:add wall from=(4000,0) to=(4000,3000) level=Ground height=2700 type=\"Brick Veneer 251\"",
  "op:add wall from=(4000,3000) to=(0,3000) level=Ground height=2700 type=\"Brick Veneer 251\"",
  "op:add wall from=(0,3000) to=(0,0) level=Ground height=2700 type=\"Brick Veneer 251\"",
  "op:add floor boundary=(0,0) (4000,0) (4000,3000) (0,3000) level=Ground type=\"Concrete Slab 200 + Tile\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(4000,0) level=Ground height=2700 type="Brick Veneer 251"` | green: op:add wall made=wall-ac091ace54bec58b changed= ms=17 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(4000,0) to=(4000,3000) level=Ground height=2700 type="Brick Veneer 251"` | green: op:add wall made=wall-393338dc59272c6b changed=wall-ac091ace54bec58b ms=6 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(4000,3000) to=(0,3000) level=Ground height=2700 type="Brick Veneer 251"` | green: op:add wall made=wall-6ad7e3b8146ae6a0 changed=wall-393338dc59272c6b ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,3000) to=(0,0) level=Ground height=2700 type="Brick Veneer 251"` | green: op:add wall made=wall-fa5b9f5d2cc91ea4 changed=wall-ac091ace54bec58b,wall-6ad7e3b8146ae6a0 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (4000,0) (4000,3000) (0,3000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-d3ff9d762c4d56cc changed= ms=6 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Window · picks (2000,0) · keys Escape Escape · fields Options Strip: Width=1800; Sill Height=1000 · expect Windows +1",
  "ribbon:Architecture:Door · picks (4000,1500) · keys Escape Escape · fields — · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Window · picks (2000,0) · keys Escape Escape · fields Options Strip: Width=1800; Sill Height=1000 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1800 reads '1800 mm'; Sill Height=1000 reads '1000 mm' \| picks: (2000,0) mm at px (706.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (4000,1500) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (4000,1500) mm at px (765.3,383.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add level elevation=2700 name=\"Eaves\"",
  "op:add roof boundary=(-300,-300) (4300,-300) (4300,3300) (-300,3300) level=Eaves slope=20 type=\"Metal Deck on Purlins 150\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=2700 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=32 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add roof boundary=(-300,-300) (4300,-300) (4300,3300) (-300,3300) level=Eaves slope=20 type="Metal Deck on Purlins 150"` | green: op:add roof made=roof-ff370c295824a6d8 changed= ms=5 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Doors 1,Floors 1,Levels 4,Openings 2,Roofs 1,Walls 4,Windows 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2048. Lay out a 16 x 8 m classroom block: two classrooms on the south side, a 2.2 m corridor on the north, a door from each classroom and a big window to each.

- Starts from: a new Architectural project
- Ends with: a 16 x 8 m block on Ground with a corridor wall and a divider forming two classrooms and a corridor, a door and a window to each classroom, three rooms named and a ceiling in each classroom
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(16000,0) level=Ground",
  "op:add wall from=(16000,0) to=(16000,8000) level=Ground",
  "op:add wall from=(16000,8000) to=(0,8000) level=Ground",
  "op:add wall from=(0,8000) to=(0,0) level=Ground",
  "op:add wall from=(0,5800) to=(16000,5800) level=Ground type=\"Interior Stud 110\"",
  "op:add wall from=(8000,0) to=(8000,5800) level=Ground type=\"Interior Stud 110\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(16000,0) level=Ground` | green: op:add wall made=wall-0afd2fc2c8615be9 changed= ms=339 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(16000,0) to=(16000,8000) level=Ground` | green: op:add wall made=wall-c3eb1fff903c5dd4 changed=wall-0afd2fc2c8615be9 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(16000,8000) to=(0,8000) level=Ground` | green: op:add wall made=wall-d87c6df13e2709d9 changed=wall-c3eb1fff903c5dd4 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground` | green: op:add wall made=wall-1a79a3af1ec441b5 changed=wall-0afd2fc2c8615be9,wall-d87c6df13e2709d9 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(0,5800) to=(16000,5800) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-d69ab03108877f26 changed= ms=6 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,5800) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-d7fcb344f6e8898c changed= ms=4 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (4000,5800) · keys Escape Escape · fields Options Strip: Width=1000 · expect Doors +1",
  "ribbon:Architecture:Door · picks (12000,5800) · keys Escape Escape · fields Options Strip: Width=1000 · expect Doors +1",
  "ribbon:Architecture:Window · picks (4000,0) · keys Escape Escape · fields Options Strip: Width=2400 · expect Windows +1",
  "ribbon:Architecture:Window · picks (12000,0) · keys Escape Escape · fields Options Strip: Width=2400 · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (4000,5800) · keys Escape Escape · fields Options Strip: Width=1000 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=1000 reads '1000 mm' \| picks: (4000,5800) mm at px (728.3,256.9) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (12000,5800) · keys Escape Escape · fields Options Strip: Width=1000 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=1000 reads '1000 mm' \| picks: (12000,5800) mm at px (963.0,256.9) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (4000,0) · keys Escape Escape · fields Options Strip: Width=2400 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=2400 reads '2400 mm' \| picks: (4000,0) mm at px (728.3,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (12000,0) · keys Escape Escape · fields Options Strip: Width=2400 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=2400 reads '2400 mm' \| picks: (12000,0) mm at px (963.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add room at=(4000,2900) level=Ground name=\"Classroom 1\" number=101",
  "op:add room at=(12000,2900) level=Ground name=\"Classroom 2\" number=102",
  "op:add room at=(8000,6900) level=Ground name=\"Corridor\" number=103",
  "op:add ceiling at=(4000,2900) level=Ground height=2700 type=\"Suspended Tile 600 x 600\"",
  "op:add ceiling at=(12000,2900) level=Ground height=2700 type=\"Suspended Tile 600 x 600\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add room at=(4000,2900) level=Ground name="Classroom 1" number=101` | green: op:add room made=room-34ce0a59255f7d83 changed= ms=16 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(12000,2900) level=Ground name="Classroom 2" number=102` | green: op:add room made=room-d0a1dd401461f3c4 changed= ms=23 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |
| `op:add room at=(8000,6900) level=Ground name="Corridor" number=103` | green: op:add room made=room-c1b55afdc8cf4b8c changed= ms=18 Check "Rooms +1": Rooms 2 -> 3 (+1, expected +1) |
| `op:add ceiling at=(4000,2900) level=Ground height=2700 type="Suspended Tile 600 x 600"` | green: op:add ceiling made=ceiling-bc03895f965320c9 changed= ms=4 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `op:add ceiling at=(12000,2900) level=Ground height=2700 type="Suspended Tile 600 x 600"` | green: op:add ceiling made=ceiling-766448222baacc30 changed= ms=4 Check "Ceilings +1": Ceilings 1 -> 2 (+1, expected +1) |

### The result

The model holds: Ceilings 2,Doors 2,Levels 3,Openings 4,Rooms 3,Walls 6,Windows 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2049. Draw a 7 x 6 m granny flat: living room, bedroom and bathroom, a front door, two windows and a hip roof.

- Starts from: a new Architectural project
- Ends with: a 7 x 6 m brick veneer flat on Ground with two stud partitions, a slab, a front door, two windows, a hip roof on an Eaves level and rooms named Living, Bedroom and Bathroom
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(7000,0) level=Ground height=2700 type=\"Brick Veneer 251\"",
  "op:add wall from=(7000,0) to=(7000,6000) level=Ground height=2700 type=\"Brick Veneer 251\"",
  "op:add wall from=(7000,6000) to=(0,6000) level=Ground height=2700 type=\"Brick Veneer 251\"",
  "op:add wall from=(0,6000) to=(0,0) level=Ground height=2700 type=\"Brick Veneer 251\"",
  "op:add wall from=(4000,0) to=(4000,6000) level=Ground height=2700 type=\"Interior Stud 110\"",
  "op:add wall from=(4000,3000) to=(7000,3000) level=Ground height=2700 type=\"Interior Stud 110\"",
  "op:add floor boundary=(0,0) (7000,0) (7000,6000) (0,6000) level=Ground type=\"Concrete Slab 200 + Tile\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(7000,0) level=Ground height=2700 type="Brick Veneer 251"` | green: op:add wall made=wall-d54cc85e6142ebaf changed= ms=331 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(7000,0) to=(7000,6000) level=Ground height=2700 type="Brick Veneer 251"` | green: op:add wall made=wall-7d07c0acdf576820 changed=wall-d54cc85e6142ebaf ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(7000,6000) to=(0,6000) level=Ground height=2700 type="Brick Veneer 251"` | green: op:add wall made=wall-ea16613b8f2d56a6 changed=wall-7d07c0acdf576820 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground height=2700 type="Brick Veneer 251"` | green: op:add wall made=wall-248801601e119ff6 changed=wall-d54cc85e6142ebaf,wall-ea16613b8f2d56a6 ms=6 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(4000,0) to=(4000,6000) level=Ground height=2700 type="Interior Stud 110"` | green: op:add wall made=wall-588bfd5292120d8e changed= ms=7 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(4000,3000) to=(7000,3000) level=Ground height=2700 type="Interior Stud 110"` | green: op:add wall made=wall-bdb6b8f83c6c495d changed= ms=6 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add floor boundary=(0,0) (7000,0) (7000,6000) (0,6000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-842c3238a14d0801 changed= ms=6 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (1500,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Window · picks (5500,0) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1",
  "ribbon:Architecture:Window · picks (2000,6000) · keys Escape Escape · fields Options Strip: Width=1800 · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (1500,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (1500,0) mm at px (692.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (5500,0) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm' \| picks: (5500,0) mm at px (809.3,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (2000,6000) · keys Escape Escape · fields Options Strip: Width=1800 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1800 reads '1800 mm' \| picks: (2000,6000) mm at px (706.7,251.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add level elevation=2700 name=\"Eaves\"",
  "op:add roof boundary=(-400,-400) (7400,-400) (7400,6400) (-400,6400) level=Eaves slope=22 type=\"Concrete Tile Battens 90\"",
  "op:add room at=(2000,3000) level=Ground name=\"Living\" number=1",
  "op:add room at=(5500,1500) level=Ground name=\"Bedroom\" number=2",
  "op:add room at=(5500,4500) level=Ground name=\"Bathroom\" number=3"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=2700 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=2 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add roof boundary=(-400,-400) (7400,-400) (7400,6400) (-400,6400) level=Eaves slope=22 type="Concrete Tile Battens 90"` | green: op:add roof made=roof-d0589729b370497f changed= ms=5 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |
| `op:add room at=(2000,3000) level=Ground name="Living" number=1` | green: op:add room made=room-3e6e908048ab652d changed= ms=15 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(5500,1500) level=Ground name="Bedroom" number=2` | green: op:add room made=room-da5cb8d5d700b19c changed= ms=13 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |
| `op:add room at=(5500,4500) level=Ground name="Bathroom" number=3` | green: op:add room made=room-6b2a1e7b60b2839e changed= ms=224 Check "Rooms +1": Rooms 2 -> 3 (+1, expected +1) |

### The result

The model holds: Doors 1,Floors 1,Levels 4,Openings 3,Roofs 1,Rooms 3,Walls 6,Windows 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2050. Fit out a 12 x 8 m medical suite: a reception and waiting area at the front, two consulting rooms behind it with a door each, and a ceiling over reception.

- Starts from: a new Architectural project
- Ends with: a 12 x 8 m suite on Ground with a stud wall across it, a divider between two consulting rooms, an entry door, two consulting room doors, three named rooms and a ceiling over reception
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(12000,0) to=(12000,8000) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(12000,8000) to=(0,8000) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(0,8000) to=(0,0) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(0,3500) to=(12000,3500) level=Ground type=\"Interior Stud 110\"",
  "op:add wall from=(6000,3500) to=(6000,8000) level=Ground type=\"Interior Stud 110\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-143e9b32ef09faa9 changed= ms=17 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,8000) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-e7e6cab1038303d4 changed=wall-143e9b32ef09faa9 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(0,8000) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-095ed63c5dcac793 changed=wall-e7e6cab1038303d4 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-0fe48bab64e355de changed=wall-095ed63c5dcac793,wall-143e9b32ef09faa9 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(0,3500) to=(12000,3500) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-927aa44d04c7f820 changed= ms=8 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(6000,3500) to=(6000,8000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-c17c49c0ab18822e changed= ms=3 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (6000,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Doors +1",
  "ribbon:Architecture:Door · picks (3000,3500) · keys Escape Escape · fields Options Strip: Width=900 · expect Doors +1",
  "ribbon:Architecture:Door · picks (9000,3500) · keys Escape Escape · fields Options Strip: Width=900 · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (6000,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=1200 reads '1200 mm' \| picks: (6000,0) mm at px (824.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (3000,3500) · keys Escape Escape · fields Options Strip: Width=900 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=900 reads '900 mm' \| picks: (3000,3500) mm at px (736.0,324.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (9000,3500) · keys Escape Escape · fields Options Strip: Width=900 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=900 reads '900 mm' \| picks: (9000,3500) mm at px (912.0,324.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 2 -> 3 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add room at=(6000,1750) level=Ground name=\"Reception\" number=1",
  "op:add room at=(3000,5750) level=Ground name=\"Consult 1\" number=2",
  "op:add room at=(9000,5750) level=Ground name=\"Consult 2\" number=3",
  "op:add ceiling at=(6000,1750) level=Ground height=2700 type=\"Plasterboard on Grid\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add room at=(6000,1750) level=Ground name="Reception" number=1` | green: op:add room made=room-edcf4de375f91edb changed= ms=1837 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(3000,5750) level=Ground name="Consult 1" number=2` | green: op:add room made=room-559019b4a5cf9723 changed= ms=23 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |
| `op:add room at=(9000,5750) level=Ground name="Consult 2" number=3` | green: op:add room made=room-4cd23735696f9b97 changed= ms=20 Check "Rooms +1": Rooms 2 -> 3 (+1, expected +1) |
| `op:add ceiling at=(6000,1750) level=Ground height=2700 type="Plasterboard on Grid"` | green: op:add ceiling made=ceiling-d29cfb91aa1e3a71 changed= ms=4 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |

### The result

The model holds: Ceilings 1,Doors 3,Levels 3,Openings 3,Rooms 3,Walls 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2051. Draw a 10 x 6 m office, then cut a cross section through it and add a south elevation.

- Starts from: a new Architectural project
- Ends with: four walls and a floor on Ground, a section named Cut A1 through the middle and an elevation named Office South
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground",
  "op:add wall from=(10000,0) to=(10000,6000) level=Ground",
  "op:add wall from=(10000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0) (10000,0) (10000,6000) (0,6000) level=Ground",
  "op:add section from=(5000,-1500) to=(5000,7500) view=48660e38a721430d899d5d8a96df3bec name=\"Cut A1\"",
  "op:add elevation at=(5000,-4000) facing=south view=48660e38a721430d899d5d8a96df3bec name=\"Office South\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground` | green: op:add wall made=wall-5465ac67153e5e9b changed= ms=364 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,6000) level=Ground` | green: op:add wall made=wall-1cec572ee912e1b2 changed=wall-5465ac67153e5e9b ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-e7872f948f34f060 changed=wall-1cec572ee912e1b2 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-6e05d1983e929dbc changed=wall-e7872f948f34f060,wall-5465ac67153e5e9b ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (10000,0) (10000,6000) (0,6000) level=Ground` | green: op:add floor made=floor-b94ad465a9040363 changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add section from=(5000,-1500) to=(5000,7500) view=48660e38a721430d899d5d8a96df3bec name="Cut A1"` | green: op:add section made=6162a16d44ad4499b92ebea7721ea722 changed= ms=13 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `op:add elevation at=(5000,-4000) facing=south view=48660e38a721430d899d5d8a96df3bec name="Office South"` | green: op:add elevation made=elev-80a7fe4ddb764cf2 changed= ms=13 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 2,mark: Section 3,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 5,view: Floor Plan 4,view: Schedule 3,view: Section 3.

## 2052. Make a Level 1 plan for the walk-up and put it on a new sheet A900.

- Starts from: a new Architectural project
- Ends with: four walls on Level 1, a plan view named First Floor Plan and a sheet A900 carrying it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=\"Level 1\"",
  "op:add wall from=(10000,0) to=(10000,6000) level=\"Level 1\"",
  "op:add wall from=(10000,6000) to=(0,6000) level=\"Level 1\"",
  "op:add wall from=(0,6000) to=(0,0) level=\"Level 1\"",
  "op:add view kind=plan level=\"Level 1\" name=\"First Floor Plan\"",
  "op:add sheet number=A900 name=\"First Floor\"",
  "op:place view view=\"First Floor Plan\" sheet=A900"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level="Level 1"` | green: op:add wall made=wall-11a86a58723cb7e1 changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,6000) level="Level 1"` | green: op:add wall made=wall-937fe013cdc353a3 changed=wall-11a86a58723cb7e1 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,6000) to=(0,6000) level="Level 1"` | green: op:add wall made=wall-39b1bac3c9f69626 changed=wall-937fe013cdc353a3 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-2f16770ea578fbce changed=wall-39b1bac3c9f69626,wall-11a86a58723cb7e1 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add view kind=plan level="Level 1" name="First Floor Plan"` | green: op:add view made=1dfd2e854ae04a40b73f1c8bf4fbdefb changed= ms=8 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add sheet number=A900 name="First Floor"` | green: op:add sheet made=sheet-A900 changed= ms=3 Check "sheet A900 exists": sheet A900 exists (9 sheet(s) in the document) |
| `op:place view view="First Floor Plan" sheet=A900` | green: op:place view made=1dfd2e854ae04a40b73f1c8bf4fbdefb::sheet-A900::5ca0695470c240a28b1b6b9f2f4cb56d changed= ms=3 Check "sheet A900 exists": sheet A900 exists (9 sheet(s) in the document) |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2053. Hang three doors in the hall and list them in a door schedule with their type and width.

- Starts from: a new Architectural project
- Ends with: a hall outline with three doors and a schedule named Hall Doors listing mark, type and width
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground",
  "op:add wall from=(12000,0) to=(12000,6000) level=Ground",
  "op:add wall from=(12000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground` | green: op:add wall made=wall-15e242c34e38cd03 changed= ms=454 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,6000) level=Ground` | green: op:add wall made=wall-778dd9123de86c9c changed=wall-15e242c34e38cd03 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-843bc589b791c344 changed=wall-778dd9123de86c9c ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-c41249b882405351 changed=wall-843bc589b791c344,wall-15e242c34e38cd03 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Door · picks (6000,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Doors +1",
  "ribbon:Architecture:Door · picks (12000,3000) · keys Escape Escape · fields — · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (2000,0) mm at px (706.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (6000,0) · keys Escape Escape · fields Options Strip: Width=1200 · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| fields: Width=1200 reads '1200 mm' \| picks: (6000,0) mm at px (824.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (12000,3000) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (12000,3000) mm at px (1000.0,339.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 2 -> 3 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=Doors fields=Mark,Type,Width name=\"Hall Doors\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category=Doors fields=Mark,Type,Width name="Hall Doors"` | green: op:add schedule made=ba72daa90d47436d9ac1d729fa68b6e1 changed= ms=325 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

### The result

The model holds: Doors 3,Levels 3,Openings 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 2054. Draw the 8 x 5 m cottage and add a north, south, east and west elevation named for it.

- Starts from: a new Architectural project
- Ends with: four walls and a floor on Ground and four elevation views named Cottage North, Cottage South, Cottage East and Cottage West
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,5000) level=Ground",
  "op:add wall from=(8000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0) (8000,0) (8000,5000) (0,5000) level=Ground",
  "op:add elevation at=(4000,7500) facing=south view=48660e38a721430d899d5d8a96df3bec name=\"Cottage North\"",
  "op:add elevation at=(4000,-2500) facing=north view=48660e38a721430d899d5d8a96df3bec name=\"Cottage South\"",
  "op:add elevation at=(10500,2500) facing=west view=48660e38a721430d899d5d8a96df3bec name=\"Cottage East\"",
  "op:add elevation at=(-2500,2500) facing=east view=48660e38a721430d899d5d8a96df3bec name=\"Cottage West\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-636069e0de01e1ad changed= ms=152 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,5000) level=Ground` | green: op:add wall made=wall-ac16e223890c1a78 changed=wall-636069e0de01e1ad ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-dc09510a042462d6 changed=wall-ac16e223890c1a78 ms=10 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-87be4c06723dfe44 changed=wall-636069e0de01e1ad,wall-dc09510a042462d6 ms=49 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (8000,0) (8000,5000) (0,5000) level=Ground` | green: op:add floor made=floor-8fc34f309cc4edf3 changed= ms=1 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add elevation at=(4000,7500) facing=south view=48660e38a721430d899d5d8a96df3bec name="Cottage North"` | green: op:add elevation made=elev-feec5cadd08c4224 changed= ms=139 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) |
| `op:add elevation at=(4000,-2500) facing=north view=48660e38a721430d899d5d8a96df3bec name="Cottage South"` | green: op:add elevation made=elev-8079f8181aca42a4 changed= ms=11 Check "view: Elevation +1": view: Elevation 5 -> 6 (+1, expected +1) |
| `op:add elevation at=(10500,2500) facing=west view=48660e38a721430d899d5d8a96df3bec name="Cottage East"` | green: op:add elevation made=elev-5a2a66d36604444f changed= ms=9 Check "view: Elevation +1": view: Elevation 6 -> 7 (+1, expected +1) |
| `op:add elevation at=(-2500,2500) facing=east view=48660e38a721430d899d5d8a96df3bec name="Cottage West"` | green: op:add elevation made=elev-a7d41cfe53b64fc6 changed= ms=110 Check "view: Elevation +1": view: Elevation 7 -> 8 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 5,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 8,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2055. Cut a long section through the 12 x 6 m office and put the plan and the section together on a new A1 sheet.

- Starts from: a new Architectural project
- Ends with: four walls and a floor on Ground, a plan view Office Plan, a section Cut B1 and a sheet A902 carrying both
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground",
  "op:add wall from=(12000,0) to=(12000,6000) level=Ground",
  "op:add wall from=(12000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0) (12000,0) (12000,6000) (0,6000) level=Ground",
  "op:add view kind=plan level=Ground name=\"Office Plan\"",
  "op:add section from=(6000,-1500) to=(6000,7500) view=\"Office Plan\" name=\"Cut B1\"",
  "op:add sheet number=A902 name=\"Office Plan and Section\" titleblock=A1",
  "op:place view view=\"Office Plan\" sheet=A902 at=(40,500)",
  "op:place view view=\"Cut B1\" sheet=A902 at=(450,500)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground` | green: op:add wall made=wall-c594397fccae97cd changed= ms=403 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,6000) level=Ground` | green: op:add wall made=wall-8c63eb38ddc44121 changed=wall-c594397fccae97cd ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-ba208ae08dab7efc changed=wall-8c63eb38ddc44121 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-22f20aab0273048a changed=wall-ba208ae08dab7efc,wall-c594397fccae97cd ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (12000,0) (12000,6000) (0,6000) level=Ground` | green: op:add floor made=floor-fe9d59c169cdf67f changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add view kind=plan level=Ground name="Office Plan"` | green: op:add view made=3fe5b2fa5b834c25bd888bd9aafdd7bd changed= ms=10 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add section from=(6000,-1500) to=(6000,7500) view="Office Plan" name="Cut B1"` | green: op:add section made=85642131ce214e338313a96b2d0cfc2b changed= ms=9 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `op:add sheet number=A902 name="Office Plan and Section" titleblock=A1` | green: op:add sheet made=sheet-A902 changed= ms=2 Check "sheet A902 exists": sheet A902 exists (9 sheet(s) in the document) |
| `op:place view view="Office Plan" sheet=A902 at=(40,500)` | green: op:place view made=3fe5b2fa5b834c25bd888bd9aafdd7bd::sheet-A902::57b9ac65f8e64b6d894a21d5999a37de changed= ms=40 note=the frame is 264.9 x 264.9 mm and its lower-left corner stands at (40,500) in sheet mm and it runs off the sheet, which is 841 x 594 mm Check "sheet A902 exists": sheet A902 exists (9 sheet(s) in the document) |
| `op:place view view="Cut B1" sheet=A902 at=(450,500)` | green: op:place view made=85642131ce214e338313a96b2d0cfc2b::sheet-A902::1c3d70d80290498aa6a0f874da419aa7 changed= ms=32 Check "sheet A902 exists": sheet A902 exists (9 sheet(s) in the document) |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 3,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 3.

## 2056. Dimension the 10 x 6 m office on a plan of its own: the south wall, the west wall and the east wall, with a note.

- Starts from: a new Architectural project
- Ends with: four walls on Ground, a plan view Dimension Plan carrying three overall dimensions and a note
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground",
  "op:add wall from=(10000,0) to=(10000,6000) level=Ground",
  "op:add wall from=(10000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add view kind=plan level=Ground name=\"Dimension Plan\"",
  "op:add dimension from=(0,0) to=(10000,0) view=\"Dimension Plan\" offset=-900",
  "op:add dimension from=(0,0) to=(0,6000) view=\"Dimension Plan\" offset=900",
  "op:add dimension from=(10000,0) to=(10000,6000) view=\"Dimension Plan\" offset=-900",
  "op:add text at=(1000,3000) view=\"Dimension Plan\" text=\"OFFICE 60 m2\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground` | green: op:add wall made=wall-536a12c0599763d3 changed= ms=11 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,6000) level=Ground` | green: op:add wall made=wall-d234e552148ddb56 changed=wall-536a12c0599763d3 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-85b6afed055025b0 changed=wall-d234e552148ddb56 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-8a4971093042b3a9 changed=wall-536a12c0599763d3,wall-85b6afed055025b0 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add view kind=plan level=Ground name="Dimension Plan"` | green: op:add view made=2e8ab2409c234fa7af464e02229fabef changed= ms=13 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(10000,0) view="Dimension Plan" offset=-900` | green: op:add dimension made=dim-63adc935458f4042 changed= ms=152 note=offset -900: the dimension line stands 900 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(0,6000) view="Dimension Plan" offset=900` | green: op:add dimension made=dim-293f502b82094ed3 changed= ms=15 note=offset 900: the dimension line stands 900 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 1 -> 2 (+1, expected +1) |
| `op:add dimension from=(10000,0) to=(10000,6000) view="Dimension Plan" offset=-900` | green: op:add dimension made=dim-6329a2eb50d64e9a changed= ms=15 note=offset -900: the dimension line stands 900 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 2 -> 3 (+1, expected +1) |
| `op:add text at=(1000,3000) view="Dimension Plan" text="OFFICE 60 m2"` | green: op:add text made=text-18fbaa3829ff4148 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 3,Levels 3,Text Notes 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2057. Divide the 9 x 5 m flat into two rooms, name them and list the rooms in a schedule with number, name and area.

- Starts from: a new Architectural project
- Ends with: a 9 x 5 m flat on Ground with a stud partition, two rooms named Lounge and Bedroom and a schedule named Flat Rooms
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground",
  "op:add wall from=(9000,0) to=(9000,5000) level=Ground",
  "op:add wall from=(9000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground",
  "op:add wall from=(5500,0) to=(5500,5000) level=Ground type=\"Interior Stud 110\"",
  "op:add room at=(2750,2500) level=Ground name=\"Lounge\" number=1",
  "op:add room at=(7250,2500) level=Ground name=\"Bedroom\" number=2",
  "op:add schedule category=Rooms fields=Number,Name,Area name=\"Flat Rooms\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground` | green: op:add wall made=wall-aae987dc3df84534 changed= ms=15 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,5000) level=Ground` | green: op:add wall made=wall-6f9a01368fe063cf changed=wall-aae987dc3df84534 ms=10 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-7bff31365f3f7405 changed=wall-6f9a01368fe063cf ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-514799297860976a changed=wall-aae987dc3df84534,wall-7bff31365f3f7405 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(5500,0) to=(5500,5000) level=Ground type="Interior Stud 110"` | green: op:add wall made=wall-976b46c3473deb03 changed= ms=6 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add room at=(2750,2500) level=Ground name="Lounge" number=1` | green: op:add room made=room-3a8c67faf8f1c0d9 changed= ms=17 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(7250,2500) level=Ground name="Bedroom" number=2` | green: op:add room made=room-002d03fc30974f09 changed= ms=15 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |
| `op:add schedule category=Rooms fields=Number,Name,Area name="Flat Rooms"` | green: op:add schedule made=cf78a26e65bb4c1fb11ace34d6fea817 changed= ms=7 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Rooms 2,Walls 5,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 2058. Add a mezzanine level at 2400 over the end of the 12 x 8 m workshop with its own plan and a floor slab.

- Starts from: a new Architectural project
- Ends with: four walls on Ground, a Mezzanine level at 2400 with its own floor plan and a 12 x 3 m floor slab on it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground height=5400",
  "op:add wall from=(12000,0) to=(12000,8000) level=Ground height=5400",
  "op:add wall from=(12000,8000) to=(0,8000) level=Ground height=5400",
  "op:add wall from=(0,8000) to=(0,0) level=Ground height=5400",
  "op:add level elevation=2400 name=\"Mezzanine\"",
  "op:add view kind=plan level=Mezzanine name=\"Mezzanine Plan\"",
  "op:add floor boundary=(0,5000) (12000,5000) (12000,8000) (0,8000) level=Mezzanine type=\"Timber Joist and Ply 240\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground height=5400` | green: op:add wall made=wall-0a2b8fe8ee99be09 changed= ms=342 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,8000) level=Ground height=5400` | green: op:add wall made=wall-e1d11ce492d3bc9e changed=wall-0a2b8fe8ee99be09 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(0,8000) level=Ground height=5400` | green: op:add wall made=wall-e61f0cbec26edaf1 changed=wall-e1d11ce492d3bc9e ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground height=5400` | green: op:add wall made=wall-4a2c6a891c68e951 changed=wall-0a2b8fe8ee99be09,wall-e61f0cbec26edaf1 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add level elevation=2400 name="Mezzanine"` | green: op:add level made=level-Mezzanine changed= ms=1 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add view kind=plan level=Mezzanine name="Mezzanine Plan"` | green: op:add view made=ca60a71e648446429327583649121f27 changed= ms=6 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add floor boundary=(0,5000) (12000,5000) (12000,8000) (0,8000) level=Mezzanine type="Timber Joist and Ply 240"` | green: op:add floor made=floor-b7c0e6b6257b336d changed= ms=5 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 4,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2059. Raise Level 1 to 3600 for a tall ground floor and stand the upper walls on it.

- Starts from: a new Architectural project
- Ends with: four walls on Ground, Level 1 raised to 3600 and four walls on Level 1 reaching up to Roof
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground",
  "op:add wall from=(9000,0) to=(9000,6000) level=Ground",
  "op:add wall from=(9000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:set id=\"level-Level 1\" key=Elevation value=3600",
  "op:add wall from=(0,0) to=(9000,0) level=\"Level 1\" top=Roof",
  "op:add wall from=(9000,0) to=(9000,6000) level=\"Level 1\" top=Roof",
  "op:add wall from=(9000,6000) to=(0,6000) level=\"Level 1\" top=Roof",
  "op:add wall from=(0,6000) to=(0,0) level=\"Level 1\" top=Roof"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground` | green: op:add wall made=wall-482152cd1131d511 changed= ms=378 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level=Ground` | green: op:add wall made=wall-791bec94398ccc5b changed=wall-482152cd1131d511 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-0435bdb03a711672 changed=wall-791bec94398ccc5b ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-34b19eab17f50fe5 changed=wall-0435bdb03a711672,wall-482152cd1131d511 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:set id="level-Level 1" key=Elevation value=3600` | green: op:set made= changed="level-Level 1",wall-482152cd1131d511,wall-791bec94398ccc5b,wall-0435bdb03a711672,wall-34b19eab17f50fe5 ms=5 Check "Levels =3": Levels = 3 (expected 3) |
| `op:add wall from=(0,0) to=(9000,0) level="Level 1" top=Roof` | green: op:add wall made=wall-2e39f1a670d66b7a changed= ms=2 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level="Level 1" top=Roof` | green: op:add wall made=wall-763a3c3389ebfa52 changed=wall-2e39f1a670d66b7a ms=3 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level="Level 1" top=Roof` | green: op:add wall made=wall-3094885c7b38582c changed=wall-763a3c3389ebfa52 ms=8 Check "Walls +1": Walls 6 -> 7 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level="Level 1" top=Roof` | green: op:add wall made=wall-348c1936b5f3e43b changed=wall-3094885c7b38582c,wall-2e39f1a670d66b7a ms=2 Check "Walls +1": Walls 7 -> 8 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 8,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2060. Roof the 12 x 6 m workshop with a gable roof and hang a gutter on each long eave.

- Starts from: a new Architectural project
- Ends with: four walls 2800 high on Ground, a gable roof picked from them on an Eaves level at 2600, and a gutter on the south and the north eave
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground height=2800",
  "op:add wall from=(12000,0) to=(12000,6000) level=Ground height=2800",
  "op:add wall from=(12000,6000) to=(0,6000) level=Ground height=2800",
  "op:add wall from=(0,6000) to=(0,0) level=Ground height=2800",
  "op:add level elevation=2600 name=\"Eaves\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground height=2800` | green: op:add wall made=wall-ace50a3795c07621 changed= ms=10 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,6000) level=Ground height=2800` | green: op:add wall made=wall-2a16b99a4914510e changed=wall-ace50a3795c07621 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,6000) to=(0,6000) level=Ground height=2800` | green: op:add wall made=wall-69b962fc50c314dc changed=wall-2a16b99a4914510e ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground height=2800` | green: op:add wall made=wall-1864d7b907f74b22 changed=wall-ace50a3795c07621,wall-69b962fc50c314dc ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add level elevation=2600 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=2 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed",
  "ribbon:Architecture:Roof · picks (6000,0) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=300 · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (12000,3000) · keys — · fields Options Strip: Defines Slope=no · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (6000,6000) · keys — · fields Options Strip: Defines Slope=yes · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (0,3000) · keys Return · fields Options Strip: Defines Slope=no · expect Roofs +1",
  "ribbon:Architecture:Roof: Gutter · picks (6000,-300) · keys Escape Escape · fields — · expect Gutters +1",
  "ribbon:Architecture:Roof: Gutter · picks (6000,6300) · keys Escape Escape · fields — · expect Gutters +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Eaves · expect dialog closed` | green: pressed 'Plan Views › Floor Plan' on View's Create panel (through its parent 'Plan Views''s arrow, the row 'Floor Plan'; the press stood 402 ms (the menu stood at 361 ms; its row ran 41 ms; the window's first paint at 41 ms in union_shell::ShellDialogWindow, dialog 'New Plan'; the dialog stood 1093 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'New Plan' opened and stood; closed by the player \| inside the modal 'New Plan' \| fields: table 'Levels' row 'Eaves' pressed, reads New 'yes' \| keys: Return (no tool, dialog 'New Plan' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window; 'Plan Views › Floor Plan' opens no dialog (its door is an action), so the step's Return went to the viewport |
| `ribbon:Architecture:Roof · picks (6000,0) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=300 · expect nothing selected` | green: pressed 'Roof' on Architecture's Build panel: the tool 'Roof' stands \| fields: Draw=Pick Walls set; Defines Slope=yes reads yes; Overhang=300 reads '300 mm' \| picks: (6000,0) mm at px (824.0,427.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (12000,3000) · keys — · fields Options Strip: Defines Slope=no · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=no reads no \| picks: (12000,3000) mm at px (1000.0,339.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (6000,6000) · keys — · fields Options Strip: Defines Slope=yes · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=yes reads yes \| picks: (6000,6000) mm at px (824.0,251.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (0,3000) · keys Return · fields Options Strip: Defines Slope=no · expect Roofs +1` | green: PlanNavBarZoomToFit pressed; a command ran; tool Roof standing \| fields: Defines Slope=no reads no \| picks: (0,3000) mm at px (648.0,339.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Return (tool Roof -> no tool) Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Roof: Gutter · picks (6000,-300) · keys Escape Escape · fields — · expect Gutters +1` | green: pressed 'Roof: Gutter' on Architecture's Build panel: the tool 'Roof: Gutter' stands \| picks: (6000,-300) mm at px (824.0,435.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Roof: Gutter -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Gutters +1": Gutters 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Roof: Gutter · picks (6000,6300) · keys Escape Escape · fields — · expect Gutters +1` | green: pressed 'Roof: Gutter' on Architecture's Build panel: the tool 'Roof: Gutter' stands \| picks: (6000,6300) mm at px (824.0,242.2) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Roof: Gutter -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Gutters +1": Gutters 1 -> 2 (+1, expected +1) |

### The result

The model holds: Gutters 2,Levels 4,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 2061. Ceiling the 6 x 4 m office at 2700 and make a reflected ceiling plan of it named Office RCP.

- Starts from: a new Architectural project
- Ends with: four walls and a ceiling 2700 above Ground and a ceiling plan view named Office RCP
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add ceiling at=(3000,2000) level=Ground height=2700 type=\"Compound Ceiling 600 x 600\"",
  "op:add view kind=ceiling level=Ground name=\"Office RCP\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-02acd99f574d93ec changed= ms=10 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-d000cdebb06056b1 changed=wall-02acd99f574d93ec ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-feac53a510ec9fd7 changed=wall-d000cdebb06056b1 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-0af37571428b6876 changed=wall-feac53a510ec9fd7,wall-02acd99f574d93ec ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add ceiling at=(3000,2000) level=Ground height=2700 type="Compound Ceiling 600 x 600"` | green: op:add ceiling made=ceiling-8fad0098f8af227f changed= ms=9 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `op:add view kind=ceiling level=Ground name="Office RCP"` | green: op:add view made=d7b52178a0ca45019010525b85f68ab7 changed= ms=15 Check "view: Ceiling Plan +1": view: Ceiling Plan 3 -> 4 (+1, expected +1) |

### The result

The model holds: Ceilings 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 4,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2062. Draw an eight-sided gazebo, 5 m across the flats, and place a room named Gazebo inside it.

- Starts from: a new Architectural project
- Ends with: eight walls in an octagon on Ground and one room named Gazebo inside them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:Wall · picks (6000,5000) (8500,5000) · keys Escape Escape · fields Options Strip: Draw=Circumscribed Polygon; Sides=8 · expect Walls +8"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Wall · picks (6000,5000) (8500,5000) · keys Escape Escape · fields Options Strip: Draw=Circumscribed Polygon; Sides=8 · expect Walls +8` | green: pressed 'Wall: Architectural' on Architecture's Build panel: the command 'Wall: Architectural' ran; status 'Click to start the wall' ('Wall' is the word of Architecture's Build panel button 'Wall: Architectural') \| fields: Draw=Circumscribed Polygon set; Sides=8 reads '8.00' \| picks: (6000,5000) mm at px (824.0,280.3) on the plan view \| (8500,5000) mm at px (897.3,280.3) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Walls +8": Walls 0 -> 8 (+8, expected +8) |

```json
ops_run {"lines":[
  "op:add room at=(6000,5000) level=Ground name=\"Gazebo\" number=1"
]}
```

| Line | UNION answered |
|---|---|
| `op:add room at=(6000,5000) level=Ground name="Gazebo" number=1` | green: op:add room made=room-4dafa4d386a71887 changed= ms=15 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Rooms 1,Walls 8,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2063. Draw a 6 x 6 m pavilion and lay its floor by picking the walls.

- Starts from: a new Architectural project
- Ends with: four walls on Ground and a floor made by picking them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,6000) level=Ground",
  "op:add wall from=(6000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-f8af4cea94ce7fd1 changed= ms=15 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,6000) level=Ground` | green: op:add wall made=wall-e1e501cea4eb3fba changed=wall-f8af4cea94ce7fd1 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-5660369feede5b49 changed=wall-e1e501cea4eb3fba ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-285d518cd4f1c0ab changed=wall-5660369feede5b49,wall-f8af4cea94ce7fd1 ms=31 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Floor: Architectural · picks (3000,0) · keys — · fields Options Strip: Draw=Pick Walls · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (6000,3000) · keys — · fields — · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (3000,6000) · keys — · fields — · expect nothing selected",
  "chrome:Canvas Zoom to Fit · picks (0,3000) · keys — · fields — · expect nothing selected",
  "contextual:Finish · picks — · keys — · fields — · expect Floors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Floor: Architectural · picks (3000,0) · keys — · fields Options Strip: Draw=Pick Walls · expect nothing selected` | green: pressed 'Floor: Architectural' on Architecture's Build panel: the command 'Floor: Architectural' ran; status 'Sketch the floor boundary, then Finish' \| fields: Draw=Pick Walls set \| picks: (3000,0) mm at px (736.0,427.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (6000,3000) · keys — · fields — · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Floor standing \| picks: (6000,3000) mm at px (824.0,339.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (3000,6000) · keys — · fields — · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Floor standing \| picks: (3000,6000) mm at px (736.0,251.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `chrome:Canvas Zoom to Fit · picks (0,3000) · keys — · fields — · expect nothing selected` | green: PlanNavBarZoomToFit pressed; a command ran; tool Floor standing \| picks: (0,3000) mm at px (648.0,339.0) on the plan view \| presses to the tool 1, selection unchanged Check "nothing selected": 0 selected |
| `contextual:Finish · picks — · keys — · fields — · expect Floors +1` | green: contextual 'Finish' on 'Modify \| Create Floor Boundary': pressed 'Finish' on Modify \| Create Floor Boundary's Mode panel: the command 'Finish' ran Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2064. Draw a 6 x 4 m office, put the last wall in the wrong place, undo it and draw it right.

- Starts from: a new Architectural project
- Ends with: four walls on Ground forming a 6 x 4 m office after one wall was drawn wrongly, undone and redrawn
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(500,500) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-041e02fb47a8f24e changed= ms=517 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-eade966c927ecfa0 changed=wall-041e02fb47a8f24e ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-454dd9ef143fbe70 changed=wall-eade966c927ecfa0 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(500,500) level=Ground` | green: op:add wall made=wall-1540ed7e43ff8a28 changed=wall-454dd9ef143fbe70 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect Walls =3"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect Walls =3` | green: QToolButton pressed; a command ran Check "Walls =3": Walls = 3 (expected 3) |

```json
ops_run {"lines":[
  "op:add wall from=(0,4000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-96a13798e1015718 changed=wall-041e02fb47a8f24e,wall-454dd9ef143fbe70 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2065. Set out grid lines A, B and C at 5 m centres with grids 1 and 2 across them and dimension the three lines as a string.

- Starts from: a new Architectural project
- Ends with: three vertical grids A, B, C at 0, 5000 and 10000, two horizontal grids 1 and 2, and one dimension string across A, B and C
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:add grid from=(5000,-2000) to=(5000,8000) name=B",
  "op:add grid from=(10000,-2000) to=(10000,8000) name=C",
  "op:add grid from=(-2000,0) to=(12000,0) name=1",
  "op:add grid from=(-2000,6000) to=(12000,6000) name=2",
  "op:add dimension chain points=(0,-1000) (5000,-1000) (10000,-1000) view=48660e38a721430d899d5d8a96df3bec offset=-1500"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=322 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(5000,-2000) to=(5000,8000) name=B` | green: op:add grid made=grid-B changed= ms=2 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(10000,-2000) to=(10000,8000) name=C` | green: op:add grid made=grid-C changed= ms=2 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add grid from=(-2000,0) to=(12000,0) name=1` | green: op:add grid made=grid-1 changed= ms=2 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |
| `op:add grid from=(-2000,6000) to=(12000,6000) name=2` | green: op:add grid made=grid-2 changed= ms=3 Check "Grids +1": Grids 4 -> 5 (+1, expected +1) |
| `op:add dimension chain points=(0,-1000) (5000,-1000) (10000,-1000) view=48660e38a721430d899d5d8a96df3bec offset=-1500` | green: op:add dimension chain made=dimstr-f6fbc177889c427a changed= ms=2023 note=segments 5000, 5000; offset -1500: the dimension line stands 1500 mm to the right of the direction from the first point to the last (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Grids 5,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2066. Click out a U-shaped school wing, 16 x 7 m overall round a 6 m courtyard, and slab it.

- Starts from: a new Architectural project
- Ends with: eight closed walls forming a U on Ground and a floor slab inside them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Architecture:Wall · picks (0,0) (16000,0) (16000,7000) (11000,7000) (11000,3000) (5000,3000) (5000,7000) (0,7000) (0,0) · keys Escape Escape · fields — · expect Walls +8"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Wall · picks (0,0) (16000,0) (16000,7000) (11000,7000) (11000,3000) (5000,3000) (5000,7000) (0,7000) (0,0) · keys Escape Escape · fields — · expect Walls +8` | green: pressed 'Wall: Architectural' on Architecture's Build panel: the command 'Wall: Architectural' ran; status 'Click to start the wall' ('Wall' is the word of Architecture's Build panel button 'Wall: Architectural') \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (16000,0) mm at px (1117.4,427.0) on the plan view \| (16000,7000) mm at px (1117.4,221.7) on the plan view \| (11000,7000) mm at px (970.7,221.7) on the plan view \| (11000,3000) mm at px (970.7,339.0) on the plan view \| (5000,3000) mm at px (794.7,339.0) on the plan view \| (5000,7000) mm at px (794.7,221.7) on the plan view \| (0,7000) mm at px (648.0,221.7) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 9, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +8": Walls 0 -> 8 (+8, expected +8) |

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0) (16000,0) (16000,7000) (11000,7000) (11000,3000) (5000,3000) (5000,7000) (0,7000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0) (16000,0) (16000,7000) (11000,7000) (11000,3000) (5000,3000) (5000,7000) (0,7000) level=Ground` | green: op:add floor made=floor-538a7a308a1e1745 changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

### The result

The model holds: Floors 1,Levels 3,Walls 8,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2067. Draw a 6 x 6 m atrium with walls to the Roof level, a slab, a ceiling at 5700 and a flat roof.

- Starts from: a new Architectural project
- Ends with: four walls from Ground up to Roof, a slab on Ground, a ceiling 5700 above Ground and a flat roof at the Roof level
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground top=Roof",
  "op:add wall from=(6000,0) to=(6000,6000) level=Ground top=Roof",
  "op:add wall from=(6000,6000) to=(0,6000) level=Ground top=Roof",
  "op:add wall from=(0,6000) to=(0,0) level=Ground top=Roof",
  "op:add floor boundary=(0,0) (6000,0) (6000,6000) (0,6000) level=Ground type=\"Concrete Slab 200 + Tile\"",
  "op:add ceiling at=(3000,3000) level=Ground height=5700 type=\"Plain Ceiling 13 mm\"",
  "op:add roof boundary=(0,0) (6000,0) (6000,6000) (0,6000) level=Roof slope=0 type=\"Concrete Inverted Membrane 250\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground top=Roof` | green: op:add wall made=wall-a47d38d108aa25a6 changed= ms=9 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,6000) level=Ground top=Roof` | green: op:add wall made=wall-a3e8df48ef7d9697 changed=wall-a47d38d108aa25a6 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,6000) to=(0,6000) level=Ground top=Roof` | green: op:add wall made=wall-085eed8b954897a1 changed=wall-a3e8df48ef7d9697 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground top=Roof` | green: op:add wall made=wall-e0f22d23f400669c changed=wall-085eed8b954897a1,wall-a47d38d108aa25a6 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0) (6000,0) (6000,6000) (0,6000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-564dad67026d1199 changed= ms=45 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add ceiling at=(3000,3000) level=Ground height=5700 type="Plain Ceiling 13 mm"` | green: op:add ceiling made=ceiling-49d7e15430c24ade changed= ms=6 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `op:add roof boundary=(0,0) (6000,0) (6000,6000) (0,6000) level=Roof slope=0 type="Concrete Inverted Membrane 250"` | green: op:add roof made=roof-3c23b2d954afcccb changed= ms=6 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Ceilings 1,Floors 1,Levels 3,Roofs 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2068. Roof the L-shaped house with one 25 degree hip roof over both wings.

- Starts from: a new Architectural project
- Ends with: six walls forming an L on Ground and one 25 degree hip roof over the L outline on an Eaves level
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground height=2700",
  "op:add wall from=(12000,0) to=(12000,4000) level=Ground height=2700",
  "op:add wall from=(12000,4000) to=(6000,4000) level=Ground height=2700",
  "op:add wall from=(6000,4000) to=(6000,8000) level=Ground height=2700",
  "op:add wall from=(6000,8000) to=(0,8000) level=Ground height=2700",
  "op:add wall from=(0,8000) to=(0,0) level=Ground height=2700",
  "op:add level elevation=2700 name=\"Eaves\"",
  "op:add roof boundary=(-400,-400) (12400,-400) (12400,4400) (6400,4400) (6400,8400) (-400,8400) level=Eaves slope=25 type=\"Concrete Tile Battens 140\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground height=2700` | green: op:add wall made=wall-f5e4729dde8d36d3 changed= ms=483 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,4000) level=Ground height=2700` | green: op:add wall made=wall-14ad05f27b29faf7 changed=wall-f5e4729dde8d36d3 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,4000) to=(6000,4000) level=Ground height=2700` | green: op:add wall made=wall-ad538133b527b659 changed=wall-14ad05f27b29faf7 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(6000,8000) level=Ground height=2700` | green: op:add wall made=wall-a5b9538b5d8891c9 changed=wall-ad538133b527b659 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(6000,8000) to=(0,8000) level=Ground height=2700` | green: op:add wall made=wall-a0fae9928abcc718 changed=wall-a5b9538b5d8891c9 ms=2 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground height=2700` | green: op:add wall made=wall-61e8c802ef7e346b changed=wall-a0fae9928abcc718,wall-f5e4729dde8d36d3 ms=4 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add level elevation=2700 name="Eaves"` | green: op:add level made=level-Eaves changed= ms=2 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add roof boundary=(-400,-400) (12400,-400) (12400,4400) (6400,4400) (6400,8400) (-400,8400) level=Eaves slope=25 type="Concrete Tile Battens 140"` | green: op:add roof made=roof-55d608d0e9f5e9f8 changed= ms=6 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 4,Roofs 1,Walls 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2069. Add a third storey to the block: make the Roof level Level 2, put a new Top Roof at 9000 and stand the walls on Level 2.

- Starts from: a new Architectural project
- Ends with: four walls on Ground and on Level 1, the old Roof level renamed Level 2, a new Top Roof level at 9000 and four walls on Level 2 reaching up to it
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=Ground",
  "op:add wall from=(9000,0) to=(9000,6000) level=Ground",
  "op:add wall from=(9000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:set id=level-Roof key=Name value=\"Level 2\"",
  "op:add level elevation=9000 name=\"Top Roof\"",
  "op:add wall from=(0,0) to=(9000,0) level=\"Level 2\" top=\"Top Roof\"",
  "op:add wall from=(9000,0) to=(9000,6000) level=\"Level 2\" top=\"Top Roof\"",
  "op:add wall from=(9000,6000) to=(0,6000) level=\"Level 2\" top=\"Top Roof\"",
  "op:add wall from=(0,6000) to=(0,0) level=\"Level 2\" top=\"Top Roof\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level=Ground` | green: op:add wall made=wall-9c29eef36413527f changed= ms=9 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level=Ground` | green: op:add wall made=wall-1a4f2e48b3236bd9 changed=wall-9c29eef36413527f ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-3737aa5e8930f66e changed=wall-1a4f2e48b3236bd9 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-5250286275c6c7d4 changed=wall-9c29eef36413527f,wall-3737aa5e8930f66e ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:set id=level-Roof key=Name value="Level 2"` | green: op:set made= changed=level-Roof ms=5 Check "Levels =3": Levels = 3 (expected 3) |
| `op:add level elevation=9000 name="Top Roof"` | green: op:add level made="level-Top Roof" changed= ms=7 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add wall from=(0,0) to=(9000,0) level="Level 2" top="Top Roof"` | green: op:add wall made=wall-3f1b007f3f760b4e changed= ms=3 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level="Level 2" top="Top Roof"` | green: op:add wall made=wall-aa6b0aa7cdc56d2f changed=wall-3f1b007f3f760b4e ms=3 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level="Level 2" top="Top Roof"` | green: op:add wall made=wall-6a5e0e3197ab05d9 changed=wall-aa6b0aa7cdc56d2f ms=2 Check "Walls +1": Walls 6 -> 7 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level="Level 2" top="Top Roof"` | green: op:add wall made=wall-e2d99727e271a843 changed=wall-3f1b007f3f760b4e,wall-6a5e0e3197ab05d9 ms=2 Check "Walls +1": Walls 7 -> 8 (+1, expected +1) |

### The result

The model holds: Levels 4,Walls 8,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2070. Build an entrance portico, 6 x 3 m, on a slab with a column at each corner and a flat roof over it.

- Starts from: a new Architectural project
- Ends with: a 6 x 3 m slab on Ground, four architectural columns at its corners and a flat concrete roof at Level 1 over them
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0) (6000,0) (6000,3000) (0,3000) level=Ground type=\"Concrete Slab 200 + Tile\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0) (6000,0) (6000,3000) (0,3000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-3111c476f7fadf2b changed= ms=11 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Column: Architectural · picks (300,300) · keys Escape Escape · fields — · expect Columns +1",
  "ribbon:Architecture:Column: Architectural · picks (5700,300) · keys Escape Escape · fields — · expect Columns +1",
  "ribbon:Architecture:Column: Architectural · picks (5700,2700) · keys Escape Escape · fields — · expect Columns +1",
  "ribbon:Architecture:Column: Architectural · picks (300,2700) · keys Escape Escape · fields — · expect Columns +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Column: Architectural · picks (300,300) · keys Escape Escape · fields — · expect Columns +1` | green: pressed 'Column: Architectural' on Architecture's Build panel: the tool 'Column: Architectural' stands \| picks: (300,300) mm at px (656.8,418.2) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Column: Architectural -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Columns +1": Columns 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Column: Architectural · picks (5700,300) · keys Escape Escape · fields — · expect Columns +1` | green: pressed 'Column: Architectural' on Architecture's Build panel: the tool 'Column: Architectural' stands \| picks: (5700,300) mm at px (815.2,418.2) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Column: Architectural -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Columns +1": Columns 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Column: Architectural · picks (5700,2700) · keys Escape Escape · fields — · expect Columns +1` | green: pressed 'Column: Architectural' on Architecture's Build panel: the tool 'Column: Architectural' stands \| picks: (5700,2700) mm at px (815.2,347.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Column: Architectural -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Columns +1": Columns 2 -> 3 (+1, expected +1) |
| `ribbon:Architecture:Column: Architectural · picks (300,2700) · keys Escape Escape · fields — · expect Columns +1` | green: pressed 'Column: Architectural' on Architecture's Build panel: the tool 'Column: Architectural' stands \| picks: (300,2700) mm at px (656.8,347.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Column: Architectural -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Columns +1": Columns 3 -> 4 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add roof boundary=(-300,-300) (6300,-300) (6300,3300) (-300,3300) level=\"Level 1\" slope=0 type=\"Concrete Roof 250\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add roof boundary=(-300,-300) (6300,-300) (6300,3300) (-300,3300) level="Level 1" slope=0 type="Concrete Roof 250"` | green: op:add roof made=roof-90e31d3e32b3509e changed= ms=6 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |

### The result

The model holds: Columns 4,Floors 1,Levels 3,Roofs 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 2071. Draw a semi-detached pair of 6 x 8 m houses sharing a block party wall, each with its own front door, a rear window and a named room.

- Starts from: a new Architectural project
- Ends with: a 12 x 8 m outline split by a block party wall on Ground, a slab, a front door and a rear window to each house and rooms named House A and House B
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(12000,0) to=(12000,8000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(12000,8000) to=(0,8000) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(0,8000) to=(0,0) level=Ground type=\"Brick Veneer 251\"",
  "op:add wall from=(6000,0) to=(6000,8000) level=Ground type=\"Block 190 Core-filled\"",
  "op:add floor boundary=(0,0) (12000,0) (12000,8000) (0,8000) level=Ground type=\"Concrete Slab 200 + Tile\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-897130c57d3d97b7 changed= ms=352 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,8000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-13b94e75cad9df78 changed=wall-897130c57d3d97b7 ms=6 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(0,8000) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-17bc074a087adf54 changed=wall-13b94e75cad9df78 ms=7 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground type="Brick Veneer 251"` | green: op:add wall made=wall-d4d9479347ede39c changed=wall-17bc074a087adf54,wall-897130c57d3d97b7 ms=7 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,8000) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-bad26272c8b30140 changed= ms=7 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add floor boundary=(0,0) (12000,0) (12000,8000) (0,8000) level=Ground type="Concrete Slab 200 + Tile"` | green: op:add floor made=floor-f61cb733e57191bb changed= ms=7 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:Architecture:Door · picks (1500,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Door · picks (10500,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Window · picks (3000,8000) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1",
  "ribbon:Architecture:Window · picks (9000,8000) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Architecture:Door · picks (1500,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (1500,0) mm at px (692.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (10500,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (10500,0) mm at px (956.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (3000,8000) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm' \| picks: (3000,8000) mm at px (736.0,192.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Window · picks (9000,8000) · keys Escape Escape · fields Options Strip: Width=1500 · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands \| fields: Width=1500 reads '1500 mm' \| picks: (9000,8000) mm at px (912.0,192.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add room at=(3000,4000) level=Ground name=\"House A\" number=1",
  "op:add room at=(9000,4000) level=Ground name=\"House B\" number=2"
]}
```

| Line | UNION answered |
|---|---|
| `op:add room at=(3000,4000) level=Ground name="House A" number=1` | green: op:add room made=room-0c0faee05b2248be changed= ms=25 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(9000,4000) level=Ground name="House B" number=2` | green: op:add room made=room-493b3f0940420f54 changed= ms=20 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |

### The result

The model holds: Doors 2,Floors 1,Levels 3,Openings 4,Rooms 2,Walls 5,Windows 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
