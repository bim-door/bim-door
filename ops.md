# UNION ops: one line per element

An op is one line that makes or changes one thing, sent in `ops_run` (1 to 500 lines, one Undo entry). This is the grammar UNION 1.0.0-beta.2 states for itself; each op links to lines played green.

One op a line. UNION's own words for a line that is neither an op, a comment nor blank: `cannot proceed: a line is 'op: ...', a '# ...' comment or blank`. A line must hold every required key and keep the rule of each group in the Key groups column; a key the row does not list is refused, as is a key written twice. A key followed by a form in brackets is written in that form (listed below the table); the other keys are names or words: a level, a view, a type, a text.

| Op | Required keys | Key groups | Optional keys |
|---|---|---|---|
| `add column` | at (point), level | - | top, type |
| `add grid` | from (point), to (point) | - | name |
| `add level` | elevation (mm) | - | name |
| `add beam` | from (point), to (point), level | - | type, usage |
| `add brace` | from (point), to (point), level | - | top, start_offset (mm), end_offset (mm), type, usage |
| `add wall` | from (point), to (point), level | - | type, height (mm), top, line, through (point) |
| `add floor` | boundary (points), level | - | type |
| `add roof` | boundary (polygon), level | - | type, slope (slope), edges (edges) |
| `add ceiling` | level | exactly one of at (point), boundary (polygon); all or none of arrow (pair), rise (mm) | height (mm), type, arrow (pair), rise (mm) |
| `add material` | - | - | name, from, library |
| `add room` | at (point), level | - | name, number |
| `add shaft` | boundary (pair), level | - | top |
| `add stair` | from (point), to (heading), level, top | - | type, width (mm) |
| `add railing` | - | exactly one of points (points), host (ids); all or none of points (points), level | type, level, points (points), host (ids) |
| `add door` | wall | exactly one of at (point), offset (mm) | sill (mm), type, flip (yesno), hand (yesno) |
| `add window` | wall | exactly one of at (point), offset (mm) | sill (mm), type, flip (yesno), hand (yesno) |
| `add detail line` | points (points), view | - | style |
| `add filled region` | boundary (polygon), view | - | type, pattern |
| `add insulation` | from (point), to (point), view | - | width (mm) |
| `add view` | kind (plankind), level | - | name |
| `add section` | from (point), to (point), view | - | depth (mm), name |
| `add elevation` | at (point), facing (facing), view | - | name |
| `add drafting view` | - | - | name, scale |
| `add legend` | - | - | name, scale |
| `add schedule` | category, fields | - | name, sortby, groupby, filter, itemize (yesno) |
| `add 3d view` | - | - | name |
| `add sheet` | - | - | number, name, titleblock |
| `place view` | view, sheet | - | at (sheetpoint), title, scale, crop (pair), table_width (mm), text_size (mm) |
| `print sheets` | path | - | - |
| `set` | id (ids), key, value | - | - |
| `set material` | name, key, value | - | - |
| `set view` | view | at least one of hide, show, map | - |
| `set element graphics` | view (viewid), id (elementids) | at least one of projection_line_colour (overridecolour), cut_line_colour (overridecolour), surface_colour (overridecolour), cut_fill_colour (overridecolour), transparency (overridetransparency) | - |
| `delete` | id (ids) | - | - |
| `delete sheet` | sheet | - | - |
| `remove view` | - | exactly one of view, id (ids); all or none of view, sheet | - |
| `move` | id (ids), by (movevector) | - | - |
| `add duct` | from (point), to (point), level | - | width (mm), height (mm), diameter (mm), elevation (mm), system |
| `add pipe` | from (point), to (point), level | - | diameter (mm), elevation (mm), system |
| `add terminal` | at (point) | at least one of level, duct | system |
| `add equipment` | at (point), level | - | elevation (mm) |
| `add duct system` | members (ids) | - | system, name |
| `add fascia` | roof, edges (edges) | - | height (mm), thickness (mm) |
| `add gutter` | roof, edges (edges) | - | height (mm), thickness (mm) |
| `add text` | at (point), view, text | - | type, leader_to (point), width (mm) |
| `add dimension` | from (point), to (point), view | - | offset (mm) |
| `add dimension chain` | points (points), view, offset (mm) | - | - |
| `add tag` | id, view | - | leader (yesno) |
| `add symbol` | at (point), view | - | symbol, rotation (degrees) |
| `place block` | family, at (point) | - | type, level, rotation (degrees), host |
| `copy` | id (ids), by (vector) | - | - |
| `rotate` | id (ids), about (point), angle (degrees) | - | copy (yesno) |
| `mirror` | id (ids), axis (pair) | - | copy (yesno) |
| `array` | id (ids), count (count) | exactly one of step (vector), about (point); all or none of about (point), angle (degrees) | group (yesno) |

| Form | Written as | Example |
|---|---|---|
| point | (x,y) in mm: two numbers | `(1000,2000)` |
| heading | (x,y) in mm: the point the run heads toward; the answer's note names where it ends | `(6000,0)` |
| points | (x,y) (x,y) ... in mm: two points or more | `(0,0) (4000,0) (4000,3000)` |
| pair | (x,y) (x,y) in mm: exactly two points | `(0,0) (4000,0)` |
| polygon | (x,y) (x,y) (x,y) ... in mm: three points or more | `(0,0) (4000,0) (4000,3000)` |
| mm | a number in mm | `1000` |
| degrees | a number in degrees | `90` |
| slope | a slope in degrees, from -89 to 89: 0 is flat | `30` |
| vector | dx,dy,dz in mm: two or three numbers | `(100,0,0)` |
| movevector | dx,dy,dz in mm: two or three numbers; the id of a placed view moves it on its sheet by dx,dy in sheet mm, y down the page (dz is 0) | `(100,0,0)` |
| sheetpoint | (x,y) in sheet mm: the placed view's frame lower-left corner, measured from the sheet's lower-left corner, y up the page | `(40,30)` |
| yesno | yes or no | `yes` |
| count | a whole number of 2 or more: the instances in all, the original included | `3` |
| ids | ids separated by commas: one or more | `a1,a2` |
| viewid | an exact view id from views.list | `view-1` |
| elementids | one or more exact model element ids separated by commas, each appearing once | `a1,a2` |
| overridecolour | an RGB colour as #RRGGBB, or None to clear it | `#5080C0` |
| overridetransparency | a whole number from 0 to 100, or None to clear it | `0` |
| edges | roof edge numbers from 0 separated by commas: one or more | `0,1` |
| plankind | plan, structural or ceiling; sections, elevations, drafting views and 3D views are made by add section, add elevation, add drafting view and add 3d view | `plan` |
| facing | north, east, south or west | `north` |

A value that holds a space is written in double quotes: `level="Level 1"`. Separate the points of a list with a space or a comma; a space inside a point's brackets is allowed.

id= of copy, move, rotate, mirror, array and delete takes an element's id or an annotation's id (a row elements.query lists under an annotation category); one line may hold both. An annotation reads by=, step=, about= and axis= as given, in the drawing mm of its own view (a plan's are model x and y), never converted for the view in front; the z of by= or step= is ignored, so a copy or an array by z alone lands on its source. add duct system and add railing take elements only.

The answer to each op is one line, shaped by `opAnswerLine` (the id in the first is a placeholder):

```
goose-script	step	ops	1	ok	op:add column	made=<id> changed= ms=0
goose-script	step	ops	2	red	op:add column	cannot proceed: add column wants at=
```

A green line ends in `note=<words>` when UNION said something while the op wrote: the op stands. A note can say a value did not follow the write ("cannot proceed: ..."); the line is still green. A green line that wrote no row has `state=unchanged` before any note, and made and changed empty: the model already stood as it asks. An id in made or changed that holds a space, a comma or a double quote is written in double quotes, a double quote inside it doubled.

Untyped adds. An op below that gives no `type` draws on the first type in its Draws on cell that applies, else its built-in; a `type` that names the built-in, by its name or its id, draws the same while the row's types.list cell says it is `implied`. A cell that says current means the category's current type: the Type Selector's pick, or the type of the last op of that kind that named one and was written. Row written is yes where the line writes the built-in as a type row of its category in the same write as the element, unless the document already holds a type row of that name, and no where the element only names the built-in.

| Op | Draws on, in order | Built-in | Row written | types.list |
|---|---|---|---|---|
| `add ceiling` | the built-in, whichever `Ceilings` types the document holds and whatever the Type Selector has picked | `Compound Ceiling 600 x 1200` | yes | `implied` until a `Ceilings` type row of that name stands |
| `add column` | current; the document's first `Structural Columns` type if it states a section | `150UC30.0` | yes | `implied` while the document holds no `Structural Columns` type row |
| `add beam` | current; the document's first `Structural Framing` type of a beam family if its section can be drawn | `150UC30.0` | yes | `implied` while the document holds no `Structural Framing` type row |
| `add brace` | the current `Structural Bracing` type (the Type Selector's pick); the current `Structural Framing` type | `150UC30.0` | yes, the row `add beam` writes | as `add beam` |
| `add roof` | current; the document's first `Roofs` type if its Thickness, or its Structure's layers where it states no Thickness, gives a thickness above zero | `Generic 125mm` | no | `implied` while the document holds no `Roofs` type row |
| `add floor` | current; the document's first `Floors` type if its Thickness, or its Structure's layers where it states no Thickness, gives a thickness above zero | `Generic 200mm` | no | `implied` while the document holds no `Floors` type row |
| `add wall` | current; the document's first `Walls` type | `Generic 300mm` | no | `implied` while the document holds no `Walls` type row |
| `add stair` | current | `Stair` | no | `implied` while the document holds no `Stairs` type row |
| `add railing` | current | `Railing` | yes | `implied` while the document holds no `Railings` type row |
| `add door` | current; the first built-in `Doors` kind, `Single Swing`, its type named by its size | `900 x 2100` | yes; where the document holds no `Doors` type row, every built-in `Doors` kind, else only the row of that kind and size, if it is missing | not listed before the add |
| `add window` | current; the first built-in `Windows` kind, `Fixed`, its type named by its size | `1200 x 1200` | yes; where the document holds no `Windows` type row, every built-in `Windows` kind, else only the row of that kind and size, if it is missing | not listed before the add |

`add filled region`, `add text` and `place block` take `type` too; their rule with no type is not stated here.

`add duct` and `add pipe` take no `type`, and no op adds a conduit or a cable tray; a duct writes no type row: its type is `implied` in types.list once a duct stands (`Rectangular`, `Round` or `Oval`, its shape). A first pipe (the `Pipe` tool, or `add pipe`), a first conduit and a first cable tray each write one type row in the same write as the first run, unless a row of that category, family and name stands: `Pipe`, family `Standard`, name `Standard`, in `Pipes`; `Conduit`, family `Conduit with Fittings`, name `Electrical Metallic Tubing (EMT)`, in `Conduits`; `Cable Tray`, family `Cable Tray with Fittings`, name `Ladder Cable Tray`, in `Cable Trays`. None of the three takes its type from the Type Selector.

System rows. A duct or pipe a line draws is listed in the `member_ids` of a row of category `Duct Systems` or `Piping Systems`, which the line writes in the same write as the run. `made` of `add duct` lists first the ducts and fittings the line wrote, and `made` of `add pipe` the pipe and fittings; then, as for every line, a new system row and the new half of a standing duct or pipe the run splits are in `made`, and a system row the line joined or deleted, and the standing duct or pipe it split, in `changed`. The system rows count in the line's `rows`, which the ops.run row of Methods describes, and elements.query with the row's category reads them. The `member_ids` are kept in the row's stored geometry, and element.get, elements.get and elements.query do not answer them by default: a system row answers its columns and its parameters System Classification, System Type name and System Name; only an elements.get that asks for `geometry` returns the stored geometry whole, the `member_ids` in it. A system row UNION writes has a System Type name of its System Classification and the word System (`Supply Air System` for the classification `Supply Air`), and its family and type read the System Classification (`Supply Air`). One `ops.run` call is one Undo: it takes back the run, the fittings and the system rows of every line in the call.

Electrical Circuits are separate: element.get and elements.get expose their own stored `member_ids` without changing its order or contents, under the presence and raw-value rules of element.get. A circuit made through Select Panel or Circuit from Devices may list its own Wires row last; identify that member by its category. This does not add a member list to duct or piping system reads or to elements.query.

`add duct` writes one `Duct Systems` row for the ducts it makes and deletes each `Duct Systems` row that lists a duct or fitting those ducts meet. A duct meets a standing duct or duct fitting when an end of one lies closer than 1 mm, measured in three dimensions, to an end or connector of the other and both hold the same System Classification (the read-only parameter that `system=` sets), whatever their levels, and so on through every duct and fitting joined to it; an end closer than 1 mm to the axis of a standing duct of the same System Classification and more than 1 mm along it from both its ends splits that duct in two and meets both halves. A duct whose run no `Duct Systems` row lists (a duct that meets nothing is one) gets a new row named `<System Classification> System <n>`, n the first number for which no `Duct Systems` or `Piping Systems` row is named `<System Classification> System <n>`. A duct whose run a row lists gets one new row, with a new id, in place of the deleted row or rows: it lists every duct and fitting joined to the new duct, each `Air Terminals` or `Mechanical Equipment` row with a connector within 1 mm of a connector of those ducts or fittings, whatever its classification, or hosted on one of them, and nothing else. It takes the System Name of the first deleted row, in file order, that stores a name not of the form `<words> System <n>`, else the first name any deleted row stores. A duct system row has the parameters System Classification, System Type name and System Name, and geometry kind `DuctSystem`. A duct's own System Name parameter is empty until `add duct system` or another system write names it.

`add pipe` writes or joins one `Piping Systems` row for the whole run. It meets the standing pipes of its own level: a pipe with an end within 1 mm of an end of the run; and, for an end of the run that no pipe end lies within 1 mm of, the first pipe in file order whose axis passes within 1 mm of that end and more than 1 mm along it from both its ends, which splits in two. The run joins the row of the first, in file order, of those pipes that hold its System Classification and that a `Piping Systems` row lists: the row keeps its id and name, its `member_ids` take the run's pipes and its fittings, the new half of a split standing pipe is listed in the row that lists that pipe, and each pipe of the run takes the row's name as its System Name. A run that meets pipes of two systems joins the first and merges nothing. A run that meets no pipe that holds its System Classification and that a row lists writes a new row named `<System Classification> System <n>`, n as above, listing the run's pipes and none of its fittings; each pipe of that run is written with its own System Name parameter empty, and the row stores the name.

A press of the `Valve` tool on a pipe, with no type picked in the Type Selector, splits the pipe in one write: the clicked pipe keeps its id and ends at the point of its axis nearest the click, no nearer an end than a hundredth of its length in plan; a `Pipe Accessories` row stands at that point and a new `Pipes` row runs from it to the pipe's old end, with the ids `<pipe id>-acc` and `<pipe id>-b` while no row holds them, else a new id; each `Piping Systems` row that lists the pipe lists the pipe, the accessory and the new pipe, in that order. A pipe with no length in plan is refused with `cannot proceed: pipe has zero length`. The press is one write: one Undo takes it back and one Redo puts it back (a `steps.run` call is one Undo whole).

The `Area` tool (Area Reinforcement) takes its first click as the host pick and as the loop's first corner; the loop is closed when its last point lands on that corner again (a rectangle is five points, the last repeating the first; the row's `points` keeps the four corners), and Finish on an open loop is refused as not closed; a click writes nothing; its Finish, on the page `Create Reinforcement Boundary`, writes one `Structural Area Reinforcement` row (kind `AreaReinforcement`) and one `depends` row, in one Undo. In a plan the host is the floor, foundation slab or part under the first click (a wall, column or beam there yields to one under the loop's middle; with none, a wall keeps the Area and a column or beam is refused). A `Wall Sweep` click on a wall, with Apply To `This Wall`, and a `Slab Edge` click on a floor's edge write at the click one `Wall Sweeps` row (kind `WallSweep`) or one `Slab Edges` row (kind `SlabEdge`) and one `depends` row, in one Undo, and the tool stays armed for the next click until `finish` ends it; `Whole Type` writes no `Wall Sweeps` row; it adds a sweep to the wall's type; a `Slab Edge` click on an edge that already holds an identical one writes nothing.

`add duct system` writes one new `Duct Systems` row over the members and writes the row's name into the System Name of each member that is not a Mechanical Equipment; with no `name=` it names the row `<System Classification> System <n>` as above; its `made` is the row's id, and a name another `Duct Systems` row holds is refused; the members leave the other `Duct Systems` rows they stood in (a Mechanical Equipment stays in each), and a row left with no member is deleted.

Delete and `delete id=` take a deleted member out of `member_ids` in the same write and delete the row in that write when no member is left; with a design option active a main-model row is only trimmed.

## op: add column

One line in `ops_run`: `op:add column key=value ...`

- Required keys: at (point), level
- Key groups: -
- Optional keys: top, type

Played lines:

```json
ops_run {"lines":["op:add column at=(0,0) level=\"Level 1\" top=Roof type=310UC158"]}
```

Answer: green, op:add column made=column-11a38e63252f663a changed= ms=4 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) (from [job 1001: Set up the levels for a four-storey steel office, 3.6 m floor to floor, with the roof at 14.4 m.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add column at=(0,0) level=\"Ground Floor\" top=\"First Floor\" type=250UC89.5"]}
```

Answer: green, op:add column made=column-86859f543372f17d changed= ms=9 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) (from [job 1002: Rename the two template levels Ground Floor and First Floor and put the first floor at 4200 mm.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add column at=(0,0) level=\"Basement\" top=\"Level 1\" type=\"400 x 400\""]}
```

Answer: green, op:add column made=column-71bc714924fecae2 changed= ms=8 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) (from [job 1003: Add a basement level 3 m below ground for a car park and stand four concrete columns in it.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add column at=(0,0) level=\"Level 1\" top=\"Level 2\" type=310UC137"]}
```

Answer: green, op:add column made=column-50dbd1f83d337b18 changed= ms=18 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) (from [job 1004: Make the ground floor double height by raising Level 2 to 6000 mm; the columns must follow.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add column at=(0,0) level=\"Level 1\" top=\"Mezzanine\" type=250UC72.9"]}
```

Answer: green, op:add column made=column-39ac1d39894f6865 changed= ms=8 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) (from [job 1007: Put a mezzanine platform at 2.7 m inside a 7 m high warehouse: a 9 x 6 m deck on four columns with edge beams.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add column at=(0,0) level=\"L00 Ground\" top=\"L02 Second\" type=200UC59.5"]}
```

Answer: green, op:add column made=column-1044b0816c2e72ec changed= ms=5 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) (from [job 1008: Name the levels L00 Ground, L01 First and L02 Second to match the client's drawing numbers, then run a column up through all three.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add column at=(0,0) level=Ground top=Roof type=250UC89.5"]}
```

Answer: green, op:add column made=column-eabbe46ac5bb55d1 changed= ms=7 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) (from [job 1009: The site is at RL 12.5: move Ground, Level 1 and the Roof up to 12500, 15900 and 19300 and run a steel column through them.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add column at=(0,0) level=Ground top=\"Level 2\" type=200UC59.5"]}
```

Answer: green, op:add column made=column-ac6d20cb65167b61 changed= ms=9 Check "Structural Columns +1": Structural Columns 0 -> 1 (+1, expected +1) (from [job 1010: Add a second floor to the house frame at 6800 mm and lift the roof to 10200 mm.](examples/setting-out-and-structure.md))


## op: add grid

One line in `ops_run`: `op:add grid key=value ...`

- Required keys: from (point), to (point)
- Key groups: -
- Optional keys: name

Played lines:

```json
ops_run {"lines":["op:add grid from=(0,-2000) to=(0,18000) name=A"]}
```

Answer: green, op:add grid made=grid-A changed= ms=73 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) (from [job 1011: Set out a square column grid, three bays each way at 8 m, lettered across and numbered up, with a column at every crossing.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add grid from=(0,-2000) to=(0,8000) name=A"]}
```

Answer: green, op:add grid made=grid-A changed= ms=566 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) (from [job 1012: The building sits skew to the boundary: set out a 7.5 x 6 m grid and swing the whole grid 30 degrees, then put columns on the crossings.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add grid from=(0,0) to=(28191,-10261) name=A"]}
```

Answer: green, op:add grid made=grid-A changed= ms=589 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) (from [job 1013: Set out a fan-shaped grid for an auditorium: five lines splayed 10 degrees apart from the stage point, cut by one cross line, with a column at each crossing.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add grid from=(0,-2000) to=(0,14000) name=A"]}
```

Answer: green, op:add grid made=grid-A changed= ms=75 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) (from [job 1014: Set out the plant room grid with uneven bays of 6.0, 7.5, 9.0, 7.5 and 6.0 m and two rows 12 m apart, with a column at every crossing.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add grid from=(0,-2000) to=(0,10000) name=A"]}
```

Answer: green, op:add grid made=grid-A changed= ms=73 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) (from [job 1015: The client calls the gridlines X, Y and Z instead of A, B and C: rename them and shift all three 250 mm east.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add grid from=(0,-2000) to=(0,10000) name=A"]}
```

Answer: green, op:add grid made=grid-A changed= ms=522 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) (from [job 1016: Shift gridline B 500 mm east to clear the stair core, then undo it and do it again.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add grid from=(0,-2000) to=(0,12000) name=A"]}
```

Answer: green, op:add grid made=grid-A changed= ms=78 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) (from [job 1017: Extend the grid east by copying gridline A six metres and then twelve metres.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add grid from=(0,-2000) to=(0,12000) name=A"]}
```

Answer: green, op:add grid made=grid-A changed= ms=561 Check "Grids +1": Grids 0 -> 1 (+1, expected +1) (from [job 1018: The building is symmetrical about a centre line at 12 m: draw the west half of the grid, mirror it east and add the centre line.](examples/setting-out-and-structure.md))


## op: add level

One line in `ops_run`: `op:add level key=value ...`

- Required keys: elevation (mm)
- Key groups: -
- Optional keys: name

Played lines:

```json
ops_run {"lines":["op:add level elevation=7200 name=\"Level 3\""]}
```

Answer: green, op:add level made="level-Level 3" changed= ms=52 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1001: Set up the levels for a four-storey steel office, 3.6 m floor to floor, with the roof at 14.4 m.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add level elevation=-3000 name=\"Basement\""]}
```

Answer: green, op:add level made=level-Basement changed= ms=74 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1003: Add a basement level 3 m below ground for a car park and stand four concrete columns in it.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add level elevation=4500 name=\"Plant\""]}
```

Answer: green, op:add level made=level-Plant changed= ms=71 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1006: Add a plant level, delete it, then bring it back with Undo and take it away again with Redo.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add level elevation=2700 name=\"Mezzanine\""]}
```

Answer: green, op:add level made=level-Mezzanine changed= ms=6 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1007: Put a mezzanine platform at 2.7 m inside a 7 m high warehouse: a 9 x 6 m deck on four columns with edge beams.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add level elevation=7200 name=\"L02 Second\""]}
```

Answer: green, op:add level made="level-L02 Second" changed= ms=32 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1008: Name the levels L00 Ground, L01 First and L02 Second to match the client's drawing numbers, then run a column up through all three.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add level elevation=6800 name=\"Level 2\""]}
```

Answer: green, op:add level made="level-Level 2" changed= ms=5 Check "Levels +1": Levels 3 -> 4 (+1, expected +1) (from [job 1010: Add a second floor to the house frame at 6800 mm and lift the roof to 10200 mm.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add level elevation=6600 name=\"Level 3\""]}
```

Answer: green, op:add level made="level-Level 3" changed= ms=37 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1026: Run four 300 dia columns up through two storeys of 3.3 m, from Level 1 to a new Level 3.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add level elevation=7200 name=\"Level 3\""]}
```

Answer: green, op:add level made="level-Level 3" changed= ms=52 Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1030: Frame a four-storey steel building 9 x 6 m: four columns full height and a ring of beams at each floor.](examples/setting-out-and-structure.md))


## op: add beam

One line in `ops_run`: `op:add beam key=value ...`

- Required keys: from (point), to (point), level
- Key groups: -
- Optional keys: type, usage

Played lines:

```json
ops_run {"lines":["op:add beam from=(0,0) to=(6000,0) level=\"First Floor\" type=360UB50.7"]}
```

Answer: green, op:add beam made=beam-f6ade2a5add715a8 changed= ms=10 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1002: Rename the two template levels Ground Floor and First Floor and put the first floor at 4200 mm.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add beam from=(0,0) to=(7500,0) level=\"Level 2\" type=530UB82.0"]}
```

Answer: green, op:add beam made=beam-f3ae7bd0682f92fe changed= ms=5 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1004: Make the ground floor double height by raising Level 2 to 6000 mm; the columns must follow.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add beam from=(0,0) to=(9000,0) level=\"Mezzanine\" type=310UB32.0"]}
```

Answer: green, op:add beam made=beam-38cd4f4764611a94 changed= ms=6 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1007: Put a mezzanine platform at 2.7 m inside a 7 m high warehouse: a 9 x 6 m deck on four columns with edge beams.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add beam from=(0,0) to=(0,8000) level=\"Level 1\" type=250UB31.4"]}
```

Answer: green, op:add beam made=beam-bcb4a13acb3db0ba changed= ms=11 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1029: Draw one 8 m secondary beam on the first floor and array it five times at 3 m centres.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add beam from=(0,0) to=(8400,0) level=\"Level 2\" type=530UB82.0"]}
```

Answer: green, op:add beam made=beam-917020b7a3d6e350 changed= ms=9 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1031: Span a 530UB82.0 beam 8.4 m between two columns at the first floor, 4.2 m up.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add beam from=(0,0) to=(0,9000) level=\"Level 2\" type=610UB125"]}
```

Answer: green, op:add beam made=beam-af808b05cdd92520 changed= ms=5 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1033: Lay out a floor bay 12 x 9 m: two 610UB125 girders 12 m apart and three 360UB50.7 joists at 3 m centres between them.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add beam from=(0,0) to=(6000,0) level=\"Level 2\" type=310UB40.4"]}
```

Answer: green, op:add beam made=beam-e2cabbba9940ed63 changed= ms=8 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1035: Put chevron bracing in a 6 m bay: two braces meeting at the middle of the first-floor beam.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add beam from=(0,0) to=(0,30000) level=\"Level 2\" type=250UB37.3"]}
```

Answer: green, op:add beam made=beam-a36036ed77237122 changed= ms=9 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1037: Set out a portal-frame shed: five frames 7.5 m apart, 24 m span, columns at every frame and an eaves beam down each side.](examples/setting-out-and-structure.md))


## op: add brace

One line in `ops_run`: `op:add brace key=value ...`

- Required keys: from (point), to (point), level
- Key groups: -
- Optional keys: top, start_offset (mm), end_offset (mm), type, usage

Played lines:

```json
ops_run {"lines":["op:add brace from=(0,0) to=(6000,0) level=\"Level 1\" top=\"Level 2\" type=168.3x6.4CHS"]}
```

Answer: green, op:add brace made=brace-d28a360cc4e4ad78 changed= ms=8 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1034: Brace one 6 m bay with a cross of two 168.3 x 6.4 tubes between the columns, ground to first floor.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add brace from=(0,0) to=(3000,0) level=\"Level 1\" top=\"Level 2\" type=139.7x3.5CHS"]}
```

Answer: green, op:add brace made=brace-55534a1ca12cd551 changed= ms=6 Check "Structural Framing +1": Structural Framing 1 -> 2 (+1, expected +1) (from [job 1035: Put chevron bracing in a 6 m bay: two braces meeting at the middle of the first-floor beam.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add brace from=(0,0) to=(15000,0) level=\"Level 1\" top=\"Level 1\" start_offset=6000 end_offset=7500 type=530UB82.0"]}
```

Answer: green, op:add brace made=brace-d2d8aa8164b977cc changed= ms=7 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1036: Set out one portal frame: 30 m span, 6 m to the eaves, ridge at 7.5 m, 310UC96.8 columns and 530UB82.0 rafters.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add brace from=(0,0) to=(6000,0) level=\"Level 1\" top=\"Level 2\" type=114.3x3.6CHS"]}
```

Answer: green, op:add brace made=brace-f8bd4ae1e1a53810 changed= ms=9 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1038: Brace a lift core over three storeys in a zigzag, 3.6 m storeys and a 6 m bay.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add brace from=(0,0) to=(6000,6000) level=\"Level 2\" top=\"Level 2\" type=48.3x2.9CHS"]}
```

Answer: green, op:add brace made=brace-46d07673731b09ba changed= ms=7 Check "Structural Framing +1": Structural Framing 4 -> 5 (+1, expected +1) (from [job 1041: Stiffen the roof plane of a 6 x 6 m bay with two crossing diagonal braces at eaves level.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add brace from=(0,0) to=(3000,0) level=Ground top=\"Level 1\" type=100UC14.8"]}
```

Answer: green, op:add brace made=brace-2cd7df14c06f6924 changed= ms=7 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1055: Brace a 3 m wide lift shaft with two 150UC37.2 columns and a cross of 100UC14.8 braces from Ground to Level 1.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add brace from=(3000,0) to=(0,0) level=\"Level 1\" top=\"Level 1\" start_offset=0 end_offset=3000 type=139.7x3.5CHS"]}
```

Answer: green, op:add brace made=brace-8af5693ef602f16c changed= ms=7 Check "Structural Framing +1": Structural Framing 0 -> 1 (+1, expected +1) (from [job 1060: Prop a wall column with a 3 m raking brace rising 3 m from the slab.](examples/setting-out-and-structure.md))


## op: add wall

One line in `ops_run`: `op:add wall key=value ...`

- Required keys: from (point), to (point), level
- Key groups: -
- Optional keys: type, height (mm), top, line, through (point)

Played lines:

```json
ops_run {"lines":["op:add wall from=(0,0) to=(6000,0) level=Ground type=\"Block 190 Core-filled\" height=1800"]}
```

Answer: green, op:add wall made=wall-5171bd3098e1f341 changed= ms=21 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) (from [job 2001: Draw a 6 m blockwork boundary wall, 1800 high, with a 3 m return at each end.](examples/architecture.md))

```json
ops_run {"lines":["op:add wall from=(0,0) to=(6000,0) level=Ground"]}
```

Answer: green, op:add wall made=wall-2313ed525eab9400 changed= ms=441 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) (from [job 2002: Set out a 6 x 4 m site office on Ground: four walls and a slab.](examples/architecture.md))

```json
ops_run {"lines":["op:add wall from=(0,0) to=(10000,0) level=Ground type=\"Brick Veneer 251\""]}
```

Answer: green, op:add wall made=wall-d502ceac74bbe749 changed= ms=22 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) (from [job 2005: Draw a 10 x 6 m house outline in brick veneer with a 110 stud partition down the middle.](examples/architecture.md))

```json
ops_run {"lines":["op:add wall from=(0,0) to=(4000,0) level=Ground height=2400"]}
```

Answer: green, op:add wall made=wall-788a086f61b791fc changed= ms=538 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) (from [job 2006: Draw three walls on Ground: a 2400 screen wall, a wall that runs up to Level 1, and a 3600 high wall.](examples/architecture.md))

```json
ops_run {"lines":["op:add wall from=(0,0) to=(0,-3000) level=Ground"]}
```

Answer: green, op:add wall made=wall-fa4918f4c7a8e2a4 changed=wall-a5e08124666912f4 ms=3 Check "Walls +1": Walls 1 -> 2 (+1, expected +1) (from [job 2007: Draw a curved feature wall, 6 m chord with a 2 m rise, and a straight return wall at each end.](examples/architecture.md))

```json
ops_run {"lines":["op:add wall from=(0,0) to=(8000,0) through=(4000,-2500) level=Ground type=\"Block 190 Core-filled\" height=1200"]}
```

Answer: green, op:add wall made=wall-b0924aa461235d38 changed= ms=532 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) (from [job 2008: Add a curved blockwork garden wall, 8 m between its ends, passing through a point 2.5 m out.](examples/architecture.md))

```json
ops_run {"lines":["op:add wall from=(0,0) to=(15000,0) level=Ground height=5400 type=\"Precast 150 + Lining\""]}
```

Answer: green, op:add wall made=wall-3209d0d0c16acbcc changed= ms=9 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) (from [job 2011: Pour a 15 x 10 m warehouse slab and stand precast walls round it.](examples/architecture.md))

```json
ops_run {"lines":["op:add wall from=(0,0) to=(7000,0) level=Ground"]}
```

Answer: green, op:add wall made=wall-53ed5520ba5a2473 changed= ms=13 Check "Walls +1": Walls 0 -> 1 (+1, expected +1) (from [job 2012: Sketch a floor slab over the walls of a 7 x 5 m classroom.](examples/architecture.md))


## op: add floor

One line in `ops_run`: `op:add floor key=value ...`

- Required keys: boundary (points), level
- Key groups: -
- Optional keys: type

Played lines:

```json
ops_run {"lines":["op:add floor boundary=(0,0) (6000,0) (6000,4000) (0,4000) level=Ground type=\"Concrete Slab 200 + Tile\""]}
```

Answer: green, op:add floor made=floor-b0cc1e2fe4688b48 changed= ms=9 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) (from [job 2002: Set out a 6 x 4 m site office on Ground: four walls and a slab.](examples/architecture.md))

```json
ops_run {"lines":["op:add floor boundary=(8000,4000) (7000,5732) (5000,5732) (4000,4000) (5000,2268) (7000,2268) level=Ground"]}
```

Answer: green, op:add floor made=floor-43f8e9f1e93f47e4 changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) (from [job 2009: Draw a hexagonal garden pavilion 4 m across the corners, with a slab and a pitched roof.](examples/architecture.md))

```json
ops_run {"lines":["op:add floor boundary=(0,0) (12000,0) (12000,4000) (6000,4000) (6000,8000) (0,8000) level=Ground"]}
```

Answer: green, op:add floor made=floor-5048783422c2fc4e changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) (from [job 2010: Draw the walls of an L-shaped house, 12 x 8 m overall with a 6 x 4 m corner cut out, and slab it.](examples/architecture.md))

```json
ops_run {"lines":["op:add floor boundary=(0,0) (15000,0) (15000,10000) (0,10000) level=Ground type=\"Waffle Pod Slab 225\""]}
```

Answer: green, op:add floor made=floor-e54838eacf6a9514 changed= ms=499 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) (from [job 2011: Pour a 15 x 10 m warehouse slab and stand precast walls round it.](examples/architecture.md))

```json
ops_run {"lines":["op:add floor boundary=(0,0) (5000,0) (5000,3000) (0,3000) level=Ground type=\"Slab Carpet 200\""]}
```

Answer: green, op:add floor made=floor-9010f46aa603bb08 changed= ms=7 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) (from [job 2013: Lay a tiled wet-area slab in the 3 x 3 m bathroom and a carpet slab in the 5 x 3 m bedroom next to it.](examples/architecture.md))

```json
ops_run {"lines":["op:add floor boundary=(0,0) (8000,0) (8000,6000) (0,6000) level=Ground type=\"Concrete Slab 200 + Tile\""]}
```

Answer: green, op:add floor made=floor-9550df1b66dd766d changed= ms=43 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) (from [job 2014: Build the ground floor of an 8 x 6 m house with its slab, then add a timber first floor and the walls of the upper level.](examples/architecture.md))

```json
ops_run {"lines":["op:add floor boundary=(-2000,-2000) (4500,-2000) (4500,4500) (-2000,4500) level=\"Level 1\""]}
```

Answer: green, op:add floor made=floor-8a547d7e2385bf4e changed= ms=2 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) (from [job 2030: Cut a 2.5 m square lift shaft from Ground up to Level 1 inside concrete walls.](examples/architecture.md))

```json
ops_run {"lines":["op:add floor boundary=(0,0) (6000,0) (6000,4000) (0,4000) level=\"Level 1\""]}
```

Answer: green, op:add floor made=floor-dbf30e3c5d9de93c changed= ms=11 Check "Floors +1": Floors 0 -> 1 (+1, expected +1) (from [job 2031: Sketch a 1.2 x 0.8 m service riser opening through the first floor slab.](examples/architecture.md))


## op: add roof

One line in `ops_run`: `op:add roof key=value ...`

- Required keys: boundary (polygon), level
- Key groups: -
- Optional keys: type, slope (slope), edges (edges)

Played lines:

```json
ops_run {"lines":["op:add roof boundary=(8000,4000) (7000,5732) (5000,5732) (4000,4000) (5000,2268) (7000,2268) level=\"Level 1\" slope=20"]}
```

Answer: green, op:add roof made=roof-1bcb13777f1255e3 changed= ms=3 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) (from [job 2009: Draw a hexagonal garden pavilion 4 m across the corners, with a slab and a pitched roof.](examples/architecture.md))

```json
ops_run {"lines":["op:add roof boundary=(0,0) (10000,0) (10000,6000) (0,6000) level=\"Level 1\" slope=0 type=\"Metal Deck Insulated 100\""]}
```

Answer: green, op:add roof made=roof-5d3199363cea12e2 changed= ms=6 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) (from [job 2018: Put an insulated metal deck flat roof over a 10 x 6 m store.](examples/architecture.md))

```json
ops_run {"lines":["op:add roof boundary=(-400,-400) (12400,-400) (12400,8400) (-400,8400) level=\"Level 1\" slope=25 type=\"Concrete Tile Battens 140\""]}
```

Answer: green, op:add roof made=roof-e59080fcc9112355 changed= ms=6 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) (from [job 2019: Roof the brick house with a 25 degree hip roof in concrete tiles on battens.](examples/architecture.md))

```json
ops_run {"lines":["op:add roof boundary=(-300,-300) (8300,-300) (8300,5300) (-300,5300) level=Eaves slope=0 type=\"Green Extensive 150\""]}
```

Answer: green, op:add roof made=roof-a4f652d18169383b changed= ms=5 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) (from [job 2023: Roof the 8 x 5 m community room flat with an extensive green roof, 300 overhang, and run a fascia round all four edges.](examples/architecture.md))

```json
ops_run {"lines":["op:add roof boundary=(-400,-400) (10400,-400) (10400,6400) (-400,6400) level=Eaves slope=30"]}
```

Answer: green, op:add roof made=roof-9272a5327eecf8a8 changed= ms=2207 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) (from [job 2024: Roof the 10 x 6 m house with a 30 degree hip roof and put a fascia and a gutter on its south eave.](examples/architecture.md))

```json
ops_run {"lines":["op:add roof boundary=(-450,-450) (12450,-450) (12450,9450) (-450,9450) level=\"Level 1\" slope=22 type=\"Terracotta Tile Battens 140\""]}
```

Answer: green, op:add roof made=roof-a72b3a9db98d402f changed= ms=7 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) (from [job 2041: Draw a small three-bedroom house, 12 x 9 m in brick veneer, with a slab, internal walls, a front door, windows, a hip roof and its rooms named.](examples/architecture.md))

```json
ops_run {"lines":["op:add roof boundary=(0,0) (9000,0) (9000,3000) (0,3000) level=\"Level 1\" slope=0 type=\"Metal Deck Insulated 75\""]}
```

Answer: green, op:add roof made=roof-2d629b3848296d4b changed= ms=7 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) (from [job 2043: Lay out a 9 x 3 m transportable site office with a slab, a door, two windows, a flat roof and its room.](examples/architecture.md))

```json
ops_run {"lines":["op:add roof boundary=(-400,-400) (10400,-400) (10400,7400) (-400,7400) level=Roof slope=20 type=\"Concrete Tile Battens 140\""]}
```

Answer: green, op:add roof made=roof-eb82a560dd9d7959 changed= ms=5 Check "Roofs +1": Roofs 0 -> 1 (+1, expected +1) (from [job 2045: Draw a two-storey walk-up block, 10 x 7 m: ground and first floor walls, a slab and a timber first floor, a stair between the levels and a hip roof.](examples/architecture.md))


## op: add ceiling

One line in `ops_run`: `op:add ceiling key=value ...`

- Required keys: level
- Key groups: exactly one of at (point), boundary (polygon); all or none of arrow (pair), rise (mm)
- Optional keys: height (mm), type, arrow (pair), rise (mm)

Played lines:

```json
ops_run {"lines":["op:add ceiling at=(3000,2000) level=Ground height=2700"]}
```

Answer: green, op:add ceiling made=ceiling-bd3843f96b73fbb6 changed= ms=6 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) (from [job 2015: Put a 2700 high ceiling in the 6 x 4 m office by clicking inside its walls.](examples/architecture.md))

```json
ops_run {"lines":["op:add ceiling boundary=(0,0) (12000,0) (12000,1800) (0,1800) level=Ground height=2400 type=\"Plasterboard on Grid\""]}
```

Answer: green, op:add ceiling made=ceiling-8bc6675b8bcdc965 changed= ms=6 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) (from [job 2016: Draw a plasterboard-on-grid ceiling over a 12 m long, 1800 wide corridor at 2400.](examples/architecture.md))

```json
ops_run {"lines":["op:add ceiling boundary=(0,0) (8000,0) (8000,9000) (0,9000) level=Ground height=2700 type=\"Suspended Tile 600 x 600\""]}
```

Answer: green, op:add ceiling made=ceiling-b884cba544ba4a3d changed= ms=10 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) (from [job 2042: Fit out an 8 x 12 m shop unit: glazed shopfront, a stock room at the back with a door, a counter and a ceiling.](examples/architecture.md))

```json
ops_run {"lines":["op:add ceiling boundary=(0,0) (8000,0) (8000,4000) (0,4000) level=Ground height=2700 type=\"Plain Ceiling 13 mm\""]}
```

Answer: green, op:add ceiling made=ceiling-78e42c1171097ac5 changed= ms=3 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) (from [job 2044: Draw an 8 x 4 m ablution block with three toilet cubicles each with its own door, a tiled floor and a ceiling.](examples/architecture.md))

```json
ops_run {"lines":["op:add ceiling at=(4000,2900) level=Ground height=2700 type=\"Suspended Tile 600 x 600\""]}
```

Answer: green, op:add ceiling made=ceiling-bc03895f965320c9 changed= ms=4 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) (from [job 2048: Lay out a 16 x 8 m classroom block: two classrooms on the south side, a 2.2 m corridor on the north, a door from each classroom and a big window to each.](examples/architecture.md))

```json
ops_run {"lines":["op:add ceiling at=(6000,1750) level=Ground height=2700 type=\"Plasterboard on Grid\""]}
```

Answer: green, op:add ceiling made=ceiling-d29cfb91aa1e3a71 changed= ms=4 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) (from [job 2050: Fit out a 12 x 8 m medical suite: a reception and waiting area at the front, two consulting rooms behind it with a door each, and a ceiling over reception.](examples/architecture.md))

```json
ops_run {"lines":["op:add ceiling at=(3000,2000) level=Ground height=2700 type=\"Compound Ceiling 600 x 600\""]}
```

Answer: green, op:add ceiling made=ceiling-8fad0098f8af227f changed= ms=9 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) (from [job 2061: Ceiling the 6 x 4 m office at 2700 and make a reflected ceiling plan of it named Office RCP.](examples/architecture.md))

```json
ops_run {"lines":["op:add ceiling at=(3000,3000) level=Ground height=5700 type=\"Plain Ceiling 13 mm\""]}
```

Answer: green, op:add ceiling made=ceiling-49d7e15430c24ade changed= ms=6 Check "Ceilings +1": Ceilings 0 -> 1 (+1, expected +1) (from [job 2067: Draw a 6 x 6 m atrium with walls to the Roof level, a slab, a ceiling at 5700 and a flat roof.](examples/architecture.md))


## op: add material

One line in `ops_run`: `op:add material key=value ...`

- Required keys: -
- Key groups: -
- Optional keys: name, from, library

Played lines:

```json
ops_run {"lines":["op:add material library=brick_red name=\"Facade Brick\""]}
```

Answer: green, op:add material made="Facade Brick" changed= ms=748 Check "every count unchanged": the counts: no count changed (from [job 5026: Add our three facade materials to the project: red brick, white render and zinc cladding, each set to its texture.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add material name=\"Shopfront Glass\""]}
```

Answer: green, op:add material made="Shopfront Glass" changed= ms=71 Check "every count unchanged": the counts: no count changed (from [job 5027: Make a blue-grey glazing material for the shopfront: mostly see-through, very smooth, with a blue-grey colour.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add material name=\"Stainless Steel Brushed\""]}
```

Answer: green, op:add material made="Stainless Steel Brushed" changed= ms=178 Check "every count unchanged": the counts: no count changed (from [job 5028: Add brushed stainless steel for the balustrade handrail: grey, mostly metal, with a satin finish.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add material library=concrete_smooth name=\"Concrete N32\""]}
```

Answer: green, op:add material made="Concrete N32" changed= ms=627 Check "every count unchanged": the counts: no count changed (from [job 5029: Set up two structural materials with their engineering properties: N32 concrete and grade 250 steel.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add material library=steel_galvanised name=\"Galvanised Duct Sheet\""]}
```

Answer: green, op:add material made="Galvanised Duct Sheet" changed= ms=216 Check "every count unchanged": the counts: no count changed (from [job 5030: Add galvanised sheet and duct lining to the project materials, with the supplier and cost on each.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add material library=timber_floor_wide name=\"Spotted Gum Floor\""]}
```

Answer: green, op:add material made="Spotted Gum Floor" changed= ms=214 Check "every count unchanged": the counts: no count changed (from [job 5031: Add a spotted gum floor finish with boards 150 mm wide, turned 90 degrees so they run across the room.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add material name=\"Paint Warm White\""]}
```

Answer: green, op:add material made="Paint Warm White" changed= ms=408 Check "every count unchanged": the counts: no count changed (from [job 5032: Set up the interior paint schedule as materials: warm white, sage green and charcoal, each lifted so it does not go grey in shade.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add material library=roof_tile_terracotta name=\"Roof Tile Terracotta\""]}
```

Answer: green, op:add material made="Roof Tile Terracotta" changed= ms=250 Check "every count unchanged": the counts: no count changed (from [job 5056: Add terracotta roof tile and a charcoal Colorbond sheet for the roof, with the tile repeat set to 330 mm.](examples/annotation-details-and-materials.md))


## op: add room

One line in `ops_run`: `op:add room key=value ...`

- Required keys: at (point), level
- Key groups: -
- Optional keys: name, number

Played lines:

```json
ops_run {"lines":["op:add room at=(3000,2000) level=Ground name=\"Office\" number=101"]}
```

Answer: green, op:add room made=room-2624f855a4f566d8 changed= ms=19 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) (from [job 2025: Place a room named Office, number 101, inside the 6 x 4 m office and tag it.](examples/architecture.md))

```json
ops_run {"lines":["op:add room at=(2000,2500) level=Ground name=\"Bedroom 1\" number=101"]}
```

Answer: green, op:add room made=room-05bef86d9d5f26db changed= ms=118 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) (from [job 2026: Divide a 12 x 5 m flat into a bedroom, a living room and a bathroom with stud partitions, and name and number each room.](examples/architecture.md))

```json
ops_run {"lines":["op:add room at=(2500,2500) level=Ground name=\"Work Area\" number=101"]}
```

Answer: green, op:add room made=room-d84743580637deb7 changed= ms=19 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) (from [job 2040: Split the 10 x 5 m open-plan office into a work area and a meeting area with a room separator line and name both rooms.](examples/architecture.md))

```json
ops_run {"lines":["op:add room at=(9000,4500) level=Ground name=\"Living\" number=101"]}
```

Answer: green, op:add room made=room-700c44abaa5c55b0 changed= ms=289 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) (from [job 2041: Draw a small three-bedroom house, 12 x 9 m in brick veneer, with a slab, internal walls, a front door, windows, a hip roof and its rooms named.](examples/architecture.md))

```json
ops_run {"lines":["op:add room at=(4000,2500) level=Ground name=\"Shop\" number=1"]}
```

Answer: green, op:add room made=room-49f646a00fb93055 changed= ms=178 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) (from [job 2042: Fit out an 8 x 12 m shop unit: glazed shopfront, a stock room at the back with a door, a counter and a ceiling.](examples/architecture.md))

```json
ops_run {"lines":["op:add room at=(4500,1500) level=Ground name=\"Site Office\" number=1"]}
```

Answer: green, op:add room made=room-6029c8f0236a70ea changed= ms=13 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) (from [job 2043: Lay out a 9 x 3 m transportable site office with a slab, a door, two windows, a flat roof and its room.](examples/architecture.md))

```json
ops_run {"lines":["op:add room at=(4000,2900) level=Ground name=\"Classroom 1\" number=101"]}
```

Answer: green, op:add room made=room-34ce0a59255f7d83 changed= ms=16 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) (from [job 2048: Lay out a 16 x 8 m classroom block: two classrooms on the south side, a 2.2 m corridor on the north, a door from each classroom and a big window to each.](examples/architecture.md))

```json
ops_run {"lines":["op:add room at=(2000,3000) level=Ground name=\"Living\" number=1"]}
```

Answer: green, op:add room made=room-3e6e908048ab652d changed= ms=15 Check "Rooms +1": Rooms 0 -> 1 (+1, expected +1) (from [job 2049: Draw a 7 x 6 m granny flat: living room, bedroom and bathroom, a front door, two windows and a hip roof.](examples/architecture.md))


## op: add shaft

One line in `ops_run`: `op:add shaft key=value ...`

- Required keys: boundary (pair), level
- Key groups: -
- Optional keys: top

Played lines:

```json
ops_run {"lines":["op:add shaft boundary=(0,0) (2500,2500) level=Ground top=\"Level 1\""]}
```

Answer: green, op:add shaft made=shaft-fc6e20056ab95831 changed= ms=9 Check "Openings +1": Openings 0 -> 1 (+1, expected +1) (from [job 2030: Cut a 2.5 m square lift shaft from Ground up to Level 1 inside concrete walls.](examples/architecture.md))

```json
ops_run {"lines":["op:add shaft boundary=(2000,1500) (5000,3000) level=Ground top=\"Level 1\""]}
```

Answer: green, op:add shaft made=shaft-df966c4622911280 changed= ms=104 Check "Openings +1": Openings 0 -> 1 (+1, expected +1) (from [job 2039: Cut a 3 x 1.5 m stair void in the first floor slab and put a railing round it.](examples/architecture.md))


## op: add stair

One line in `ops_run`: `op:add stair key=value ...`

- Required keys: from (point), to (heading), level, top
- Key groups: -
- Optional keys: type, width (mm)

Played lines:

```json
ops_run {"lines":["op:add stair from=(1000,1000) to=(5000,1000) level=Ground top=\"Level 1\" width=1200"]}
```

Answer: green, op:add stair made=stair-f8a6e8e3b0d9d573 changed= ms=21 note=the run ends at its last riser (5760,1000) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) (from [job 2032: Run a 1200 wide straight stair from Ground up to Level 1 and put a handrail along each side.](examples/architecture.md))

```json
ops_run {"lines":["op:add stair from=(1000,1000) to=(5000,1000) level=Ground top=\"Level 1\" width=1100"]}
```

Answer: green, op:add stair made=stair-1d627a11765c5738 changed= ms=3 note=the run ends at its last riser (5760,1000) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) (from [job 2045: Draw a two-storey walk-up block, 10 x 7 m: ground and first floor walls, a slab and a timber first floor, a stair between the levels and a hip roof.](examples/architecture.md))

```json
ops_run {"lines":["op:add stair from=(1000,1000) to=(1000,5000) level=Ground top=\"Level 1\" width=1000"]}
```

Answer: green, op:add stair made=stair-641691f84a7b7362 changed= ms=498 note=the run ends at its last riser (1000,5760) Check "Stairs +1": Stairs 0 -> 1 (+1, expected +1) (from [job 4018: Put a straight stair between Ground and Level 1 in my house and list it with its base and top levels.](examples/views-sheets-and-schedules.md))


## op: add railing

One line in `ops_run`: `op:add railing key=value ...`

- Required keys: -
- Key groups: exactly one of points (points), host (ids); all or none of points (points), level
- Optional keys: type, level, points (points), host (ids)

Played lines:

```json
ops_run {"lines":["op:add railing points=(1000,300) (4760,300) level=Ground"]}
```

Answer: green, op:add railing made=railing-24dfca25c300fab6 changed= ms=4 Check "Railings +1": Railings 0 -> 1 (+1, expected +1) (from [job 2032: Run a 1200 wide straight stair from Ground up to Level 1 and put a handrail along each side.](examples/architecture.md))

```json
ops_run {"lines":["op:add railing points=(0,0) (0,1500) (4000,1500) (4000,0) level=\"Level 1\""]}
```

Answer: green, op:add railing made=railing-af87615341603b75 changed= ms=6 Check "Railings +1": Railings 0 -> 1 (+1, expected +1) (from [job 2033: Add a 4 x 1.5 m balcony slab at Level 1 with a balustrade round its three free sides.](examples/architecture.md))

```json
ops_run {"lines":["op:add railing points=(1000,300) (11000,300) level=Ground"]}
```

Answer: green, op:add railing made=railing-3c031b6c25b2aa16 changed= ms=41 Check "Railings +1": Railings 0 -> 1 (+1, expected +1) (from [job 2038: Draw a 10 m long, 1200 wide access ramp up from Ground and put a handrail along each side.](examples/architecture.md))

```json
ops_run {"lines":["op:add railing points=(2000,1500) (5000,1500) (5000,3000) (2000,3000) (2000,1500) level=\"Level 1\""]}
```

Answer: green, op:add railing made=railing-d10b42efdaa4bf2e changed= ms=5 Check "Railings +1": Railings 0 -> 1 (+1, expected +1) (from [job 2039: Cut a 3 x 1.5 m stair void in the first floor slab and put a railing round it.](examples/architecture.md))


## op: add door

One line in `ops_run`: `op:add door key=value ...`

- Required keys: wall
- Key groups: exactly one of at (point), offset (mm)
- Optional keys: sill (mm), type, flip (yesno), hand (yesno)

## op: add window

One line in `ops_run`: `op:add window key=value ...`

- Required keys: wall
- Key groups: exactly one of at (point), offset (mm)
- Optional keys: sill (mm), type, flip (yesno), hand (yesno)

## op: add detail line

One line in `ops_run`: `op:add detail line key=value ...`

- Required keys: points (points), view
- Key groups: -
- Optional keys: style

## op: add filled region

One line in `ops_run`: `op:add filled region key=value ...`

- Required keys: boundary (polygon), view
- Key groups: -
- Optional keys: type, pattern

## op: add insulation

One line in `ops_run`: `op:add insulation key=value ...`

- Required keys: from (point), to (point), view
- Key groups: -
- Optional keys: width (mm)

Played lines:

```json
ops_run {"lines":["op:add insulation from=(150,-100) to=(150,-1400) view=\"Wall Detail\" width=90"]}
```

Answer: green, op:add insulation made=insul-8e66ae9b0a7eca0d changed= ms=2 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) (from [job 4061: Draw a 1:10 wall detail with a 300 mm outline, a brick region, a 90 mm insulation batt and a width dimension, and put it on a sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add insulation from=(70,-880) to=(70,-20) view=\"Timber Eaves Detail\" width=100"]}
```

Answer: green, op:add insulation made=insul-5032be30154f2f32 changed= ms=3 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) (from [job 5001: Draw a 1:10 eaves detail for our timber frame wall: stud frame, rafter, batt insulation, plasterboard, notes and a dimension.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add insulation from=(-20,170) to=(-20,310) view=\"Duct Hanger Detail\" width=40"]}
```

Answer: green, op:add insulation made=insul-4452ea7dce8907d2 changed= ms=2 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) (from [job 5004: Draw the 1:10 hanger detail for our rectangular ducts: the duct, two threaded rods, the angle bearer and a note on the rod size.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add insulation from=(900,220) to=(260,220) view=\"Parapet Detail\" width=100"]}
```

Answer: green, op:add insulation made=insul-ac71161de7e03723 changed= ms=3 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) (from [job 5012: Detail a flat roof parapet at 1:10: concrete upstand, membrane turned up, capping, insulation and the heights noted.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add insulation from=(-125,100) to=(-125,380) view=\"Diffuser Connection Detail\" width=25"]}
```

Answer: green, op:add insulation made=insul-a80e8317acbc88d5 changed= ms=3 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) (from [job 5041: Detail the flexible duct connection to a ceiling diffuser at 1:10 with the spigot, clamp and the plenum box.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add insulation from=(35,20) to=(35,880) view=\"Batt Sizes\" width=70"]}
```

Answer: green, op:add insulation made=insul-a4e64da3cf5b464f changed= ms=4 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) (from [job 5046: Show our three wall batt sizes side by side in a stud wall section: 70, 90 and 140 mm.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add insulation from=(-350,250) to=(350,250) view=\"Lagged Duct Section\" width=50"]}
```

Answer: green, op:add insulation made=insul-1953ffb3c2576790 changed= ms=18 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) (from [job 5047: Draw an externally lagged round duct section at 1:5: the duct wall, 50 mm lagging all round and a foil jacket.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add insulation from=(-30,-208) to=(220,-208) view=\"Fire Damper Detail\" width=15"]}
```

Answer: green, op:add insulation made=insul-4ada9a403ba62037 changed= ms=3 Check "Detail Items +1": Detail Items 0 -> 1 (+1, expected +1) (from [job 5065: Detail a duct passing through a fire wall at 1:10 with a fire damper in the wall, the retaining angle and the packing.](examples/annotation-details-and-materials.md))


## op: add view

One line in `ops_run`: `op:add view key=value ...`

- Required keys: kind (plankind), level
- Key groups: -
- Optional keys: name

Played lines:

```json
ops_run {"lines":["op:add view kind=structural level=\"Level 3\" name=\"Level 3 Framing Plan\""]}
```

Answer: green, op:add view made=826a52100f52452d8cada04e68191e3e changed= ms=8 Check "view: Structural Plan +1": view: Structural Plan 2 -> 3 (+1, expected +1) (from [job 1059: Add Level 3 at 7200 mm with its own structural framing plan and put a beam on it.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:add view kind=plan level=\"Level 1\" name=\"First Floor Plan\""]}
```

Answer: green, op:add view made=1dfd2e854ae04a40b73f1c8bf4fbdefb changed= ms=8 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) (from [job 2052: Make a Level 1 plan for the walk-up and put it on a new sheet A900.](examples/architecture.md))

```json
ops_run {"lines":["op:add view kind=plan level=Ground name=\"Office Plan\""]}
```

Answer: green, op:add view made=3fe5b2fa5b834c25bd888bd9aafdd7bd changed= ms=10 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) (from [job 2055: Cut a long section through the 12 x 6 m office and put the plan and the section together on a new A1 sheet.](examples/architecture.md))

```json
ops_run {"lines":["op:add view kind=plan level=Ground name=\"Dimension Plan\""]}
```

Answer: green, op:add view made=2e8ab2409c234fa7af464e02229fabef changed= ms=13 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) (from [job 2056: Dimension the 10 x 6 m office on a plan of its own: the south wall, the west wall and the east wall, with a note.](examples/architecture.md))

```json
ops_run {"lines":["op:add view kind=plan level=Mezzanine name=\"Mezzanine Plan\""]}
```

Answer: green, op:add view made=ca60a71e648446429327583649121f27 changed= ms=6 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) (from [job 2058: Add a mezzanine level at 2400 over the end of the 12 x 8 m workshop with its own plan and a floor slab.](examples/architecture.md))

```json
ops_run {"lines":["op:add view kind=ceiling level=Ground name=\"Office RCP\""]}
```

Answer: green, op:add view made=d7b52178a0ca45019010525b85f68ab7 changed= ms=15 Check "view: Ceiling Plan +1": view: Ceiling Plan 3 -> 4 (+1, expected +1) (from [job 2061: Ceiling the 6 x 4 m office at 2700 and make a reflected ceiling plan of it named Office RCP.](examples/architecture.md))

```json
ops_run {"lines":["op:add view kind=plan level=\"Level 1\" name=\"Level 1 Furniture Plan\""]}
```

Answer: green, op:add view made=51258adb960043e6a6b1b7f43d87147c changed= ms=12 Check "view: Floor Plan +1": view: Floor Plan 4 -> 5 (+1, expected +1) (from [job 4003: Give me a separate Level 1 plan for the furniture layout of the 9 by 6 m upstairs flat, at 1:50 on its own sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add view kind=ceiling level=Ground name=\"Ground Lighting Plan\""]}
```

Answer: green, op:add view made=dcce147650d442158fc3df9c6cbbff8f changed= ms=16 Check "view: Ceiling Plan +1": view: Ceiling Plan 3 -> 4 (+1, expected +1) (from [job 4004: Draw a 2700 mm ceiling over my 7 by 5 m studio and make a lighting ceiling plan of it at 1:50 on a new sheet.](examples/views-sheets-and-schedules.md))


## op: add section

One line in `ops_run`: `op:add section key=value ...`

- Required keys: from (point), to (point), view
- Key groups: -
- Optional keys: depth (mm), name

Played lines:

```json
ops_run {"lines":["op:add section from=(5000,-1500) to=(5000,7500) view=48660e38a721430d899d5d8a96df3bec name=\"Cut A1\""]}
```

Answer: green, op:add section made=6162a16d44ad4499b92ebea7721ea722 changed= ms=13 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) (from [job 2051: Draw a 10 x 6 m office, then cut a cross section through it and add a south elevation.](examples/architecture.md))

```json
ops_run {"lines":["op:add section from=(6000,-1500) to=(6000,7500) view=\"Office Plan\" name=\"Cut B1\""]}
```

Answer: green, op:add section made=85642131ce214e338313a96b2d0cfc2b changed= ms=9 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) (from [job 2055: Cut a long section through the 12 x 6 m office and put the plan and the section together on a new A1 sheet.](examples/architecture.md))

```json
ops_run {"lines":["op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name=\"Office Cross Section\" view=48660e38a721430d899d5d8a96df3bec"]}
```

Answer: green, op:add section made=aedf804a8b50442a906b6a3244119300 changed= ms=17 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) (from [job 4001: Cut a section through my 8 by 6 m office and put it on its own sheet at 1:50.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add section from=(3500,-1500) to=(3500,6500) depth=5000 name=\"Studio Section\" view=\"Studio Plan\""]}
```

Answer: green, op:add section made=a4435073f68b4c1e94b0347e9d00654a changed= ms=12 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) (from [job 4028: Put the plan and a section of my 7 by 5 m studio on one sheet, the plan at 1:100 and the section at 1:50.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add section from=(-2000,4000) to=(14000,4000) depth=5000 name=\"Long Section\" view=48660e38a721430d899d5d8a96df3bec"]}
```

Answer: green, op:add section made=07f9b1e8d6ec47c990d4577a052efeb5 changed= ms=30 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) (from [job 4036: Cut a long section and a cross section through my 12 by 8 m workshop.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add section from=(4000,7500) to=(4000,4500) depth=1500 name=\"North Wall Section\" view=48660e38a721430d899d5d8a96df3bec"]}
```

Answer: green, op:add section made=e29100712ac746ed9586aebedf17078d changed= ms=34 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) (from [job 4037: Cut a shallow wall section through the north wall of my 8 by 6 m room, set to medium detail.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name=\"Gable Section\" view=48660e38a721430d899d5d8a96df3bec"]}
```

Answer: green, op:add section made=ee82bd7f721243c1b6b422f340de992e changed= ms=13 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) (from [job 4057: I put the section on the wrong sheet; take it off sheet A310 and put it on A311.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add section from=(4000,-1500) to=(4000,7500) depth=6000 name=\"Cottage Section\" view=\"Cottage Plan\""]}
```

Answer: green, op:add section made=9f6c40381b724ae5a7ce4d3cebfa543f changed= ms=11 Check "view: Section +1": view: Section 2 -> 3 (+1, expected +1) (from [job 4070: Make a drawing set for my 8 by 6 m cottage: a plan, a section, an elevation and the door list, all on one sheet.](examples/views-sheets-and-schedules.md))


## op: add elevation

One line in `ops_run`: `op:add elevation key=value ...`

- Required keys: at (point), facing (facing), view
- Key groups: -
- Optional keys: name

Played lines:

```json
ops_run {"lines":["op:add elevation at=(5000,-4000) facing=south view=48660e38a721430d899d5d8a96df3bec name=\"Office South\""]}
```

Answer: green, op:add elevation made=elev-80a7fe4ddb764cf2 changed= ms=13 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) (from [job 2051: Draw a 10 x 6 m office, then cut a cross section through it and add a south elevation.](examples/architecture.md))

```json
ops_run {"lines":["op:add elevation at=(4000,7500) facing=south view=48660e38a721430d899d5d8a96df3bec name=\"Cottage North\""]}
```

Answer: green, op:add elevation made=elev-feec5cadd08c4224 changed= ms=139 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) (from [job 2054: Draw the 8 x 5 m cottage and add a north, south, east and west elevation named for it.](examples/architecture.md))

```json
ops_run {"lines":["op:add elevation at=(5000,-6000) facing=north name=\"House Front Elevation\" view=48660e38a721430d899d5d8a96df3bec"]}
```

Answer: green, op:add elevation made=elev-e7d0aec17b1e4b9f changed= ms=18 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) (from [job 4002: Make the front and side elevations of my 10 by 7 m house and put both on one A1 sheet at 1:100.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add elevation at=(5000,-7000) facing=north name=\"House South Face\" view=48660e38a721430d899d5d8a96df3bec"]}
```

Answer: green, op:add elevation made=elev-d8bb7ebc7dae45e3 changed= ms=407 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) (from [job 4035: Make all four exterior elevations of my 10 by 8 m house.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add elevation at=(4000,-6000) facing=north name=\"Cottage Front Elevation\" view=\"Cottage Plan\""]}
```

Answer: green, op:add elevation made=elev-326877b91deb4d53 changed= ms=10 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) (from [job 4070: Make a drawing set for my 8 by 6 m cottage: a plan, a section, an elevation and the door list, all on one sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add elevation at=(4000,-6000) facing=north name=\"Frame Elevation\" view=\"Frame Plan\""]}
```

Answer: green, op:add elevation made=elev-fd20f4f1f7cf4abf changed= ms=13 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) (from [job 4071: Make a drawing set for my steel frame: a framing plan, a section, an elevation and the column and beam schedules, on one sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add elevation at=(4000,-6000) facing=north name=\"Frame South Face\" view=\"Level 1\""]}
```

Answer: green, op:add elevation made=elev-eaa3cce601fa4880 changed= ms=15 Check "view: Elevation +1": view: Elevation 4 -> 5 (+1, expected +1) (from [job 4079: Make elevations of the north and south faces of my steel frame.](examples/views-sheets-and-schedules.md))


## op: add drafting view

One line in `ops_run`: `op:add drafting view key=value ...`

- Required keys: -
- Key groups: -
- Optional keys: name, scale

## op: add legend

One line in `ops_run`: `op:add legend key=value ...`

- Required keys: -
- Key groups: -
- Optional keys: name, scale

Played lines:

```json
ops_run {"lines":["op:add legend name=\"Door Types\" scale=1:20"]}
```

Answer: green, op:add legend made=135b4d0f29f84b67ae6822b1a5d54c74 changed= ms=25 Check "view: Legend +1": view: Legend 0 -> 1 (+1, expected +1) (from [job 4007: Add a legend called Door Types to the drawing set and put it on the schedules sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add legend name=Symbols scale=1:50"]}
```

Answer: green, op:add legend made=b72dc5cd4e964f1793cce8f5a208700d changed= ms=18 Check "view: Legend +1": view: Legend 0 -> 1 (+1, expected +1) (from [job 4075: Put a symbols legend and the general notes together on one cover sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add legend name=\"Electrical Symbols\" scale=1:20"]}
```

Answer: green, op:add legend made=df8fa37ed3ce41868a9a70559010c756 changed= ms=15 Check "view: Legend +1": view: Legend 0 -> 1 (+1, expected +1) (from [job 4077: Open an electrical sheet and put a legend of the symbols on it.](examples/views-sheets-and-schedules.md))


## op: add schedule

One line in `ops_run`: `op:add schedule key=value ...`

- Required keys: category, fields
- Key groups: -
- Optional keys: name, sortby, groupby, filter, itemize (yesno)

Played lines:

```json
ops_run {"lines":["op:add schedule category=Doors fields=Mark,Type,Width name=\"Hall Doors\""]}
```

Answer: green, op:add schedule made=ba72daa90d47436d9ac1d729fa68b6e1 changed= ms=325 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) (from [job 2053: Hang three doors in the hall and list them in a door schedule with their type and width.](examples/architecture.md))

```json
ops_run {"lines":["op:add schedule category=Rooms fields=Number,Name,Area name=\"Flat Rooms\""]}
```

Answer: green, op:add schedule made=cf78a26e65bb4c1fb11ace34d6fea817 changed= ms=7 Check "view: Schedule +1": view: Schedule 3 -> 4 (+1, expected +1) (from [job 2057: Divide the 9 x 5 m flat into two rooms, name them and list the rooms in a schedule with number, name and area.](examples/architecture.md))

```json
ops_run {"lines":["op:add schedule category=Ducts fields=Mark,Type,Width,Height name=\"Duct Schedule\""]}
```

Answer: green, op:add schedule made=eb6d307c03364d13b444322625356528 changed= ms=70 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) (from [job 3019: Draw three supply ducts of different sizes and make a duct schedule listing mark, type, width and height.](examples/building-services.md))

```json
ops_run {"lines":["op:add schedule category=\"Air Terminals\" fields=Type,Count name=\"Diffuser Schedule\" itemize=no"]}
```

Answer: green, op:add schedule made=5c715ff19a42481182b8e9ddaad689ba changed= ms=172 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) (from [job 3020: Put four diffusers on a supply duct and make a schedule of the air terminals by type with a count.](examples/building-services.md))

```json
ops_run {"lines":["op:add schedule category=\"Mechanical Equipment\" fields=Mark,Type name=\"Equipment Schedule\""]}
```

Answer: green, op:add schedule made=ba616b507be2462caf78db5ac08af5fe changed= ms=296 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) (from [job 3021: Place an air handling unit, a fan coil unit and an exhaust fan and schedule the mechanical equipment with mark and type.](examples/building-services.md))

```json
ops_run {"lines":["op:add schedule category=Pipes fields=Type,Count name=\"Pipe Schedule\" itemize=no"]}
```

Answer: green, op:add schedule made=80ef2bff3bc64cd194bbda5186a6d2e8 changed= ms=16 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) (from [job 3042: Draw three pipes of 100, 50 and 25 mm and make a pipe schedule by type with a count.](examples/building-services.md))

```json
ops_run {"lines":["op:add schedule category=\"Plumbing Fixtures\" fields=Type,Count name=\"Fixture Schedule\" itemize=no"]}
```

Answer: green, op:add schedule made=898cf274bf554a999c16a433b37990b4 changed= ms=385 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) (from [job 3043: Place three plumbing fixtures and schedule them by type with a count.](examples/building-services.md))

```json
ops_run {"lines":["op:add schedule category=Sprinklers fields=Type,Count name=\"Sprinkler Schedule\" itemize=no"]}
```

Answer: green, op:add schedule made=e8a39a0d06fe46e489e4b00ff23758bb changed= ms=20 Check "view: Schedule +1": view: Schedule 0 -> 1 (+1, expected +1) (from [job 3059: Put six sprinklers on a branch line and schedule them by type with a count.](examples/building-services.md))


## op: add 3d view

One line in `ops_run`: `op:add 3d view key=value ...`

- Required keys: -
- Key groups: -
- Optional keys: name

## op: add sheet

One line in `ops_run`: `op:add sheet key=value ...`

- Required keys: -
- Key groups: -
- Optional keys: number, name, titleblock

Played lines:

```json
ops_run {"lines":["op:add sheet number=A900 name=\"First Floor\""]}
```

Answer: green, op:add sheet made=sheet-A900 changed= ms=3 Check "sheet A900 exists": sheet A900 exists (9 sheet(s) in the document) (from [job 2052: Make a Level 1 plan for the walk-up and put it on a new sheet A900.](examples/architecture.md))

```json
ops_run {"lines":["op:add sheet number=A902 name=\"Office Plan and Section\" titleblock=A1"]}
```

Answer: green, op:add sheet made=sheet-A902 changed= ms=2 Check "sheet A902 exists": sheet A902 exists (9 sheet(s) in the document) (from [job 2055: Cut a long section through the 12 x 6 m office and put the plan and the section together on a new A1 sheet.](examples/architecture.md))

```json
ops_run {"lines":["op:add sheet number=A310 name=\"Office Section\" titleblock=A1"]}
```

Answer: green, op:add sheet made=sheet-A310 changed= ms=5 Check "sheet A310 exists": sheet A310 exists (9 sheet(s) in the document) (from [job 4001: Cut a section through my 8 by 6 m office and put it on its own sheet at 1:50.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add sheet number=A211 name=\"House Elevations\" titleblock=A1"]}
```

Answer: green, op:add sheet made=sheet-A211 changed= ms=5 Check "sheet A211 exists": sheet A211 exists (9 sheet(s) in the document) (from [job 4002: Make the front and side elevations of my 10 by 7 m house and put both on one A1 sheet at 1:100.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add sheet number=A122 name=\"Level 1 Furniture Layout\" titleblock=A1"]}
```

Answer: green, op:add sheet made=sheet-A122 changed= ms=9 Check "sheet A122 exists": sheet A122 exists (9 sheet(s) in the document) (from [job 4003: Give me a separate Level 1 plan for the furniture layout of the 9 by 6 m upstairs flat, at 1:50 on its own sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add sheet number=A140 name=\"Ground Lighting Plan\" titleblock=A1"]}
```

Answer: green, op:add sheet made=sheet-A140 changed= ms=6 Check "sheet A140 exists": sheet A140 exists (9 sheet(s) in the document) (from [job 4004: Draw a 2700 mm ceiling over my 7 by 5 m studio and make a lighting ceiling plan of it at 1:50 on a new sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add sheet number=S101 name=\"Level 1 Framing Plan\" titleblock=A1"]}
```

Answer: green, op:add sheet made=sheet-S101 changed= ms=6 Check "sheet S101 exists": sheet S101 exists (1 sheet(s) in the document) (from [job 4005: Set out a four column steel bay on Level 1 with two beams, make a Level 1 framing plan at 1:100 and put it on sheet S101.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add sheet number=A002 name=\"General Notes\" titleblock=A1"]}
```

Answer: green, op:add sheet made=sheet-A002 changed= ms=4 Check "sheet A002 exists": sheet A002 exists (9 sheet(s) in the document) (from [job 4006: Write the general notes for the job as a drawing and put them on a sheet.](examples/views-sheets-and-schedules.md))


## op: place view

One line in `ops_run`: `op:place view key=value ...`

- Required keys: view, sheet
- Key groups: -
- Optional keys: at (sheetpoint), title, scale, crop (pair), table_width (mm), text_size (mm)

Played lines:

```json
ops_run {"lines":["op:place view view=\"First Floor Plan\" sheet=A900"]}
```

Answer: green, op:place view made=1dfd2e854ae04a40b73f1c8bf4fbdefb::sheet-A900::5ca0695470c240a28b1b6b9f2f4cb56d changed= ms=3 Check "sheet A900 exists": sheet A900 exists (9 sheet(s) in the document) (from [job 2052: Make a Level 1 plan for the walk-up and put it on a new sheet A900.](examples/architecture.md))

```json
ops_run {"lines":["op:place view view=\"Office Plan\" sheet=A902 at=(40,500)"]}
```

Answer: green, op:place view made=3fe5b2fa5b834c25bd888bd9aafdd7bd::sheet-A902::57b9ac65f8e64b6d894a21d5999a37de changed= ms=40 note=the frame is 264.9 x 264.9 mm and its lower-left corner stands at (40,500) in sheet mm and it runs off the sheet, which is 841 x 594 mm Check "sheet A902 exists": sheet A902 exists (9 sheet(s) in the document) (from [job 2055: Cut a long section through the 12 x 6 m office and put the plan and the section together on a new A1 sheet.](examples/architecture.md))

```json
ops_run {"lines":["op:place view view=\"Office Cross Section\" sheet=A310 at=(100,100) scale=1:50"]}
```

Answer: green, op:place view made=aedf804a8b50442a906b6a3244119300::sheet-A310::a73ccc99cc1e429db891b3965807f4b4 changed= ms=4518 Check "—": no expectation (from [job 4001: Cut a section through my 8 by 6 m office and put it on its own sheet at 1:50.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:place view view=\"House Front Elevation\" sheet=A211 at=(40,60) scale=1:100"]}
```

Answer: green, op:place view made=elev-e7d0aec17b1e4b9f::sheet-A211::ac180e1d15af4ec2aa7399d0a41a6a28 changed= ms=116 Check "—": no expectation (from [job 4002: Make the front and side elevations of my 10 by 7 m house and put both on one A1 sheet at 1:100.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:place view view=\"Level 1 Furniture Plan\" sheet=A122 at=(100,60) crop=(-2000,-2000) (11000,8000)"]}
```

Answer: green, op:place view made=51258adb960043e6a6b1b7f43d87147c::sheet-A122::81df023d65bf4ace8d0902954e40a2f5 changed= ms=577 Check "—": no expectation (from [job 4003: Give me a separate Level 1 plan for the furniture layout of the 9 by 6 m upstairs flat, at 1:50 on its own sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:place view view=\"Ground Lighting Plan\" sheet=A140 at=(100,60) scale=1:50 crop=(-2000,-2000) (9000,7000)"]}
```

Answer: green, op:place view made=dcce147650d442158fc3df9c6cbbff8f::sheet-A140::d66ab87b9d8943478685f662f4ae1499 changed= ms=308 Check "—": no expectation (from [job 4004: Draw a 2700 mm ceiling over my 7 by 5 m studio and make a lighting ceiling plan of it at 1:50 on a new sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:place view view=\"Level 1 Framing Plan\" sheet=S101 at=(80,100)"]}
```

Answer: green, op:place view made=553e6d8e70ec4cd0a9007ba23298ab6a::sheet-S101::d08e28ad5c3b4bdd97ce65d7664b1ad3 changed= ms=80 Check "—": no expectation (from [job 4005: Set out a four column steel bay on Level 1 with two beams, make a Level 1 framing plan at 1:100 and put it on sheet S101.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:place view view=\"General Notes\" sheet=A002 at=(40,500)"]}
```

Answer: green, op:place view made=e71fb59e35614898a047f1644fde82dc::sheet-A002::8e8a3a8358064815af646957187515e2 changed= ms=21 Check "—": no expectation (from [job 4006: Write the general notes for the job as a drawing and put them on a sheet.](examples/views-sheets-and-schedules.md))


## op: print sheets

One line in `ops_run`: `op:print sheets key=value ...`

- Required keys: path
- Key groups: -
- Optional keys: -

## op: set

One line in `ops_run`: `op:set key=value ...`

- Required keys: id (ids), key, value
- Key groups: -
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:set id=\"Level 2\" key=Elevation value=3600"]}
```

Answer: green, op:set made= changed="Level 2" ms=23 Check "every count unchanged": the counts: no count changed (from [job 1001: Set up the levels for a four-storey steel office, 3.6 m floor to floor, with the roof at 14.4 m.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:set id=\"Level 1\" key=Name value=\"Ground Floor\""]}
```

Answer: green, op:set made= changed="Level 1" ms=518 Check "every count unchanged": the counts: no count changed (from [job 1002: Rename the two template levels Ground Floor and First Floor and put the first floor at 4200 mm.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:set id=\"Level 2\" key=Elevation value=6000"]}
```

Answer: green, op:set made= changed="Level 2",column-50dbd1f83d337b18,column-5d8e8f7cc3df5bc6 ms=7 Check "every count unchanged": the counts: no count changed (from [job 1004: Make the ground floor double height by raising Level 2 to 6000 mm; the columns must follow.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:set id=\"Level 2\" key=Elevation value=3400"]}
```

Answer: green, op:set made= changed="Level 2" ms=14 Check "every count unchanged": the counts: no count changed (from [job 1005: Copy Level 2 up three times at 3.4 m to make the typical floors of a tower.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:set id=\"Level 2\" key=Elevation value=7000"]}
```

Answer: green, op:set made= changed="Level 2" ms=333 Check "every count unchanged": the counts: no count changed (from [job 1007: Put a mezzanine platform at 2.7 m inside a 7 m high warehouse: a 9 x 6 m deck on four columns with edge beams.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:set id=\"Level 1\" key=Name value=\"L00 Ground\""]}
```

Answer: green, op:set made= changed="Level 1" ms=602 Check "every count unchanged": the counts: no count changed (from [job 1008: Name the levels L00 Ground, L01 First and L02 Second to match the client's drawing numbers, then run a column up through all three.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:set id=level-Roof key=Elevation value=19300"]}
```

Answer: green, op:set made= changed=level-Roof ms=661 Check "every count unchanged": the counts: no count changed (from [job 1009: The site is at RL 12.5: move Ground, Level 1 and the Roof up to 12500, 15900 and 19300 and run a steel column through them.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:set id=\"level-Level 1\" key=Elevation value=3400"]}
```

Answer: green, op:set made= changed="level-Level 1" ms=17 Check "every count unchanged": the counts: no count changed (from [job 1010: Add a second floor to the house frame at 6800 mm and lift the roof to 10200 mm.](examples/setting-out-and-structure.md))


## op: set material

One line in `ops_run`: `op:set material key=value ...`

- Required keys: name, key, value
- Key groups: -
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:set material name=\"Facade Brick\" key=texture_size value=1200"]}
```

Answer: green, op:set material made= changed="Facade Brick" ms=51 Check "every count unchanged": the counts: no count changed (from [job 5026: Add our three facade materials to the project: red brick, white render and zinc cladding, each set to its texture.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:set material name=\"Shopfront Glass\" key=render_colour value=#7E9AAE"]}
```

Answer: green, op:set material made= changed="Shopfront Glass" ms=12 Check "every count unchanged": the counts: no count changed (from [job 5027: Make a blue-grey glazing material for the shopfront: mostly see-through, very smooth, with a blue-grey colour.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:set material name=\"Stainless Steel Brushed\" key=render_colour value=#B9BEC4"]}
```

Answer: green, op:set material made= changed="Stainless Steel Brushed" ms=39 Check "every count unchanged": the counts: no count changed (from [job 5028: Add brushed stainless steel for the balustrade handrail: grey, mostly metal, with a satin finish.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:set material name=\"Concrete N32\" key=density value=2400"]}
```

Answer: green, op:set material made= changed= ms=11 state=unchanged Check "every count unchanged": the counts: no count changed (from [job 5029: Set up two structural materials with their engineering properties: N32 concrete and grade 250 steel.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:set material name=\"Galvanised Duct Sheet\" key=manufacturer value=\"Metal Duct Supplies\""]}
```

Answer: green, op:set material made= changed="Galvanised Duct Sheet" ms=11 Check "every count unchanged": the counts: no count changed (from [job 5030: Add galvanised sheet and duct lining to the project materials, with the supplier and cost on each.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:set material name=\"Spotted Gum Floor\" key=texture_size value=900"]}
```

Answer: green, op:set material made= changed="Spotted Gum Floor" ms=24 Check "every count unchanged": the counts: no count changed (from [job 5031: Add a spotted gum floor finish with boards 150 mm wide, turned 90 degrees so they run across the room.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:set material name=\"Paint Warm White\" key=render_colour value=#f4f1ea"]}
```

Answer: green, op:set material made= changed="Paint Warm White" ms=14 Check "every count unchanged": the counts: no count changed (from [job 5032: Set up the interior paint schedule as materials: warm white, sage green and charcoal, each lifted so it does not go grey in shade.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:set material name=\"Roof Tile Terracotta\" key=texture_size value=330"]}
```

Answer: green, op:set material made= changed="Roof Tile Terracotta" ms=23 Check "every count unchanged": the counts: no count changed (from [job 5056: Add terracotta roof tile and a charcoal Colorbond sheet for the roof, with the tile repeat set to 330 mm.](examples/annotation-details-and-materials.md))


## op: set view

One line in `ops_run`: `op:set view key=value ...`

- Required keys: view
- Key groups: at least one of hide, show, map
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:set view view=\"Office Cross Section\" hide=Grids"]}
```

Answer: green, op:set view made= changed=aedf804a8b50442a906b6a3244119300 ms=17 Check "—": no expectation (from [job 4001: Cut a section through my 8 by 6 m office and put it on its own sheet at 1:50.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set view view=\"Level 1 Furniture Plan\" hide=Levels"]}
```

Answer: green, op:set view made= changed=51258adb960043e6a6b1b7f43d87147c ms=37 Check "—": no expectation (from [job 4003: Give me a separate Level 1 plan for the furniture layout of the 9 by 6 m upstairs flat, at 1:50 on its own sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set view view=view-3d hide=Levels,Grids map=plain:lightgrey"]}
```

Answer: green, op:set view made= changed=view-3d ms=29 Check "—": no expectation (from [job 4010: Take the level and grid lines off the 3D view and give it a light grey background.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set view view=\"Wall Setout Plan\" hide=\"Doors,Windows\""]}
```

Answer: green, op:set view made= changed=b40d63d162ff45758d02328b43ec247a ms=21 Check "—": no expectation (from [job 4021: Make a plan for the brickie that shows the walls only, with no doors or windows, for my 9 by 6 m house.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set view view=\"Tender Plan\" hide=\"Rooms,Room Tags\""]}
```

Answer: green, op:set view made= changed=91323cbe7b5343f9af5519b31a039ceb ms=17 Check "—": no expectation (from [job 4022: Make a Level 1 plan without room names or tags for the tender set of my 8 by 5 m unit.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set view view=\"Client Plan\" hide=\"Grids,Levels\""]}
```

Answer: green, op:set view made= changed=e0474405e0174f45afedfed7252b2b91 ms=51 Check "—": no expectation (from [job 4023: I want one Ground plan for the client with no grid lines and one for the builder with them showing.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set view view=\"Ground Copy 1\" hide=\"Furniture,Dimensions\""]}
```

Answer: green, op:set view made= changed=6d7813e5a59748b8afd5c4ce03cd8e80 ms=16 Check "—": no expectation (from [job 4029: Duplicate the Ground plan for the structural engineer and hide the furniture and dimensions on the copy.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set view view=view-3d hide=Levels,Grids map=plain:darkgrey"]}
```

Answer: green, op:set view made= changed=view-3d ms=26 Check "—": no expectation (from [job 4050: Show my steel frame in 3D on a dark grey background without level or grid lines.](examples/views-sheets-and-schedules.md))


## op: set element graphics

One line in `ops_run`: `op:set element graphics key=value ...`

- Required keys: view (viewid), id (elementids)
- Key groups: at least one of projection_line_colour (overridecolour), cut_line_colour (overridecolour), surface_colour (overridecolour), cut_fill_colour (overridecolour), transparency (overridetransparency)
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A,grid-B projection_line_colour=#CC0000"]}
```

Answer: green, op:set element graphics made= changed= ms=1 Check "—": no expectation (from [job 4009: Make grid lines A and B red in the Ground plan only.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A projection_line_colour=#0050A0"]}
```

Answer: green, op:set element graphics made= changed= ms=3 Check "—": no expectation (from [job 4027: Make grid A blue in the Ground plan, then change my mind and put it back to its normal colour.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:set element graphics view=48660e38a721430d899d5d8a96df3bec id=grid-A,grid-B projection_line_colour=#808080 transparency=60"]}
```

Answer: green, op:set element graphics made= changed= ms=2 Check "—": no expectation (from [job 4066: Make grids A and B grey and half see-through in the Ground plan so they do not fight the walls.](examples/views-sheets-and-schedules.md))


## op: delete

One line in `ops_run`: `op:delete key=value ...`

- Required keys: id (ids)
- Key groups: -
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:delete id=\"level-Plant\""]}
```

Answer: green, op:delete made= changed=level-Plant ms=13 Check "Levels -1": Levels 3 -> 2 (-1, expected -1) (from [job 1006: Add a plant level, delete it, then bring it back with Undo and take it away again with Redo.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:delete id=grid-C"]}
```

Answer: green, op:delete made= changed=grid-C ms=511 Check "Grids -1": Grids 4 -> 3 (-1, expected -1) (from [job 1020: Take gridline C out of a four-line grid, change my mind with Undo, then take it out again with Redo.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:delete id=level-Plant"]}
```

Answer: green, op:delete made= changed=level-Plant ms=24 Check "Levels -1": Levels 4 -> 3 (-1, expected -1) (from [job 6024: Add the plant level at 9000, delete it, then undo and redo the delete.](examples/change-modify-and-freeform.md))

```json
ops_run {"lines":["op:delete id=grid-A"]}
```

Answer: green, op:delete made= changed=grid-A ms=1842 Check "Grids -1": Grids 2 -> 1 (-1, expected -1) (from [job 6026: Move grid A 500 mm east, copy it 8 m for the second line, rename the original to Z, then delete it and take the delete back.](examples/change-modify-and-freeform.md))


## op: delete sheet

One line in `ops_run`: `op:delete sheet key=value ...`

- Required keys: sheet
- Key groups: -
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:delete sheet sheet=A602"]}
```

Answer: green, op:delete sheet made= changed=sheet-A602 ms=3 note=sheet A602 deleted; its views stand unplaced Check "—": no expectation (from [job 4019: Open three A3 sheets for the first issue: a cover, the notes and the details, and take out the notes sheet again.](examples/views-sheets-and-schedules.md))


## op: remove view

One line in `ops_run`: `op:remove view key=value ...`

- Required keys: -
- Key groups: exactly one of view, id (ids); all or none of view, sheet
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:remove view view=\"Site Plan\" sheet=A100"]}
```

Answer: green, op:remove view made= changed=7c4df2b0-7e72-46b6-bda2-c289caa51776::sheet-A100::853005318d254b5abd699a51092ebd69 ms=19 Check "—": no expectation (from [job 4020: Put the site plan back on its sheet at 1:500, cropped to my 60 by 40 m site.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:remove view view=\"Gable Section\" sheet=A310"]}
```

Answer: green, op:remove view made= changed=ee82bd7f721243c1b6b422f340de992e::sheet-A310::8c09fd54974345c0a3b001dab3eba1d8 ms=4 Check "—": no expectation (from [job 4057: I put the section on the wrong sheet; take it off sheet A310 and put it on A311.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:remove view view=\"Shed Plan\" sheet=A120"]}
```

Answer: green, op:remove view made= changed=8118ddc0cf44418d94dad9ed7dc7b698::sheet-A120::70adac3dab8240d4b6f2ae289df5a7c2 ms=4 Check "—": no expectation (from [job 4058: The plan is too big on sheet A120; take it off and put it back at 1:100.](examples/views-sheets-and-schedules.md))


## op: move

One line in `ops_run`: `op:move key=value ...`

- Required keys: id (ids), by (movevector)
- Key groups: -
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:move id=grid-A,grid-B,grid-C by=(250,0,0)"]}
```

Answer: green, op:move made= changed=grid-A,grid-B,grid-C ms=8 Check "moved": 3 element(s) moved: grid-A  -> ; grid-B  -> ; grid-C  -> (from [job 1015: The client calls the gridlines X, Y and Z instead of A, B and C: rename them and shift all three 250 mm east.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:move id=grid-B by=(500,0,0)"]}
```

Answer: green, op:move made= changed=grid-B ms=350 Check "moved": 1 element(s) moved: grid-B  -> (from [job 1016: Shift gridline B 500 mm east to clear the stair core, then undo it and do it again.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:move id=grid-A by=(-400,0,0)"]}
```

Answer: green, op:move made= changed=grid-A ms=30 Check "moved": 1 element(s) moved: grid-A  -> (from [job 1051: Fit the grid to an angled boundary: pull gridline A 400 mm west and swing gridline B 5 degrees about its foot.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:move id=grid-A by=(500,0,0)"]}
```

Answer: green, op:move made= changed=grid-A ms=58 Check "moved": 1 element(s) moved: grid-A  -> (from [job 6026: Move grid A 500 mm east, copy it 8 m for the second line, rename the original to Z, then delete it and take the delete back.](examples/change-modify-and-freeform.md))


## op: add duct

One line in `ops_run`: `op:add duct key=value ...`

- Required keys: from (point), to (point), level
- Key groups: -
- Optional keys: width (mm), height (mm), diameter (mm), elevation (mm), system

Played lines:

```json
ops_run {"lines":["op:add duct from=(0,0) to=(12000,0) level=\"Level 1\" width=600 height=250 elevation=2700 system=\"Supply Air\""]}
```

Answer: green, op:add duct made=duct-4957bd24e7d6c2a7,system-0e862b4bebf0e8ee changed= ms=7 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) (from [job 3001: Run a 600 x 250 supply duct 12 m down the corridor at 2700 mm and put four diffusers on it.](examples/building-services.md))

```json
ops_run {"lines":["op:add duct from=(0,0) to=(20000,0) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Supply Air\""]}
```

Answer: green, op:add duct made=duct-72131ac0d3442984,system-e3b047f99252a55b changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) (from [job 3002: Draw a supply duct and a return duct side by side along a 20 m corridor, with a diffuser every 5 m on the supply and a grille every 5 m on the return.](examples/building-services.md))

```json
ops_run {"lines":["op:add duct from=(0,0) to=(20000,0) level=\"Level 1\" width=500 height=250 elevation=2700 system=\"Supply Air\""]}
```

Answer: green, op:add duct made=duct-b3c7c299af687794,system-3754e978c2b3976d changed= ms=2 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) (from [job 3003: Put an air handling unit at the end of the corridor and run its supply and return ducts down the corridor between the corridor walls.](examples/building-services.md))

```json
ops_run {"lines":["op:add duct from=(0,0) to=(9000,0) level=\"Level 1\" diameter=300 elevation=2800 system=\"Exhaust Air\""]}
```

Answer: green, op:add duct made=duct-596abffd6effbc21,system-87122f720f1484fa changed= ms=5 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) (from [job 3004: Run a 300 mm round exhaust duct 9 m from the toilet block to the exhaust fan and put the fan at the end of it.](examples/building-services.md))

```json
ops_run {"lines":["op:add duct from=(0,0) to=(12000,0) level=\"Level 1\" width=800 height=300 elevation=2700"]}
```

Answer: green, op:add duct made=duct-9655587c3e9da2a5,system-7853c180dcc4c544 changed= ms=7 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) (from [job 3005: Draw a 12 m main supply duct 800 x 300 with two 400 x 250 branches going north at 4 m and 8 m, each ending in a diffuser.](examples/building-services.md))

```json
ops_run {"lines":["op:add duct from=(0,0) to=(6000,0) level=\"Level 1\" width=800 height=300 elevation=2700"]}
```

Answer: green, op:add duct made=duct-b5ad47bd4e2d1f15,system-2226e405c5dc2ae8 changed= ms=77 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) (from [job 3006: Draw an 18 m supply duct that steps down in size every 6 m: 800 x 300, then 600 x 300, then 400 x 250.](examples/building-services.md))

```json
ops_run {"lines":["op:add duct from=(0,0) to=(8000,0) level=\"Level 1\" width=500 height=250 elevation=2700"]}
```

Answer: green, op:add duct made=duct-adc49d323603a483,system-8910af67f928d3ba changed= ms=6 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) (from [job 3007: Run a 500 x 250 supply duct 8 m east, turn it north for 5 m with an elbow, and end it with a diffuser.](examples/building-services.md))

```json
ops_run {"lines":["op:add duct from=(0,0) to=(10000,0) level=\"Level 1\" width=600 height=300 elevation=2600 system=\"Return Air\""]}
```

Answer: green, op:add duct made=duct-0d824943661efd34,system-3f156862fe9e8536 changed= ms=6 Check "Ducts +1 and Duct Systems +1": Ducts 0 -> 1 (+1, expected +1); [green] Duct Systems 0 -> 1 (+1, expected +1) (from [job 3008: Draw a 10 m return air duct 600 x 300 at 2600 mm and put three return grilles on it.](examples/building-services.md))


## op: add pipe

One line in `ops_run`: `op:add pipe key=value ...`

- Required keys: from (point), to (point), level
- Key groups: -
- Optional keys: diameter (mm), elevation (mm), system

Played lines:

```json
ops_run {"lines":["op:add pipe from=(0,0) to=(10000,0) level=\"Level 1\" diameter=100 elevation=2500 system=\"Domestic Cold Water\""]}
```

Answer: green, op:add pipe made=pipe-8f422a04b42fc66a,system-1e76fac043089b27 changed= ms=184 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) (from [job 3030: Run a 100 mm cold water main 10 m along the north wall at 2500 mm with three 25 mm branches going south at 2, 5 and 8 m.](examples/building-services.md))

```json
ops_run {"lines":["op:add pipe from=(0,0) to=(14000,0) level=\"Level 1\" diameter=50 elevation=2600 system=\"Domestic Cold Water\""]}
```

Answer: green, op:add pipe made=pipe-887cbec9dd91db66,system-ae4d87546c15fa41 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) (from [job 3031: Run a 40 mm hot water pipe and a 50 mm cold water pipe side by side down the service corridor, 300 mm apart.](examples/building-services.md))

```json
ops_run {"lines":["op:add pipe from=(0,0) to=(5000,0) level=\"Level 1\" diameter=50 elevation=2800 system=\"Vent\""]}
```

Answer: green, op:add pipe made=pipe-79a70ec6f6749ec8,system-8869c5266ab833de changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) (from [job 3034: Run a 50 mm vent pipe 5 m at 2800 mm and a 100 mm sanitary pipe 5 m beside it.](examples/building-services.md))

```json
ops_run {"lines":["op:add pipe from=(1500,0) to=(7500,0) level=\"Level 1\" diameter=50 elevation=1000 system=\"Domestic Cold Water\""]}
```

Answer: green, op:add pipe made=pipe-0522c34d7eda6f37,system-50f188c47618232f changed= ms=3 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) (from [job 3035: Place a water tank, run a 50 mm outlet pipe 6 m from it and put an isolating valve in the pipe.](examples/building-services.md))

```json
ops_run {"lines":["op:add pipe from=(0,0) to=(7000,0) level=\"Level 1\" diameter=32 elevation=800 system=\"Domestic Cold Water\""]}
```

Answer: green, op:add pipe made=pipe-7d3487f31315e4ba,system-1b134dd57f7f7523 changed= ms=5 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) (from [job 3036: Run a 32 mm cold water pipe 7 m along the wall and put four basins on the other side of it.](examples/building-services.md))

```json
ops_run {"lines":["op:add pipe from=(0,0) to=(6000,0) level=\"Level 1\" diameter=65 elevation=2500 system=\"Domestic Cold Water\""]}
```

Answer: green, op:add pipe made=pipe-4f2c7e0ddd0b2896,system-629f8bd8042eb8b6 changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) (from [job 3037: Draw a 65 mm pipe 6 m long, put a valve in it at 1.5 m and a pipe fitting at 4.5 m.](examples/building-services.md))

```json
ops_run {"lines":["op:add pipe from=(0,0) to=(8000,0) level=\"Level 1\" diameter=65 elevation=2500 system=\"Domestic Cold Water\""]}
```

Answer: green, op:add pipe made=pipe-212456be65ca8dab,system-b81b8e8a601b355c changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) (from [job 3039: Run a 65 mm cold water pipe 8 m on Level 1 and the same pipe on Level 2 above it.](examples/building-services.md))

```json
ops_run {"lines":["op:add pipe from=(0,0) to=(8000,0) level=\"Level 1\" diameter=50 elevation=2500 system=\"Domestic Cold Water\""]}
```

Answer: green, op:add pipe made=pipe-23f70a89467b4f8c,system-8d131be39d5e6f48 changed= ms=6 Check "Pipes +1 and Piping Systems +1": Pipes 0 -> 1 (+1, expected +1); [green] Piping Systems 0 -> 1 (+1, expected +1) (from [job 3041: Draw the cold water and the hot water pipes and put a pipe legend beside them.](examples/building-services.md))


## op: add terminal

One line in `ops_run`: `op:add terminal key=value ...`

- Required keys: at (point)
- Key groups: at least one of level, duct
- Optional keys: system

Played lines:

```json
ops_run {"lines":["op:add terminal at=(1500,0) level=\"Level 1\""]}
```

Answer: green, op:add terminal made=terminal-6383ab51522e593f changed=system-0e862b4bebf0e8ee ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) (from [job 3001: Run a 600 x 250 supply duct 12 m down the corridor at 2700 mm and put four diffusers on it.](examples/building-services.md))

```json
ops_run {"lines":["op:add terminal at=(2500,0) level=\"Level 1\""]}
```

Answer: green, op:add terminal made=terminal-31bd5214aee48796 changed=system-e3b047f99252a55b ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) (from [job 3002: Draw a supply duct and a return duct side by side along a 20 m corridor, with a diffuser every 5 m on the supply and a grille every 5 m on the return.](examples/building-services.md))

```json
ops_run {"lines":["op:add terminal at=(10000,0) level=\"Level 1\""]}
```

Answer: green, op:add terminal made=terminal-2964c70f496a43c6 changed=system-3754e978c2b3976d ms=2 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) (from [job 3003: Put an air handling unit at the end of the corridor and run its supply and return ducts down the corridor between the corridor walls.](examples/building-services.md))

```json
ops_run {"lines":["op:add terminal at=(4000,4500) level=\"Level 1\""]}
```

Answer: green, op:add terminal made=terminal-b28a1a2746baf46d changed=system-5772da85079e247f ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) (from [job 3005: Draw a 12 m main supply duct 800 x 300 with two 400 x 250 branches going north at 4 m and 8 m, each ending in a diffuser.](examples/building-services.md))

```json
ops_run {"lines":["op:add terminal at=(8000,4500) level=\"Level 1\""]}
```

Answer: green, op:add terminal made=terminal-ae32d8ba5daa4dde changed=system-5c04542264f91c50 ms=5 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) (from [job 3007: Run a 500 x 250 supply duct 8 m east, turn it north for 5 m with an elbow, and end it with a diffuser.](examples/building-services.md))

```json
ops_run {"lines":["op:add terminal at=(2000,0) level=\"Level 1\""]}
```

Answer: green, op:add terminal made=terminal-7d2beb4ef9e76dd4 changed=system-3f156862fe9e8536 ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) (from [job 3008: Draw a 10 m return air duct 600 x 300 at 2600 mm and put three return grilles on it.](examples/building-services.md))

```json
ops_run {"lines":["op:add terminal at=(5000,0) level=\"Level 1\""]}
```

Answer: green, op:add terminal made=terminal-f77f6130940de081 changed=system-6a831a00bbebbfd0 ms=3 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) (from [job 3010: Run a 500 x 250 supply duct along the same line on both floors, with a diffuser on each.](examples/building-services.md))

```json
ops_run {"lines":["op:add terminal at=(2000,3500) level=\"Level 1\""]}
```

Answer: green, op:add terminal made=terminal-fe79340afa84a4a3 changed=system-570f2e881f6a66ca ms=4 Check "Air Terminals +1": Air Terminals 0 -> 1 (+1, expected +1) (from [job 3011: Lay out the supply air for an office floor: a 12 m main with four branches at 2 m, 5 m, 8 m and 11 m, each ending in a diffuser.](examples/building-services.md))


## op: add equipment

One line in `ops_run`: `op:add equipment key=value ...`

- Required keys: at (point), level
- Key groups: -
- Optional keys: elevation (mm)

Played lines:

```json
ops_run {"lines":["op:add equipment at=(-1500,450) level=\"Level 1\" elevation=0"]}
```

Answer: green, op:add equipment made=equipment-371f491fe37f4d4c changed= ms=3 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) (from [job 3003: Put an air handling unit at the end of the corridor and run its supply and return ducts down the corridor between the corridor walls.](examples/building-services.md))

```json
ops_run {"lines":["op:add equipment at=(9600,0) level=\"Level 1\" elevation=2800"]}
```

Answer: green, op:add equipment made=equipment-e2bb3ef4e4eb023d changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) (from [job 3004: Run a 300 mm round exhaust duct 9 m from the toilet block to the exhaust fan and put the fan at the end of it.](examples/building-services.md))

```json
ops_run {"lines":["op:add equipment at=(6600,0) level=\"Level 1\" elevation=3000"]}
```

Answer: green, op:add equipment made=equipment-437e8084b53ebef0 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) (from [job 3009: Run a 500 x 400 kitchen exhaust duct 6 m long at 3000 mm and put the exhaust fan at its end.](examples/building-services.md))

```json
ops_run {"lines":["op:add equipment at=(2000,3000) level=\"Level 1\" elevation=0"]}
```

Answer: green, op:add equipment made=equipment-ce8ee0ee8e8f07f9 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) (from [job 3012: Draw an 8 x 6 m plant room with two air handling units in it and run a supply and a return duct out of the east side.](examples/building-services.md))

```json
ops_run {"lines":["op:add equipment at=(0,0) level=\"Level 1\" elevation=0"]}
```

Answer: green, op:add equipment made=equipment-a8840c1a233aecac changed= ms=4 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) (from [job 3021: Place an air handling unit, a fan coil unit and an exhaust fan and schedule the mechanical equipment with mark and type.](examples/building-services.md))

```json
ops_run {"lines":["op:add equipment at=(0,0) level=\"Level 2\" elevation=0"]}
```

Answer: green, op:add equipment made=equipment-f822a570822f71ff changed= ms=5 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) (from [job 3026: Set two air handling units on the roof plant deck and run a 600 x 300 exhaust duct between them.](examples/building-services.md))

```json
ops_run {"lines":["op:add equipment at=(-1500,0) level=\"Level 1\" elevation=0"]}
```

Answer: green, op:add equipment made=equipment-8aec808643e555cc changed= ms=4 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) (from [job 3027: Feed two corridors from two air handling units: each unit gets its own 500 x 250 supply duct, 10 m long, with a diffuser in the middle.](examples/building-services.md))

```json
ops_run {"lines":["op:add equipment at=(1500,2500) level=Ground elevation=0"]}
```

Answer: green, op:add equipment made=equipment-3f5b1aae06522870 changed= ms=2 Check "Mechanical Equipment +1": Mechanical Equipment 0 -> 1 (+1, expected +1) (from [job 3092: Draw a 6 x 5 m boiler room with a boiler and a pump in it and run hydronic flow and return pipes out through the east wall.](examples/building-services.md))


## op: add duct system

One line in `ops_run`: `op:add duct system key=value ...`

- Required keys: members (ids)
- Key groups: -
- Optional keys: system, name

## op: add fascia

One line in `ops_run`: `op:add fascia key=value ...`

- Required keys: roof, edges (edges)
- Key groups: -
- Optional keys: height (mm), thickness (mm)

## op: add gutter

One line in `ops_run`: `op:add gutter key=value ...`

- Required keys: roof, edges (edges)
- Key groups: -
- Optional keys: height (mm), thickness (mm)

## op: add text

One line in `ops_run`: `op:add text key=value ...`

- Required keys: at (point), view, text
- Key groups: -
- Optional keys: type, leader_to (point), width (mm)

Played lines:

```json
ops_run {"lines":["op:add text at=(1000,3000) view=\"Dimension Plan\" text=\"OFFICE 60 m2\""]}
```

Answer: green, op:add text made=text-18fbaa3829ff4148 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) (from [job 2056: Dimension the 10 x 6 m office on a plan of its own: the south wall, the west wall and the east wall, with a note.](examples/architecture.md))

```json
ops_run {"lines":["op:add text at=(0,-10) view=\"General Notes\" text=\"1. All dimensions are in millimetres.\""]}
```

Answer: green, op:add text made=text-26e5dd4b5a824f81 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) (from [job 4006: Write the general notes for the job as a drawing and put them on a sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add text at=(170,-100) view=\"Eaves Block Detail\" text=\"150 x 200 treated pine\""]}
```

Answer: green, op:add text made=text-0a4f5809445b4a75 changed= ms=4 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) (from [job 4038: Draw a 150 by 200 mm timber eaves block with a note as a 1:5 detail and put it on a detail sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add text at=(0,-10) view=\"Cover Notes\" text=\"1. Refer to the specification for finishes.\""]}
```

Answer: green, op:add text made=text-80c2e24ab09941a3 changed= ms=6 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) (from [job 4075: Put a symbols legend and the general notes together on one cover sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add text at=(450,-400) view=\"Timber Eaves Detail\" text=\"140 x 45 STUD FRAME\" leader_to=(140,-450)"]}
```

Answer: green, op:add text made=text-173b7466327e4cca changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) (from [job 5001: Draw a 1:10 eaves detail for our timber frame wall: stud frame, rafter, batt insulation, plasterboard, notes and a dimension.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add text at=(1000,500) view=\"Strip Footing Detail\" text=\"100 CONCRETE SLAB ON DPM\" leader_to=(900,100)"]}
```

Answer: green, op:add text made=text-fe1f0bf9f5f642b2 changed= ms=3 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) (from [job 5002: I need a 1:20 strip footing detail under a brick wall with a ground slab, DPM, gravel and the footing dimensions.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add text at=(500,300) view=\"Column Base Plate Detail\" text=\"400 x 400 x 20 BASE PLATE\" leader_to=(400,10)"]}
```

Answer: green, op:add text made=text-9c2a471c3d3b494f changed= ms=2 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) (from [job 5003: Detail a steel column base plate on a pad at 1:10 with the grout, two anchor bolts and the plate size noted.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add text at=(900,500) view=\"Duct Hanger Detail\" text=\"M10 GALV. THREADED ROD\" leader_to=(630,500)"]}
```

Answer: green, op:add text made=text-539df8a617cc4f37 changed= ms=2 Check "Text Notes +1": Text Notes 0 -> 1 (+1, expected +1) (from [job 5004: Draw the 1:10 hanger detail for our rectangular ducts: the duct, two threaded rods, the angle bearer and a note on the rod size.](examples/annotation-details-and-materials.md))


## op: add dimension

One line in `ops_run`: `op:add dimension key=value ...`

- Required keys: from (point), to (point), view
- Key groups: -
- Optional keys: offset (mm)

Played lines:

```json
ops_run {"lines":["op:add dimension from=(0,0) to=(10000,0) view=\"Dimension Plan\" offset=-900"]}
```

Answer: green, op:add dimension made=dim-63adc935458f4042 changed= ms=152 note=offset -900: the dimension line stands 900 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) (from [job 2056: Dimension the 10 x 6 m office on a plan of its own: the south wall, the west wall and the east wall, with a note.](examples/architecture.md))

```json
ops_run {"lines":["op:add dimension chain points=(0,-1000) (5000,-1000) (10000,-1000) view=48660e38a721430d899d5d8a96df3bec offset=-1500"]}
```

Answer: green, op:add dimension chain made=dimstr-f6fbc177889c427a changed= ms=2023 note=segments 5000, 5000; offset -1500: the dimension line stands 1500 mm to the right of the direction from the first point to the last (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) (from [job 2065: Set out grid lines A, B and C at 5 m centres with grids 1 and 2 across them and dimension the three lines as a string.](examples/architecture.md))

```json
ops_run {"lines":["op:add dimension chain points=(0,-1000) (8000,-1000) (16000,-1000) view=48660e38a721430d899d5d8a96df3bec offset=-3000"]}
```

Answer: green, op:add dimension chain made=dimstr-70f0f74cff3e4641 changed= ms=60 note=segments 8000, 8000; offset -3000: the dimension line stands 3000 mm to the right of the direction from the first point to the last (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) (from [job 4060: Dimension grids A to C across the Ground plan and put a north arrow on it.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add dimension from=(0,0) to=(300,0) view=\"Wall Detail\" offset=100"]}
```

Answer: green, op:add dimension made=dim-99e0bb52b6c14f86 changed= ms=90 note=offset 100: the dimension line stands 100 mm to the left of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) (from [job 4061: Draw a 1:10 wall detail with a 300 mm outline, a brick region, a 90 mm insulation batt and a width dimension, and put it on a sheet.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add dimension from=(0,-900) to=(140,-900) view=\"Timber Eaves Detail\" offset=-150"]}
```

Answer: green, op:add dimension made=dim-c7cd316f484d4faf changed= ms=149 note=offset -150: the dimension line stands 150 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) (from [job 5001: Draw a 1:10 eaves detail for our timber frame wall: stud frame, rafter, batt insulation, plasterboard, notes and a dimension.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add dimension from=(0,-300) to=(600,-300) view=\"Strip Footing Detail\" offset=-200"]}
```

Answer: green, op:add dimension made=dim-532b46e6a4f24eac changed= ms=39 note=offset -200: the dimension line stands 200 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) (from [job 5002: I need a 1:20 strip footing detail under a brick wall with a ground slab, DPM, gravel and the footing dimensions.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add dimension from=(0,0) to=(400,0) view=\"Column Base Plate Detail\" offset=-400"]}
```

Answer: green, op:add dimension made=dim-322ff8ea40284a18 changed= ms=632 note=offset -400: the dimension line stands 400 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) (from [job 5003: Detail a steel column base plate on a pad at 1:10 with the grout, two anchor bolts and the plate size noted.](examples/annotation-details-and-materials.md))

```json
ops_run {"lines":["op:add dimension from=(0,0) to=(600,0) view=\"Duct Hanger Detail\" offset=-250"]}
```

Answer: green, op:add dimension made=dim-595b58abffa84750 changed= ms=11 note=offset -250: the dimension line stands 250 mm to the right of the measured line, from the first reference (from=) to the second (to=) (positive is left, negative is right) Check "Dimensions +1": Dimensions 0 -> 1 (+1, expected +1) (from [job 5004: Draw the 1:10 hanger detail for our rectangular ducts: the duct, two threaded rods, the angle bearer and a note on the rod size.](examples/annotation-details-and-materials.md))


## op: add dimension chain

One line in `ops_run`: `op:add dimension chain key=value ...`

- Required keys: points (points), view, offset (mm)
- Key groups: -
- Optional keys: -

## op: add tag

One line in `ops_run`: `op:add tag key=value ...`

- Required keys: id, view
- Key groups: -
- Optional keys: leader (yesno)

## op: add symbol

One line in `ops_run`: `op:add symbol key=value ...`

- Required keys: at (point), view
- Key groups: -
- Optional keys: symbol, rotation (degrees)

Played lines:

```json
ops_run {"lines":["op:add symbol at=(-3000,7000) view=48660e38a721430d899d5d8a96df3bec"]}
```

Answer: green, op:add symbol made=symbol-6b87884ca2514765 changed= ms=8 Check "Symbol +1": Symbol 0 -> 1 (+1, expected +1) (from [job 4060: Dimension grids A to C across the Ground plan and put a north arrow on it.](examples/views-sheets-and-schedules.md))

```json
ops_run {"lines":["op:add symbol at=(15000,3000) view=48660e38a721430d899d5d8a96df3bec rotation=15"]}
```

Answer: green, op:add symbol made=symbol-8f2841a01fca4c0e changed= ms=4 Check "Symbol +1": Symbol 2 -> 3 (+1, expected +1) (from [job 5017: Put a north arrow and a scale bar beside the building on the Ground plan.](examples/annotation-details-and-materials.md))


## op: place block

One line in `ops_run`: `op:place block key=value ...`

- Required keys: family, at (point)
- Key groups: -
- Optional keys: type, level, rotation (degrees), host

## op: copy

One line in `ops_run`: `op:copy key=value ...`

- Required keys: id (ids), by (vector)
- Key groups: -
- Optional keys: -

Played lines:

```json
ops_run {"lines":["op:copy id=\"Level 2\" by=(0,0,3400)"]}
```

Answer: green, op:copy made="level-Level 3" changed= ms=14 note=Level 3 placed at 6800 mm; Floor Plan made Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1005: Copy Level 2 up three times at 3.4 m to make the typical floors of a tower.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:copy id=grid-A by=(6000,0,0)"]}
```

Answer: green, op:copy made=grid-A-2e0803fadd9865a2 changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) (from [job 1017: Extend the grid east by copying gridline A six metres and then twelve metres.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:copy id=\"Level 2\" by=(0,0,3800)"]}
```

Answer: green, op:copy made="level-Level 3" changed= ms=22 note=Level 3 placed at 7600 mm; Floor Plan made Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1048: Build a five-storey steel frame at 3.8 m storeys by copying Level 2 up, then run four corner columns to the top.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:copy id=\"Level 2\" by=(0,0,4200)"]}
```

Answer: green, op:copy made="level-Level 3" changed= ms=11 note=Level 3 placed at 8400 mm; Floor Plan made Check "Levels +1": Levels 2 -> 3 (+1, expected +1) (from [job 1062: Copy Level 2 up 4.2 m for the hospital's plant floor, call the copy Plant Floor and run a column up to it.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:copy id=level-Mezzanine by=(0,0,3000)"]}
```

Answer: green, op:copy made="level-Level 2" changed= ms=8 note=Level 2 placed at 4500 mm; Floor Plan made Check "Levels +1": Levels 4 -> 5 (+1, expected +1) (from [job 6023: Add a mezzanine level at 1500, copy it up 3 m for the plant deck, then undo the copy.](examples/change-modify-and-freeform.md))

```json
ops_run {"lines":["op:copy id=grid-A by=(8000,0,0)"]}
```

Answer: green, op:copy made=grid-A-ca404e1d07fe4b14 changed= ms=4 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) (from [job 6026: Move grid A 500 mm east, copy it 8 m for the second line, rename the original to Z, then delete it and take the delete back.](examples/change-modify-and-freeform.md))


## op: rotate

One line in `ops_run`: `op:rotate key=value ...`

- Required keys: id (ids), about (point), angle (degrees)
- Key groups: -
- Optional keys: copy (yesno)

Played lines:

```json
ops_run {"lines":["op:rotate id=grid-A,grid-B,grid-1,grid-2 about=(0,0) angle=30"]}
```

Answer: green, op:rotate made= changed=grid-A,grid-B,grid-1,grid-2 ms=54 Check "moved": 4 element(s) moved: grid-1  -> ; grid-2  -> ; grid-A  -> (from [job 1012: The building sits skew to the boundary: set out a 7.5 x 6 m grid and swing the whole grid 30 degrees, then put columns on the crossings.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:rotate id=grid-R about=(0,0) angle=15 copy=yes"]}
```

Answer: green, op:rotate made=grid-R-5764f6aed80a7f47 changed= ms=8 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) (from [job 1019: Set out a radial grid for a circular tank farm: one line 20 m long, copied round the centre every 15 degrees to 60 degrees.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:rotate id=grid-B about=(6000,0) angle=5"]}
```

Answer: green, op:rotate made= changed=grid-B ms=5 Check "moved": 1 element(s) moved: grid-B  -> (from [job 1051: Fit the grid to an angled boundary: pull gridline A 400 mm west and swing gridline B 5 degrees about its foot.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:rotate id=grid-A about=(0,0) angle=45 copy=yes"]}
```

Answer: green, op:rotate made=grid-A-57fe1877ad052be8 changed= ms=40 Check "Grids +1": Grids 1 -> 2 (+1, expected +1) (from [job 1063: Two grid lines cross at 45 degrees on a corner site: draw one, copy it round 45 degrees and put a column where they cross.](examples/setting-out-and-structure.md))


## op: mirror

One line in `ops_run`: `op:mirror key=value ...`

- Required keys: id (ids), axis (pair)
- Key groups: -
- Optional keys: copy (yesno)

Played lines:

```json
ops_run {"lines":["op:mirror id=grid-A,grid-B axis=(12000,-2000) (12000,12000) copy=yes"]}
```

Answer: green, op:mirror made=grid-A-284865f099432cdc,grid-B-f0c20987777683f4 changed= ms=12 Check "Grids +2": Grids 2 -> 4 (+2, expected +2) (from [job 1018: The building is symmetrical about a centre line at 12 m: draw the west half of the grid, mirror it east and add the centre line.](examples/setting-out-and-structure.md))


## op: array

One line in `ops_run`: `op:array key=value ...`

- Required keys: id (ids), count (count)
- Key groups: exactly one of step (vector), about (point); all or none of about (point), angle (degrees)
- Optional keys: group (yesno)

Played lines:

```json
ops_run {"lines":["op:array id=grid-A count=3 step=(8000,0,0)"]}
```

Answer: green, op:array made=grid-A-a6fd9408f2f65bb9,grid-A-f5d2c9bf05a2cc50 changed= ms=4 Check "Grids +2": Grids 1 -> 3 (+2, expected +2) (from [job 1011: Set out a square column grid, three bays each way at 8 m, lettered across and numbered up, with a column at every crossing.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:array id=grid-1 count=5 step=(0,7500,0)"]}
```

Answer: green, op:array made=grid-1-b50b0834ed2f6011,grid-1-08ac5858ccc883dd,grid-1-549cd847e32ffdf3,grid-1-42fb313282b51b31 changed= ms=6 Check "Grids +4": Grids 3 -> 7 (+4, expected +4) (from [job 1037: Set out a portal-frame shed: five frames 7.5 m apart, 24 m span, columns at every frame and an eaves beam down each side.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:array id=grid-A count=7 step=(9000,0,0)"]}
```

Answer: green, op:array made=grid-A-03ba2dac1b8d5bb6,grid-A-22c4cc55bfe71326,grid-A-24d9cce585c464a7,grid-A-cb7a0c9d1b925ba7,grid-A-c030f2dba61d5ded,grid-A-22991361b3e5e9ac changed= ms=6 Check "Grids +6": Grids 1 -> 7 (+6, expected +6) (from [job 1042: Set out the column grid for a warehouse: six 9 m bays along its length, three 10 m bays across, a column at every crossing.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:array id=grid-A count=5 step=(8100,0,0)"]}
```

Answer: green, op:array made=grid-A-f7f90ab9add271f3,grid-A-096de265b2b858b3,grid-A-4e37bac410c2d577,grid-A-f29a79cc0efcc183 changed= ms=7 Check "Grids +4": Grids 1 -> 5 (+4, expected +4) (from [job 1043: Lay out the column grid of a car-park deck: four bays of 8.1 m and two rows of columns 16.2 m apart.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:array id=grid-A count=4 step=(8100,0,0)"]}
```

Answer: green, op:array made=grid-A-ac4ca5edd054202d,grid-A-08130d38c71e86f9,grid-A-f7837e7ccaf688ac changed= ms=8 Check "Grids +3": Grids 1 -> 4 (+3, expected +3) (from [job 1044: Add a basement car park 3.2 m down and put its columns on a 8.1 x 16.2 m grid, up to the ground floor.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:array id=grid-A count=3 step=(7500,0,0)"]}
```

Answer: green, op:array made=grid-A-5b380abe4fe66b5f,grid-A-d73a505e8c27e0a4 changed= ms=7 Check "Grids +2": Grids 1 -> 3 (+2, expected +2) (from [job 1045: Set out a mezzanine at 3 m on its own grid, three lines 7.5 m apart by two lines 6 m apart, with a beam along each grid line.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:array id=grid-A count=4 step=(8100,0,0)"]}
```

Answer: green, op:array made=grid-A-47d0153e35935f79,grid-A-564e8786db9a0457,grid-A-d236d27db0d655d2 changed= ms=7 Check "Grids +3": Grids 1 -> 4 (+3, expected +3) (from [job 1047: Stack the columns of a two-deck car park: decks at 2.9 m and 5.8 m, eight columns on each deck, on a 8.1 x 16.2 m grid.](examples/setting-out-and-structure.md))

```json
ops_run {"lines":["op:array id=grid-A count=3 step=(6000,0,0)"]}
```

Answer: green, op:array made=grid-A-db975bb695c99021,grid-A-6ffa0c915a288036 changed= ms=6 Check "Grids +2": Grids 1 -> 3 (+2, expected +2) (from [job 1053: Put a 3 x 2 grid at 6 m on the house plan and a column at every crossing on the ground floor.](examples/setting-out-and-structure.md))

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
