# UNION examples: Views, sheets and schedules

76 drafting jobs, each the request in plain words, the exact calls an AI sends to UNION, and UNION's answer to each, played green on UNION 1.0.0-beta.2.

## 4001. Cut a section through my 8 by 6 m office and put it on its own sheet at 1:50.

- Starts from: a new Architectural project
- Ends with: Four office walls on Ground, a section view named Office Cross Section with its grid lines hidden, and sheet A310 holding that section at 1:50.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name=\"Office Cross Section\" view=48660e38a721430d899d5d8a96df3bec",
  "op:set view view=\"Office Cross Section\" hide=Grids",
  "op:add sheet number=A310 name=\"Office Section\" titleblock=A1",
  "op:place view view=\"Office Cross Section\" sheet=A310 at=(100,100) scale=1:50"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-14251b7ba8345406 changed= ms=515 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-4877041afbf4a964 changed=wall-14251b7ba8345406 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-633a2e012775154f changed=wall-4877041afbf4a964 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-e81a20f250d09c7f changed=wall-633a2e012775154f,wall-14251b7ba8345406 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name="Office Cross Section" view=48660e38a721430d899d5d8a96df3bec` | green: op:add section made=aedf804a8b50442a906b6a3244119300 changed= ms=17 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `op:set view view="Office Cross Section" hide=Grids` | green: op:set view made= changed=aedf804a8b50442a906b6a3244119300 ms=17 Check "—": no expectation |
| `op:add sheet number=A310 name="Office Section" titleblock=A1` | green: op:add sheet made=sheet-A310 changed= ms=5 Check "sheet A310 exists": sheet A310 exists (9 sheet(s) in the document) |
| `op:place view view="Office Cross Section" sheet=A310 at=(100,100) scale=1:50` | green: op:place view made=aedf804a8b50442a906b6a3244119300::sheet-A310::a73ccc99cc1e429db891b3965807f4b4 changed= ms=4518 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 3,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 3.

## 4002. Make the front and side elevations of my 10 by 7 m house and put both on one A1 sheet at 1:100.

- Starts from: a new Architectural project
- Ends with: Four house walls on Ground, two new elevation views, and sheet A211 holding both at 1:100.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground",
  "op:add wall from=(10000,0) to=(10000,7000) level=Ground",
  "op:add wall from=(10000,7000) to=(0,7000) level=Ground",
  "op:add wall from=(0,7000) to=(0,0) level=Ground",
  "op:add elevation at=(5000,-6000) facing=north name=\"House Front Elevation\" view=48660e38a721430d899d5d8a96df3bec",
  "op:add elevation at=(-6000,3500) facing=east name=\"House Side Elevation\" view=48660e38a721430d899d5d8a96df3bec",
  "op:add sheet number=A211 name=\"House Elevations\" titleblock=A1",
  "op:place view view=\"House Front Elevation\" sheet=A211 at=(40,60) scale=1:100",
  "op:place view view=\"House Side Elevation\" sheet=A211 at=(320,60) scale=1:100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground` | green: op:add wall made=wall-f1b3a7ccd05f53a6 changed= ms=154 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,7000) level=Ground` | green: op:add wall made=wall-7adfbb3759497e18 changed=wall-f1b3a7ccd05f53a6 ms=49 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,7000) to=(0,7000) level=Ground` | green: op:add wall made=wall-fa0600a6f55a2583 changed=wall-7adfbb3759497e18 ms=8 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,7000) to=(0,0) level=Ground` | green: op:add wall made=wall-e7448b572f307058 changed=wall-fa0600a6f55a2583,wall-f1b3a7ccd05f53a6 ms=6 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add elevation at=(5000,-6000) facing=north name="House Front Elevation" view=48660e38a721430d899d5d8a96df3bec` | green: op:add elevation made=elev-e7d0aec17b1e4b9f changed= ms=18 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) |
| `op:add elevation at=(-6000,3500) facing=east name="House Side Elevation" view=48660e38a721430d899d5d8a96df3bec` | green: op:add elevation made=elev-68397b9035094a4d changed= ms=12 Check "view: Elevation +1": view: Elevation 5 -> 6 (+1, expected +1) |
| `op:add sheet number=A211 name="House Elevations" titleblock=A1` | green: op:add sheet made=sheet-A211 changed= ms=5 Check "sheet A211 exists": sheet A211 exists (9 sheet(s) in the document) |
| `op:place view view="House Front Elevation" sheet=A211 at=(40,60) scale=1:100` | green: op:place view made=elev-e7d0aec17b1e4b9f::sheet-A211::ac180e1d15af4ec2aa7399d0a41a6a28 changed= ms=116 Check "—": no expectation |
| `op:place view view="House Side Elevation" sheet=A211 at=(320,60) scale=1:100` | green: op:place view made=elev-68397b9035094a4d::sheet-A211::e87a1f43ef5748948b67c91170e84c20 changed= ms=987 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 3,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 6,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4003. Give me a separate Level 1 plan for the furniture layout of the 9 by 6 m upstairs flat, at 1:50 on its own sheet.

- Starts from: a new Architectural project
- Ends with: Four walls on Level 1, a floor plan named Level 1 Furniture Plan at 1:50 with its level lines hidden, and sheet A122 holding it cropped to the flat.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(9000,0) level=\"Level 1\"",
  "op:add wall from=(9000,0) to=(9000,6000) level=\"Level 1\"",
  "op:add wall from=(9000,6000) to=(0,6000) level=\"Level 1\"",
  "op:add wall from=(0,6000) to=(0,0) level=\"Level 1\"",
  "op:add view kind=plan level=\"Level 1\" name=\"Level 1 Furniture Plan\"",
  "op:set id=\"Level 1 Furniture Plan\" key=Scale value=1:50",
  "op:set view view=\"Level 1 Furniture Plan\" hide=Levels",
  "op:add sheet number=A122 name=\"Level 1 Furniture Layout\" titleblock=A1",
  "op:place view view=\"Level 1 Furniture Plan\" sheet=A122 at=(100,60) crop=(-2000,-2000) (11000,8000)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(9000,0) level="Level 1"` | green: op:add wall made=wall-586a0635bdf3d2ed changed= ms=18 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(9000,0) to=(9000,6000) level="Level 1"` | green: op:add wall made=wall-0a4fa12826907380 changed=wall-586a0635bdf3d2ed ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(9000,6000) to=(0,6000) level="Level 1"` | green: op:add wall made=wall-c6a5f1e58c5b52bf changed=wall-0a4fa12826907380 ms=5 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-37d6ad969a6ad2dd changed=wall-586a0635bdf3d2ed,wall-c6a5f1e58c5b52bf ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add view kind=plan level="Level 1" name="Level 1 Furniture Plan"` | green: op:add view made=51258adb960043e6a6b1b7f43d87147c changed= ms=12 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:set id="Level 1 Furniture Plan" key=Scale value=1:50` | green: op:set made= changed="Level 1 Furniture Plan" ms=5 Check "—": no expectation |
| `op:set view view="Level 1 Furniture Plan" hide=Levels` | green: op:set view made= changed=51258adb960043e6a6b1b7f43d87147c ms=37 Check "—": no expectation |
| `op:add sheet number=A122 name="Level 1 Furniture Layout" titleblock=A1` | green: op:add sheet made=sheet-A122 changed= ms=9 Check "sheet A122 exists": sheet A122 exists (9 sheet(s) in the document) |
| `op:place view view="Level 1 Furniture Plan" sheet=A122 at=(100,60) crop=(-2000,-2000) (11000,8000)` | green: op:place view made=51258adb960043e6a6b1b7f43d87147c::sheet-A122::81df023d65bf4ace8d0902954e40a2f5 changed= ms=577 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 4004. Draw a 2700 mm ceiling over my 7 by 5 m studio and make a lighting ceiling plan of it at 1:50 on a new sheet.

- Starts from: a new Architectural project
- Ends with: Four studio walls, one ceiling at 2700 mm, a ceiling plan named Ground Lighting Plan at 1:50, and sheet A140 holding it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(7000,0) level=Ground",
  "op:add wall from=(7000,0) to=(7000,5000) level=Ground",
  "op:add wall from=(7000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground",
  "op:add ceiling boundary=(0,0) (7000,0) (7000,5000) (0,5000) level=Ground height=2700",
  "op:add view kind=ceiling level=Ground name=\"Ground Lighting Plan\"",
  "op:set id=\"Ground Lighting Plan\" key=Scale value=1:50",
  "op:add sheet number=A140 name=\"Ground Lighting Plan\" titleblock=A1",
  "op:place view view=\"Ground Lighting Plan\" sheet=A140 at=(100,60) scale=1:50 crop=(-2000,-2000) (9000,7000)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(7000,0) level=Ground` | green: op:add wall made=wall-53b9d07376a6aefa changed= ms=23 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(7000,0) to=(7000,5000) level=Ground` | green: op:add wall made=wall-b8e659783ea7c4d1 changed=wall-53b9d07376a6aefa ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(7000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-ab146af1c08eab33 changed=wall-b8e659783ea7c4d1 ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-b012abdd35e144bc changed=wall-53b9d07376a6aefa,wall-ab146af1c08eab33 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add ceiling boundary=(0,0) (7000,0) (7000,5000) (0,5000) level=Ground height=2700` | green: op:add ceiling made=ceiling-ac714bc480292bce changed= ms=19 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `op:add view kind=ceiling level=Ground name="Ground Lighting Plan"` | green: op:add view made=dcce147650d442158fc3df9c6cbbff8f changed= ms=16 Check "view: Ceiling Plan +1": view: Ceiling Plan 3 -> 4 (+1, expected +1) |
| `op:set id="Ground Lighting Plan" key=Scale value=1:50` | green: op:set made= changed="Ground Lighting Plan" ms=4 Check "—": no expectation |
| `op:add sheet number=A140 name="Ground Lighting Plan" titleblock=A1` | green: op:add sheet made=sheet-A140 changed= ms=6 Check "sheet A140 exists": sheet A140 exists (9 sheet(s) in the document) |
| `op:place view view="Ground Lighting Plan" sheet=A140 at=(100,60) scale=1:50 crop=(-2000,-2000) (9000,7000)` | green: op:place view made=dcce147650d442158fc3df9c6cbbff8f::sheet-A140::d66ab87b9d8943478685f662f4ae1499 changed= ms=308 Check "—": no expectation |

### The result

The model holds: Ceilings 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 4,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4005. Set out a four column steel bay on Level 1 with two beams, make a Level 1 framing plan at 1:100 and put it on sheet S101.

- Starts from: a new Structural project
- Ends with: Four columns and two beams on Level 1, a structural plan named Level 1 Framing Plan at 1:100, and sheet S101 holding it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\"",
  "op:add column at=(8000,0) level=\"Level 1\"",
  "op:add column at=(0,6000) level=\"Level 1\"",
  "op:add column at=(8000,6000) level=\"Level 1\"",
  "op:add beam from=(0,0) to=(8000,0) level=\"Level 1\"",
  "op:add beam from=(0,6000) to=(8000,6000) level=\"Level 1\"",
  "op:add view kind=structural level=\"Level 1\" name=\"Level 1 Framing Plan\"",
  "op:set id=\"Level 1 Framing Plan\" key=Scale value=1:100",
  "op:add sheet number=S101 name=\"Level 1 Framing Plan\" titleblock=A1",
  "op:place view view=\"Level 1 Framing Plan\" sheet=S101 at=(80,100)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1"` | green: op:add column made=column-d104ac14fb9ee084 changed= ms=17 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(8000,0) level="Level 1"` | green: op:add column made=column-d01fbc2609dc1932 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 1"` | green: op:add column made=column-fe41b3d54f24dbf1 changed= ms=4 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(8000,6000) level="Level 1"` | green: op:add column made=column-91e209746c358c78 changed= ms=3 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add beam from=(0,0) to=(8000,0) level="Level 1"` | green: op:add beam made=beam-4be7ed58fbc07c48 changed= ms=4 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,6000) to=(8000,6000) level="Level 1"` | green: op:add beam made=beam-20776eb4d5db7fe4 changed= ms=4 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add view kind=structural level="Level 1" name="Level 1 Framing Plan"` | green: op:add view made=553e6d8e70ec4cd0a9007ba23298ab6a changed= ms=253 Check "view: Structural Plan +1": view: Structural Plan 2 -> 3 (+1, expected +1) |
| `op:set id="Level 1 Framing Plan" key=Scale value=1:100` | green: op:set made= changed= ms=331 state=unchanged Check "—": no expectation |
| `op:add sheet number=S101 name="Level 1 Framing Plan" titleblock=A1` | green: op:add sheet made=sheet-S101 changed= ms=6 Check "sheet S101 exists": sheet S101 exists (1 sheet(s) in the document) |
| `op:place view view="Level 1 Framing Plan" sheet=S101 at=(80,100)` | green: op:place view made=553e6d8e70ec4cd0a9007ba23298ab6a::sheet-S101::d08e28ad5c3b4bdd97ce65d7664b1ad3 changed= ms=80 Check "—": no expectation |

### The result

The model holds: Levels 2,Structural Columns 4,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 3.

## 4006. Write the general notes for the job as a drawing and put them on a sheet.

- Starts from: a new Architectural project
- Ends with: A drafting view named General Notes holding three notes, placed on a new sheet A002.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"General Notes\" scale=1:1",
  "op:add text at=(0,-10) view=\"General Notes\" text=\"1. All dimensions are in millimetres.\"",
  "op:add text at=(0,-18) view=\"General Notes\" text=\"2. Check all dimensions on site before ordering.\"",
  "op:add text at=(0,-26) view=\"General Notes\" text=\"3. Do not scale from this drawing.\"",
  "op:add sheet number=A002 name=\"General Notes\" titleblock=A1",
  "op:place view view=\"General Notes\" sheet=A002 at=(40,500)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="General Notes" scale=1:1` | green: op:add drafting view made=e71fb59e35614898a047f1644fde82dc changed= ms=1910 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-10) view="General Notes" text="1. All dimensions are in millimetres."` | green: op:add text made=text-26e5dd4b5a824f81 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-18) view="General Notes" text="2. Check all dimensions on site before ordering."` | green: op:add text made=text-e88e5ba72e81475f changed= ms=4 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add text at=(0,-26) view="General Notes" text="3. Do not scale from this drawing."` | green: op:add text made=text-0826e70afc424e2c changed= ms=3 Check "Text Notes +1": Text Notes 2 -> 3 (+1, expected +1) |
| `op:add sheet number=A002 name="General Notes" titleblock=A1` | green: op:add sheet made=sheet-A002 changed= ms=4 Check "sheet A002 exists": sheet A002 exists (9 sheet(s) in the document) |
| `op:place view view="General Notes" sheet=A002 at=(40,500)` | green: op:place view made=e71fb59e35614898a047f1644fde82dc::sheet-A002::8e8a3a8358064815af646957187515e2 changed= ms=21 Check "—": no expectation |

### The result

The model holds: Levels 3,Text Notes 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4007. Add a legend called Door Types to the drawing set and put it on the schedules sheet.

- Starts from: a new Architectural project
- Ends with: A legend view named Door Types at 1:20 placed on sheet A501.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add legend name=\"Door Types\" scale=1:20",
  "op:place view view=\"Door Types\" sheet=A501 at=(500,60)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add legend name="Door Types" scale=1:20` | green: op:add legend made=135b4d0f29f84b67ae6822b1a5d54c74 changed= ms=25 Check "view: Legend +1": view: Legend 0 -> 1 (+1, expected +1) |
| `op:place view view="Door Types" sheet=A501 at=(500,60)` | green: op:place view made=135b4d0f29f84b67ae6822b1a5d54c74::sheet-A501::c37c56de47714487906230fa508a05f1 changed= ms=21 Check "—": no expectation |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Legend 1,view: Schedule 3,view: Section 2.

## 4008. I have an office with a front door and a back door; give me a door list sorted by mark and put it on the schedules sheet.

- Starts from: a new Architectural project
- Ends with: Two walls with two doors on Ground, a new door schedule Entrance Door List sorted by Mark, placed on sheet A501.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4",
  "ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Door · picks (6000,6000) · keys Escape Escape · fields — · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4` | green: pressed 'Wall' on Structure's Structure panel: the tool 'Wall' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,0) mm at px (882.7,427.0) on the plan view \| (8000,6000) mm at px (882.7,251.0) on the plan view \| (0,6000) mm at px (648.0,251.0) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +4": Walls 0 -> 4 (+4, expected +4) |
| `ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (2000,0) mm at px (706.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (6000,6000) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (6000,6000) mm at px (824.0,251.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=Doors fields=Mark,Level,Type,Width,Height name=\"Entrance Door List\" sortby=Mark",
  "op:place view view=\"Entrance Door List\" sheet=A501 at=(20,300) table_width=220 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category=Doors fields=Mark,Level,Type,Width,Height name="Entrance Door List" sortby=Mark` | green: op:add schedule made=1ad036a90584414a89cb78c46a1a44a3 changed= ms=441 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |
| `op:place view view="Entrance Door List" sheet=A501 at=(20,300) table_width=220 text_size=3.5` | green: op:place view made=1ad036a90584414a89cb78c46a1a44a3::sheet-A501::4b8ec657df5547a9be2b05397e9d4533 changed= ms=181 Check "—": no expectation |

### The result

The model holds: Doors 2,Levels 3,Openings 2,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4009. Make grid lines A and B red in the Ground plan only.

- Starts from: a new Architectural project
- Ends with: Grids A and B on Ground, drawn red in the Ground floor plan only.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:add grid from=(8000,-2000) to=(8000,8000) name=B",
  "op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A,grid-B projection_line_colour=#CC0000"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=30 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(8000,-2000) to=(8000,8000) name=B` | green: op:add grid made=grid-B changed= ms=2 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A,grid-B projection_line_colour=#CC0000` | green: op:set element graphics made= changed= ms=1 Check "—": no expectation |

### The result

The model holds: Grids 2,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4010. Take the level and grid lines off the 3D view and give it a light grey background.

- Starts from: a new Architectural project
- Ends with: Four walls and a floor on Ground, and the 3D view with levels and grids hidden on a light grey map.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0),(6000,0),(6000,4000),(0,4000) level=Ground",
  "op:set view view=view-3d hide=Levels,Grids map=plain:lightgrey"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-e9a47057959ad8dc changed= ms=17 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-ef70686861154665 changed=wall-e9a47057959ad8dc ms=416 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-e3bd1b9d93f61899 changed=wall-ef70686861154665 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-956354804984b1cc changed=wall-e9a47057959ad8dc,wall-e3bd1b9d93f61899 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0),(6000,0),(6000,4000),(0,4000) level=Ground` | green: op:add floor made=floor-a17073c4b6717223 changed= ms=3 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:set view view=view-3d hide=Levels,Grids map=plain:lightgrey` | green: op:set view made= changed=view-3d ms=29 Check "—": no expectation |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4011. List the windows of my 8 by 6 m cottage by sill height, highest first, and put the list on the schedules sheet.

- Starts from: a new Architectural project
- Ends with: Four walls with two windows on Ground, a window schedule named Window Sill List sorted by Sill Height descending, placed on sheet A501.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4",
  "ribbon:Structure:Opening:Window · picks (5000,6000) · keys Escape Escape · fields — · expect Windows +1",
  "ribbon:Structure:Opening:Window · picks (8000,3000) · keys Escape Escape · fields — · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4` | green: pressed 'Wall' on Structure's Structure panel: the tool 'Wall' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,0) mm at px (882.7,427.0) on the plan view \| (8000,6000) mm at px (882.7,251.0) on the plan view \| (0,6000) mm at px (648.0,251.0) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +4": Walls 0 -> 4 (+4, expected +4) |
| `ribbon:Structure:Opening:Window · picks (5000,6000) · keys Escape Escape · fields — · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands (the walk names Structure; the tile stands on Architecture) \| picks: (5000,6000) mm at px (794.7,251.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |
| `ribbon:Structure:Opening:Window · picks (8000,3000) · keys Escape Escape · fields — · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands (the walk names Structure; the tile stands on Architecture) \| picks: (8000,3000) mm at px (882.7,339.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=Windows fields=\"Mark,Level,Type,Width,Height,Sill Height\" sortby=\"Sill Height;descending\" name=\"Window Sill List\"",
  "op:place view view=\"Window Sill List\" sheet=A501 at=(20,380) table_width=240 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category=Windows fields="Mark,Level,Type,Width,Height,Sill Height" sortby="Sill Height;descending" name="Window Sill List"` | green: op:add schedule made=e8e5cf2bc7404e81bbb69d934f98b8d6 changed= ms=15 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |
| `op:place view view="Window Sill List" sheet=A501 at=(20,380) table_width=240 text_size=3.5` | green: op:place view made=e8e5cf2bc7404e81bbb69d934f98b8d6::sheet-A501::ac8db55c08f946828fae698ca1f3414a changed= ms=48 Check "—": no expectation |

### The result

The model holds: Levels 3,Openings 2,Walls 4,Windows 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4012. Name the two rooms of my 8 by 6 m flat, Living and Bedroom, and give me a room area list on the schedules sheet.

- Starts from: a new Architectural project
- Ends with: Five walls and two named rooms on Ground, a room schedule named Flat Room Areas sorted by Number, placed on sheet A501.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add wall from=(4000,0) to=(4000,6000) level=Ground",
  "op:add room at=(2000,3000) level=Ground name=Living number=1",
  "op:add room at=(6000,3000) level=Ground name=Bedroom number=2",
  "op:add schedule category=Rooms fields=Number,Name,Area,Level sortby=Number name=\"Flat Room Areas\"",
  "op:place view view=\"Flat Room Areas\" sheet=A501 at=(20,330) table_width=160 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-310294ca0a4281ad changed= ms=48 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-ce6159707a09e17d changed=wall-310294ca0a4281ad ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-6013804f71dac0aa changed=wall-ce6159707a09e17d ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-e71f598dd9199df0 changed=wall-6013804f71dac0aa,wall-310294ca0a4281ad ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(4000,0) to=(4000,6000) level=Ground` | green: op:add wall made=wall-03bbbdf53875a7dc changed= ms=2 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add room at=(2000,3000) level=Ground name=Living number=1` | green: op:add room made=room-2509a65a576342e2 changed= ms=26 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(6000,3000) level=Ground name=Bedroom number=2` | green: op:add room made=room-2bb1c787a3dc588b changed= ms=16 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |
| `op:add schedule category=Rooms fields=Number,Name,Area,Level sortby=Number name="Flat Room Areas"` | green: op:add schedule made=6f4b70e90a364c69b22c2c5909a5b180 changed= ms=15 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |
| `op:place view view="Flat Room Areas" sheet=A501 at=(20,330) table_width=160 text_size=3.5` | green: op:place view made=6f4b70e90a364c69b22c2c5909a5b180::sheet-A501::75878f894e1b446e9f800d34e082154d changed= ms=55 Check "—": no expectation |

### The result

The model holds: Levels 3,Rooms 2,Walls 5,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4013. Give me the wall lengths by type for a 12 by 8 m shed with brick cavity side walls and block end walls.

- Starts from: a new Architectural project
- Ends with: Four walls on Ground of two types, a wall schedule named Wall Quantities by Type with one row a type, placed on sheet A501.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground type=\"Brick Cavity 280\"",
  "op:add wall from=(12000,0) to=(12000,8000) level=Ground type=\"Block 190 Core-filled\"",
  "op:add wall from=(12000,8000) to=(0,8000) level=Ground type=\"Brick Cavity 280\"",
  "op:add wall from=(0,8000) to=(0,0) level=Ground type=\"Block 190 Core-filled\"",
  "op:add schedule category=Walls fields=Type,Count,Length name=\"Wall Quantities by Type\" itemize=no",
  "op:place view view=\"Wall Quantities by Type\" sheet=A501 at=(300,330) table_width=180 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground type="Brick Cavity 280"` | green: op:add wall made=wall-97a9311dc59275d8 changed= ms=25 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,8000) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-fefccfd20f116328 changed=wall-97a9311dc59275d8 ms=12 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(0,8000) level=Ground type="Brick Cavity 280"` | green: op:add wall made=wall-1b2eb524ad50991e changed=wall-fefccfd20f116328 ms=119 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground type="Block 190 Core-filled"` | green: op:add wall made=wall-153f54bd27f7923f changed=wall-97a9311dc59275d8,wall-1b2eb524ad50991e ms=72 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add schedule category=Walls fields=Type,Count,Length name="Wall Quantities by Type" itemize=no` | green: op:add schedule made=025fe7f36e9045b89cc6fcbefe6e2ef0 changed= ms=29 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |
| `op:place view view="Wall Quantities by Type" sheet=A501 at=(300,330) table_width=180 text_size=3.5` | green: op:place view made=025fe7f36e9045b89cc6fcbefe6e2ef0::sheet-A501::27a27ba60ae14a9c900dbf77622f5ad3 changed= ms=71 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4014. Set out six columns on a 2 by 3 grid with four beams and give me column and beam schedules by type on a new sheet.

- Starts from: a new Structural project
- Ends with: Six columns and four beams on Level 1, a column schedule and a beam schedule by type, both placed on sheet S201.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\"",
  "op:add column at=(6000,0) level=\"Level 1\"",
  "op:add column at=(12000,0) level=\"Level 1\"",
  "op:add column at=(0,7000) level=\"Level 1\"",
  "op:add column at=(6000,7000) level=\"Level 1\"",
  "op:add column at=(12000,7000) level=\"Level 1\"",
  "op:add beam from=(0,0) to=(12000,0) level=\"Level 1\"",
  "op:add beam from=(0,7000) to=(12000,7000) level=\"Level 1\"",
  "op:add schedule category=\"Structural Columns\" fields=Type,Count,Length name=\"Column Schedule by Type\" itemize=no",
  "op:add schedule category=\"Structural Framing\" fields=Type,Count,Length name=\"Beam Schedule by Type\" itemize=no",
  "op:add sheet number=S201 name=\"Member Schedules\" titleblock=A1",
  "op:place view view=\"Column Schedule by Type\" sheet=S201 at=(40,300) table_width=200 text_size=3.5",
  "op:place view view=\"Beam Schedule by Type\" sheet=S201 at=(300,300) table_width=200 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1"` | green: op:add column made=column-e576ae9649c433a3 changed= ms=76 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1"` | green: op:add column made=column-2f5cba693c3ca0c8 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(12000,0) level="Level 1"` | green: op:add column made=column-aefd407fca370a1b changed= ms=2 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(0,7000) level="Level 1"` | green: op:add column made=column-0b55e72105350fe6 changed= ms=3 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add column at=(6000,7000) level="Level 1"` | green: op:add column made=column-f3c0c0d6bdca96c9 changed= ms=3 Check "Structural Columns +1": Structural Columns 4 -> 5 (+1, expected +1) |
| `op:add column at=(12000,7000) level="Level 1"` | green: op:add column made=column-2edf294bc3680aec changed= ms=17 Check "Structural Columns +1": Structural Columns 5 -> 6 (+1, expected +1) |
| `op:add beam from=(0,0) to=(12000,0) level="Level 1"` | green: op:add beam made=beam-49e48aec4a427db1 changed= ms=3 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,7000) to=(12000,7000) level="Level 1"` | green: op:add beam made=beam-b1e30f110c150c69 changed= ms=3 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add schedule category="Structural Columns" fields=Type,Count,Length name="Column Schedule by Type" itemize=no` | green: op:add schedule made=8eb8a479c8014f7ca7833b467e5ac5ba changed= ms=20 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |
| `op:add schedule category="Structural Framing" fields=Type,Count,Length name="Beam Schedule by Type" itemize=no` | green: op:add schedule made=bae40562750a480593a0867eb6c224b3 changed= ms=16 Check "view: Schedule +1": view: Schedule 1 -> 2 (+1, expected +1) |
| `op:add sheet number=S201 name="Member Schedules" titleblock=A1` | green: op:add sheet made=sheet-S201 changed= ms=4 Check "sheet S201 exists": sheet S201 exists (1 sheet(s) in the document) |
| `op:place view view="Column Schedule by Type" sheet=S201 at=(40,300) table_width=200 text_size=3.5` | green: op:place view made=8eb8a479c8014f7ca7833b467e5ac5ba::sheet-S201::d4f07f852eda4e81b1672c54d31d6330 changed= ms=99 Check "—": no expectation |
| `op:place view view="Beam Schedule by Type" sheet=S201 at=(300,300) table_width=200 text_size=3.5` | green: op:place view made=bae40562750a480593a0867eb6c224b3::sheet-S201::2d5823c68c814a8682e22f71d4029475 changed= ms=132 Check "—": no expectation |

### The result

The model holds: Levels 2,Structural Columns 6,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Schedule 2,view: Structural Plan 2.

## 4015. Add a floor to each storey of my 10 by 7 m house and list the floor areas by level.

- Starts from: a new Architectural project
- Ends with: One floor on Ground and one on Level 1, a floor schedule named Floor Areas by Level sorted by Level, placed on sheet A501.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add floor boundary=(0,0),(10000,0),(10000,7000),(0,7000) level=Ground",
  "op:add floor boundary=(0,0),(10000,0),(10000,7000),(0,7000) level=\"Level 1\"",
  "op:add schedule category=Floors fields=Level,Type,Area,Perimeter sortby=Level name=\"Floor Areas by Level\"",
  "op:place view view=\"Floor Areas by Level\" sheet=A501 at=(300,430) table_width=180 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add floor boundary=(0,0),(10000,0),(10000,7000),(0,7000) level=Ground` | green: op:add floor made=floor-a6d4dce9e9bf1260 changed= ms=444 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add floor boundary=(0,0),(10000,0),(10000,7000),(0,7000) level="Level 1"` | green: op:add floor made=floor-0077435872c2a732 changed= ms=3 Check "Floors +1": Floors 1 -> 2 (+1, expected +1) |
| `op:add schedule category=Floors fields=Level,Type,Area,Perimeter sortby=Level name="Floor Areas by Level"` | green: op:add schedule made=4ea914b459854bd1b25587821c09d841 changed= ms=18 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |
| `op:place view view="Floor Areas by Level" sheet=A501 at=(300,430) table_width=180 text_size=3.5` | green: op:place view made=4ea914b459854bd1b25587821c09d841::sheet-A501::4c6e2695a8a54f7db201badc7ee801be changed= ms=360 Check "—": no expectation |

### The result

The model holds: Floors 2,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4016. Add Level 2 at 6600 and grids A to C, then list the levels by elevation and the grids by name.

- Starts from: a new Architectural project
- Ends with: Level 2 at 6600 mm and grids A, B and C, a level schedule sorted by Elevation and a grid schedule sorted by Name.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=6600 name=\"Level 2\"",
  "op:add grid from=(0,-2000) to=(0,12000) name=A",
  "op:add grid from=(8000,-2000) to=(8000,12000) name=B",
  "op:add grid from=(16000,-2000) to=(16000,12000) name=C",
  "op:add schedule category=Levels fields=Name,Elevation sortby=Elevation name=\"Level List\"",
  "op:add schedule category=Grids fields=Name name=\"Grid List\" sortby=Name"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=6600 name="Level 2"` | green: op:add level made="level-Level 2" changed= ms=373 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add grid from=(0,-2000) to=(0,12000) name=A` | green: op:add grid made=grid-A changed= ms=36 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(8000,-2000) to=(8000,12000) name=B` | green: op:add grid made=grid-B changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(16000,-2000) to=(16000,12000) name=C` | green: op:add grid made=grid-C changed= ms=4 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add schedule category=Levels fields=Name,Elevation sortby=Elevation name="Level List"` | green: op:add schedule made=c297ade301d1411584e3c725464bfc4b changed= ms=16 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |
| `op:add schedule category=Grids fields=Name name="Grid List" sortby=Name` | green: op:add schedule made=f95a77f272f641dc97aaed147c9ec121 changed= ms=15 Check "view: Schedule +1": view: Schedule 4 -> 5 (+1, expected +1) |

### The result

The model holds: Grids 3,Levels 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 5,view: Section 2.

## 4017. Put a 25 degree roof over my 9 by 6 m extension and list its area and slope.

- Starts from: a new Architectural project
- Ends with: One roof at 25 degrees over the extension footprint, a roof schedule named Roof Area and Slope placed on sheet A501.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add roof boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground slope=25",
  "op:add schedule category=Roofs fields=Level,Type,Area,Slope name=\"Roof Area and Slope\"",
  "op:place view view=\"Roof Area and Slope\" sheet=A501 at=(20,430) table_width=160 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add roof boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground slope=25` | green: op:add roof made=roof-42c8691154485d18 changed= ms=21 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |
| `op:add schedule category=Roofs fields=Level,Type,Area,Slope name="Roof Area and Slope"` | green: op:add schedule made=4ddecb6b06814a7786d0ce72e570ce0e changed= ms=19 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |
| `op:place view view="Roof Area and Slope" sheet=A501 at=(20,430) table_width=160 text_size=3.5` | green: op:place view made=4ddecb6b06814a7786d0ce72e570ce0e::sheet-A501::14721822f30049e9b001a1cc3b43ff22 changed= ms=317 Check "—": no expectation |

### The result

The model holds: Levels 3,Roofs 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4018. Put a straight stair between Ground and Level 1 in my house and list it with its base and top levels.

- Starts from: a new Architectural project
- Ends with: One stair rising from Ground to Level 1, a stair schedule named Stair List.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add stair from=(1000,1000) to=(1000,5000) level=Ground top=\"Level 1\" width=1000",
  "op:add schedule category=Stairs fields=\"Type,Base Level,Top Level\" name=\"Stair List\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add stair from=(1000,1000) to=(1000,5000) level=Ground top="Level 1" width=1000` | green: op:add stair made=stair-641691f84a7b7362 changed= ms=498 note=the run ends at its last riser (1000,5760) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) |
| `op:add schedule category=Stairs fields="Type,Base Level,Top Level" name="Stair List"` | green: op:add schedule made=31288cc85e894489b5adadb344fce5c3 changed= ms=25 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Stairs 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4019. Open three A3 sheets for the first issue: a cover, the notes and the details, and take out the notes sheet again.

- Starts from: a new Architectural project
- Ends with: Sheets A601 and A603 stand on A3 title blocks; sheet A602 was made and deleted.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add sheet number=A601 name=\"Cover Sheet\" titleblock=A3",
  "op:add sheet number=A602 name=\"Notes Sheet\" titleblock=A3",
  "op:add sheet number=A603 name=\"Details Sheet\" titleblock=A3",
  "op:delete sheet sheet=A602"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=A601 name="Cover Sheet" titleblock=A3` | green: op:add sheet made=sheet-A601 changed= ms=11 Check "sheet A601 exists": sheet A601 exists (9 sheet(s) in the document) |
| `op:add sheet number=A602 name="Notes Sheet" titleblock=A3` | green: op:add sheet made=sheet-A602 changed= ms=5 Check "sheet A602 exists": sheet A602 exists (10 sheet(s) in the document) |
| `op:add sheet number=A603 name="Details Sheet" titleblock=A3` | green: op:add sheet made=sheet-A603 changed= ms=4 Check "sheet A603 exists": sheet A603 exists (11 sheet(s) in the document) |
| `op:delete sheet sheet=A602` | green: op:delete sheet made= changed=sheet-A602 ms=3 note=sheet A602 deleted; its views stand unplaced Check "—": no expectation |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4020. Put the site plan back on its sheet at 1:500, cropped to my 60 by 40 m site.

- Starts from: a new Architectural project
- Ends with: The Site Plan viewport taken off sheet A100 and placed again at 1:500 with a 60 by 40 m crop.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:remove view view=\"Site Plan\" sheet=A100",
  "op:place view view=\"Site Plan\" sheet=A100 at=(100,100) scale=1:500 crop=(-10000,-10000) (50000,30000)"
]}
```

| Line | UNION answered |
|---|---|
| `op:remove view view="Site Plan" sheet=A100` | green: op:remove view made= changed=7c4df2b0-7e72-46b6-bda2-c289caa51776::sheet-A100::853005318d254b5abd699a51092ebd69 ms=19 Check "—": no expectation |
| `op:place view view="Site Plan" sheet=A100 at=(100,100) scale=1:500 crop=(-10000,-10000) (50000,30000)` | green: op:place view made=7c4df2b0-7e72-46b6-bda2-c289caa51776::sheet-A100::16294531df0b4731bdaa61763d44c92e changed= ms=769 Check "—": no expectation |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4021. Make a plan for the brickie that shows the walls only, with no doors or windows, for my 9 by 6 m house.

- Starts from: a new Architectural project
- Ends with: Four walls with one door and one window on Ground, and a floor plan named Wall Setout Plan with doors and windows hidden.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Structure:Wall · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4",
  "ribbon:Architecture:Door · picks (3000,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Structure:Opening:Window · picks (9000,3000) · keys Escape Escape · fields — · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Wall · picks (0,0) (9000,0) (9000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4` | green: pressed 'Wall' on Structure's Structure panel: the tool 'Wall' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (9000,0) mm at px (912.0,427.0) on the plan view \| (9000,6000) mm at px (912.0,251.0) on the plan view \| (0,6000) mm at px (648.0,251.0) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +4": Walls 0 -> 4 (+4, expected +4) |
| `ribbon:Architecture:Door · picks (3000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (3000,0) mm at px (736.0,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Structure:Opening:Window · picks (9000,3000) · keys Escape Escape · fields — · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands (the walk names Structure; the tile stands on Architecture) \| picks: (9000,3000) mm at px (912.0,339.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add view kind=plan level=Ground name=\"Wall Setout Plan\"",
  "op:set view view=\"Wall Setout Plan\" hide=\"Doors,Windows\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add view kind=plan level=Ground name="Wall Setout Plan"` | green: op:add view made=b40d63d162ff45758d02328b43ec247a changed= ms=12 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:set view view="Wall Setout Plan" hide="Doors,Windows"` | green: op:set view made= changed=b40d63d162ff45758d02328b43ec247a ms=21 Check "—": no expectation |

### The result

The model holds: Doors 1,Levels 3,Openings 2,Walls 4,Windows 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 4022. Make a Level 1 plan without room names or tags for the tender set of my 8 by 5 m unit.

- Starts from: a new Architectural project
- Ends with: Four walls and one room on Level 1, and a Level 1 plan named Tender Plan with rooms and room tags hidden.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=\"Level 1\"",
  "op:add wall from=(8000,0) to=(8000,5000) level=\"Level 1\"",
  "op:add wall from=(8000,5000) to=(0,5000) level=\"Level 1\"",
  "op:add wall from=(0,5000) to=(0,0) level=\"Level 1\"",
  "op:add room at=(4000,2500) level=\"Level 1\" name=Unit number=101",
  "op:add view kind=plan level=\"Level 1\" name=\"Tender Plan\"",
  "op:set view view=\"Tender Plan\" hide=\"Rooms,Room Tags\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level="Level 1"` | green: op:add wall made=wall-f74d9ee1bd8c4d13 changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,5000) level="Level 1"` | green: op:add wall made=wall-25e4c5299e5ba638 changed=wall-f74d9ee1bd8c4d13 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,5000) to=(0,5000) level="Level 1"` | green: op:add wall made=wall-b562504a5a495f13 changed=wall-25e4c5299e5ba638 ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-3cc9925894ea2af9 changed=wall-f74d9ee1bd8c4d13,wall-b562504a5a495f13 ms=20 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add room at=(4000,2500) level="Level 1" name=Unit number=101` | green: op:add room made=room-05d076a5589b411d changed= ms=49 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add view kind=plan level="Level 1" name="Tender Plan"` | green: op:add view made=91323cbe7b5343f9af5519b31a039ceb changed= ms=15 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:set view view="Tender Plan" hide="Rooms,Room Tags"` | green: op:set view made= changed=91323cbe7b5343f9af5519b31a039ceb ms=17 Check "—": no expectation |

### The result

The model holds: Levels 3,Rooms 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 4023. I want one Ground plan for the client with no grid lines and one for the builder with them showing.

- Starts from: a new Architectural project
- Ends with: Two grids on Ground, a Client Plan with grids and levels hidden and a Builder Plan with grids shown.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:add grid from=(8000,-2000) to=(8000,8000) name=B",
  "op:add view kind=plan level=Ground name=\"Client Plan\"",
  "op:add view kind=plan level=Ground name=\"Builder Plan\"",
  "op:set view view=\"Client Plan\" hide=\"Grids,Levels\"",
  "op:set view view=\"Builder Plan\" show=Grids"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=359 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(8000,-2000) to=(8000,8000) name=B` | green: op:add grid made=grid-B changed= ms=3 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add view kind=plan level=Ground name="Client Plan"` | green: op:add view made=e0474405e0174f45afedfed7252b2b91 changed= ms=18 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add view kind=plan level=Ground name="Builder Plan"` | green: op:add view made=37ae7999ecf842189975fe7ca63893d0 changed= ms=13 Check "view: Floor Plan +1": view: Floor Plan 5 -> 6 (+1, expected +1) |
| `op:set view view="Client Plan" hide="Grids,Levels"` | green: op:set view made= changed=e0474405e0174f45afedfed7252b2b91 ms=51 Check "—": no expectation |
| `op:set view view="Builder Plan" show=Grids` | green: op:set view made= changed=37ae7999ecf842189975fe7ca63893d0 ms=63 Check "—": no expectation |

### The result

The model holds: Grids 2,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 6,view: Schedule 3,view: Section 2.

## 4024. List only the walls longer than 5 m in my 8 by 6 m house with a 3 m porch wall.

- Starts from: a new Architectural project
- Ends with: Five walls on Ground, a wall schedule named Long Walls holding only walls longer than 5000 mm.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add wall from=(8000,1500) to=(11000,1500) level=Ground",
  "op:add schedule category=Walls fields=\"Mark,Type,Length,Level\" filter=\"Length;greater than;5000\" name=\"Long Walls\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-5df676121a656033 changed= ms=380 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-294f4e0920ee9209 changed=wall-5df676121a656033 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-35ac4f16380a3746 changed=wall-294f4e0920ee9209 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-8909f6aef7fb880e changed=wall-5df676121a656033,wall-35ac4f16380a3746 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(8000,1500) to=(11000,1500) level=Ground` | green: op:add wall made=wall-f6a75319ba4b025d changed= ms=2 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add schedule category=Walls fields="Mark,Type,Length,Level" filter="Length;greater than;5000" name="Long Walls"` | green: op:add schedule made=2194be93b1044b7b8d68865a2c2d648e changed= ms=16 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 5,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4025. Number the rooms on both storeys of my 8 by 6 m house and total the room areas for each level.

- Starts from: a new Architectural project
- Ends with: Nine walls on Ground and Level 1 with rooms 1, 2 and 101, a room schedule named Rooms by Level grouped by Level with area totals.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add wall from=(4000,0) to=(4000,6000) level=Ground",
  "op:add wall from=(0,0) to=(8000,0) level=\"Level 1\"",
  "op:add wall from=(8000,0) to=(8000,6000) level=\"Level 1\"",
  "op:add wall from=(8000,6000) to=(0,6000) level=\"Level 1\"",
  "op:add wall from=(0,6000) to=(0,0) level=\"Level 1\"",
  "op:add room at=(2000,3000) level=Ground name=Lounge number=1",
  "op:add room at=(6000,3000) level=Ground name=Kitchen number=2",
  "op:add room at=(4000,3000) level=\"Level 1\" name=\"Main Bedroom\" number=101",
  "op:add schedule category=Rooms fields=\"Level,Number,Name,Area\" groupby=\"Level;total;Area\" sortby=Number name=\"Rooms by Level\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-1aa5929b887c3176 changed= ms=13 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-fe5f4081b36daa3c changed=wall-1aa5929b887c3176 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-0f0502e14de9ca4d changed=wall-fe5f4081b36daa3c ms=6 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-e2d5e0948f29288b changed=wall-0f0502e14de9ca4d,wall-1aa5929b887c3176 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add wall from=(4000,0) to=(4000,6000) level=Ground` | green: op:add wall made=wall-7d7a14c45cbf62c9 changed= ms=11 Check "Walls +1": Walls 4 -> 5 (+1, expected +1) |
| `op:add wall from=(0,0) to=(8000,0) level="Level 1"` | green: op:add wall made=wall-820dae84b639f82d changed= ms=3 Check "Walls +1": Walls 5 -> 6 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level="Level 1"` | green: op:add wall made=wall-2a1ef70179617727 changed=wall-820dae84b639f82d ms=522 Check "Walls +1": Walls 6 -> 7 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level="Level 1"` | green: op:add wall made=wall-e82baee607dc4a01 changed=wall-2a1ef70179617727 ms=4 Check "Walls +1": Walls 7 -> 8 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level="Level 1"` | green: op:add wall made=wall-91b8861cfdcc9dbf changed=wall-e82baee607dc4a01,wall-820dae84b639f82d ms=10 Check "Walls +1": Walls 8 -> 9 (+1, expected +1) |
| `op:add room at=(2000,3000) level=Ground name=Lounge number=1` | green: op:add room made=room-40eaf1ed40e1a576 changed= ms=197 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) |
| `op:add room at=(6000,3000) level=Ground name=Kitchen number=2` | green: op:add room made=room-766f6a2d3e31420d changed= ms=332 Check "Rooms +1": Rooms 1 -> 2 (+1, expected +1) |
| `op:add room at=(4000,3000) level="Level 1" name="Main Bedroom" number=101` | green: op:add room made=room-01dbf906b479b2a2 changed= ms=87 Check "Rooms +1": Rooms 2 -> 3 (+1, expected +1) |
| `op:add schedule category=Rooms fields="Level,Number,Name,Area" groupby="Level;total;Area" sortby=Number name="Rooms by Level"` | green: op:add schedule made=30294cfd24224c2795919d343d8d38c1 changed= ms=19 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Rooms 3,Walls 9,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4026. Put four columns on each level of the frame and list them grouped by level.

- Starts from: a new Structural project
- Ends with: Four columns on Level 1 and four on Level 2, a column schedule named Columns by Level grouped by Level.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\"",
  "op:add column at=(6000,0) level=\"Level 1\"",
  "op:add column at=(0,6000) level=\"Level 1\"",
  "op:add column at=(6000,6000) level=\"Level 1\"",
  "op:add column at=(0,0) level=\"Level 2\"",
  "op:add column at=(6000,0) level=\"Level 2\"",
  "op:add column at=(0,6000) level=\"Level 2\"",
  "op:add column at=(6000,6000) level=\"Level 2\"",
  "op:add schedule category=\"Structural Columns\" fields=\"Level,Type,Mark,Length\" groupby=Level sortby=Level name=\"Columns by Level\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1"` | green: op:add column made=column-fed96ca9f8903209 changed= ms=16 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 1"` | green: op:add column made=column-fcaa4344064b5df6 changed= ms=4 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 1"` | green: op:add column made=column-d9c1748159308009 changed= ms=3 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(6000,6000) level="Level 1"` | green: op:add column made=column-3c56dfb8412b175d changed= ms=2 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add column at=(0,0) level="Level 2"` | green: op:add column made=column-30ca99e83a7a6914 changed= ms=4 Check "Structural Columns +1": Structural Columns 4 -> 5 (+1, expected +1) |
| `op:add column at=(6000,0) level="Level 2"` | green: op:add column made=column-f64f4add852508b4 changed= ms=4 Check "Structural Columns +1": Structural Columns 5 -> 6 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 2"` | green: op:add column made=column-97dd8874851df630 changed= ms=3 Check "Structural Columns +1": Structural Columns 6 -> 7 (+1, expected +1) |
| `op:add column at=(6000,6000) level="Level 2"` | green: op:add column made=column-d6e88128c20144db changed= ms=3 Check "Structural Columns +1": Structural Columns 7 -> 8 (+1, expected +1) |
| `op:add schedule category="Structural Columns" fields="Level,Type,Mark,Length" groupby=Level sortby=Level name="Columns by Level"` | green: op:add schedule made=def7bf0571d7416eaac9aa06f6cb0267 changed= ms=17 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 8,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Schedule 1,view: Structural Plan 2.

## 4027. Make grid A blue in the Ground plan, then change my mind and put it back to its normal colour.

- Starts from: a new Architectural project
- Ends with: Grid A on Ground with no colour override left in the Ground floor plan.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A projection_line_colour=#0050A0",
  "op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A projection_line_colour=None"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=402 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A projection_line_colour=#0050A0` | green: op:set element graphics made= changed= ms=3 Check "—": no expectation |
| `op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A projection_line_colour=None` | green: op:set element graphics made= changed= ms=2 Check "—": no expectation |

### The result

The model holds: Grids 1,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4028. Put the plan and a section of my 7 by 5 m studio on one sheet, the plan at 1:100 and the section at 1:50.

- Starts from: a new Architectural project
- Ends with: Four studio walls, a plan named Studio Plan at 1:100 and a section named Studio Section at 1:50 on sheet A130.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(7000,0) level=Ground",
  "op:add wall from=(7000,0) to=(7000,5000) level=Ground",
  "op:add wall from=(7000,5000) to=(0,5000) level=Ground",
  "op:add wall from=(0,5000) to=(0,0) level=Ground",
  "op:add view kind=plan level=Ground name=\"Studio Plan\"",
  "op:add section from=(3500,-1500) to=(3500,6500) depth=5000 name=\"Studio Section\" view=\"Studio Plan\"",
  "op:add sheet number=A130 name=\"Studio Plan and Section\" titleblock=A1",
  "op:place view view=\"Studio Plan\" sheet=A130 at=(120,60) scale=1:100 crop=(-1500,-1500) (8500,6500)",
  "op:place view view=\"Studio Section\" sheet=A130 at=(420,60) scale=1:50"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(7000,0) level=Ground` | green: op:add wall made=wall-32033de572f5d1c3 changed= ms=14 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(7000,0) to=(7000,5000) level=Ground` | green: op:add wall made=wall-50ae739e03e5ea7b changed=wall-32033de572f5d1c3 ms=288 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(7000,5000) to=(0,5000) level=Ground` | green: op:add wall made=wall-a25621b5de0b9ac1 changed=wall-50ae739e03e5ea7b ms=4 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,5000) to=(0,0) level=Ground` | green: op:add wall made=wall-4786ed9544dc171f changed=wall-a25621b5de0b9ac1,wall-32033de572f5d1c3 ms=439 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add view kind=plan level=Ground name="Studio Plan"` | green: op:add view made=aedf6698db904431a0a93d9827c92c3c changed= ms=60 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add section from=(3500,-1500) to=(3500,6500) depth=5000 name="Studio Section" view="Studio Plan"` | green: op:add section made=a4435073f68b4c1e94b0347e9d00654a changed= ms=12 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `op:add sheet number=A130 name="Studio Plan and Section" titleblock=A1` | green: op:add sheet made=sheet-A130 changed= ms=4 Check "sheet A130 exists": sheet A130 exists (9 sheet(s) in the document) |
| `op:place view view="Studio Plan" sheet=A130 at=(120,60) scale=1:100 crop=(-1500,-1500) (8500,6500)` | green: op:place view made=aedf6698db904431a0a93d9827c92c3c::sheet-A130::b560fcc8875a479f9fc1e819ebe6b33d changed= ms=168 Check "—": no expectation |
| `op:place view view="Studio Section" sheet=A130 at=(420,60) scale=1:50` | green: op:place view made=a4435073f68b4c1e94b0347e9d00654a::sheet-A130::5bccf63894f94628923a0896a565029c changed= ms=214 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 3,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 3.

## 4029. Duplicate the Ground plan for the structural engineer and hide the furniture and dimensions on the copy.

- Starts from: a new Architectural project
- Ends with: Four walls on Ground and a duplicate of the Ground plan named Ground Copy 1 with furniture and dimensions hidden.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-36d0cfc388d8c491 changed= ms=480 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-7e80a613019e2bec changed=wall-36d0cfc388d8c491 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-7363f37b1e75609f changed=wall-7e80a613019e2bec ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-e4cf4a1c5965280b changed=wall-36d0cfc388d8c491,wall-7363f37b1e75609f ms=6 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Duplicate View › Duplicate · picks — · keys — · fields — · expect view: Floor Plan +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Duplicate View › Duplicate · picks — · keys — · fields — · expect view: Floor Plan +1` | green: pressed 'Duplicate View › Duplicate' on View's Create panel (through its parent 'Duplicate View''s arrow, the row 'Duplicate'; the press stood 864 ms (the menu stood at 392 ms; its row ran 470 ms; it made 0 child widgets native)): the command 'Duplicate View › Duplicate' ran; status 'Ground Copy 1 made' Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:set view view=\"Ground Copy 1\" hide=\"Furniture,Dimensions\""
]}
```

| Line | UNION answered |
|---|---|
| `op:set view view="Ground Copy 1" hide="Furniture,Dimensions"` | green: op:set view made= changed=6d7813e5a59748b8afd5c4ce03cd8e80 ms=16 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 4030. Show my 6 by 4 m shed in the 3D view as a realistic picture without edge lines.

- Starts from: a new Architectural project
- Ends with: Four walls and a floor on Ground, and the 3D view opened with Display Options set to Realistic, no edges, shadows on.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0),(6000,0),(6000,4000),(0,4000) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-def0af78ee3fdd84 changed= ms=17 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-8c804bad18424bc3 changed=wall-def0af78ee3fdd84 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-b38cde9c15cda1d9 changed=wall-8c804bad18424bc3 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-a7dcca809f3e178b changed=wall-b38cde9c15cda1d9,wall-def0af78ee3fdd84 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0),(6000,0),(6000,4000),(0,4000) level=Ground` | green: op:add floor made=floor-c166af5ba4fea8ec changed= ms=3 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:3D View · picks — · keys — · fields — · expect —",
  "ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; OK= · expect dialog closed"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:3D View · picks — · keys — · fields — · expect —` | green: pressed '3D View' on View's Create panel: the command '3D View' ran; status 'Opened the 3D view {3D}' Check "—": no expectation |
| `ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; OK= · expect dialog closed` | green: pressed 'Display Options' on View's Graphics panel (through its fold) (the window's first paint at 90 ms in union_shell::ShellDialogWindow, dialog 'Display Options'): the dialog 'Display Options' opened and stood; closed by the player \| inside the modal 'Display Options' \| fields: Style=Realistic reads 'Realistic'; Show Edges=no reads no; Silhouette Edges=no reads no; Shadows=yes reads yes; 'OK' pressed; the dialog closed Check "dialog closed": no modal dialog stands, and no non-modal dialog window |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4031. Fill in the project details for the Harbour Street office and open a cover sheet for the set.

- Starts from: a new Architectural project
- Ends with: Project details written (name, number, client, address) and sheet A010 Cover Sheet on an A1 title block.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Manage:Project Information · picks — · keys Return · fields Project Details: Project name=Harbour Street Office; Project number=2611; Client=Harbour Street Pty Ltd; Project address=14 Harbour Street · expect dialog closed"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Manage:Project Information · picks — · keys Return · fields Project Details: Project name=Harbour Street Office; Project number=2611; Client=Harbour Street Pty Ltd; Project address=14 Harbour Street · expect dialog closed` | green: pressed 'Project Information' on Manage's Project panel (through its fold) (the window's first paint at 169 ms in union_shell::ShellDialogWindow, dialog 'Project Details'): the dialog 'Project Details' opened and stood; closed by the player \| inside the modal 'Project Details' \| fields: Project name=Harbour Street Office reads 'Harbour Street Office'; Project number=2611 reads '2611'; Client=Harbour Street Pty Ltd reads 'Harbour Street Pty Ltd'; Project address=14 Harbour Street reads '14 Harbour Street' \| keys: Return (no tool, dialog 'Project Details' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window |

```json
ops_run {"lines":[
  "op:add sheet number=A010 name=\"Cover Sheet\" titleblock=A1"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=A010 name="Cover Sheet" titleblock=A1` | green: op:add sheet made=sheet-A010 changed= ms=4 Check "sheet A010 exists": sheet A010 exists (9 sheet(s) in the document) |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4032. Open an elevations sheet and put my initials and today's issue date on it.

- Starts from: a new Architectural project
- Ends with: Sheet A220 Elevations with Drawn By JW and Sheet Issue Date 2026-11-21.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add sheet number=A220 name=Elevations titleblock=A1"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=A220 name=Elevations titleblock=A1` | green: op:add sheet made=sheet-A220 changed= ms=13 Check "sheet A220 exists": sheet A220 exists (9 sheet(s) in the document) |

```json
steps_run {"steps":[
  "ctx:sheet:Rename · picks — · keys Return · fields Project Tree: view=A220 - Elevations; Drawing: Drawn By=JW; Sheet Issue Date=2026-11-21 · expect —"
]}
```

| Line | UNION answered |
|---|---|
| `ctx:sheet:Rename · picks — · keys Return · fields Project Tree: view=A220 - Elevations; Drawing: Drawn By=JW; Sheet Issue Date=2026-11-21 · expect —` | green: right press on the Project Tree's row 'A220 - Elevations' (under 'Sheets') at px (163,218); the tree now holds 'A220 - Elevations'; its menu carried 10 row(s); the Project Tree's own menu on 'A220 - Elevations'; 'Rename' pressed: ran 0, unknown 0, modal 'Sheet' closed, 3702 ms \| inside the modal 'Sheet' \| fields: view A220 - Elevations (the row under 'Sheets') open; Drawn By=JW reads 'JW'; Sheet Issue Date=2026-11-21 reads '2026-11-21' \| keys: Return (no tool, dialog 'Sheet' -> no tool) Check "—": no expectation \| the window's first paint at 115 ms in union_shell::ShellDialogWindow, dialog 'Drawing' |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4033. Delete the trial sheet A650 from the project tree and open a proper A650 in its place.

- Starts from: a new Architectural project
- Ends with: Trial sheet A650 deleted from the project tree and a new sheet A650 Tender Notes standing in its place.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add sheet number=A650 name=\"Trial Sheet\" titleblock=A3"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=A650 name="Trial Sheet" titleblock=A3` | green: op:add sheet made=sheet-A650 changed= ms=64 Check "sheet A650 exists": sheet A650 exists (9 sheet(s) in the document) |

```json
steps_run {"steps":[
  "ctx:browser:Delete · picks — · keys Alt+Y · fields Project Tree: view=A650 - Trial Sheet · expect —"
]}
```

| Line | UNION answered |
|---|---|
| `ctx:browser:Delete · picks — · keys Alt+Y · fields Project Tree: view=A650 - Trial Sheet · expect —` | green: right press on the Project Tree's row 'A650 - Trial Sheet' (under 'Sheets') at px (163,218); the tree now holds 'A650 - Trial Sheet'; its menu carried 10 row(s); the Project Tree's own menu on 'A650 - Trial Sheet'; 'Delete' pressed: ran 0, unknown 0, modal 'Delete' closed, 1189 ms \| inside the modal 'Delete' \| fields: Project Tree: view=A650 - Trial Sheet skipped (the ctx band right-pressed that row) \| keys: Alt skipped (the picks stage's); Alt+Y delivered to QPushButton (taken) Check "—": no expectation \| the window's first paint at 320 ms in QMessageBox |

```json
ops_run {"lines":[
  "op:add sheet number=A650 name=\"Tender Notes\" titleblock=A3"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=A650 name="Tender Notes" titleblock=A3` | green: op:add sheet made=sheet-A650 changed= ms=4 Check "sheet A650 exists": sheet A650 exists (9 sheet(s) in the document) |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4034. Open three sheets for the issue and give me the sheet list schedule.

- Starts from: a new Architectural project
- Ends with: Sheets A701, A702 and A703 and the Sheet List schedule made.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add sheet number=A701 name=\"Site and Ground Plan\" titleblock=A1",
  "op:add sheet number=A702 name=\"Elevations\" titleblock=A1",
  "op:add sheet number=A703 name=\"Sections and Details\" titleblock=A1"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=A701 name="Site and Ground Plan" titleblock=A1` | green: op:add sheet made=sheet-A701 changed= ms=16 Check "sheet A701 exists": sheet A701 exists (9 sheet(s) in the document) |
| `op:add sheet number=A702 name="Elevations" titleblock=A1` | green: op:add sheet made=sheet-A702 changed= ms=4 Check "sheet A702 exists": sheet A702 exists (10 sheet(s) in the document) |
| `op:add sheet number=A703 name="Sections and Details" titleblock=A1` | green: op:add sheet made=sheet-A703 changed= ms=5 Check "sheet A703 exists": sheet A703 exists (11 sheet(s) in the document) |

```json
steps_run {"steps":[
  "ribbon:View:Schedules › Sheet List · picks — · keys Return · fields — · expect —"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Schedules › Sheet List · picks — · keys Return · fields — · expect —` | green: pressed 'Schedules › Sheet List' on View's Schedule Views panel (through its fold) (through its parent 'Schedules''s arrow, the row 'Sheet List'; the press stood 78 ms (the menu stood at 31 ms; its row ran 46 ms; the window's first paint at 47 ms in QDialog#SchedulesWindow; it made 0 child widgets native)): the command 'Schedules › Sheet List' ran; status 'Sheet List made' \| keys: Return (no tool, dialog 'Schedules' -> no tool) Check "—": no expectation |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4035. Make all four exterior elevations of my 10 by 8 m house.

- Starts from: a new Architectural project
- Ends with: Four house walls on Ground and four elevation views named for their sides.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground",
  "op:add wall from=(10000,0) to=(10000,8000) level=Ground",
  "op:add wall from=(10000,8000) to=(0,8000) level=Ground",
  "op:add wall from=(0,8000) to=(0,0) level=Ground",
  "op:add elevation at=(5000,-7000) facing=north name=\"House South Face\" view=48660e38a721430d899d5d8a96df3bec",
  "op:add elevation at=(17000,4000) facing=west name=\"House East Face\" view=48660e38a721430d899d5d8a96df3bec",
  "op:add elevation at=(5000,15000) facing=south name=\"House North Face\" view=48660e38a721430d899d5d8a96df3bec",
  "op:add elevation at=(-7000,4000) facing=east name=\"House West Face\" view=48660e38a721430d899d5d8a96df3bec"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground` | green: op:add wall made=wall-7484f4de9c5e792f changed= ms=447 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,8000) level=Ground` | green: op:add wall made=wall-3c28d5d404d44f93 changed=wall-7484f4de9c5e792f ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,8000) to=(0,8000) level=Ground` | green: op:add wall made=wall-38b24c1a447a07b4 changed=wall-3c28d5d404d44f93 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground` | green: op:add wall made=wall-2b3d2b7df3579e68 changed=wall-7484f4de9c5e792f,wall-38b24c1a447a07b4 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add elevation at=(5000,-7000) facing=north name="House South Face" view=48660e38a721430d899d5d8a96df3bec` | green: op:add elevation made=elev-d8bb7ebc7dae45e3 changed= ms=407 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) |
| `op:add elevation at=(17000,4000) facing=west name="House East Face" view=48660e38a721430d899d5d8a96df3bec` | green: op:add elevation made=elev-829b7480d26d411f changed= ms=198 Check "view: Elevation +1": view: Elevation 5 -> 6 (+1, expected +1) |
| `op:add elevation at=(5000,15000) facing=south name="House North Face" view=48660e38a721430d899d5d8a96df3bec` | green: op:add elevation made=elev-354678f6b3e34eb5 changed= ms=2372 Check "view: Elevation +1": view: Elevation 6 -> 7 (+1, expected +1) |
| `op:add elevation at=(-7000,4000) facing=east name="House West Face" view=48660e38a721430d899d5d8a96df3bec` | green: op:add elevation made=elev-86b0e6dbfe3644c5 changed= ms=291 Check "view: Elevation +1": view: Elevation 7 -> 8 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 5,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 8,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4036. Cut a long section and a cross section through my 12 by 8 m workshop.

- Starts from: a new Architectural project
- Ends with: Four workshop walls and two section views, Long Section and Cross Section.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(12000,0) level=Ground",
  "op:add wall from=(12000,0) to=(12000,8000) level=Ground",
  "op:add wall from=(12000,8000) to=(0,8000) level=Ground",
  "op:add wall from=(0,8000) to=(0,0) level=Ground",
  "op:add section from=(-2000,4000) to=(14000,4000) depth=5000 name=\"Long Section\" view=48660e38a721430d899d5d8a96df3bec",
  "op:add section from=(6000,-2000) to=(6000,10000) depth=5000 name=\"Cross Section\" view=48660e38a721430d899d5d8a96df3bec"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(12000,0) level=Ground` | green: op:add wall made=wall-7ec429eb89bc66cc changed= ms=13 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(12000,0) to=(12000,8000) level=Ground` | green: op:add wall made=wall-11eeca85c6cfbb57 changed=wall-7ec429eb89bc66cc ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(12000,8000) to=(0,8000) level=Ground` | green: op:add wall made=wall-77343beef8a3f211 changed=wall-11eeca85c6cfbb57 ms=15 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,8000) to=(0,0) level=Ground` | green: op:add wall made=wall-c1bf8a979e8fde9c changed=wall-77343beef8a3f211,wall-7ec429eb89bc66cc ms=27 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add section from=(-2000,4000) to=(14000,4000) depth=5000 name="Long Section" view=48660e38a721430d899d5d8a96df3bec` | green: op:add section made=07f9b1e8d6ec47c990d4577a052efeb5 changed= ms=30 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `op:add section from=(6000,-2000) to=(6000,10000) depth=5000 name="Cross Section" view=48660e38a721430d899d5d8a96df3bec` | green: op:add section made=01c08e07d5b44a99870a2adb39bfb56e changed= ms=15 Check "view: Section +1": view: Section 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 4,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 4.

## 4037. Cut a shallow wall section through the north wall of my 8 by 6 m room, set to medium detail.

- Starts from: a new Architectural project
- Ends with: Four walls on Ground and a section named North Wall Section, 1500 mm deep, at medium detail level.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add section from=(4000,7500) to=(4000,4500) depth=1500 name=\"North Wall Section\" view=48660e38a721430d899d5d8a96df3bec",
  "op:set id=\"North Wall Section\" key=\"Detail Level\" value=Medium"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-881f2c6d97992b71 changed= ms=473 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-71fddca9703b21cb changed=wall-881f2c6d97992b71 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-67175ee18242fd15 changed=wall-71fddca9703b21cb ms=6 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-3736009dbede69fc changed=wall-67175ee18242fd15,wall-881f2c6d97992b71 ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add section from=(4000,7500) to=(4000,4500) depth=1500 name="North Wall Section" view=48660e38a721430d899d5d8a96df3bec` | green: op:add section made=e29100712ac746ed9586aebedf17078d changed= ms=34 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `op:set id="North Wall Section" key="Detail Level" value=Medium` | green: op:set made= changed= ms=560 state=unchanged Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 3,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 3.

## 4038. Draw a 150 by 200 mm timber eaves block with a note as a 1:5 detail and put it on a detail sheet.

- Starts from: a new Architectural project
- Ends with: A drafting view named Eaves Block Detail at 1:5 holding a rectangle and a note, placed on sheet A160.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Eaves Block Detail\" scale=1:5",
  "op:add detail line points=(0,0) (150,0) (150,-200) (0,-200) (0,0) view=\"Eaves Block Detail\"",
  "op:add text at=(170,-100) view=\"Eaves Block Detail\" text=\"150 x 200 treated pine\"",
  "op:add sheet number=A160 name=\"Eaves Details\" titleblock=A3",
  "op:place view view=\"Eaves Block Detail\" sheet=A160 at=(60,100)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Eaves Block Detail" scale=1:5` | green: op:add drafting view made=1ab371109cd84ac3a0ed6b8e2df0d8c9 changed= ms=288 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (150,0) (150,-200) (0,-200) (0,0) view="Eaves Block Detail"` | green: op:add detail line made=detail-80f8d999df614f5d,detail-9707110cb03e466d,detail-2f7dc12e8f74402d,detail-5434244a355342ce changed= ms=18 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add text at=(170,-100) view="Eaves Block Detail" text="150 x 200 treated pine"` | green: op:add text made=text-0a4f5809445b4a75 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add sheet number=A160 name="Eaves Details" titleblock=A3` | green: op:add sheet made=sheet-A160 changed= ms=4 Check "sheet A160 exists": sheet A160 exists (9 sheet(s) in the document) |
| `op:place view view="Eaves Block Detail" sheet=A160 at=(60,100)` | green: op:place view made=1ab371109cd84ac3a0ed6b8e2df0d8c9::sheet-A160::22b1c881c9514b659c132ead9329de3b changed= ms=39 Check "—": no expectation |

### The result

The model holds: Levels 3,Lines 4,Text Notes 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4040. Run a supply duct with a diffuser along the corridor on Level 1 and put the plan on a sheet.

- Starts from: a new Mechanical project
- Ends with: One duct with one air terminal and one air handling unit on Level 1, and sheet M101 holding the Level 1 plan at 1:100.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Duct · picks (1000,1000) (6000,1000) · keys Escape Escape · fields Options Strip: Width=300; Height=200; System Type=Supply Air · expect Ducts +1",
  "ribbon:Systems:Air Terminal · picks (3000,1000) · keys Escape Escape · fields — · expect Air Terminals +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Duct · picks (1000,1000) (6000,1000) · keys Escape Escape · fields Options Strip: Width=300; Height=200; System Type=Supply Air · expect Ducts +1` | green: pressed 'Duct' on Systems's HVAC panel: the tool 'Duct' stands \| fields: Width=300 reads '300 mm'; Height=200 reads '200 mm'; System Type=Supply Air reads 'Supply Air' \| picks: (1000,1000) mm at px (666.6,408.4) on the plan view \| (6000,1000) mm at px (759.7,408.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ducts +1": Ducts 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Air Terminal · picks (3000,1000) · keys Escape Escape · fields — · expect Air Terminals +1` | green: pressed 'Air Terminal' on Systems's HVAC panel: the command 'Air Terminal' ran; status 'Click a face to place the air terminal' \| picks: (3000,1000) mm at px (703.8,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Diffuser -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add equipment at=(500,500) level=\"Level 1\"",
  "op:add sheet number=M101 name=\"Level 1 Ducts\" titleblock=A1",
  "op:place view view=\"Level 1\" sheet=M101 at=(60,60) scale=1:100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add equipment at=(500,500) level="Level 1"` | green: op:add equipment made=equipment-8f2386d40169a40c changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add sheet number=M101 name="Level 1 Ducts" titleblock=A1` | green: op:add sheet made=sheet-M101 changed= ms=2 Check "sheet M101 exists": sheet M101 exists (1 sheet(s) in the document) |
| `op:place view view="Level 1" sheet=M101 at=(60,60) scale=1:100` | green: op:place view made=view-level-1::sheet-M101::5525f713e7464534a15df58fdaf9d016 changed= ms=1664 Check "—": no expectation |

### The result

The model holds: Air Terminals 1,Duct Systems 1,Ducts 1,Levels 2,Mechanical Equipment 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 4041. Run a 50 mm cold water pipe along the north wall on Level 1, schedule the pipes and put the plan on a sheet.

- Starts from: a new Hydraulic project
- Ends with: Two pipes on Level 1, a pipe schedule named Pipe List and sheet P101 holding the Level 1 plan at 1:100.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (1000,5000) (7000,5000) · keys Escape Escape · fields — · expect Pipes +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (1000,5000) (7000,5000) · keys Escape Escape · fields — · expect Pipes +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| picks: (1000,5000) mm at px (666.6,333.9) on the plan view \| (7000,5000) mm at px (778.3,333.9) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add pipe from=(1000,3000) to=(7000,3000) level=\"Level 1\" diameter=50 elevation=2400",
  "op:add schedule category=Pipes fields=\"Mark,Level,Type,Diameter,Count\" name=\"Pipe List\"",
  "op:add sheet number=P101 name=\"Level 1 Pipework\" titleblock=A1",
  "op:place view view=\"Level 1\" sheet=P101 at=(60,60) scale=1:100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add pipe from=(1000,3000) to=(7000,3000) level="Level 1" diameter=50 elevation=2400` | green: op:add pipe made=pipe-341d7bee3e0d7b07,system-fc660a8fa8b528d2 changed= ms=375 Check "Pipes +1": Pipes 1 -> 2 (+1, expected +1) |
| `op:add schedule category=Pipes fields="Mark,Level,Type,Diameter,Count" name="Pipe List"` | green: op:add schedule made=01786c71cd58406c8dbccbada7584e4a changed= ms=15 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |
| `op:add sheet number=P101 name="Level 1 Pipework" titleblock=A1` | green: op:add sheet made=sheet-P101 changed= ms=39 Check "sheet P101 exists": sheet P101 exists (1 sheet(s) in the document) |
| `op:place view view="Level 1" sheet=P101 at=(60,60) scale=1:100` | green: op:place view made=view-level-1::sheet-P101::673d06008d334aa1af524d3f1d517824 changed= ms=2751 Check "—": no expectation |

### The result

The model holds: Levels 2,Pipes 2,Piping Systems 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 4042. Lay out four sprinkler heads on a branch pipe on Level 1 and list the heads.

- Starts from: a new Fire Protection project
- Ends with: One branch pipe and four sprinklers on Level 1 and a sprinkler schedule named Sprinkler List.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (1000,1000) (7000,1000) · keys Escape Escape · fields — · expect Pipes +1",
  "ribbon:Systems:Sprinkler · picks (2000,1000) · keys Escape Escape · fields — · expect Sprinklers +1",
  "ribbon:Systems:Sprinkler · picks (3500,1000) · keys Escape Escape · fields — · expect Sprinklers +1",
  "ribbon:Systems:Sprinkler · picks (5000,1000) · keys Escape Escape · fields — · expect Sprinklers +1",
  "ribbon:Systems:Sprinkler · picks (6500,1000) · keys Escape Escape · fields — · expect Sprinklers +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (1000,1000) (7000,1000) · keys Escape Escape · fields — · expect Pipes +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| picks: (1000,1000) mm at px (666.6,408.4) on the plan view \| (7000,1000) mm at px (778.3,408.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Sprinkler · picks (2000,1000) · keys Escape Escape · fields — · expect Sprinklers +1` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| picks: (2000,1000) mm at px (685.2,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +1": Sprinklers 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Sprinkler · picks (3500,1000) · keys Escape Escape · fields — · expect Sprinklers +1` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| picks: (3500,1000) mm at px (713.1,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +1": Sprinklers 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Sprinkler · picks (5000,1000) · keys Escape Escape · fields — · expect Sprinklers +1` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| picks: (5000,1000) mm at px (741.1,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +1": Sprinklers 2 -> 3 (+1, expected +1) |
| `ribbon:Systems:Sprinkler · picks (6500,1000) · keys Escape Escape · fields — · expect Sprinklers +1` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| picks: (6500,1000) mm at px (769.0,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +1": Sprinklers 3 -> 4 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=Sprinklers fields=\"Mark,Level,Type,Count\" name=\"Sprinkler List\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category=Sprinklers fields="Mark,Level,Type,Count" name="Sprinkler List"` | green: op:add schedule made=83b2a9647697460d8d2a65193117811b changed= ms=271 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Sprinklers 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 4043. Put three power outlets and a conduit run on Level 1 and make an electrical sheet for the plan.

- Starts from: a new Electrical project
- Ends with: Three outlets and one conduit on Level 1, a fixtures schedule named Outlet List and sheet E101 holding the Level 1 plan.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Outlet · picks (1000,1000) · keys Escape Escape · fields — · expect Electrical Fixtures +1",
  "ribbon:Systems:Outlet · picks (3000,1000) · keys Escape Escape · fields — · expect Electrical Fixtures +1",
  "ribbon:Systems:Outlet · picks (5000,1000) · keys Escape Escape · fields — · expect Electrical Fixtures +1",
  "ribbon:Systems:Conduit · picks (1000,3000) (6000,3000) · keys Escape Escape · fields — · expect Conduits +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Outlet · picks (1000,1000) · keys Escape Escape · fields — · expect Electrical Fixtures +1` | green: pressed 'Outlet' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Outlet'; the press stood 1048 ms (the menu stood at 57 ms; its row ran 989 ms; it made 0 child widgets native)): the tool 'Outlet' stands \| picks: (1000,1000) mm at px (666.6,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Outlet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Fixtures +1": Electrical Fixtures 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Outlet · picks (3000,1000) · keys Escape Escape · fields — · expect Electrical Fixtures +1` | green: pressed 'Outlet' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Outlet'; the press stood 2101 ms (the menu stood at 135 ms; its row ran 1964 ms; it made 0 child widgets native)): the tool 'Outlet' stands \| picks: (3000,1000) mm at px (703.8,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Outlet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Fixtures +1": Electrical Fixtures 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Outlet · picks (5000,1000) · keys Escape Escape · fields — · expect Electrical Fixtures +1` | green: pressed 'Outlet' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Outlet'; the press stood 1040 ms (the menu stood at 31 ms; its row ran 984 ms; it made 0 child widgets native)): the tool 'Outlet' stands \| picks: (5000,1000) mm at px (741.1,408.4) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Outlet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Fixtures +1": Electrical Fixtures 2 -> 3 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (1000,3000) (6000,3000) · keys Escape Escape · fields — · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| picks: (1000,3000) mm at px (666.6,371.2) on the plan view \| (6000,3000) mm at px (759.7,371.2) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=\"Electrical Fixtures\" fields=\"Mark,Level,Type,Count\" name=\"Outlet List\"",
  "op:add sheet number=E101 name=\"Level 1 Power\" titleblock=A1",
  "op:place view view=\"Level 1\" sheet=E101 at=(60,60) scale=1:100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category="Electrical Fixtures" fields="Mark,Level,Type,Count" name="Outlet List"` | green: op:add schedule made=2091bec6df5c4e5fb3766d68da9fa49d changed= ms=121 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |
| `op:add sheet number=E101 name="Level 1 Power" titleblock=A1` | green: op:add sheet made=sheet-E101 changed= ms=5 Check "sheet E101 exists": sheet E101 exists (1 sheet(s) in the document) |
| `op:place view view="Level 1" sheet=E101 at=(60,60) scale=1:100` | green: op:place view made=view-level-1::sheet-E101::14d716dd58e94be789a632cec78c3938 changed= ms=1234 Check "—": no expectation |

### The result

The model holds: Conduits 1,Electrical Fixtures 3,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 4044. Make the sections and elevations for every grid line of my 8 by 6 m building in one go.

- Starts from: a new Architectural project
- Ends with: Four grids and four walls on Ground, plus the sections and elevations Automatic Sections made from the grids, with their sheets.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:add grid from=(8000,-2000) to=(8000,8000) name=B",
  "op:add grid from=(-2000,0) to=(10000,0) name=1",
  "op:add grid from=(-2000,6000) to=(10000,6000) name=2"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=574 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(8000,-2000) to=(8000,8000) name=B` | green: op:add grid made=grid-B changed= ms=3 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(-2000,0) to=(10000,0) name=1` | green: op:add grid made=grid-1 changed= ms=4 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add grid from=(-2000,6000) to=(10000,6000) name=2` | green: op:add grid made=grid-2 changed= ms=5 Check "Grids +1": Grids 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:views-autosections-dialog · picks — · keys — · fields Automatic Sections Settings: Sections=yes; Elevations=yes; Sheets=yes; Grids=all; OK= · expect view: Section +2"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:views-autosections-dialog · picks — · keys — · fields Automatic Sections Settings: Sections=yes; Elevations=yes; Sheets=yes; Grids=all; OK= · expect view: Section +2` | green: pressed 'views-autosections-dialog' on View's Create panel (the window's first paint at 118 ms in union_shell::ShellDialogWindow, dialog 'views-autosections'): the dialog 'Automatic Sections Settings' opened and stood; closed by the player \| inside the modal 'Automatic Sections Settings' \| fields: Sections=yes reads yes; Elevations=yes reads yes; Sheets=yes reads yes; Grids=all reads 'all'; 'OK' pressed; the dialog closed Check "view: Section +2": view: Section 2 -> 4 (+2, expected +2) |

### The result

The model holds: Grids 4,Levels 3,mark: Elevation 5,mark: Section 4,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 8,view: Floor Plan 4,view: Schedule 3,view: Section 4.

## 4045. Draw an enlargement callout around the entrance of my 8 by 6 m house.

- Starts from: a new Architectural project
- Ends with: Four walls on Ground and a callout view drawn as a rectangle around the entrance.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-62dc04b6d8198755 changed= ms=45 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-65e2362418ce81e1 changed=wall-62dc04b6d8198755 ms=13 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-0c4ea3657eedd19e changed=wall-65e2362418ce81e1 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-f73c20092d66aac0 changed=wall-62dc04b6d8198755,wall-0c4ea3657eedd19e ms=4 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Callout › Rectangle · picks (1000,-500) (3500,1500) · keys Escape Escape · fields — · expect view: Callout +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Callout › Rectangle · picks (1000,-500) (3500,1500) · keys Escape Escape · fields — · expect view: Callout +1` | green: pressed 'Callout › Rectangle' on View's Create panel (through its parent 'Callout''s arrow, the row 'Rectangle'; the press stood 1789 ms (the menu stood at 608 ms; its row ran 1180 ms; it made 0 child widgets native)): the command 'Callout › Rectangle' ran; status 'Click to draw the enlargement, or sketch it' \| picks: (1000,-500) mm at px (677.3,441.7) on the plan view \| (3500,1500) mm at px (750.7,383.0) on the plan view \| presses to the tool 2 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "view: Callout +1": view: Callout 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Callout 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4046. Put a section line and an elevation marker on the Ground plan of my 8 by 6 m house.

- Starts from: a new Architectural project
- Ends with: Four walls on Ground, one section line south of the house and one elevation marker.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-364b5103757e7a34 changed= ms=44 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-c3cca97760fd225c changed=wall-364b5103757e7a34 ms=4 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-e3c1fe0146581c73 changed=wall-c3cca97760fd225c ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-d65eea4b821df95e changed=wall-364b5103757e7a34,wall-e3c1fe0146581c73 ms=3 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Section · picks (2000,3000) (6000,3000) · keys Escape Escape · fields — · expect view: Section +1",
  "ribbon:View:Elevation · picks (4000,-3000) · keys Escape Escape · fields — · expect view: Elevation +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Section · picks (2000,3000) (6000,3000) · keys Escape Escape · fields — · expect view: Section +1` | green: pressed 'Section' on View's Create panel: the tool 'Section' stands \| picks: (2000,3000) mm at px (706.7,339.0) on the plan view \| (6000,3000) mm at px (824.0,339.0) on the plan view \| presses to the tool 2, selection changed \| keys: Escape (tool Section -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `ribbon:View:Elevation · picks (4000,-3000) · keys Escape Escape · fields — · expect view: Elevation +1` | green: pressed 'Elevation' on View's Create panel: the tool 'Elevation' stands \| picks: (4000,-3000) mm at px (765.3,515.0) on the plan view \| presses to the tool 1 (the tool ended on the press), selection unchanged \| keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 2,mark: Section 3,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 5,view: Floor Plan 4,view: Schedule 3,view: Section 3.

## 4047. Start a 1:10 drafting view called Gutter Detail, open a sheet for it and place it.

- Starts from: a new Architectural project
- Ends with: A drafting view named Gutter Detail at 1:10 and sheet A170 Gutter Detail holding it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Gutter Detail; Scale=1:10 · expect view: Drafting View +1",
  "ribbon:View:Sheet · picks — · keys Return · fields New Sheet: Name=Gutter Detail; Number=A170 · expect dialog closed",
  "ribbon:View:Viewport · picks — · keys Return · fields Place View: Views=Drafting View · expect dialog closed",
  "ribbon:View:Viewport · picks (300,450) · keys Return · fields Place View: Views=Drafting View · expect dialog closed"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Gutter Detail; Scale=1:10 · expect view: Drafting View +1` | green: pressed 'Drafting View' on View's Create panel (the window's first paint at 180 ms in union_shell::ShellDialogWindow, dialog 'New Drafting View'): the dialog 'New Drafting View' opened and stood; closed by the player \| inside the modal 'New Drafting View' \| fields: Name=Gutter Detail reads 'Gutter Detail'; Scale=1:10 reads '1:10' \| keys: Return (no tool, dialog 'New Drafting View' -> no tool) Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `ribbon:View:Sheet · picks — · keys Return · fields New Sheet: Name=Gutter Detail; Number=A170 · expect dialog closed` | green: pressed 'Sheet' on View's Sheet Composition panel (through its fold) (the window's first paint at 163 ms in union_shell::ShellDialogWindow, dialog 'New Sheet'): the dialog 'New Sheet' opened and stood; closed by the player \| inside the modal 'New Sheet' \| fields: Name=Gutter Detail reads 'Gutter Detail'; Number=A170 reads 'A170' \| keys: Return (no tool, dialog 'New Sheet' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window |
| `ribbon:View:Viewport · picks — · keys Return · fields Place View: Views=Drafting View · expect dialog closed` | green: pressed 'Viewport' on View's Sheet Composition panel (through its fold) (the window's first paint at 102 ms in union_shell::ShellDialogWindow, dialog 'Place View'): the tool 'Viewport' stands; a dialog opened (the player plays the step's fields and keys inside it, R-3545b) \| inside the modal 'Views' \| fields: table 'Views' row 'Drafting View' pressed \| keys: Return (no tool, dialog 'Views' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window |
| `ribbon:View:Viewport · picks (300,450) · keys Return · fields Place View: Views=Drafting View · expect dialog closed` | green: pressed 'Viewport' on View's Sheet Composition panel (through its fold) (the window's first paint at 112 ms in union_shell::ShellDialogWindow, dialog 'Place View'): the dialog 'Views' opened and stood; closed by the player \| inside the modal 'Views' \| fields: table 'Views' row 'Drafting View' pressed \| picks: (300,450) mm at px (475.6,226.1) on the sheet view \| presses to the tool 0 (the tool ended on the press), selection unchanged \| keys: Return (no tool, dialog 'Views' -> no tool) Check "dialog closed": no modal dialog stands, and no non-modal dialog window |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4048. Hide all the 900 x 2100 doors in the Ground plan with a view filter.

- Starts from: a new Architectural project
- Ends with: Walls and one 900 x 2100 door on Ground, a view filter named Hide 900 Doors on Doors with Type equals 900 x 2100, applied to the Ground plan.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4",
  "ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1",
  "view-filters:add:Hide 900 Doors:Doors;Type;equals;900 x 2100:hide=1 · picks — · keys — · fields — · expect —",
  "view-filters:apply:Hide 900 Doors · picks — · keys — · fields — · expect —"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4` | green: pressed 'Wall' on Structure's Structure panel: the tool 'Wall' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,0) mm at px (882.7,427.0) on the plan view \| (8000,6000) mm at px (882.7,251.0) on the plan view \| (0,6000) mm at px (648.0,251.0) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +4": Walls 0 -> 4 (+4, expected +4) |
| `ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (2000,0) mm at px (706.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `view-filters:add:Hide 900 Doors:Doors;Type;equals;900 x 2100:hide=1 · picks — · keys — · fields — · expect —` | green: filter 'Hide 900 Doors' reads back with 1 rule(s), category 'Doors' Check "—": no expectation |
| `view-filters:apply:Hide 900 Doors · picks — · keys — · fields — · expect —` | green: filter 'Hide 900 Doors' bound at 1 of 1, enabled 1 Check "—": no expectation |

### The result

The model holds: Doors 1,Levels 3,Openings 1,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4050. Show my steel frame in 3D on a dark grey background without level or grid lines.

- Starts from: a new Structural project
- Ends with: Four columns and two beams on Level 1, and the 3D view with levels and grids hidden on a dark grey map.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\"",
  "op:add column at=(7000,0) level=\"Level 1\"",
  "op:add column at=(0,5000) level=\"Level 1\"",
  "op:add column at=(7000,5000) level=\"Level 1\"",
  "op:add beam from=(0,0) to=(7000,0) level=\"Level 1\"",
  "op:add beam from=(0,5000) to=(7000,5000) level=\"Level 1\"",
  "op:set view view=view-3d hide=Levels,Grids map=plain:darkgrey"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1"` | green: op:add column made=column-7733f0c67f0a780e changed= ms=15 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(7000,0) level="Level 1"` | green: op:add column made=column-fed97fb26dfcdb4b changed= ms=113 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(0,5000) level="Level 1"` | green: op:add column made=column-9b4eb091f20879d4 changed= ms=3 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(7000,5000) level="Level 1"` | green: op:add column made=column-8417baf50b4d2bfb changed= ms=3 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add beam from=(0,0) to=(7000,0) level="Level 1"` | green: op:add beam made=beam-08b24e82d1cb1f55 changed= ms=5 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,5000) to=(7000,5000) level="Level 1"` | green: op:add beam made=beam-4e39501aec24a3d0 changed= ms=4 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:set view view=view-3d hide=Levels,Grids map=plain:darkgrey` | green: op:set view made= changed=view-3d ms=26 Check "—": no expectation |

### The result

The model holds: Levels 2,Structural Columns 4,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 2.

## 4051. Make a framing plan for Level 2 that shows the beams only, not the columns.

- Starts from: a new Structural project
- Ends with: Four columns and two beams on Level 2, and a structural plan named Level 2 Beams Only with Structural Columns hidden.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 2\"",
  "op:add column at=(8000,0) level=\"Level 2\"",
  "op:add column at=(0,6000) level=\"Level 2\"",
  "op:add column at=(8000,6000) level=\"Level 2\"",
  "op:add beam from=(0,0) to=(8000,0) level=\"Level 2\"",
  "op:add beam from=(0,6000) to=(8000,6000) level=\"Level 2\"",
  "op:add view kind=structural level=\"Level 2\" name=\"Level 2 Beams Only\"",
  "op:set view view=\"Level 2 Beams Only\" hide=\"Structural Columns\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 2"` | green: op:add column made=column-6e39451a1a2d4913 changed= ms=16 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(8000,0) level="Level 2"` | green: op:add column made=column-ec85aae30c3af590 changed= ms=3 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 2"` | green: op:add column made=column-b9e026bc4037b91f changed= ms=4 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(8000,6000) level="Level 2"` | green: op:add column made=column-082f5f55691bd893 changed= ms=2 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add beam from=(0,0) to=(8000,0) level="Level 2"` | green: op:add beam made=beam-ce933ce353a7cb57 changed= ms=3 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,6000) to=(8000,6000) level="Level 2"` | green: op:add beam made=beam-ce47518c7724efa7 changed= ms=5 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add view kind=structural level="Level 2" name="Level 2 Beams Only"` | green: op:add view made=f34b3776a8544ec7970929c459f42ecd changed= ms=12 Check "view: Structural Plan +1": view: Structural Plan 2 -> 3 (+1, expected +1) |
| `op:set view view="Level 2 Beams Only" hide="Structural Columns"` | green: op:set view made= changed=f34b3776a8544ec7970929c459f42ecd ms=12 Check "—": no expectation |

### The result

The model holds: Levels 2,Structural Columns 4,Structural Framing 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Structural Plan 3.

## 4052. Put ceilings at 2700 mm in my two rooms and list the ceiling areas by level.

- Starts from: a new Architectural project
- Ends with: Two ceilings at 2700 mm on Ground, a ceiling schedule named Ceiling Areas sorted by Level.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add ceiling boundary=(0,0) (4000,0) (4000,5000) (0,5000) level=Ground height=2700",
  "op:add ceiling boundary=(4000,0) (8000,0) (8000,5000) (4000,5000) level=Ground height=2700",
  "op:add schedule category=Ceilings fields=Level,Type,Area,Perimeter sortby=Level name=\"Ceiling Areas\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add ceiling boundary=(0,0) (4000,0) (4000,5000) (0,5000) level=Ground height=2700` | green: op:add ceiling made=ceiling-1f33b36760624728 changed= ms=258 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) |
| `op:add ceiling boundary=(4000,0) (8000,0) (8000,5000) (4000,5000) level=Ground height=2700` | green: op:add ceiling made=ceiling-dddab7a48fc90c36 changed= ms=4 Check "Ceilings +1": Ceilings 1 -> 2 (+1, expected +1) |
| `op:add schedule category=Ceilings fields=Level,Type,Area,Perimeter sortby=Level name="Ceiling Areas"` | green: op:add schedule made=d89e006e716945eb85dd73649926581a changed= ms=10 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

### The result

The model holds: Ceilings 2,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4054. List only the beams longer than 6 m from my four-beam frame.

- Starts from: a new Structural project
- Ends with: Four beams of 5000, 6500, 5000 and 8000 mm on Level 1, a beam schedule named Long Beams holding only beams longer than 6000 mm.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add beam from=(0,0) to=(5000,0) level=\"Level 1\"",
  "op:add beam from=(0,4000) to=(6500,4000) level=\"Level 1\"",
  "op:add beam from=(0,8000) to=(5000,8000) level=\"Level 1\"",
  "op:add beam from=(0,12000) to=(8000,12000) level=\"Level 1\"",
  "op:add schedule category=\"Structural Framing\" fields=\"Mark,Type,Length,Level\" filter=\"Length;greater than;6000\" name=\"Long Beams\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add beam from=(0,0) to=(5000,0) level="Level 1"` | green: op:add beam made=beam-95ab1dba9bc50ec1 changed= ms=16 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,4000) to=(6500,4000) level="Level 1"` | green: op:add beam made=beam-4f098f0cb3c56fb9 changed= ms=21 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add beam from=(0,8000) to=(5000,8000) level="Level 1"` | green: op:add beam made=beam-8e04b5c62ad43947 changed= ms=6 Check "Structural Framing +1": Structural Framing 2 -> 3 (+1, expected +1) |
| `op:add beam from=(0,12000) to=(8000,12000) level="Level 1"` | green: op:add beam made=beam-296398fb0938016a changed= ms=4 Check "Structural Framing +1": Structural Framing 3 -> 4 (+1, expected +1) |
| `op:add schedule category="Structural Framing" fields="Mark,Type,Length,Level" filter="Length;greater than;6000" name="Long Beams"` | green: op:add schedule made=a5bba30d79d54e32b35606e6c0f6e6ea changed= ms=24 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Framing 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 1,view: Schedule 1,view: Structural Plan 2.

## 4055. Schedule the ducts on Level 1 by system type and put the list on its own sheet.

- Starts from: a new Mechanical project
- Ends with: Two ducts and one diffuser on Level 1, a duct schedule named Duct List and sheet M201 holding it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Duct · picks (1000,1000) (6000,1000) · keys Escape Escape · fields — · expect Ducts +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Duct · picks (1000,1000) (6000,1000) · keys Escape Escape · fields — · expect Ducts +1` | green: pressed 'Duct' on Systems's HVAC panel: the tool 'Duct' stands \| picks: (1000,1000) mm at px (666.6,408.4) on the plan view \| (6000,1000) mm at px (759.7,408.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Ducts +1": Ducts 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add duct from=(1000,3000) to=(6000,3000) level=\"Level 1\" width=300 height=150 elevation=2700 system=\"Return Air\"",
  "op:add schedule category=Ducts fields=\"Mark,Level,Type,Width,Height,System Type\" sortby=\"System Type\" name=\"Duct List\"",
  "op:add sheet number=M201 name=\"Duct Schedule\" titleblock=A1",
  "op:place view view=\"Duct List\" sheet=M201 at=(40,300) table_width=260 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add duct from=(1000,3000) to=(6000,3000) level="Level 1" width=300 height=150 elevation=2700 system="Return Air"` | green: op:add duct made=duct-22971d795a99d63a,system-65e26bc356469daa changed= ms=2 Check "Ducts +1": Ducts 1 -> 2 (+1, expected +1) |
| `op:add schedule category=Ducts fields="Mark,Level,Type,Width,Height,System Type" sortby="System Type" name="Duct List"` | green: op:add schedule made=04e01abaa5ed476397e3562c9d4620b5 changed= ms=8 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |
| `op:add sheet number=M201 name="Duct Schedule" titleblock=A1` | green: op:add sheet made=sheet-M201 changed= ms=5 Check "sheet M201 exists": sheet M201 exists (1 sheet(s) in the document) |
| `op:place view view="Duct List" sheet=M201 at=(40,300) table_width=260 text_size=3.5` | green: op:place view made=04e01abaa5ed476397e3562c9d4620b5::sheet-M201::042010f26167456b9a70ffdc19ede4a1 changed= ms=43 Check "—": no expectation |

### The result

The model holds: Duct Systems 2,Ducts 2,Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 4056. List the air handling units and diffusers on Level 1 of the mechanical model.

- Starts from: a new Mechanical project
- Ends with: Two air handling units and three diffusers on Level 1, an equipment schedule named Plant List and a terminal schedule named Diffuser List.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add equipment at=(500,500) level=\"Level 1\"",
  "op:add equipment at=(500,3000) level=\"Level 1\"",
  "op:add terminal at=(3000,1000) level=\"Level 1\"",
  "op:add terminal at=(5000,1000) level=\"Level 1\"",
  "op:add terminal at=(7000,1000) level=\"Level 1\"",
  "op:add schedule category=\"Mechanical Equipment\" fields=\"Mark,Level,Type,Count\" name=\"Plant List\"",
  "op:add schedule category=\"Air Terminals\" fields=\"Mark,Level,Type,Count\" name=\"Diffuser List\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add equipment at=(500,500) level="Level 1"` | green: op:add equipment made=equipment-633659e26860e25f changed= ms=4 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add equipment at=(500,3000) level="Level 1"` | green: op:add equipment made=equipment-c4b3677f96c1a927 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(3000,1000) level="Level 1"` | green: op:add terminal made=terminal-f604cd4e91974a63 changed= ms=1 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) |
| `op:add terminal at=(5000,1000) level="Level 1"` | green: op:add terminal made=terminal-20155836904b4a50 changed= ms=2 Check "Air Terminals +1": Air Terminals 1 -> 2 (+1, expected +1) |
| `op:add terminal at=(7000,1000) level="Level 1"` | green: op:add terminal made=terminal-d6d1bff692d17ef3 changed= ms=1 Check "Air Terminals +1": Air Terminals 2 -> 3 (+1, expected +1) |
| `op:add schedule category="Mechanical Equipment" fields="Mark,Level,Type,Count" name="Plant List"` | green: op:add schedule made=a76754baea7e4f169a9591238d27821d changed= ms=11 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |
| `op:add schedule category="Air Terminals" fields="Mark,Level,Type,Count" name="Diffuser List"` | green: op:add schedule made=eb215d29a8fb460bb1c15340c15fa411 changed= ms=8 Check "view: Schedule +1": view: Schedule 1 -> 2 (+1, expected +1) |

### The result

The model holds: Air Terminals 3,Levels 2,Mechanical Equipment 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 2.

## 4057. I put the section on the wrong sheet; take it off sheet A310 and put it on A311.

- Starts from: a new Architectural project
- Ends with: Section Gable Section placed on A310, taken off, and placed again on sheet A311.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name=\"Gable Section\" view=48660e38a721430d899d5d8a96df3bec",
  "op:add sheet number=A310 name=\"Sections\" titleblock=A1",
  "op:add sheet number=A311 name=\"Gable Sections\" titleblock=A1",
  "op:place view view=\"Gable Section\" sheet=A310 at=(100,100) scale=1:50",
  "op:remove view view=\"Gable Section\" sheet=A310",
  "op:place view view=\"Gable Section\" sheet=A311 at=(100,100) scale=1:50"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-63df04bde7078b22 changed= ms=336 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-db852e66750f094a changed=wall-63df04bde7078b22 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-81c54d0661457db1 changed=wall-db852e66750f094a ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-c3be616b22413bc5 changed=wall-81c54d0661457db1,wall-63df04bde7078b22 ms=5 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name="Gable Section" view=48660e38a721430d899d5d8a96df3bec` | green: op:add section made=ee82bd7f721243c1b6b422f340de992e changed= ms=13 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `op:add sheet number=A310 name="Sections" titleblock=A1` | green: op:add sheet made=sheet-A310 changed= ms=3 Check "sheet A310 exists": sheet A310 exists (9 sheet(s) in the document) |
| `op:add sheet number=A311 name="Gable Sections" titleblock=A1` | green: op:add sheet made=sheet-A311 changed= ms=3 Check "sheet A311 exists": sheet A311 exists (10 sheet(s) in the document) |
| `op:place view view="Gable Section" sheet=A310 at=(100,100) scale=1:50` | green: op:place view made=ee82bd7f721243c1b6b422f340de992e::sheet-A310::8c09fd54974345c0a3b001dab3eba1d8 changed= ms=76 Check "—": no expectation |
| `op:remove view view="Gable Section" sheet=A310` | green: op:remove view made= changed=ee82bd7f721243c1b6b422f340de992e::sheet-A310::8c09fd54974345c0a3b001dab3eba1d8 ms=4 Check "—": no expectation |
| `op:place view view="Gable Section" sheet=A311 at=(100,100) scale=1:50` | green: op:place view made=ee82bd7f721243c1b6b422f340de992e::sheet-A311::90ec5cd273c542baa7ad8c79c5a9418e changed= ms=50 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 3,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 3.

## 4058. The plan is too big on sheet A120; take it off and put it back at 1:100.

- Starts from: a new Architectural project
- Ends with: Plan Shed Plan placed on A120 at 1:50, removed, and placed again at 1:100.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(10000,0) level=Ground",
  "op:add wall from=(10000,0) to=(10000,6000) level=Ground",
  "op:add wall from=(10000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground",
  "op:add view kind=plan level=Ground name=\"Shed Plan\"",
  "op:add sheet number=A120 name=\"Shed Plan\" titleblock=A1",
  "op:place view view=\"Shed Plan\" sheet=A120 at=(60,40) scale=1:50",
  "op:remove view view=\"Shed Plan\" sheet=A120",
  "op:place view view=\"Shed Plan\" sheet=A120 at=(60,100) scale=1:100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(10000,0) level=Ground` | green: op:add wall made=wall-fa6ccbcbb2447ad4 changed= ms=12 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(10000,0) to=(10000,6000) level=Ground` | green: op:add wall made=wall-42591300abdc3907 changed=wall-fa6ccbcbb2447ad4 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(10000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-4686392619f42566 changed=wall-42591300abdc3907 ms=3 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-09ff5aad0b2798a8 changed=wall-fa6ccbcbb2447ad4,wall-4686392619f42566 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add view kind=plan level=Ground name="Shed Plan"` | green: op:add view made=8118ddc0cf44418d94dad9ed7dc7b698 changed= ms=12 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add sheet number=A120 name="Shed Plan" titleblock=A1` | green: op:add sheet made=sheet-A120 changed= ms=3 Check "sheet A120 exists": sheet A120 exists (9 sheet(s) in the document) |
| `op:place view view="Shed Plan" sheet=A120 at=(60,40) scale=1:50` | green: op:place view made=8118ddc0cf44418d94dad9ed7dc7b698::sheet-A120::70adac3dab8240d4b6f2ae289df5a7c2 changed= ms=81 note=the frame is 514.7 x 514.7 mm and its lower-left corner stands at (-72.4,187.5) in sheet mm and it runs off the sheet, which is 841 x 594 mm Check "—": no expectation |
| `op:remove view view="Shed Plan" sheet=A120` | green: op:remove view made= changed=8118ddc0cf44418d94dad9ed7dc7b698::sheet-A120::70adac3dab8240d4b6f2ae289df5a7c2 ms=4 Check "—": no expectation |
| `op:place view view="Shed Plan" sheet=A120 at=(60,100) scale=1:100` | green: op:place view made=8118ddc0cf44418d94dad9ed7dc7b698::sheet-A120::c37634fadab34447af87810997f855b7 changed= ms=595 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 4059. The client wants US and A4 paper: open an ANSI D, an ARCH D, an A4 and a sheet with no title block.

- Starts from: a new Architectural project
- Ends with: Sheets A801 on ANSI_D, A802 on ARCH_D, A803 with no title block and A804 on A4.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add sheet number=A801 name=\"US Plans\" titleblock=ANSI_D",
  "op:add sheet number=A802 name=\"US Elevations\" titleblock=ARCH_D",
  "op:add sheet number=A803 name=\"Loose Details\" titleblock=None",
  "op:add sheet number=A804 name=\"Site Note\" titleblock=A4"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=A801 name="US Plans" titleblock=ANSI_D` | green: op:add sheet made=sheet-A801 changed= ms=14 Check "sheet A801 exists": sheet A801 exists (9 sheet(s) in the document) |
| `op:add sheet number=A802 name="US Elevations" titleblock=ARCH_D` | green: op:add sheet made=sheet-A802 changed= ms=4 Check "sheet A802 exists": sheet A802 exists (10 sheet(s) in the document) |
| `op:add sheet number=A803 name="Loose Details" titleblock=None` | green: op:add sheet made=sheet-A803 changed= ms=3 Check "sheet A803 exists": sheet A803 exists (11 sheet(s) in the document) |
| `op:add sheet number=A804 name="Site Note" titleblock=A4` | green: op:add sheet made=sheet-A804 changed= ms=3 Check "sheet A804 exists": sheet A804 exists (12 sheet(s) in the document) |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4060. Dimension grids A to C across the Ground plan and put a north arrow on it.

- Starts from: a new Architectural project
- Ends with: Grids A, B and C on Ground, one dimension string across them below the plan and a north arrow beside the plan.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:add grid from=(8000,-2000) to=(8000,8000) name=B",
  "op:add grid from=(16000,-2000) to=(16000,8000) name=C",
  "op:add dimension chain points=(0,-1000) (8000,-1000) (16000,-1000) view=48660e38a721430d899d5d8a96df3bec offset=-3000",
  "op:add symbol at=(-3000,7000) view=48660e38a721430d899d5d8a96df3bec"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=328 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(8000,-2000) to=(8000,8000) name=B` | green: op:add grid made=grid-B changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:add grid from=(16000,-2000) to=(16000,8000) name=C` | green: op:add grid made=grid-C changed= ms=3 Check "Grids +1": Grids 2 -> 3 (+1, expected +1) |
| `op:add dimension chain points=(0,-1000) (8000,-1000) (16000,-1000) view=48660e38a721430d899d5d8a96df3bec offset=-3000` | green: op:add dimension chain made=dimstr-70f0f74cff3e4641 changed= ms=60 note=segments 8000, 8000; offset -3000: the dimension line stands 3000 mm to the right of the direction from the first point to the last (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add symbol at=(-3000,7000) view=48660e38a721430d899d5d8a96df3bec` | green: op:add symbol made=symbol-6b87884ca2514765 changed= ms=8 Check "Symbol +1": Symbol 0 -> 1 (+1, expected +1) |

### The result

The model holds: Dimensions 1,Grids 3,Levels 3,Symbol 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4061. Draw a 1:10 wall detail with a 300 mm outline, a brick region, a 90 mm insulation batt and a width dimension, and put it on a sheet.

- Starts from: a new Architectural project
- Ends with: A drafting view named Wall Detail at 1:10 with an outline, a filled region, an insulation batt and a dimension, placed on sheet A180.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add drafting view name=\"Wall Detail\" scale=1:10",
  "op:add detail line points=(0,0) (300,0) (300,-1500) (0,-1500) (0,0) view=\"Wall Detail\"",
  "op:add filled region boundary=(310,0) (400,0) (400,-1500) (310,-1500) view=\"Wall Detail\"",
  "op:add insulation from=(150,-100) to=(150,-1400) view=\"Wall Detail\" width=90",
  "op:add dimension from=(0,0) to=(300,0) view=\"Wall Detail\" offset=100",
  "op:add sheet number=A180 name=\"Wall Details\" titleblock=A3",
  "op:place view view=\"Wall Detail\" sheet=A180 at=(60,80)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add drafting view name="Wall Detail" scale=1:10` | green: op:add drafting view made=ef602e2bf616464c887997f0057f055c changed= ms=12 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add detail line points=(0,0) (300,0) (300,-1500) (0,-1500) (0,0) view="Wall Detail"` | green: op:add detail line made=detail-1c2b43dec5224e8c,detail-29de4f384f734f62,detail-203a7ff4a7da42f2,detail-36b2e40aa78c4f09 changed= ms=2 Check "Lines +4": Lines 0 -> 4 (+4, expected +4) |
| `op:add filled region boundary=(310,0) (400,0) (400,-1500) (310,-1500) view="Wall Detail"` | green: op:add filled region made=region-72c37e760dc64093 changed= ms=3 Check "Filled Regions +1": Filled Regions 0 -> 1 (+1, expected +1) |
| `op:add insulation from=(150,-100) to=(150,-1400) view="Wall Detail" width=90` | green: op:add insulation made=insul-8e66ae9b0a7eca0d changed= ms=2 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) |
| `op:add dimension from=(0,0) to=(300,0) view="Wall Detail" offset=100` | green: op:add dimension made=dim-99e0bb52b6c14f86 changed= ms=90 note=offset 100: the dimension line stands 100 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) |
| `op:add sheet number=A180 name="Wall Details" titleblock=A3` | green: op:add sheet made=sheet-A180 changed= ms=3 Check "sheet A180 exists": sheet A180 exists (9 sheet(s) in the document) |
| `op:place view view="Wall Detail" sheet=A180 at=(60,80)` | green: op:place view made=ef602e2bf616464c887997f0057f055c::sheet-A180::5a9a6a31b7144e32abdbbaae0b67df48 changed= ms=15 Check "—": no expectation |

### The result

The model holds: Detail Items 1,Dimensions 1,Filled Regions 1,Levels 3,Lines 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4062. Put the 3D view of my 6 by 4 m shed on a presentation sheet.

- Starts from: a new Architectural project
- Ends with: Four walls and a floor on Ground, and sheet A900 holding the 3D view at 1:100.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(6000,0) level=Ground",
  "op:add wall from=(6000,0) to=(6000,4000) level=Ground",
  "op:add wall from=(6000,4000) to=(0,4000) level=Ground",
  "op:add wall from=(0,4000) to=(0,0) level=Ground",
  "op:add floor boundary=(0,0),(6000,0),(6000,4000),(0,4000) level=Ground",
  "op:add sheet number=A900 name=\"Presentation\" titleblock=A1",
  "op:place view view=view-3d sheet=A900 at=(80,80) scale=1:100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(6000,0) level=Ground` | green: op:add wall made=wall-bbab98ff5647ab69 changed= ms=496 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(6000,0) to=(6000,4000) level=Ground` | green: op:add wall made=wall-6c6dccdec5eaeedc changed=wall-bbab98ff5647ab69 ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(6000,4000) to=(0,4000) level=Ground` | green: op:add wall made=wall-965ee9d29d07e911 changed=wall-6c6dccdec5eaeedc ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,4000) to=(0,0) level=Ground` | green: op:add wall made=wall-27531cf7a1ca01a1 changed=wall-965ee9d29d07e911,wall-bbab98ff5647ab69 ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0),(6000,0),(6000,4000),(0,4000) level=Ground` | green: op:add floor made=floor-7dd503405ffe32e5 changed= ms=1 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add sheet number=A900 name="Presentation" titleblock=A1` | green: op:add sheet made=sheet-A900 changed= ms=16 Check "sheet A900 exists": sheet A900 exists (9 sheet(s) in the document) |
| `op:place view view=view-3d sheet=A900 at=(80,80) scale=1:100` | green: op:place view made=view-3d::sheet-A900::112a1fe51fa34a5fb138b35c2eb388b2 changed= ms=72 Check "—": no expectation |

### The result

The model holds: Floors 1,Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4063. Count my doors by level, one row a level, with the count for each.

- Starts from: a new Architectural project
- Ends with: Four walls with two doors on Ground and a door schedule named Door Count by Level, grouped by Level, one row a type.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4",
  "ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Architecture:Door · picks (6000,6000) · keys Escape Escape · fields — · expect Doors +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4` | green: pressed 'Wall' on Structure's Structure panel: the tool 'Wall' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,0) mm at px (882.7,427.0) on the plan view \| (8000,6000) mm at px (882.7,251.0) on the plan view \| (0,6000) mm at px (648.0,251.0) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +4": Walls 0 -> 4 (+4, expected +4) |
| `ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (2000,0) mm at px (706.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Architecture:Door · picks (6000,6000) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (6000,6000) mm at px (824.0,251.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=Doors fields=Level,Type,Count groupby=Level itemize=no name=\"Door Count by Level\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category=Doors fields=Level,Type,Count groupby=Level itemize=no name="Door Count by Level"` | green: op:add schedule made=70f53e8eb69d4f2aab94838d52c1de1a changed= ms=14 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

### The result

The model holds: Doors 2,Levels 3,Openings 2,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4064. Make a level schedule, then undo it and put it back.

- Starts from: a new Architectural project
- Ends with: A level schedule named Level Check made, undone with Undo and made again with Redo.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add schedule category=Levels fields=Name,Elevation sortby=Elevation name=\"Level Check\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category=Levels fields=Name,Elevation sortby=Elevation name="Level Check"` | green: op:add schedule made=2252ef68618941d09670472459a749dc changed= ms=14 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "qa:Undo · picks — · keys — · fields — · expect view: Schedule -1",
  "qa:Redo · picks — · keys — · fields — · expect view: Schedule +1"
]}
```

| Line | UNION answered |
|---|---|
| `qa:Undo · picks — · keys — · fields — · expect view: Schedule -1` | green: QToolButton pressed; a command ran Check "view: Schedule -1": view: Schedule 4 -> 3 (-1, expected -1) |
| `qa:Redo · picks — · keys — · fields — · expect view: Schedule +1` | green: QToolButton pressed; a command ran Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |

### The result

The model holds: Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 4,view: Section 2.

## 4065. Add a mezzanine at 3000 mm with its own floor plan at 1:50 and a floor over a 6 by 4 m deck.

- Starts from: a new Architectural project
- Ends with: A level named Mezzanine at 3000 mm, a floor on it, and a floor plan named Mezzanine Plan at 1:50.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=3000 name=Mezzanine",
  "op:add floor boundary=(0,0),(6000,0),(6000,4000),(0,4000) level=Mezzanine",
  "op:add view kind=plan level=Mezzanine name=\"Mezzanine Plan\"",
  "op:set id=\"Mezzanine Plan\" key=Scale value=1:50"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=3000 name=Mezzanine` | green: op:add level made=level-Mezzanine changed= ms=12 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add floor boundary=(0,0),(6000,0),(6000,4000),(0,4000) level=Mezzanine` | green: op:add floor made=floor-ab0270f6ff17d7da changed= ms=3 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add view kind=plan level=Mezzanine name="Mezzanine Plan"` | green: op:add view made=4c3431fc54274c039da8e8ffbe36b4c6 changed= ms=8 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:set id="Mezzanine Plan" key=Scale value=1:50` | green: op:set made= changed="Mezzanine Plan" ms=2 Check "—": no expectation |

### The result

The model holds: Floors 1,Levels 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 4066. Make grids A and B grey and half see-through in the Ground plan so they do not fight the walls.

- Starts from: a new Architectural project
- Ends with: Grids A and B on Ground drawn grey with 60 per cent transparency in the Ground floor plan only.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add grid from=(0,-2000) to=(0,8000) name=A",
  "op:add grid from=(8000,-2000) to=(8000,8000) name=B",
  "op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A,grid-B projection_line_colour=#808080 transparency=60"
]}
```

| Line | UNION answered |
|---|---|
| `op:add grid from=(0,-2000) to=(0,8000) name=A` | green: op:add grid made=grid-A changed= ms=29 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) |
| `op:add grid from=(8000,-2000) to=(8000,8000) name=B` | green: op:add grid made=grid-B changed= ms=3 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) |
| `op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A,grid-B projection_line_colour=#808080 transparency=60` | green: op:set element graphics made= changed= ms=2 Check "—": no expectation |

### The result

The model holds: Grids 2,Levels 3,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 4,view: Schedule 3,view: Section 2.

## 4070. Make a drawing set for my 8 by 6 m cottage: a plan, a section, an elevation and the door list, all on one sheet.

- Starts from: a new Architectural project
- Ends with: Four walls, a door and a window on Ground, a Cottage Plan, Cottage Section, Cottage Front Elevation and Cottage Door List, all four placed on sheet A401.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4",
  "ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1",
  "ribbon:Structure:Opening:Window · picks (5000,6000) · keys Escape Escape · fields — · expect Windows +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4` | green: pressed 'Wall' on Structure's Structure panel: the tool 'Wall' stands \| picks: (0,0) mm at px (648.0,427.0) on the plan view \| (8000,0) mm at px (882.7,427.0) on the plan view \| (8000,6000) mm at px (882.7,251.0) on the plan view \| (0,6000) mm at px (648.0,251.0) on the plan view \| (0,0) mm at px (648.0,427.0) on the plan view \| presses to the tool 5, selection unchanged \| keys: Escape (tool Wall -> tool Wall, 'Wall' still stands (the key went to union_shell::Viewport)); Escape (tool Wall -> no tool) Check "Walls +4": Walls 0 -> 4 (+4, expected +4) |
| `ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1` | green: pressed 'Door' on Architecture's Build panel: the tool 'Door' stands \| picks: (2000,0) mm at px (706.7,427.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Doors +1": Doors 0 -> 1 (+1, expected +1) |
| `ribbon:Structure:Opening:Window · picks (5000,6000) · keys Escape Escape · fields — · expect Windows +1` | green: pressed 'Window' on Architecture's Build panel: the tool 'Window' stands (the walk names Structure; the tile stands on Architecture) \| picks: (5000,6000) mm at px (794.7,251.0) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Windows +1": Windows 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add view kind=plan level=Ground name=\"Cottage Plan\"",
  "op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name=\"Cottage Section\" view=\"Cottage Plan\"",
  "op:add elevation at=(4000,-6000) facing=north name=\"Cottage Front Elevation\" view=\"Cottage Plan\"",
  "op:add schedule category=Doors fields=Mark,Level,Type,Width,Height name=\"Cottage Door List\" sortby=Mark",
  "op:add sheet number=A401 name=\"Cottage Drawings\" titleblock=A1",
  "op:place view view=\"Cottage Plan\" sheet=A401 at=(40,300) scale=1:100",
  "op:place view view=\"Cottage Section\" sheet=A401 at=(300,300) scale=1:100",
  "op:place view view=\"Cottage Front Elevation\" sheet=A401 at=(560,300) scale=1:100",
  "op:place view view=\"Cottage Door List\" sheet=A401 at=(560,100) table_width=200 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add view kind=plan level=Ground name="Cottage Plan"` | green: op:add view made=d22a7056a53542458eb39aae8c12c376 changed= ms=6 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name="Cottage Section" view="Cottage Plan"` | green: op:add section made=9f6c40381b724ae5a7ce4d3cebfa543f changed= ms=11 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) |
| `op:add elevation at=(4000,-6000) facing=north name="Cottage Front Elevation" view="Cottage Plan"` | green: op:add elevation made=elev-326877b91deb4d53 changed= ms=10 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) |
| `op:add schedule category=Doors fields=Mark,Level,Type,Width,Height name="Cottage Door List" sortby=Mark` | green: op:add schedule made=31793d5e51774514bfe26788b6dd87b0 changed= ms=8 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) |
| `op:add sheet number=A401 name="Cottage Drawings" titleblock=A1` | green: op:add sheet made=sheet-A401 changed= ms=3 Check "sheet A401 exists": sheet A401 exists (9 sheet(s) in the document) |
| `op:place view view="Cottage Plan" sheet=A401 at=(40,300) scale=1:100` | green: op:place view made=d22a7056a53542458eb39aae8c12c376::sheet-A401::6c07446697904387aa54fafd7a144453 changed= ms=1138 Check "—": no expectation |
| `op:place view view="Cottage Section" sheet=A401 at=(300,300) scale=1:100` | green: op:place view made=9f6c40381b724ae5a7ce4d3cebfa543f::sheet-A401::89acadabb2bd4b06a7f8762ece50a032 changed= ms=56 Check "—": no expectation |
| `op:place view view="Cottage Front Elevation" sheet=A401 at=(560,300) scale=1:100` | green: op:place view made=elev-326877b91deb4d53::sheet-A401::bc59fd6ce0ce439c8a266f6b416d2b8b changed= ms=882 Check "—": no expectation |
| `op:place view view="Cottage Door List" sheet=A401 at=(560,100) table_width=200 text_size=3.5` | green: op:place view made=31793d5e51774514bfe26788b6dd87b0::sheet-A401::ee8fa60703224ce48291824920acfd65 changed= ms=105 Check "—": no expectation |

### The result

The model holds: Doors 1,Levels 3,Openings 2,Walls 4,Windows 1,mark: Elevation 2,mark: Section 3,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 5,view: Floor Plan 5,view: Schedule 4,view: Section 3.

## 4071. Make a drawing set for my steel frame: a framing plan, a section, an elevation and the column and beam schedules, on one sheet.

- Starts from: a new Structural project
- Ends with: Four columns and two beams on Level 1, a Frame Plan, Frame Section, Frame Elevation, Frame Columns and Frame Beams, all placed on sheet S301.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\"",
  "op:add column at=(8000,0) level=\"Level 1\"",
  "op:add column at=(0,6000) level=\"Level 1\"",
  "op:add column at=(8000,6000) level=\"Level 1\"",
  "op:add beam from=(0,0) to=(8000,0) level=\"Level 1\"",
  "op:add beam from=(0,6000) to=(8000,6000) level=\"Level 1\"",
  "op:add view kind=structural level=\"Level 1\" name=\"Frame Plan\"",
  "op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name=\"Frame Section\" view=\"Frame Plan\"",
  "op:add elevation at=(4000,-6000) facing=north name=\"Frame Elevation\" view=\"Frame Plan\"",
  "op:add schedule category=\"Structural Columns\" fields=Type,Count,Length name=\"Frame Columns\" itemize=no",
  "op:add schedule category=\"Structural Framing\" fields=Type,Count,Length name=\"Frame Beams\" itemize=no",
  "op:add sheet number=S301 name=\"Frame Drawings\" titleblock=A1",
  "op:place view view=\"Frame Plan\" sheet=S301 at=(40,300) scale=1:100",
  "op:place view view=\"Frame Section\" sheet=S301 at=(300,300) scale=1:100",
  "op:place view view=\"Frame Elevation\" sheet=S301 at=(560,300) scale=1:100",
  "op:place view view=\"Frame Columns\" sheet=S301 at=(40,100) table_width=160 text_size=3.5",
  "op:place view view=\"Frame Beams\" sheet=S301 at=(300,100) table_width=160 text_size=3.5"
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1"` | green: op:add column made=column-816ecdb19399e035 changed= ms=13 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(8000,0) level="Level 1"` | green: op:add column made=column-e6627b09d7d73ec4 changed= ms=2 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 1"` | green: op:add column made=column-c3ee86321a4476d7 changed= ms=2 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(8000,6000) level="Level 1"` | green: op:add column made=column-63c9f164cb5d5283 changed= ms=2 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add beam from=(0,0) to=(8000,0) level="Level 1"` | green: op:add beam made=beam-ce846bb618331388 changed= ms=17 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,6000) to=(8000,6000) level="Level 1"` | green: op:add beam made=beam-891059eb0cfc8e90 changed= ms=4 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add view kind=structural level="Level 1" name="Frame Plan"` | green: op:add view made=7b3ddc267d484135bb1424ad49eda9dc changed= ms=14 Check "view: Structural Plan +1": view: Structural Plan 2 -> 3 (+1, expected +1) |
| `op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name="Frame Section" view="Frame Plan"` | green: op:add section made=1ec0d41570254968a2d50033636f4dab changed= ms=13 Check "view: Section +1": view: Section 0 -> 1 (+1, expected +1) |
| `op:add elevation at=(4000,-6000) facing=north name="Frame Elevation" view="Frame Plan"` | green: op:add elevation made=elev-fd20f4f1f7cf4abf changed= ms=13 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) |
| `op:add schedule category="Structural Columns" fields=Type,Count,Length name="Frame Columns" itemize=no` | green: op:add schedule made=d9d99640752c4d6bbeae9b724e6c1a49 changed= ms=13 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |
| `op:add schedule category="Structural Framing" fields=Type,Count,Length name="Frame Beams" itemize=no` | green: op:add schedule made=339c06629b3f4e90a2a0204f8ef609c7 changed= ms=10 Check "view: Schedule +1": view: Schedule 1 -> 2 (+1, expected +1) |
| `op:add sheet number=S301 name="Frame Drawings" titleblock=A1` | green: op:add sheet made=sheet-S301 changed= ms=4 Check "sheet S301 exists": sheet S301 exists (1 sheet(s) in the document) |
| `op:place view view="Frame Plan" sheet=S301 at=(40,300) scale=1:100` | green: op:place view made=7b3ddc267d484135bb1424ad49eda9dc::sheet-S301::7c1288cd7e964e8690c4f24653dc21dd changed= ms=125 Check "—": no expectation |
| `op:place view view="Frame Section" sheet=S301 at=(300,300) scale=1:100` | green: op:place view made=1ec0d41570254968a2d50033636f4dab::sheet-S301::8a1cdbe64a2341b7ab59f3814aa4561f changed= ms=57 Check "—": no expectation |
| `op:place view view="Frame Elevation" sheet=S301 at=(560,300) scale=1:100` | green: op:place view made=elev-fd20f4f1f7cf4abf::sheet-S301::f82c0ef28b21475692934fe0abd72f5c changed= ms=63 Check "—": no expectation |
| `op:place view view="Frame Columns" sheet=S301 at=(40,100) table_width=160 text_size=3.5` | green: op:place view made=d9d99640752c4d6bbeae9b724e6c1a49::sheet-S301::1fb7bb48ab3e41ffbbbf39b20deb6b28 changed= ms=72 Check "—": no expectation |
| `op:place view view="Frame Beams" sheet=S301 at=(300,100) table_width=160 text_size=3.5` | green: op:place view made=339c06629b3f4e90a2a0204f8ef609c7::sheet-S301::9f282b8c77914316957f49bf0a39ffc8 changed= ms=82 Check "—": no expectation |

### The result

The model holds: Levels 2,Structural Columns 4,Structural Framing 2,mark: Elevation 5,mark: Section 1,view: 3D View 1,view: Elevation 5,view: Floor Plan 1,view: Schedule 2,view: Section 1,view: Structural Plan 3.

## 4072. Lay out four light fittings and a cable tray on Level 1 and list the fittings.

- Starts from: a new Electrical project
- Ends with: Four lighting fixtures and one cable tray on Level 1, and a fixture schedule named Light Fitting List.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Lighting Fixture · picks (1500,1500) · keys Escape Escape · fields — · expect Lighting Fixtures +1",
  "ribbon:Systems:Lighting Fixture · picks (4500,1500) · keys Escape Escape · fields — · expect Lighting Fixtures +1",
  "ribbon:Systems:Lighting Fixture · picks (1500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +1",
  "ribbon:Systems:Lighting Fixture · picks (4500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +1",
  "ribbon:Systems:Cable Tray · picks (500,3000) (5500,3000) · keys Escape Escape · fields — · expect Cable Trays +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Lighting Fixture · picks (1500,1500) · keys Escape Escape · fields — · expect Lighting Fixtures +1` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (1500,1500) mm at px (675.9,399.1) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +1": Lighting Fixtures 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Lighting Fixture · picks (4500,1500) · keys Escape Escape · fields — · expect Lighting Fixtures +1` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (4500,1500) mm at px (731.7,399.1) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +1": Lighting Fixtures 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Lighting Fixture · picks (1500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +1` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (1500,4500) mm at px (675.9,343.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +1": Lighting Fixtures 2 -> 3 (+1, expected +1) |
| `ribbon:Systems:Lighting Fixture · picks (4500,4500) · keys Escape Escape · fields — · expect Lighting Fixtures +1` | green: pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands \| picks: (4500,4500) mm at px (731.7,343.3) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Lighting Fixtures +1": Lighting Fixtures 3 -> 4 (+1, expected +1) |
| `ribbon:Systems:Cable Tray · picks (500,3000) (5500,3000) · keys Escape Escape · fields — · expect Cable Trays +1` | green: pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands \| picks: (500,3000) mm at px (657.3,371.2) on the plan view \| (5500,3000) mm at px (750.4,371.2) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Cable Trays +1": Cable Trays 0 -> 1 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=\"Lighting Fixtures\" fields=\"Mark,Level,Type,Count\" name=\"Light Fitting List\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category="Lighting Fixtures" fields="Mark,Level,Type,Count" name="Light Fitting List"` | green: op:add schedule made=03fb309a0304435ab822e40a60478b41 changed= ms=13 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Cable Trays 1,Levels 2,Lighting Fixtures 4,Lighting Fixtures Tags 4,Tags 4,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 4073. Place three fixtures on a 50 mm supply pipe on Level 1 and list the fixtures.

- Starts from: a new Hydraulic project
- Ends with: One supply pipe and three plumbing fixtures on Level 1, and a fixture schedule named Fixture List.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Hydraulic** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (500,1000) (6500,1000) · keys Escape Escape · fields — · expect Pipes +1",
  "ribbon:Systems:Plumbing Fixture · picks (1500,2000) · keys Escape Escape · fields — · expect Plumbing Fixtures +1",
  "ribbon:Systems:Plumbing Fixture · picks (3000,2000) · keys Escape Escape · fields — · expect Plumbing Fixtures +1",
  "ribbon:Systems:Plumbing Fixture · picks (4500,2000) · keys Escape Escape · fields — · expect Plumbing Fixtures +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (500,1000) (6500,1000) · keys Escape Escape · fields — · expect Pipes +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| picks: (500,1000) mm at px (657.3,408.4) on the plan view \| (6500,1000) mm at px (769.0,408.4) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Plumbing Fixture · picks (1500,2000) · keys Escape Escape · fields — · expect Plumbing Fixtures +1` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (1500,2000) mm at px (675.9,389.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +1": Plumbing Fixtures 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Plumbing Fixture · picks (3000,2000) · keys Escape Escape · fields — · expect Plumbing Fixtures +1` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (3000,2000) mm at px (703.8,389.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +1": Plumbing Fixtures 1 -> 2 (+1, expected +1) |
| `ribbon:Systems:Plumbing Fixture · picks (4500,2000) · keys Escape Escape · fields — · expect Plumbing Fixtures +1` | green: pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands \| picks: (4500,2000) mm at px (731.7,389.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Plumbing Fixtures +1": Plumbing Fixtures 2 -> 3 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=\"Plumbing Fixtures\" fields=\"Mark,Level,Type,Count\" name=\"Fixture List\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category="Plumbing Fixtures" fields="Mark,Level,Type,Count" name="Fixture List"` | green: op:add schedule made=ca8fb6ae72d94a7dbb8b2039f18cf45d changed= ms=10 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Plumbing Fixtures 3,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 4074. Put the switchboard in the plant room on Level 1 with two conduit runs and a conduit schedule.

- Starts from: a new Electrical project
- Ends with: One electrical equipment item and two conduit runs on Level 1, and a conduit schedule named Conduit List by length.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Electrical Equipment · picks (500,500) · keys Escape Escape · fields — · expect Electrical Equipment +1",
  "ribbon:Systems:Conduit · picks (1000,500) (6000,500) · keys Escape Escape · fields — · expect Conduits +1",
  "ribbon:Systems:Conduit · picks (1000,2500) (4000,2500) · keys Escape Escape · fields — · expect Conduits +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Electrical Equipment · picks (500,500) · keys Escape Escape · fields — · expect Electrical Equipment +1` | green: pressed 'Electrical Equipment' on Systems's Electrical panel (through its fold): the tool 'Electrical Equipment' stands \| picks: (500,500) mm at px (657.3,417.7) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Electrical Equipment -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Electrical Equipment +1": Electrical Equipment 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (1000,500) (6000,500) · keys Escape Escape · fields — · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| picks: (1000,500) mm at px (666.6,417.7) on the plan view \| (6000,500) mm at px (759.7,417.7) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Conduit · picks (1000,2500) (4000,2500) · keys Escape Escape · fields — · expect Conduits +1` | green: pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands \| picks: (1000,2500) mm at px (666.6,380.5) on the plan view \| (4000,2500) mm at px (722.4,380.5) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Conduits +1": Conduits 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add schedule category=Conduits fields=\"Mark,Level,Type,Length,Diameter\" sortby=Length name=\"Conduit List\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add schedule category=Conduits fields="Mark,Level,Type,Length,Diameter" sortby=Length name="Conduit List"` | green: op:add schedule made=433c6ef8aa224ae8abb0a084b1d3bbca changed= ms=9 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) |

### The result

The model holds: Conduits 2,Electrical Equipment 1,Electrical Equipment Tags 1,Levels 2,Tags 1,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Schedule 1.

## 4075. Put a symbols legend and the general notes together on one cover sheet.

- Starts from: a new Architectural project
- Ends with: A legend named Symbols and a drafting view named Cover Notes with two notes, both placed on sheet A001.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add legend name=Symbols scale=1:50",
  "op:add drafting view name=\"Cover Notes\" scale=1:1",
  "op:add text at=(0,-10) view=\"Cover Notes\" text=\"1. Refer to the specification for finishes.\"",
  "op:add text at=(0,-18) view=\"Cover Notes\" text=\"2. Levels are in metres above the datum.\"",
  "op:add sheet number=A001 name=\"Cover Sheet\" titleblock=A1",
  "op:place view view=\"Symbols\" sheet=A001 at=(60,300)",
  "op:place view view=\"Cover Notes\" sheet=A001 at=(300,300)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add legend name=Symbols scale=1:50` | green: op:add legend made=b72dc5cd4e964f1793cce8f5a208700d changed= ms=18 Check "view: Legend +1": view: Legend 0 -> 1 (+1, expected +1) |
| `op:add drafting view name="Cover Notes" scale=1:1` | green: op:add drafting view made=1822c7a2ac9246de9d56716d1a0d1ba7 changed= ms=9 Check "view: Drafting View +1": view: Drafting View 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-10) view="Cover Notes" text="1. Refer to the specification for finishes."` | green: op:add text made=text-80c2e24ab09941a3 changed= ms=6 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) |
| `op:add text at=(0,-18) view="Cover Notes" text="2. Levels are in metres above the datum."` | green: op:add text made=text-91b99bf910124d47 changed= ms=2 Check "Text Notes +1": Text Notes 1 -> 2 (+1, expected +1) |
| `op:add sheet number=A001 name="Cover Sheet" titleblock=A1` | green: op:add sheet made=sheet-A001 changed= ms=3 Check "sheet A001 exists": sheet A001 exists (9 sheet(s) in the document) |
| `op:place view view="Symbols" sheet=A001 at=(60,300)` | green: op:place view made=b72dc5cd4e964f1793cce8f5a208700d::sheet-A001::f2c23c6aae3342749e4af9e8a4c71ec1 changed= ms=16 Check "—": no expectation |
| `op:place view view="Cover Notes" sheet=A001 at=(300,300)` | green: op:place view made=1822c7a2ac9246de9d56716d1a0d1ba7::sheet-A001::98bffbb97133460dbbc3f357d2baef76 changed= ms=14 Check "—": no expectation |

### The result

The model holds: Levels 3,Text Notes 2,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Drafting View 1,view: Elevation 4,view: Floor Plan 4,view: Legend 1,view: Schedule 3,view: Section 2.

## 4076. Run a sprinkler branch on Level 1, make a sheet for it and put the Level 1 plan on it at 1:100.

- Starts from: a new Fire Protection project
- Ends with: One pipe and two sprinklers on Level 1, and sheet FP101 holding the Level 1 plan at 1:100.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Fire Protection** template (File, New): on the AI door that press is the person's own.

```json
steps_run {"steps":[
  "ribbon:Systems:Pipe · picks (1000,2000) (6000,2000) · keys Escape Escape · fields — · expect Pipes +1",
  "ribbon:Systems:Sprinkler · picks (2500,2000) · keys Escape Escape · fields — · expect Sprinklers +1",
  "ribbon:Systems:Sprinkler · picks (4500,2000) · keys Escape Escape · fields — · expect Sprinklers +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:Systems:Pipe · picks (1000,2000) (6000,2000) · keys Escape Escape · fields — · expect Pipes +1` | green: pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands \| picks: (1000,2000) mm at px (666.6,389.8) on the plan view \| (6000,2000) mm at px (759.7,389.8) on the plan view \| presses to the tool 2, selection unchanged \| keys: Escape (tool Pipe -> tool Pipe, 'Pipe' still stands (the key went to union_shell::Viewport)); Escape (tool Pipe -> no tool) Check "Pipes +1": Pipes 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Sprinkler · picks (2500,2000) · keys Escape Escape · fields — · expect Sprinklers +1` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| picks: (2500,2000) mm at px (694.5,389.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +1": Sprinklers 0 -> 1 (+1, expected +1) |
| `ribbon:Systems:Sprinkler · picks (4500,2000) · keys Escape Escape · fields — · expect Sprinklers +1` | green: pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands \| picks: (4500,2000) mm at px (731.7,389.8) on the plan view \| presses to the tool 1, selection unchanged \| keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "Sprinklers +1": Sprinklers 1 -> 2 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add sheet number=FP101 name=\"Level 1 Sprinklers\" titleblock=A1",
  "op:place view view=\"Level 1\" sheet=FP101 at=(60,60) scale=1:100"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=FP101 name="Level 1 Sprinklers" titleblock=A1` | green: op:add sheet made=sheet-FP101 changed= ms=2 Check "sheet FP101 exists": sheet FP101 exists (1 sheet(s) in the document) |
| `op:place view view="Level 1" sheet=FP101 at=(60,60) scale=1:100` | green: op:place view made=view-level-1::sheet-FP101::f11d2404bc0643d9acc934bd0cb846cf changed= ms=92 Check "—": no expectation |

### The result

The model holds: Levels 2,Pipes 1,Piping Systems 1,Sprinklers 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3.

## 4077. Open an electrical sheet and put a legend of the symbols on it.

- Starts from: a new Electrical project
- Ends with: A legend named Electrical Symbols at 1:20 placed on sheet E001.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Electrical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add legend name=\"Electrical Symbols\" scale=1:20",
  "op:add sheet number=E001 name=\"Electrical Legend\" titleblock=A1",
  "op:place view view=\"Electrical Symbols\" sheet=E001 at=(60,300)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add legend name="Electrical Symbols" scale=1:20` | green: op:add legend made=df8fa37ed3ce41868a9a70559010c756 changed= ms=15 Check "view: Legend +1": view: Legend 0 -> 1 (+1, expected +1) |
| `op:add sheet number=E001 name="Electrical Legend" titleblock=A1` | green: op:add sheet made=sheet-E001 changed= ms=2 Check "sheet E001 exists": sheet E001 exists (1 sheet(s) in the document) |
| `op:place view view="Electrical Symbols" sheet=E001 at=(60,300)` | green: op:place view made=df8fa37ed3ce41868a9a70559010c756::sheet-E001::616bde150aed426688fce6bfc216ef9d changed= ms=12 Check "—": no expectation |

### The result

The model holds: Levels 2,mark: Elevation 4,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Legend 1.

## 4078. Cut a section through the plant room on Level 1 and name it Plant Section.

- Starts from: a new Mechanical project
- Ends with: One air handling unit on Level 1 and a section view named Plant Section cut through it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Mechanical** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add equipment at=(2000,2000) level=\"Level 1\"",
  "op:add section from=(2000,-2000) to=(2000,6000) depth=4000 name=\"Plant Section\" view=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add equipment at=(2000,2000) level="Level 1"` | green: op:add equipment made=equipment-6cc6a9b2fe62988f changed= ms=3 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) |
| `op:add section from=(2000,-2000) to=(2000,6000) depth=4000 name="Plant Section" view="Level 1"` | green: op:add section made=8a8eee1dce4043ec823b311adbd4f151 changed= ms=18 Check "view: Section +1": view: Section 0 -> 1 (+1, expected +1) |

### The result

The model holds: Levels 2,Mechanical Equipment 1,mark: Elevation 4,mark: Section 1,view: 3D View 1,view: Elevation 4,view: Floor Plan 3,view: Section 1.

## 4079. Make elevations of the north and south faces of my steel frame.

- Starts from: a new Structural project
- Ends with: Four columns and two beams on Level 1 and two elevation views, Frame North Face and Frame South Face.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Structural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add column at=(0,0) level=\"Level 1\"",
  "op:add column at=(8000,0) level=\"Level 1\"",
  "op:add column at=(0,6000) level=\"Level 1\"",
  "op:add column at=(8000,6000) level=\"Level 1\"",
  "op:add beam from=(0,0) to=(8000,0) level=\"Level 1\"",
  "op:add beam from=(0,6000) to=(8000,6000) level=\"Level 1\"",
  "op:add elevation at=(4000,-6000) facing=north name=\"Frame South Face\" view=\"Level 1\"",
  "op:add elevation at=(4000,12000) facing=south name=\"Frame North Face\" view=\"Level 1\""
]}
```

| Line | UNION answered |
|---|---|
| `op:add column at=(0,0) level="Level 1"` | green: op:add column made=column-97f00623f7d2be5e changed= ms=50 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) |
| `op:add column at=(8000,0) level="Level 1"` | green: op:add column made=column-af588a76391ff4a6 changed= ms=66 Check "Structural Columns +1": Structural Columns 1 -> 2 (+1, expected +1) |
| `op:add column at=(0,6000) level="Level 1"` | green: op:add column made=column-c17d0f83e268aae6 changed= ms=3 Check "Structural Columns +1": Structural Columns 2 -> 3 (+1, expected +1) |
| `op:add column at=(8000,6000) level="Level 1"` | green: op:add column made=column-66535645b204e850 changed= ms=3 Check "Structural Columns +1": Structural Columns 3 -> 4 (+1, expected +1) |
| `op:add beam from=(0,0) to=(8000,0) level="Level 1"` | green: op:add beam made=beam-b23ac611edf480ae changed= ms=5 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) |
| `op:add beam from=(0,6000) to=(8000,6000) level="Level 1"` | green: op:add beam made=beam-15842c5c9269fa1e changed= ms=5 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) |
| `op:add elevation at=(4000,-6000) facing=north name="Frame South Face" view="Level 1"` | green: op:add elevation made=elev-eaa3cce601fa4880 changed= ms=15 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) |
| `op:add elevation at=(4000,12000) facing=south name="Frame North Face" view="Level 1"` | green: op:add elevation made=elev-127bc6676e05434f changed= ms=13 Check "view: Elevation +1": view: Elevation 5 -> 6 (+1, expected +1) |

### The result

The model holds: Levels 2,Structural Columns 4,Structural Framing 2,mark: Elevation 6,view: 3D View 1,view: Elevation 6,view: Floor Plan 1,view: Structural Plan 2.

## 4080. Make a roof plan of my 9 by 6 m house at 1:100 and put it on a sheet of its own.

- Starts from: a new Architectural project
- Ends with: A 25 degree roof over the house, a floor plan named Roof Setout Plan on the Roof level at 1:100, and sheet A135 holding it.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add roof boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground slope=25",
  "op:add view kind=plan level=Roof name=\"Roof Setout Plan\"",
  "op:set id=\"Roof Setout Plan\" key=Scale value=1:100",
  "op:add sheet number=A135 name=\"Roof Plan\" titleblock=A1",
  "op:place view view=\"Roof Setout Plan\" sheet=A135 at=(80,100)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add roof boundary=(0,0) (9000,0) (9000,6000) (0,6000) level=Ground slope=25` | green: op:add roof made=roof-19890b3e0c849dad changed= ms=10 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) |
| `op:add view kind=plan level=Roof name="Roof Setout Plan"` | green: op:add view made=1bd6e71861d24f8bb72ea8a53f731b81 changed= ms=10 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:set id="Roof Setout Plan" key=Scale value=1:100` | green: op:set made= changed= ms=47 state=unchanged Check "—": no expectation |
| `op:add sheet number=A135 name="Roof Plan" titleblock=A1` | green: op:add sheet made=sheet-A135 changed= ms=7 Check "sheet A135 exists": sheet A135 exists (9 sheet(s) in the document) |
| `op:place view view="Roof Setout Plan" sheet=A135 at=(80,100)` | green: op:place view made=1bd6e71861d24f8bb72ea8a53f731b81::sheet-A135::8fe1e15165be4b62a12e54ba68295c00 changed= ms=234 Check "—": no expectation |

### The result

The model holds: Levels 3,Roofs 1,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 4082. Duplicate the Ground plan and put the copy on a sheet for the electrician.

- Starts from: a new Architectural project
- Ends with: Four walls on Ground, a duplicate named Ground Copy 1, and sheet A190 Electrician Plan holding the copy.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add wall from=(0,0) to=(8000,0) level=Ground",
  "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
  "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
  "op:add wall from=(0,6000) to=(0,0) level=Ground"
]}
```

| Line | UNION answered |
|---|---|
| `op:add wall from=(0,0) to=(8000,0) level=Ground` | green: op:add wall made=wall-712f5b0625c623fe changed= ms=11 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) |
| `op:add wall from=(8000,0) to=(8000,6000) level=Ground` | green: op:add wall made=wall-eefa3a0217c356fd changed=wall-712f5b0625c623fe ms=2 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) |
| `op:add wall from=(8000,6000) to=(0,6000) level=Ground` | green: op:add wall made=wall-b17b4e6f0539db4f changed=wall-eefa3a0217c356fd ms=2 Check "Walls +1": Walls 2 -> 3 (+1, expected +1) |
| `op:add wall from=(0,6000) to=(0,0) level=Ground` | green: op:add wall made=wall-e19ce6e92c3793cc changed=wall-b17b4e6f0539db4f,wall-712f5b0625c623fe ms=2 Check "Walls +1": Walls 3 -> 4 (+1, expected +1) |

```json
steps_run {"steps":[
  "ribbon:View:Duplicate View › Duplicate · picks — · keys — · fields — · expect view: Floor Plan +1"
]}
```

| Line | UNION answered |
|---|---|
| `ribbon:View:Duplicate View › Duplicate · picks — · keys — · fields — · expect view: Floor Plan +1` | green: pressed 'Duplicate View › Duplicate' on View's Create panel (through its parent 'Duplicate View''s arrow, the row 'Duplicate'; the press stood 777 ms (the menu stood at 361 ms; its row ran 416 ms; it made 0 child widgets native)): the command 'Duplicate View › Duplicate' ran; status 'Ground Copy 1 made' Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |

```json
ops_run {"lines":[
  "op:add sheet number=A190 name=\"Electrician Plan\" titleblock=A1",
  "op:place view view=\"Ground Copy 1\" sheet=A190 at=(80,100)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add sheet number=A190 name="Electrician Plan" titleblock=A1` | green: op:add sheet made=sheet-A190 changed= ms=3 Check "sheet A190 exists": sheet A190 exists (9 sheet(s) in the document) |
| `op:place view view="Ground Copy 1" sheet=A190 at=(80,100)` | green: op:place view made=31e7e2eaa22d4a6f9594b3a5b310b97d::sheet-A190::df7f775ef1d4400082a15988ec3b2756 changed= ms=1036 Check "—": no expectation |

### The result

The model holds: Levels 3,Walls 4,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 5,view: Schedule 3,view: Section 2.

## 4086. Add Levels 2 to 4 above my house plan, give each a floor and a plan at 1:200, and put the three plans on one sheet.

- Starts from: a new Architectural project
- Ends with: Levels 2, 3 and 4 at 6000, 9000 and 12000 mm with a floor each, three plans named Typical Plan Level 2, 3 and 4 at 1:200, all on sheet A150.
- Played on UNION 1.0.0-beta.2, 21 November 2026: every line green

### The calls

The person opens a new project from the **Architectural** template (File, New): on the AI door that press is the person's own.

```json
ops_run {"lines":[
  "op:add level elevation=6000 name=\"Level 2\"",
  "op:add level elevation=9000 name=\"Level 3\"",
  "op:add level elevation=12000 name=\"Level 4\"",
  "op:add floor boundary=(0,0),(12000,0),(12000,9000),(0,9000) level=\"Level 2\"",
  "op:add floor boundary=(0,0),(12000,0),(12000,9000),(0,9000) level=\"Level 3\"",
  "op:add floor boundary=(0,0),(12000,0),(12000,9000),(0,9000) level=\"Level 4\"",
  "op:add view kind=plan level=\"Level 2\" name=\"Typical Plan Level 2\"",
  "op:add view kind=plan level=\"Level 3\" name=\"Typical Plan Level 3\"",
  "op:add view kind=plan level=\"Level 4\" name=\"Typical Plan Level 4\"",
  "op:set id=\"Typical Plan Level 2\" key=Scale value=1:200",
  "op:set id=\"Typical Plan Level 3\" key=Scale value=1:200",
  "op:set id=\"Typical Plan Level 4\" key=Scale value=1:200",
  "op:add sheet number=A150 name=\"Typical Floor Plans\" titleblock=A1",
  "op:place view view=\"Typical Plan Level 2\" sheet=A150 at=(40,250)",
  "op:place view view=\"Typical Plan Level 3\" sheet=A150 at=(300,250)",
  "op:place view view=\"Typical Plan Level 4\" sheet=A150 at=(560,250)"
]}
```

| Line | UNION answered |
|---|---|
| `op:add level elevation=6000 name="Level 2"` | green: op:add level made="level-Level 2" changed= ms=17 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) |
| `op:add level elevation=9000 name="Level 3"` | green: op:add level made="level-Level 3" changed= ms=5 Check "Levels +1": Levels 4 -> 5 (+1, expected +1) |
| `op:add level elevation=12000 name="Level 4"` | green: op:add level made="level-Level 4" changed= ms=7 Check "Levels +1": Levels 5 -> 6 (+1, expected +1) |
| `op:add floor boundary=(0,0),(12000,0),(12000,9000),(0,9000) level="Level 2"` | green: op:add floor made=floor-1327a3c5242d649b changed= ms=3 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) |
| `op:add floor boundary=(0,0),(12000,0),(12000,9000),(0,9000) level="Level 3"` | green: op:add floor made=floor-8e1ccedc2817eb74 changed= ms=1 Check "Floors +1": Floors 1 -> 2 (+1, expected +1) |
| `op:add floor boundary=(0,0),(12000,0),(12000,9000),(0,9000) level="Level 4"` | green: op:add floor made=floor-b8244146babcba7c changed= ms=2 Check "Floors +1": Floors 2 -> 3 (+1, expected +1) |
| `op:add view kind=plan level="Level 2" name="Typical Plan Level 2"` | green: op:add view made=194cdee1c10743ea9013af65b6f2bc73 changed= ms=9 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) |
| `op:add view kind=plan level="Level 3" name="Typical Plan Level 3"` | green: op:add view made=e120299555fb4a8fb4a56dc2980666df changed= ms=11 Check "view: Floor Plan +1": view: Floor Plan 5 -> 6 (+1, expected +1) |
| `op:add view kind=plan level="Level 4" name="Typical Plan Level 4"` | green: op:add view made=b6318ef5257e42e99f30d59b597b89c5 changed= ms=14 Check "view: Floor Plan +1": view: Floor Plan 6 -> 7 (+1, expected +1) |
| `op:set id="Typical Plan Level 2" key=Scale value=1:200` | green: op:set made= changed="Typical Plan Level 2" ms=3 Check "—": no expectation |
| `op:set id="Typical Plan Level 3" key=Scale value=1:200` | green: op:set made= changed="Typical Plan Level 3" ms=3 Check "—": no expectation |
| `op:set id="Typical Plan Level 4" key=Scale value=1:200` | green: op:set made= changed="Typical Plan Level 4" ms=3 Check "—": no expectation |
| `op:add sheet number=A150 name="Typical Floor Plans" titleblock=A1` | green: op:add sheet made=sheet-A150 changed= ms=5 Check "sheet A150 exists": sheet A150 exists (9 sheet(s) in the document) |
| `op:place view view="Typical Plan Level 2" sheet=A150 at=(40,250)` | green: op:place view made=194cdee1c10743ea9013af65b6f2bc73::sheet-A150::c7d6d5b2b9af41aabb0ca63f0c649441 changed= ms=49 Check "—": no expectation |
| `op:place view view="Typical Plan Level 3" sheet=A150 at=(300,250)` | green: op:place view made=e120299555fb4a8fb4a56dc2980666df::sheet-A150::ae94eda1a0e043a3845152c6617f4d36 changed= ms=64 Check "—": no expectation |
| `op:place view view="Typical Plan Level 4" sheet=A150 at=(560,250)` | green: op:place view made=b6318ef5257e42e99f30d59b597b89c5::sheet-A150::c5ca860dcb554f6a894aa3d97bd53575 changed= ms=59 Check "—": no expectation |

### The result

The model holds: Floors 3,Levels 6,mark: Elevation 1,mark: Section 2,view: 3D View 1,view: Ceiling Plan 3,view: Elevation 4,view: Floor Plan 7,view: Schedule 3,view: Section 2.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
