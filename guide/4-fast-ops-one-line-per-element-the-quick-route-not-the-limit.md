# 4. Fast ops: one line per element (the quick route, not the limit)


In this part: every op kind with its keys. Pieces: the call and its answer; value forms; levels, grids, walls, floors, ceilings, rooms, shafts; roofs, stairs, railings, fascias, gutters; columns, beams, braces; doors, windows, blocks; services; views and sections; sheets, schedules, printing; annotation; materials and types; change, move, copy, array, delete; facts met in play. Ops are the quick route. A thing with no op line is reached with `commands_run` or a ribbon step (part 5, Commands, steps and dialogs) after a look-up in part 2 (Find any control).

An op line is `op:<verb> <kind> key=value ...`. `ops_run` takes up to 500 lines as ONE Undo step; on a large model send 25 to 35. Units are mm and degrees; points are model x, y. A wrong kind is answered with the list of the kinds. A real call and its answer:

    ops_run {"name":"play: material on forms","lines":["op:set id=0da7758bd7bcd48999b9b0359b180785 key=Material value=\"Play White\"","op:set id=3e554d07689842945392daad3f37a354 key=Material value=\"Play White\""]}
    {"results":[{"changed":["0da7758bd7bcd48999b9b0359b180785"],"line":1,"ok":true,"rows":1,"state":"changed"},{"changed":["3e554d07689842945392daad3f37a354"],"line":2,"ok":true,"rows":1,"state":"changed"}],"undo":"Add-in: play: material on forms"}

Look it up:

    commands_list {"name":"Freeform Curve"}

## The ops_run call, its answer, batches and Undo

Every line starts with `op:`.

Five lines and the whole answer:

    ops_run {"name":"play: materials 2","lines":["op:add material library=copper name=\"Play Copper\"","op:add material library=zinc_cladding name=\"Play Zinc\"","op:set id=3e554d07689842945392daad3f37a354 key=Material value=\"Play Copper\"","op:set id=3f9108493f1e01717395b83138b70760 key=Material value=\"Play Zinc\"","op:add floor boundary=(-6000,-18000)(30000,-18000)(30000,14000)(-6000,14000) level=\"Ground\""]}
    {"results":[{"line":1,"made":["Play Copper"],"ok":true,"rows":3,"state":"changed"},{"line":2,"made":["Play Zinc"],"ok":true,"rows":3,"state":"changed"},{"changed":["3e554d07689842945392daad3f37a354"],"line":3,"ok":true,"rows":1,"state":"changed"},{"changed":["3f9108493f1e01717395b83138b70760"],"line":4,"ok":true,"rows":1,"state":"changed"},{"line":5,"made":["floor-4083a1d163c3bee6"],"ok":true,"rows":2,"state":"changed"}],"undo":"Add-in: play: materials 2"}

Read each result:
- Its reply is `ops.run` in the reference. A material's id is its name. A `delete` answers the id it removed in `changed`.

A refused line does not stop the lines after it. Line 1 of a four-line call answered `{"line":1,"ok":false,"state":"refused","words":"cannot proceed: the library holds no texture set named 'zinc_standing_seam'; nothing was written"}` and lines 2 to 4 were written.

A wrong word on purpose lists what exists: a refusal names its fix and the valid words (types, parameters, views, card kinds).

A wrong kind lists the kinds. `op:add gable at=(0,0)` answered:

    cannot proceed: 'gable' is not a kind of add (add column, add grid, add level, add beam, add brace, add wall, add floor, add roof, add ceiling, add material, add room, add shaft, add stair, add railing, add door, add window, add detail line, add filled region, add insulation, add view, add section, add elevation, add drafting view, add legend, add schedule, add 3d view, add sheet, place view, print sheets, set, set material, set view, set element graphics, delete, delete sheet, remove view, move, add duct, add pipe, add terminal, add equipment, add duct system, add fascia, add gutter, add text, add dimension, add dimension chain, add tag, add symbol, place block, copy, rotate, mirror, array)

Batches:
- On a large model send 25 to 35 lines a call.
- A row of identical members is one `array` line (piece "Change, move, copy, mirror, array and delete").
- One drawing call at a time. `another AI chat's drawing call is still running in UNION; retry in a moment` is not a failure: send the call again.
- Every write rebuilds the 3D view. Write with a plan view in front (`view_activate` a floor plan); part 6 (See your work) shows the 3D view once.

Ids in angle brackets come from the `made` of an earlier line.

## Value forms: point, points, polygon, pair, heading, slope, vector, count, ids and the rest

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
| edges | roof edge numbers from 0 separated by commas: one or more | `0,1` |
| plankind | plan, structural or ceiling; sections, elevations, drafting views and 3D views are made by add section, add elevation, add drafting view and add 3d view | `plan` |
| facing | north, east, south or west | `north` |

Rules of writing:
- Separate the points of a list with a space or a comma; a space inside a point's brackets is allowed. Points written touching, `(-6000,-18000)(30000,-18000)(30000,14000)`, were read as a list too.
- A one-point key (`at`, `from`, `to`) takes one point. A second bare point after it is refused: `cannot proceed: 'column (1,1)' is not a kind of add (add column, add grid, ...)`.
- `level` is a level's name (`Ground`). `view` is a view's name or id from `views_list`. Give the id: where a floor plan and a ceiling plan share a name (`Ground`), an op's `view=` takes the floor plan (piece "Views, sections, elevations and 3D views").

## Levels, grids, walls, floors, ceilings, rooms and shafts

Every example uses the Architectural template's names (levels Ground at 0, Level 1 at 3000, Roof at 6000; a name that exists is refused).

`add level`: needs elevation (mm). May take name.
Example:

    op:add level elevation=3000 name="Level 2"

- Move or rename a template level with `set`: `op:set id="level-Level 1" key=Elevation value=3600`, then `op:set id=level-Roof key=Elevation value=7200` and `op:set id=level-Roof key=Name value="Level 2"`. The id stays `level-Roof` after the rename. `levels_list` reads levels back.
- A level made by `op:add level` gets its plan view from `add view` (piece "Views, sections, elevations and 3D views").
- The landscape pad stands at the lowest level whose name is like "Ground". Name the lowest site level so, or lower parts are buried.

`add grid`: needs from (point), to (point). May take name.
Example:

    op:add grid from=(0,-2000) to=(0,12000) name=A

A grid named with digits plays as `name=1` or `name="1"`. `grids_list` reads grids back.

`add wall`: needs from (point), to (point), level. May take type, height (mm), top, line.
Example:

    op:add wall from=(0,0) to=(8000,0) level=Ground

- One line is one wall: four walls are four lines. `made` is the wall's id.
- The top is `top` (a level name) or `height` (mm); both together are refused: `cannot proceed: add wall takes top= (a level) or height= (mm), not both`.
- `height` is the wall's own height in mm, measured from its level. A wall on Level 1 with `height=2700` starts at 3000: `op:add wall from=(50000,0) to=(56000,0) level="Level 1" height=2700` made a wall whose line reads z = 3000.
- Height and Base Offset order: piece "Facts met in play". Curtain walls and glass: piece "Materials and types".
- A curved wall is the `Wall: Architectural` tool (step `ribbon:Architecture:Wall`) with `Draw=Start-End-Radius Arc` set on the options strip inside the ribbon step that presses it; three picks: start, end, a point on the arc. Part 14 (Recipes) recipe (t).

`add floor`: needs boundary (points), level. May take type.
Example:

    op:add floor boundary=(-6000,-18000)(30000,-18000)(30000,14000)(-6000,14000) level="Ground"

- `boundary` closes itself: do not repeat the first point.
- With no `type` the floor is "Generic 300mm", 300 mm thick. Read a type's thickness from `types_list {"category":"Floors"}`: its `layers` give each layer in mm. "Concrete Slab 200 + Tile" is Ceramic 10 over Concrete 200:

        op:add floor boundary=(0,0) (8400,0) (8400,8400) (0,8400) level="Level 1" type="Concrete Slab 200 + Tile"

`add ceiling`: needs level. Exactly one of at (point), boundary (polygon). May take height (mm), type.
Example:

    op:add ceiling boundary=(0,0) (8000,0) (8000,6000) (0,6000) level="Level 1" height=2500

- `boundary` needs no walls; an outline that already holds a ceiling is refused. `height` is mm above the level; `type` a Ceilings type name. Left out, the tool's starting values stand.
- `at` works inside four walls on `level` or over a Room. A point in no walls is refused in the tool's words: `cannot proceed: no room at this point of Ground and no closed walls round it`.

`add room`: needs at (point), level. May take name, number.

`add shaft`: needs boundary (pair), level. May take top.

## Roofs, stairs, railings, fascias and gutters

`add roof`: needs boundary (polygon), level. May take type, slope (slope).
Examples:

    op:add roof boundary=(0,0) (8000,0) (8000,6000) (0,6000) level="Level 1" slope=45
    op:add roof boundary=(20000,0) (28400,0) (28400,8400) (20000,8400) level="Level 2" slope=0

- `boundary` closes itself. `type` is a Roofs type name. With no `slope` the roof is a hip of 30 degrees (Form Hip, Slope 30). `slope` sets every edge. `slope=0` makes a flat roof (Form Flat, Slope 0). `made` is the roof's id.
- Write the slope in the add line.
- The `Roof` tool (tab Architecture, panel Build; prompt "Sketch the roof footprint"; options Offset, Radius, Overhang, Defines Slope, Extend to wall core, Sides; draw modes include Pick Walls, Pick Lines, Circle, Spline) drew a roof from a closed footprint, the first point repeated to close it. It answered `Roof: 5 point(s)`:

        commands_run {"name":"Roof","points":[[30000,20000],[38000,20000],[38000,25000],[30000,25000],[30000,20000]],"finish":true}

- A gable roof is played with the Roof tool in Pick Walls mode, with `Defines Slope` set to no on the two gable-end walls. The draw mode and its options are set on the options strip inside the ribbon step that presses the tool. The first step line of the play, in a `steps_run` call:

        ribbon:Architecture:Roof · picks (34000,20000) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=400 · expect —

  The whole call is in part 14 (Recipes) recipe (s). A draw mode set in `commands_run` is refused: `cannot proceed: Roof has no option Draw Mode; nothing was written`.
- The gable roof was made at its level. Lift a pitched roof by the wall height less overhang x tan(slope), because its base is the eave edge, out at the overhang: with Overhang 400 and Slope 35 that is 280 mm, about 2420 on 2700 walls. Base Offset 2700 stood about 280 mm above the wall tops; Base Offset 2500 sat on the walls with no gap seen. The played call lifted by the full 2700 (send less to sit on the walls); `element_get` read Base Offset 2700 and Slope 35:

        ops_run {"name":"lift roof","lines":["op:move id=<roof id> by=(0,0,2700)","op:set id=<roof id> key=Slope value=35"]}

- The dormer opening is the sketch tool `Roof Cut-out` (tab Structural, panel Opening; ribbon button Dormer, step `ribbon:Architecture:Dormer`); `commands_list {"name":"Dormer"}` answered it.
- Lofts, sweeps and revolves make freeform surfaces: part 9 (Forms, freeform curves and surfaces).

`add stair`: needs from (point), to (heading), level, top. May take type, width (mm).
Example:

    op:add stair from=(0,0) to=(6000,0) level=Ground top="Level 1" width=1200

- `from` is the start of the run, `to` the point it heads toward, not its end. `top` is the level it reaches; `type` a Stairs type name. The answer's note names the end, `the run ends at its last riser (x,y)`: read it, the run follows its risers.
- The spiral stair takes two points, the centre and then where it starts. Its call is in part 3 (The map), piece "Walls, floors, ceilings, stairs, ramps...".

`add railing`: needs nothing by itself. Exactly one of points (points), host (ids). All or none of points (points), level. May take type, level, points (points), host (ids).
Examples:

    op:add railing points=(0,5000) (6000,5000) (6000,8000) level=Ground
    op:add railing host=<stair id>

- `points` is a path of two points or more with `level`. `host` is one stair id from an `add stair` answer, with no `level`: `cannot proceed: add railing host= takes no level=: the railing follows the stair`. `made` holds the railings' ids (a stair answered two, one a side).

`add fascia`: needs roof, edges (edges). May take height (mm), thickness (mm).

`add gutter`: needs roof, edges (edges). May take height (mm), thickness (mm).

## Columns, beams, braces and structure

`add column`: needs at (point), level. May take top, type.
Example:

    op:add column at=(0,0) level=Ground type=310UC158

`top` is a level name; left out, the column stands up to the next level above. `type` is a type's name from `types_list`. The rows `Base Offset` and `Top Offset` are written after the add with `op:set`.

`add beam`: needs from (point), to (point), level. May take type, usage.
Example:

    op:add beam from=(0,0) to=(8000,0) level=Ground type=530UB82.0

`add brace`: needs from (point), to (point), level. May take top, start_offset (mm), end_offset (mm), type, usage.

- Many braces at many heights: the ALBATROSS card `Brace between Points` (part 10, ALBATROSS: cards through the door).

A height that is not a storey. A member between levels keeps its level and takes an offset from it; do not add a level for each height. Read the kind's rows with `element_get` before you add a level.
- Beam: `add beam` takes no height. Set `Start Level Offset` and `End Level Offset` (mm above the level, negative below, both 0 when added; unequal ones make a sloped beam) after the add; one line sets a whole row of beams:

        op:set id=<beam> key="Start Level Offset" value=1200
        op:set id=<beam> key="End Level Offset" value=1200

- A beam's top face stands on its level plus that end's offset, and the section hangs below it (`z Justification` is Top by default; its words are Top, Center, Origin, Bottom). A 610UB125 beam (612 deep) at Level 1 (3000) read Bottom 2388 and Top 3000; after both offsets were set to -1295 it read Bottom 1093 and Top 1705.

## Doors, windows and blocks: add door, add window, place block

Part 8 (Blocks) holds the block library, colour and texture. These are the lines.

`add door`: needs wall. Exactly one of at (point), offset (mm). May take sill (mm), type, flip (yesno), hand (yesno).
`add window`: needs wall. Exactly one of at (point), offset (mm). May take sill (mm), type, flip (yesno), hand (yesno).
Examples:

    op:add door wall=<south wall id> at=(2000,0)
    op:add window wall=<north wall id> at=(5000,6000)

- `wall` is the host wall's id, from the `made` of a wall line. `at` is a point near the wall's line; `offset` is mm (0 or more) from the wall's start to the centre of the opening. `sill` is mm, 0 or more. `type` is a Doors or Windows type the model holds. A door adds an Opening, so Doors +1 reads Openings +1.
- A door or window placed with `op:add door` or `op:add window` cuts its opening. `hand=yes` was written to put the hinge at the wall's end and `flip=yes` to swing the leaf the other way.
- Read back where it stands: `element_get {"id":"<id>"}` answers `host` (the wall) and `location` `{"point":[x,y]}`.

`place block`: needs family, at (point). May take type, level, rotation (degrees), host.
Example:

    op:place block family="Circular Hollow Section - Hot-Finished" type=323.9x10CHS at=(0,-20000) level=Ground

- `family` is a Block Database block name (`library_list {"category":"<category>"}` lists them); it loads into the model when it is not there. `library_list` needs a category; `library_list {"category":"Furniture","limit":5}` answered `{"category":"Furniture","count":5,"more":true,"names":["Armchair","Banquette Booth","Bar Stool","Bed - Bunk","Bed - Double"],"next":5,"total":204}`, and `library_list {}` answered `library.list needs a category`. A ceiling-hung block needs `host=<ceiling id>`. A block's category must be one of UNION's categories, or placing answers "load it first". A family in a model holds only the types that were placed.
- One texture for the whole block: `op:set id=<id,id,...> key=Material value="<file material>"` (piece "Materials and types"). An instance parameter (a Length on a skirting run) is written after placing with `op:set id= key= value=`.

## Services: add duct, add pipe, add terminal, add equipment, add duct system

`add duct`: needs from (point), to (point), level. May take width (mm), height (mm), diameter (mm), elevation (mm), system.

`add pipe`: needs from (point), to (point), level. May take diameter (mm), elevation (mm), system.

`add terminal`: needs at (point). At least one of level, duct. May take system.

`add equipment`: needs at (point), level. May take elevation (mm).

`add duct system`: needs members (ids). May take system, name.

## Views, sections, elevations and 3D views: add view, add section, add elevation, add drafting view, add legend, set view

Use names the model does not hold (`N Elevation`, `Cut A`) and keep the `made` id. A name a view already holds is refused, yet the line stays green and the new view keeps UNION's own name: read `words` for `was made but its name was refused`.

`add view`: needs kind (plankind), level. May take name.
Example:

    op:add view kind=plan level="Level 8" name="Level 8 Plan"

`kind` is plan, structural or ceiling; `level` is required (a level that does not exist is refused naming it). Another kind is refused: `kind= wants plan, structural or ceiling; sections, elevations, drafting views and 3D views are made by add section, add elevation, add drafting view and add 3d view`. `made` is the view's id.

`add section`: needs from (point), to (point), view. May take depth (mm), name.
Example, the plan named by its id:

    op:add section from=(50000,-2000) to=(56000,-2000) depth=8000 name="Probe Section" view=48660e38a721430d899d5d8a96df3bec

`view` is the plan the cut is made in: a view's name or its id from `views_list`. Where a floor plan and a ceiling plan share the name, as `Ground` does in the Architectural template, the op takes the floor plan; give the id to be exact. In the Architectural template the Ground floor plan's id is `48660e38a721430d899d5d8a96df3bec`. `depth` is the far clip in mm; a depth left out, or 0 or less, gives the default (a note says so). `made` is the section view's id.

`add elevation`: needs at (point), facing (facing), view. May take name.
Example, the plan named by its id:

    op:add elevation at=(53000,-6000) facing=north name="Probe Elevation" view=48660e38a721430d899d5d8a96df3bec

`view` takes a name or an id, as for `add section`. `at` is the marker's point on the plan `view`. The marker stands outside the face and faces the building: a marker north of it facing south is the north elevation. A marker placed over another is moved clear and a note gives where it stands. A view that is not a plan is refused in the tool's words.

`add drafting view`: needs nothing. May take name, scale.
Example:

    op:add drafting view name="Roof Junction" scale=1:10

With no name or scale the New Drafting View dialog's own stand; one it refuses is a red line.

`add legend`: needs nothing. May take name, scale.

`add 3d view`: needs nothing. May take name.
Example:

    op:add 3d view

The templates hold one 3D View, so nothing is written, `made` is empty and the note names the view; the line is green. Look with `view_activate {"view":"{3D}"}` (part 6, See your work). The 3D view is named `{3D}` in `view_activate`; its id is `view-3d` (`element_get`, `op:set`).

`set view`: needs view. At least one of hide, show, map.
Level and grid lines in a live 3D view are hidden with `hide=Levels,Grids`; the black lines labelled Roof, Level 1 and Ground were gone from the picture:

    ops_run {"name":"hide level lines in 3D","lines":["op:set view view=view-3d hide=Levels,Grids"]}

More examples:

    op:set view view=view-3d hide=Levels,Grids map=plain:lightgrey
    op:set view view="Level 8 Plan" show=Grids

- `hide` and `show` take category names. A category hide takes whole categories (`hide="Structural Framing,Structural Columns"` hid every mark and every beam). A name that is no category is refused: `no category named Braces in the Visibility/Graphics`. A view filter hides one kind of member: steps, part 5 (Commands, steps and dialogs).
- Scale and detail are rows of the view, written with `set`: `op:set id=<view id> key=Scale value=1:200` and `op:set id=<view id> key="Detail Level" value=Coarse`. If `op:set` of a view answers `no such row`, press the Attributes palette instead (`dock:Properties`, part 5).
- A view's own rows are read with `element_get {"id":"view-3d"}`; `op:set id=view-3d key="Section Box" value=no` writes one, where `param_set` refuses a view.
- Commands for views no op line reaches: `views-autosections`.

## Sheets, viewports, schedules and printing: add sheet, place view, add schedule, print sheets

Order that played: finish the model; make views and set their scale; put the annotation on each view (`view_activate` it first); then make sheets and place the views. Annotating after placing also played. The whole drawing set as a recipe: part 14 (Recipes).

`add sheet`: needs nothing. May take number, name, titleblock.
Example:

    op:add sheet number=A104 name="Level 8 Plan" titleblock=A1

`titleblock` is A0 to A4, ANSI_B to ANSI_E, ARCH_C to ARCH_E1 or None. A number that exists is refused: the Architectural template holds sheets A000, A100 to A103, A201, A301, A501, and the schedules Door Schedule, Window Schedule and Room Schedule on sheet A501 (columns of the Door Schedule: Mark, Level, Family (heading Block), Type, Width, Height, Fire Rating). Give a new schedule a name the template does not hold. The title block prints the project name from Project Information, a dialog (part 5).

`place view`: needs view, sheet. May take at (sheetpoint), title, scale, crop (pair), table_width (mm), text_size (mm).
Example:

    op:place view view="Level 8 Plan" sheet=A104 at=(115,140)

- `view` is a name or id (place by the `made` id, not by a name the template holds: the Ground and Level 1 floor plans share a name with a ceiling plan). `sheet` is a sheet's id or number. `title` defaults to the view's own name.
- The frame is the view's own size at its own scale. Two frames overlap if you do not space them, and a big model runs off the sheet. The crop belongs to the view, so one plan takes one crop: make one plan each for two buildings.
- A plan sits on one sheet. When a sheet holds it, `op:remove view view="Site Plan" sheet=A100` first, else `view already on a sheet: A100`.
- A schedule or legend is placed the same way with `table_width=420 text_size=3.5` (mm).

`remove view`: needs nothing by itself. Exactly one of view, id (ids). All or none of view, sheet.
Example:

    op:remove view view="Site Plan" sheet=A100

`delete sheet`: needs sheet.
Example:

    op:delete sheet sheet=A104

The sheet's views stand unplaced.

`add schedule`: needs category, fields. May take name, sortby, groupby, filter, itemize (yesno).
Example:

    op:add schedule category="Structural Columns" fields=Type,Count,Length name="Column Schedule by Type" itemize=no

`itemize=no` gives one row a type; left out, one row an element (528 rows for 528 columns). Read it with `schedule_read {"view":"Column Schedule by Type"}`.

`print sheets`: needs path.

## Annotation: add text, add dimension, add dimension chain, add tag, add symbol, add detail line, add filled region, add insulation

`add text`: needs at (point), view, text. May take type, leader_to (point), width (mm).
Example:

    op:add text at=(0,-10) view="General Notes" text="1. All dimensions are in millimetres."

`text` is the words; `leader_to` is the leader's point; `width` is the wrap width on paper in mm, 0 or more; `type` is a text type (default: the Text tool's). Notes in a drafting view went a line every 8 mm down; place that view on the sheet.

`add dimension`: needs from (point), to (point), view. May take offset (mm).

`add dimension chain`: needs points (points), view, offset (mm).
Example:

    op:add dimension chain points=(0,-1000) (8400,-1000) (16800,-1000) view=<plan id> offset=-3000

Each point must fall on a live element, a grid line in practice. A point past a grid's end answers `a dimension string reference found no live element within this command's own tolerance of (8400, -5000)`. A chain takes elements, not level lines. `commands_run {"name":"annotate-autodim"}` with the plan active draws the grid strings in one command.

`add tag`: needs id, view. May take leader (yesno).
Example:

    op:add tag id=<element id> view=<plan id> leader=no

One element a line; batch as the first piece says. All of a kind: `view_activate` the plan, then `commands_run {"name":"Tag All","points":[[16800,12600]]}` with ONE point inside the plan; always give the point.

`add symbol`: needs at (point), view. May take symbol, rotation (degrees).
Example:

    op:add symbol at=(-9000,30000) view=<plan id>

A north arrow in model mm; put it inside the crop.

`add detail line`: needs points (points), view. May take style.

`add filled region`: needs boundary (polygon), view. May take type, pattern.

`add insulation`: needs from (point), to (point), view. May take width (mm).

## Materials and types: add material, set material, the Material row, type_set and glass walls

`add material`: needs nothing. May take name, from, library.
Example:

    op:add material name="Blue-Grey Glass"

Example with a library set:

    op:add material library=copper name="Play Copper"

`set material`: needs name, key, value.
Examples:

    op:set material name="Play White" key=render_colour value=#f4f1ea
    op:set material name="Play White" key=glow value=0.2

- One key a line. Keys that reach the Realistic view: `texture`, `texture_size` (mm), `texture_rotation`, `render_colour`, `roughness`, `metallic`, `bump`, `transparency`, `glow`. `shading_colour` was played too. A wrong key is refused and lists the 33 keys a material keeps. `op:set material name="Play White" key=zzz value=1` answered:

        cannot proceed: a material keeps no 'zzz' (its keys: density, elastic_modulus, poisson_ratio, yield_strength, rigidity_modulus, tensile_strength, compressive_strength, thermal_expansion, heat_conductivity, render_colour, texture, texture_size, texture_rotation, roughness, metallic, bump, transparency, glow, relief_depth, relief_shadow, height_gain, cut_pattern, surface_pattern, shading_colour, surface_pattern_angle, surface_pattern_follows, description, material_class, material_keynote, material_mark, material_comments, manufacturer, cost)

- `library=<set>` adds one of the 67 shipped texture sets with its ready-made graph. A set name is lower case with `_`. A set the library does not hold is refused: `cannot proceed: the library holds no texture set named 'zinc_standing_seam'; nothing was written`. Sets are photographs and show in their own colours; `render_colour` does not change them, except nine sets that draw brightness only (lawn_mown, roof_tile_concrete, paving_stone, box_profile, precast_panel, brick_grey, brick_cream, steel_plate_painted, steel_sheet_worn). Names, graphs and the repeat of a texture: part 7 (Materials, textures and the material node graph).
- Pale materials go grey on faces away from the sun: `glow` 0.2 to 0.45 keeps them pale.

The Material row of an element carries the texture. `op:set id=<id,id,...> key=Material value="<file material>"` worked on block categories, doors and windows. A Form takes the row too (`element_get` then shows `"Material":"Play White"`). With no Material set a block takes its category's default finish; part 8 (Blocks) gives the remedies.

A native wall, floor or roof takes its material from its TYPE: `add wall`, `add column` and `add beam` take `type=`. The Realistic view draws the material of the type's STRUCTURE layer, so set every layer to the finish with `type_set` key `Layer <n> Material`. `types_list {"category":"Walls"}` reads each type's layers. The key `Layer 1 Material` on a wall type, with its answer:

    type_set {"category":"Walls","type":"Generic 200mm","key":"Layer 1 Material","value":"Play White"}
    {"category":"Walls","id":"3043cea2-...","key":"Layer 1 Material","layers":[{"function":"Structure","layer":1,"material":"Play White","thickness":200}],"type":"Generic 200mm","value":"Play White"}

A curtain wall is a wall of a type whose Function is Curtain: `op:add wall ... type=<that type>`, and the wall takes its grid of panels in the same Undo entry. The template's "Curtain Wall" type reads one Concrete layer, 32 MPa, 50 mm, with no spacing entries; the glass types are "Exterior Glazing" and "Storefront" (one Glass layer, 24 mm). Played on a blank template:

    op:add material name="Blue-Grey Glass"
    op:set material name="Blue-Grey Glass" key=render_colour value=#7E9AAE
    type_duplicate {"category":"Walls","type":"Exterior Glazing","name":"Blue-grey glass"}
    type_set {"category":"Walls","type":"Blue-grey glass","key":"Layer 1 Material","value":"Blue-Grey Glass"}
    type_set {"category":"Walls","type":"Blue-grey glass","key":"Vertical Spacing","value":2100}
    type_set {"category":"Walls","type":"Blue-grey glass","key":"Horizontal Spacing","value":3600}
    op:add wall from=(40000,0) to=(48400,0) level=Ground top="Level 2" type="Blue-grey glass"

- To put a wall that is already drawn on a new type: `type_duplicate`, `type_set` `Layer n Material`, then `param_set {"ids":["<wall id>"],"key":"@type","value":"Blue-grey glass"}` (the `@type` write: piece "Change, move, copy, mirror, array and delete").
- `type_duplicate` answers the copy's `type` ("Blue-grey glass", or "Blue-grey glass 2" if the name was held) and its layers. Vertical Spacing and Horizontal Spacing are mm between panel lines. With levels at 3,600 mm, one 8,400 mm wall from Ground to Level 2 read Curtain Grids 4 and Curtain Panels 8; a second read 8 and 16. A wall per face, Ground to the top level, is one facade and one Undo step.

## Change, move, copy, mirror, array and delete: set, delete, move, copy, rotate, mirror, array

`set`: needs id (ids), key, value.
Examples:

    op:set id=<form id> key=Material value="Play White"
    op:set id="level-Level 1" key=Elevation value=3600

`key` is a row of the Attributes palette; read the rows of one element with `element_get {"id":"<id>"}` (`params`). `id` takes several ids separated by commas, so one line sets a row of elements. A key the element does not list is refused in words. `param_set {"ids":["<id>"],"key":"Mark","value":"D1"}` set Mark on one element. It refused a view.

A row that begins with `@` is an element column. `param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}` answered `{"changed":1,"elements":1}` and `element_get` then read the new family and type; the same call on a roof (`"value":"Terracotta Tile Battens 90"`) answered the same. `op:set id=<id> key=Type value=...` is refused: `A Roof has no parameter 'Type'`.

`delete`: needs id (ids).
Example:

    op:delete id=<made id>

The answer carries the removed id in `changed`; a floor deleted drops Floors by 1.

`move`: needs id (ids), by (movevector).
Example:

    op:move id=<roof id> by=(0,0,2700)

`by` is dx,dy,dz in mm; the roof example above lifted a roof by 2700.

`copy`: needs id (ids), by (vector).

`rotate`: needs id (ids), about (point), angle (degrees). May take copy (yesno).

`mirror`: needs id (ids), axis (pair). May take copy (yesno).

`array`: needs id (ids), count (count). Exactly one of step (vector), about (point). All or none of about (point), angle (degrees). May take group (yesno).
Example:

    op:array id=<seed> count=5 step=(8400,0,0)

- The seed stays and 4 copies follow, 8,400 mm apart in x; their ids are in `made` (`<seed>-<hash>`).
- Several ids repeat a whole row in the next direction: `op:array id=<seed>,<copy>,<copy>,<copy>,<copy> count=4 step=(0,-8400,0)`. A `step` with a z (`step=(0,0,3600)`) lifts each copy by that height.
- A frame of N crossings and S storeys is a few calls, each taking the ids the last answered: seed a column and a beam (one `ops_run`); a row each along x; the rows along y with all the ids so far; then every column id and every beam id with the storey step. Two beam rows (along x and along y) are two seeds.
- After a z step a column copy takes the level its new height falls on (a column at Ground copied up 3600 read Level 1), but a beam copy keeps its seed's Reference Level: `elements_query {"category":"Structural Framing","level":"Level 1"}` missed the copies. Count beams by category, not by level.

## Facts met in play: wall height and Base Offset, hip roofs, floors, elements_query rows

- A wall's height is its top above its level. Set Base Offset after the height and the top stays. `op:set id=<wall> key="Unconnected Height" value=3120` changes the height later.
- `op:add roof` makes hip roofs from a boundary and a slope. The `Roof` tool drew a roof from a sketch and a gable through Pick Walls (piece "Roofs, stairs, railings, fascias and gutters"; part 14 recipe (s)); Freeform Curve, Loft, Revolve and Sweep were played (part 9, Forms, freeform curves and surfaces).
- `element_get` on a floor or a room gives no `location`, so keep the boundary points you sent.
- `elements_query` answers its rows under `rows`. A real answer, first row shown:

        elements_query {"category":"Form"}
        {"category":"Form","count":3,"more":false,"rows":[{"family":"Form","id":"0da7758bd7bcd48999b9b0359b180785","kind":"Form","level":"","row":7,"type":"Form"}, ...]}

  Row keys: `id`, `family`, `type`, `level`, `kind`, `row`. `element_get {"id":"3e554d07689842945392daad3f37a354"}` answered `category`, `family`, `guid`, `id`, `kind`, `level`, `option`, `params`, `phase`, `row`, `type`, `workset`; its `params` held `{"Comments":"","Control Net U":9,"Control Net V":5,"Mark":"","Material":"Play White","Name":"","Phase Created":"New Construction"}`.
- `fields:["id","level","params"]` adds `params` to each row; `limit` is 1 to 1000 and the default 100; `more` and `next` continue. A door row read `family` Single Swing, `type` 900 x 2100; its params: Comments, Height, Mark, Phase Created, Sill Height, Width.
- A cheap check after a batch: `document_info {"categories":true}` answers the count of every category.
- A green line can still be the wrong result: read the element back.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
