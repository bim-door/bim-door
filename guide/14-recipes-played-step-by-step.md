# 14. Recipes (played step by step)


In this part: calls played through the door, with what UNION answered. A recipe is one example, not the list of what UNION does: part 3 (The map) maps the whole, part 16 (Index) lists every command. For a job with no recipe, look the control up and read UNION's words. Step lines use part 5's five-part form.
- (a) new project from a template
- (b) levels and grids
- (c) columns and beams
- (d) walls, floor, door, window
- (e) a 1:10 detail in a drafting view
- (f) a duct run with an air terminal
- (g) a drafting view on a sheet
- (h) read a settings table's rows
- (i) a floor on the level above
- (j) read back what you placed
- (k) look at the 3D view
- (l) keep replies small
- (m) a drawing set: views, sheets, strings, tags, schedules
- (n) a realistic picture of the model
- (o) materials on a wall type and on blocks
- (p) a freeform surface: curves, loft, panels, material
- (s) a gable roof on four walls (Roof tool, Pick Walls, Defines Slope)
- (t) a curved wall and a spline line (draw modes on the options strip)
- (u) a spiral stair between two levels

Look it up: a command with its prompt and its `draw_modes`:
    commands_list {"name":"Roof"}
`get_guide {"part":"reference"}` lists the reference.

## (a) New project from a template
    1  start:Architectural · picks — · keys — · fields — · expect view Ground active
Result: a document from the Architectural template: Levels 3, Elevation 4, Floor Plan 4, Section 2, Schedule 3, 3D View 1, Ceiling Plan 3. Other words: start:Structural, Mechanical, Hydraulic, Fire Protection, Electrical. `start:Structural` opens on the view 'Level 1' (Levels 2, Structural Plan 2, Floor Plan 1, 3D View 1, Elevation 4; no Ground level): its expect is `view Level 1 active`. A drafting view works the same in every template. A `start:` with no model opens UNION's own start page, where the ribbon is hidden.
On the person's own door this step is red with UNION's words `cannot proceed: 'New' is the person's own control, not UNION AI's; ask the person to press it` (part 1). Read the model that stands: `document_info {"categories":true}`, `levels_list`, `views_list`.

## (b) Levels and grids
    1  op:add level elevation=3000 name="Level 2" · picks — · keys — · fields — · expect Levels +1
    2  op:add grid from=(0,-2000) to=(0,12000) name=A · picks — · keys — · fields — · expect Grids +1
    3  op:add grid from=(8000,-2000) to=(8000,12000) name=B · picks — · keys — · fields — · expect Grids +1
    4  op:add grid from=(-2000,0) to=(10000,0) name=1 · picks — · keys — · fields — · expect Grids +1
    5  op:add grid from=(-2000,6000) to=(10000,6000) name=2 · picks — · keys — · fields — · expect Grids +1
Rules: template level names (Ground, Level 1, Roof) already exist: a repeat is refused (`cannot proceed: a level named Roof already exists`). To move or rename one, the Two Towers set plays:
    op:set id="level-Level 1" key=Elevation value=3600
    op:set id=level-Roof key=Name value="Level 2"
A grid named with digits only plays as `name=1` or `name="1"`.

## (c) Columns and beams
    1  op:add column at=(0,0) level=Ground · picks — · keys — · fields — · expect Structural Columns +1
    2  op:add beam from=(0,0) to=(8000,0) level=Ground · picks — · keys — · fields — · expect Structural Framing +1
Rules: `type` is a type's name from `types_list` (`type=310UC158` for a column, `type=530UB82.0` for a beam). `top` may be left out: a column then stands up to the next level above. A beam's top face stands on its level. A beam at a height between levels keeps its level and takes `Start Level Offset` and `End Level Offset`, never a new level: part 4 (Fast ops), piece "Columns, beams, braces and structure". A row of identical members is one `array` line (part 4).

## (d) Walls, floor, door, window (Ground plan)
Make the Ground floor plan the active plan first: the step form draws on the plan in front. Name it by its id: `views_list {"kind":"Floor Plan"}`, then `view_activate {"view":"<Ground floor plan id>"}`.
    1  ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4
    2  ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1
    3  ribbon:Structure:Opening:Window · picks (5000,6000) · keys Escape Escape · fields — · expect Windows +1
    4  ribbon:Structure:Floor · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys — · fields — · expect nothing selected
    5  contextual:Finish · picks — · keys — · fields — · expect Floors +1
Two wall buttons: `ribbon:Structure:Wall` presses `Wall` on the Structure panel and `ribbon:Architecture:Wall` presses `Wall: Architectural`. The Structure one: `ribbon:Structure:Wall · picks (1000,1000) (3000,1000) · keys Escape Escape · fields — · expect Walls +1` (picks lie on the part of the plan the window shows). A draw mode set with `Draw=` was played on `ribbon:Architecture:Wall` (recipe (t)).
Rules: one press of Wall chains walls corner to corner (5 picks = 4 walls). A door or window picked on a wall's line also adds an Opening (Doors +1 also read Openings 0 -> 1). Step 4's expect is `nothing selected`; it played green on the Filled Region sketch of (e) and on the Floor tool (recipe (i)). The Window step's words read "(the walk names Structure; the tile stands on Architecture)": the step is green. A floor on the level above is recipe (i); what the model reads back of a door or window is recipe (j).
The five steps played green as one `steps_run` on a plan with the first walls already standing (5 steps; Walls 4 -> 8, Doors +1, Windows +1, Floors +1), and one `qa:Undo` took back the whole call (UNION: `undid 'Add-in: steps.run'`, Walls 8 -> 4). Undo and redo are steps. The five-part form below and the short form `qa:Undo · expect —` both played green:
    qa:Undo · picks — · keys — · fields — · expect —
    qa:Redo · picks — · keys — · fields — · expect —
Both green (`undo=d21/u0>d20/u1 undid 'Add-in: steps.run'`, `changed=Walls 6>5`; then `redid`). The short `qa:Undo · expect —` undid with `changed=Walls 5>4`.
Op form, the same building through `ops_run`, in two calls, because a door and a window name the wall they stand in and a wall's id is in the first call's answer. One `add wall` line is one wall.
    ops_run {"name":"Walls and floor","lines":[
      "op:add wall from=(0,0) to=(8000,0) level=Ground",
      "op:add wall from=(8000,0) to=(8000,6000) level=Ground",
      "op:add wall from=(8000,6000) to=(0,6000) level=Ground",
      "op:add wall from=(0,6000) to=(0,0) level=Ground",
      "op:add floor boundary=(0,0),(8000,0),(8000,6000),(0,6000) level=Ground"]}
The answer's `results[0]` to `results[3]` hold each wall's id in `made`, `results[4]` the floor's. Then, with the ids of the south wall (`results[0].made`) and the north wall (`results[2].made`):
    ops_run {"name":"Door and window","lines":[
      "op:add door wall=<south wall id> at=(2000,0)",
      "op:add window wall=<north wall id> at=(5000,6000)"]}
Read the result with `document_info {"categories":true}`: Walls 4, Floors 1, Doors 1, Windows 1; the op form also adds an Opening for the door and one for the window (Openings +2), as the ribbon form does. A `delete` of a floor id answers `changed:[<the id>]` and Floors falls by 1.

## (e) The 1:10 drafting-view detail (lines, batt, filled region, note with leader, dimension, title)
    1  ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Timber Eaves Detail; Scale=1:10 · expect view: Drafting View +1
    2  ribbon:Annotate:Detail Line › Rectangle · picks (0,-800) (145,-90) · keys Escape Escape · fields — · expect Lines +4
    3  ribbon:Annotate:Detail Line › Rectangle · picks (0,-90) (145,0) · keys Escape Escape · fields — · expect Lines +4
    4  ribbon:Annotate:Insulation · picks (72,-780) (72,-100) · keys Escape Escape · fields Options Strip: Width=100 · expect Detail Items +1
    5  ribbon:Annotate:Region › Filled Region · picks (-60,-800) (0,-800) (0,-90) (-60,-90) (-60,-800) · keys — · fields — · expect nothing selected
    6  contextual:Finish · picks — · keys — · fields — · expect Filled Regions +1
    7  ribbon:Annotate:Text · picks (145,-500) (500,-500) · keys S T U D Space 1 4 5 Return Escape · fields Options Strip: Leader=on · expect Text Notes +1
    8  ribbon:Annotate:Aligned · picks (0,-800) (145,-800) (72,-950) · keys Escape Escape · fields — · expect Dimensions +1
    9  ribbon:Annotate:Text · picks (0,-1250) · keys T I M B E R Space E A V E S Return Escape · fields Options Strip: Leader=off · expect Text Notes +1
    10 chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect nothing selected
Rules that played:
- The drafting view opens as the active tab at 1:10. Detail Line Rectangle = 4 lines at exact mm; a chain `Detail Line › Line` of 8 picks = 7 lines.
- The batt is `ribbon:Annotate:Insulation` (on screen Annotate > Detail > Insulation). Two picks along any line, including a sloped run; `Width` is the batt width (reads '100 mm'); UNION draws the standard zig-zag batt with angled end caps. It makes a Detail Item annotation (expect `Detail Items +1`, not Lines).
- Filled Region: close the loop by repeating the first point, then `contextual:Finish` (picture: crosshatch strip; default type "Diagonal Crosshatch").
- Repeat the first point EXACTLY; a pick 12 mm from it is a fifth corner.
- Text with Leader=on: FIRST pick = the arrowhead tip, SECOND = the text. Leader=off: one pick. Typed text stands as typed (capitals if typed as capitals); size 3.5 mm Arial.
- Aligned dimension: picks ON existing line endpoints, the third pick places the dimension line outside the drawing (a pick 26 mm off any line was refused).
- Draw the Filled Region before the lines you want on top of it. A `plan:select` pick on a hatched area selects the region first (Tab cycles alternates).
- Reinforcement drawn in a detail view uses lines, circles and a region; a cogged bar is a 3-pick chain, a ligature a 2-pick line. That is the 2D detail method.
- A plan of any level, made active, so you can draw on it: `ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Level 2 · expect dialog closed`. It is also the way to draw on a level other than the start view.
- Read the template's levels before adding any: the start answer's `counts=` gives how many, a plan's Attributes give each one's elevation. A level name that already exists is refused.
- `op:set` is written `op:set id=<element id> key=<Attributes row> value=<value>`; take the id from a step's `made=` answer; an id that holds a space, a comma or a double quote is written in double quotes there, a double quote inside it doubled.

## (f) A duct run with an air terminal (Ground plan, BEFORE any sheet)
Step 1 is the person's on the person's own door (recipe (a)). Where a model is open, make the Ground floor plan active by its id (recipe (d)) and send steps 2 to 6.
    1  start:Architectural · picks — · keys — · fields — · expect view Ground active
    2  ribbon:Systems:Duct · picks (1000,1000) (5000,1000) · keys Escape Escape · fields — · expect Ducts +1
    3  ribbon:Systems:Air Terminal · picks (3000,1000) · keys Escape Escape · fields — · expect Air Terminals +1
    4  ribbon:Systems:Duct · picks (1000,3000) (6000,3000) · keys Escape Escape · fields Options Strip: Width=300; Height=150; Middle Elevation=2700; System Type=Return Air · expect Ducts +1
    5  ribbon:Systems:Air Terminal · picks (3500,3000) · keys Escape Escape · fields — · expect Air Terminals +1
    6  chrome:Canvas Zoom to Fit · picks — · keys — · fields — · expect nothing selected
Result (door counts): Ducts 2, Duct Systems 2, Air Terminals 2; each duct made its own Duct System. Supply Air draws cyan, Return Air red.
Rules:
- TWO picks per duct. Three picks made ONE duct (Ducts 0 -> 1): the third pick starts a segment that Escape throws away.
- Air Terminal: pick ON the duct (status "Click a face to place the air terminal"); a cross-in-box sits on the duct.
- The Duct options strip holds exactly: Storey (Level), Width, Height, Diameter, Middle Elevation, Lock, Apply, Start Offset, End Offset, System Type. Use those names: a field `Offset` was refused with "the options strip has no 'Offset' (its options: Storey (Level), Width, Height, Diameter, Middle Elevation, Lock, Apply, Start Offset, End Offset, System Type)", and `Size` likewise. Defaults read: Width 400 mm, Height 200 mm, Diameter 300 mm, Middle Elevation 2400 mm, Start and End Offset 2400 mm, System Type Supply Air. Played values: Width=300 reads '300 mm', Height=150 '150 mm', Middle Elevation=2700 '2700 mm'. System Type items: Supply Air / Return Air / Exhaust Air.
- Ceiling diffuser: make or read the ceiling (`op:add ceiling boundary=(0,0) (8000,0) (8000,6000) (0,6000) level=Ground height=2700` is the form of part 4). Then place the block on it, with the ceiling's id in `host=` (part 8, Place a block): `host=<ceiling id>` was played with another ceiling-hung block. A duct under it runs at a Middle Elevation below the ceiling height.
- The plan must be the active view. With a sheet in front UNION refused the duct and the air terminal: `cannot proceed: Duct works in a plan, section or elevation view: a sheet is in front; use Activate View on one of its viewports to work in that view`.

## (g) A drafting view on a sheet
    1  ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Timber Eaves Detail; Scale=1:10 · expect view: Drafting View +1
    2  ribbon:View:Sheet · picks — · keys Return · fields New Sheet: Name=Eaves Detail; Number=A150 · expect dialog closed
    3  ribbon:View:Viewport · picks — · keys Return · fields Place View: Views=Drafting View · expect dialog closed
    4  ribbon:View:Viewport · picks (300,450) · keys Return · fields Place View: Views=Drafting View · expect dialog closed
Draw the detail with (e) between steps 1 and 2. Result: sheet A150 created (A0, the template's title block, tab "A150 - Eaves Detail", the sheet becomes the active view); the viewport placed (undo entry 'Place Timber Eaves Detail'; the project tree shows the view under A150; the sheet shows the tag "Timber Eaves Detail 1:10").
Rules:
- Viewport (View > Sheet Composition) opens Place View, whose table `Views` lists the views NOT yet on a sheet BY KIND (rows read: Ceiling Plan, 3D View, Drafting View, Schedule x3). The row is the kind ("Drafting View"), not the view's own name. Row + `keys Return` closes the dialog and the Viewport tool STANDS (UNION: "Click on the sheet to place the view"); the next pick on the sheet places the view, as step 4 did.
- A second placement of a view was refused: `cannot proceed: view already on a sheet: A150`. End a standing tool with `keys Escape Escape` before pressing Viewport again.
- On this template the Place View table listed no Floor Plan row, because its 4 floor plans already stand on sheets A100 to A103. The row Ceiling Plan placed the view named "Roof" (tag "Roof" 1:100) at the pick (700,450).
- A sheet number that exists is refused: `cannot proceed: sheet number exists: A102` (template sheets A000, A100 to A103, A201 ...).
- A placed viewport shows the view itself, at the view's scale, inside its frame (recipe (m)).

## (h) Open a settings table and read its rows (Fill Patterns, Line Styles, Line Weights, Arrowheads, Object Styles)
    1  ribbon:Manage:Additional Settings › Fill Patterns · picks — · keys Return · fields Fill Patterns: Patterns=Gravel · expect dialog closed
    2  ribbon:Manage:Additional Settings › Line Styles · picks — · keys Return · fields Line Styles: Styles=Wide Lines · expect dialog closed
    3  ribbon:Manage:Additional Settings › Line Weights · picks — · keys Return · fields Line Weights: Weights=3 · expect dialog closed
    4  ribbon:Manage:Additional Settings › Arrowheads · picks — · keys Return · fields Arrowheads: Arrowheads=Arrow Filled · expect dialog closed
    5  ribbon:Manage:Object Styles · picks — · keys Return · fields Object Styles: Categories=Air Terminals · expect dialog closed
All five played green. The row only SELECTS a row. To read a table's rows, give a wrong row (`table 'X'=zzz`): UNION answers with the rows (the step is red, nothing changes). The same method lists the rows of any dialog: part 2 (Find any control).

## (i) A floor on the level above (after the walls of (d) on Ground)
Activate the plan of the level by its id (`views_list {"kind":"Floor Plan"}` gives it; a plan name shared with a ceiling plan is refused, recipe (d)).
Then:
    1  ribbon:Structure:Floor · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys — · fields — · expect nothing selected
    2  contextual:Finish · picks — · keys — · fields — · expect Floors +1
Read the level back: `elements_query {"category":"Floors"}` answers the floor with `"level":"level-Level 1"` and type `Generic 300mm`; `{"category":"Floors","level":"Level 1"}` answers it and `"level":"Ground"` answers count 0. A level's id is `level-` and its name (`levels_list`).
Rules: the floor takes the level of the ACTIVE plan, so activate the plan first (step 1's facts read `view='Level 1'`). `views_list {"kind":"Floor Plan"}` names the plans (Ground, Level 1, Roof, Site Plan). A picture of the Level 1 plan shows the floor outline and the walls of Ground are absent from it. A level made by `op:add level` starts with no plan view, so a step draws on it once its plan is made (recipe (e), the `New Plan` step). `op:add floor ... level="<name>"` (part 4, Fast ops) needs no plan and is also the fast form for many floors (28 floors in one `ops_run` took 0.2 s; one floor by `steps_run` took 1.5 s).

## (j) Read back what you placed (door, windows, walls)
With (d)'s walls and these picks for (d)'s steps 2 and 3: a door at (4000,0) on the 8000 mm south wall, windows at (2000,6000) and (6000,6000).
- `elements_query {"category":"Doors"}` answers per element: `id`, `family` (Single Swing), `type` (900 x 2100), `level`, `kind`, `row`. With `"fields":["id","level","params"]` it adds `params`: Comments, Height, Mark, Phase Created, Sill Height, Width (a window: 1200 x 1200, Sill Height 900). A wall's params: Base Offset, Location Line (Wall Centerline), Top Offset, Structural Usage and more; its type is Generic 200mm. `element_get {"id":"<id>"}` answers the element's row with every column (category, phase, option, workset, guid) and its params.
- Where it stands: `element_get` and `elements_get {"ids":["<id>","<id>"]}` (ids that are no element come back in `missing`, with `forbidden:[]`) answer beside the columns and params a `host` (the id of the wall a door or window stands on) and a `location` in mm: a door, a window, a column or a stair `{"point":[x,y]}` (a door at (2000,0): `{"point":[2000,0]}`); a wall or a beam `{"curve":{"start":[0,0,0],"end":[8000,0,0]}}`, three numbers each, z last; an arc adds `"arc":true` and `"midpoint"`. An element with no single placement (a floor, a room) answers no `location`; one that stands on nothing, no `host`. For `location`, take the ids from `elements_query`, then ask `elements_get`.
- A schedule's table: `schedule_read {"view":"Door Schedule","limit":50}` (the schedule's name or id from `views_list {"kind":"Schedule"}`) read a model with one door as `rows:[["D1","Ground","Single Swing","900 x 2100","900 mm","2100 mm",""]]` under `headings` Mark, Level, Block, Type, Width, Height, Fire Rating. Its reply is `schedule.read` in the reference; `after` is an offset. A view that is no schedule is `bad_request`, an unknown name `not_found`. Give `limit` on a large schedule.
- A cheap check after a batch: `document_info {"categories":true}` answers the count of every category in 620 bytes (Doors 1, Floors 1, Walls 4, Windows 2, Openings 3).
- `elements_query` answers its rows under `rows`.

## (k) Look at the 3D view
The calls. For a picture that reads as a building, set the Display Options first: recipe (n).
    view_activate {"view":"view-3d"}
    view_camera {"fit":true}
    view_image {"view":"view-3d","window":"main","width":900}
`view_image` takes a view (a name or id from `views_list`; the 3D view is `{3D}`, id `view-3d`), a width and a window. The picture is the whole UNION window, ribbon and palettes included (`{3D}` in the main window came 900 x 653 px, the ALBATROSS window 900 x 573 px). With a 3D view in front it waits until the model is built, at most 20 seconds; if the model has not stood whole the answer is `unavailable` and no picture: ask again once, then send `view_image {"window":"main"}` with no view (recipe (n)). Do not judge the model from an error.
FIT FIRST: the 3D view keeps its earlier framing, so the first picture after writes can show the model small and off to one side, or only two dash-dot lines on white; a view with nothing in it is not a wrong model. `view_camera {"fit":true}` takes 4 ms to 0.2 s; send it before the first `view_image` and again after the model grows. `ids` frames the elements named: fit the whole model for a whole-model picture.
THE ALBATROSS TRAP: once `albatross_place` has opened the ALBATROSS window and it is in front, `view_image {"view":"view-3d"}` with no `window` returns a picture of the ALBATROSS window, not the model. Write `"window":"main"` for the model and `"window":"albatross"` for the graph. A window that is not open answers `cannot proceed: the viewer window is not open; windows open now: main, albatross`.
Read the camera: `view_camera {"view":"view-3d"}` with no angle, `fit` or `ids` moves nothing and reads the camera. Its reply is `view.camera` in the reference. `{"view":"view-3d","azimuth":35,"pitch":25}` turned it and answered the angles; the eye keeps its target and distance, and any roll is cleared. A view that is not 3D answers refused in words; a 3D view the person has locked refuses a turn in its own words.

## (l) Keep replies small
Ask narrow: the advice below is what to keep; the sizes are examples measured on a small model (4 walls, 1 door, 2 windows) and grow with the model.
- `params_schema {"category":"Structural Columns"}` answers 80 rows (36 KB). With no category it answers the 29 categories and their row counts (2.5 KB). `{"category":"Doors"}` answers `{category, count, rows, open:true}` (11 rows: `@category`, `@family`, `@type`, `@level`, `@guid`, `@id`, `Mark`, `Comments`, `Design Option`, `Phase Created`, `Phase Demolished`); `open:true` says an element stores more than the list, and a door's Width, Height and Sill Height show under `params` of `element_get`. `param_set {"ids":["<door id>"],"key":"Mark","value":"D1"}` answered `{changed:1, elements:1}` and the Door Schedule then read D1. An `@` row is an element column. `@type` sets the element's type (recipe (o), step 3). An annotation or analytical category, or a name the catalogue does not know, answers `not_found`. To see a parameter's name and value read one element: `element_get {"id":"<id>"}`.
- `elements_query`: give `fields` and `limit`. The default fields are id, family, type, level, kind; `"fields":["id","type"]` is smaller, and `params` makes each row several times larger. It answers 100 rows unless you give `limit` (1 to 1000; `more` and `next` continue it).
- `commands_list`: give `tab` (and `kind`: `tool`, `action` or `dialog`) or `name`. `{"name":"Wall","brief":true}` answers 1 command; `{"brief":true,"tab":"View"}` answers the tab's commands. Index: part 16.
- `steps_run`: each result repeats the counts in `facts`, so a reply grows with every step. Send 3 to 8 steps a call and read each result's `state`, the expect clause at the end of `words`, and the last result's `counts=`.
- `ops_run`: 25 to 35 lines a call on a large model.
- `view_image`: a picture is a large reply (80 to 200 KB at width 800 to 1000). Use the smallest width that shows what you need. Read counts after each batch; take a picture once, at the end (recipe (n)).

## (m) A drawing set (views, scale and crop, sheets, dimension strings, tags, schedules, view filters)
Order: finish the model; steps 1 and 2 (views, their scale); steps 6 to 11 (what goes on each view, `view_activate` it first); then steps 3 and 4 (sheets, place the views). Annotating after placing also played.
Read first: `sheets_list` and `views_list`. The Architectural template already holds sheets A000, A100 to A103, A201, A301, A501 (a number that exists is refused) and views North, East, South and West Elevation, Section A, Section B, Site Plan, and plans of Ground, Level 1 and Roof (the Ground and Level 1 floor plans share a name with a ceiling plan: place those by id), and the schedules Door Schedule, Window Schedule and Room Schedule on sheet A501 (the Door Schedule's columns: Mark, Level, Family (heading Block), Type, Width, Height, Fire Rating). Give a new schedule a name the template does not hold. A name a view already holds is refused, yet the line stays green and the new view keeps UNION's own name: read `words` for `was made but its name was refused`. So use names the model does not hold (`N Elevation`, `Cut A`) and place by the `made` id, never by a name the template holds.
1. VIEWS in one `ops_run`: `op:add view kind=plan|structural|ceiling level="Level 8" name="Level 8 Plan"` (`made` is the view's id); `op:add section from=(x,y) to=(x,y) depth=9000 name="Cut A" view=<plan id>`; `op:add elevation at=(x,y) facing=south name="N Elevation" view=<plan id>`; `op:add drafting view name="General Notes" scale=1:1`. A batch of 20 view lines took 83 ms. The elevation marker stands outside the face and looks at the building: a marker north of it facing south gives the north elevation. Name the plan by its id; the Architectural template's Ground floor plan is 48660e38a721430d899d5d8a96df3bec. These two made a section and an elevation:
    op:add section from=(50000,-2000) to=(56000,-2000) depth=8000 name="Probe Section" view=48660e38a721430d899d5d8a96df3bec
    op:add elevation at=(53000,-6000) facing=north name="Probe Elevation" view=48660e38a721430d899d5d8a96df3bec
2. SCALE AND DETAIL of each view, one `ops_run` of many lines (18 lines in 20 to 160 ms): `op:set id=<view id> key=Scale value=1:200` and `op:set id=<view id> key="Detail Level" value=Coarse` (Coarse and Medium played). Take the id from `made` or `views_list`. If `op:set` of a view answers `no such row`, the route is the Attributes palette: `view_activate`, then `steps_run {"steps":["dock:Properties · picks — · keys — · fields Attributes: Scale=1:200 · expect —"]}`.
3. SHEETS: `op:add sheet number=A104 name="Level 8 Plan" titleblock=A1` (titleblock A0 to A4, ANSI_B to ANSI_E, ARCH_C to ARCH_E1 or None; 2 to 5 ms a sheet). The title block prints the project name from Project Information: `steps_run {"steps":["ribbon:Manage:Project Information · picks — · keys Return · fields Project Details: Project name=<name> · expect dialog closed"]}` (fields: Project name, Project number, Client, Project address, Organisation, Organisation Description, Building, Drawn by, Issue Date, Status). `op:set` and the Attributes palette refused a sheet's own Drawn By and Issue Date. One step per sheet writes them: `steps_run {"steps":["ctx:sheet:Rename · picks — · keys Return · fields Project Tree: view=A104 - Level 8 Plan; Drawing: Drawn By=<initials>; Sheet Issue Date=<date> · expect —"]}`. Never `dialog:Drawing` for a second sheet in a session. To take a sheet away: `steps_run {"steps":["ctx:browser:Delete · picks — · keys Alt+Y · fields Project Tree: view=A104 - Level 8 Plan · expect —"]}`; Return answers No to the box and the step stays green with the sheet still there.
4. PLACE, scale and crop: `op:place view view="Level 8 Plan" sheet=A104 at=(115,140)`. The frame is the view's own size at its own scale, so two frames overlap if you do not space them and a big model runs off the sheet. Fit it with `scale=1:500` and `crop=(x0,y0) (x1,y1)`: the crop is a box in the view's own millimetres (a plan: model mm) and the frame is that box plus a margin (a site plan 112 m by 53 m at 1:500; a 1:50 bay section `crop=(4000,-500) (12000,8000)`). The crop belongs to the view, so one plan holds one crop: for two buildings make one plan each (`op:add view`, or `commands_run {"name":"Copy View"}` on the active plan, step 12), each cropped and placed on its own sheet. A plan sits on one sheet: when a sheet already holds it (the template's Site Plan stands on A100), `op:remove view view="Site Plan" sheet=A100` first (else `view already on a sheet: A100`). A schedule or legend is placed the same way with `table_width=420 text_size=3.5` (mm; a 24-row sheet list used 420).
5. WHAT THE VIEW SHOWS: a plan at 1:200 draws a column as a dot and a 2.5 mm text as 2.5 px in a sheet picture (an A1 sheet is about 850 px wide), so a picture of a sheet reads small by nature; judge by the elements and the counts, and make a framing plan 1:100 per tower (`crop`) when marks must be read.
6. DIMENSION CHAINS (strings): `op:add dimension chain points=(0,-1000) (8400,-1000) (16800,-1000) view=<plan id> offset=-3000`. Each point must fall on a live element, a grid line in practice; a point past a grid's end answers `a dimension string reference found no live element within this command's own tolerance of (8400, -5000)`. `view_activate` the plan first (always right), then send its strings, one plan at a time, and read back `elements_query {"category":"Dimensions","limit":50}` and count the strings by view. `add dimension from= to= view= offset=` is one aligned dimension. The grid strings in one command: `view_activate` the plan, then `commands_run {"name":"annotate-autodim"}` (overall and grid-to-grid; a second run rewrites the same two; 31 ms).
7. NORTH POINT: `op:add symbol at=(-9000,30000) view=<plan id>`: a north arrow in model mm; put it inside the crop.
8. TAGS: one element, `op:add tag id=<element id> view=<plan id> leader=no`; many, one such line each, in batches of 25 to 35 lines on a large model. All of a kind: `view_activate` the plan, then `commands_run {"name":"Tag All","points":[[16800,12600]]}` with ONE point inside the plan (84 to 157 ms; tags are too small to read at 1:200 on screen and read as the member type at 1:100 in print). Always give the point.
9. SCHEDULES BY TYPE: `op:add schedule category="Structural Columns" fields=Type,Count,Length name="Column Schedule by Type" itemize=no` (20 ms; `sortby`, `groupby` and `filter` are optional) reads one row a type; `itemize` left out gives one row an element (528 rows for 528 columns). Read it with `schedule_read {"view":"Column Schedule by Type"}` and place it with `op:place view ... table_width=300 text_size=3.5`. A placed schedule showed its rows on screen: look at the sheet before you say it holds rows.
10. NOTES AND TEXT ON A SHEET: make a drafting view (step 1), write into it `op:add text at=(0,-10) view="General Notes" text="1. All dimensions are in millimetres."` (a line every 8 mm down) and place that view on the sheet. Played so.
11. VIEW FILTERS, to take one kind of member off a view and keep the rest. A lattice of tube members can scatter dotted marks round a plan. A category hide takes the beams with it (`op:set view view="Level 8 Plan" hide="Structural Framing,Structural Columns"` hid every mark and every beam; `hide=Braces` answers `no category named Braces in the Visibility/Graphics`). A filter does not: once per document `steps_run {"steps":["view-filters:add:Braces:Structural Framing;Structural Usage;equals;Other:hide=1 · picks — · keys — · fields — · expect —"]}`, then, with each plan open (`view_activate`), `steps_run {"steps":["view-filters:apply:Braces · picks — · keys — · fields — · expect —"]}`: on screen the marks go and the beams stay. Also played: `op:set view view=view-3d hide=Levels,Grids`; `op:set view view=view-3d hide=Levels,Grids map=plain:lightgrey`; `op:set view view="Level 8 Plan" show=Grids`. A Visibility/Graphics step with no `OK=` leaves its modal standing and the door busy: do not play one.
12. A SHORT ROAD for views: `view_activate` a plan, then `commands_run {"name":"views-autosections","options":{"Sections":true,"Elevations":true,"Sheets":true,"Grids":"all"}}`. On a 2 by 2 grid it made 3 elevations and 2 sections in 27 ms (the template's South Elevation stood, so South was not made); with `Sheets` true it made 4 sheets for the 5 views (North got none), numbered and named by UNION, in 9 ms (the views already stood). `Grids` takes "all" or a list. `commands_run {"name":"Copy View"}` duplicates the active plan.
13. LOOK AND COUNT: `sheets_list` (the count), `view_activate {"view":"A104"}`, `view_image {"view":"A104","window":"main","width":1100}`, `document_info {"categories":true}` (Dimensions, Symbol, Text Notes, Tags). A heavy view draws late on its sheet: leave the sheet in front and look once.
`op:delete sheet` takes a sheet away and its views stand unplaced.

## (n) A realistic picture of the model
A picture that reads as a building, not as a line drawing. The order matters: edit with a plan in front, show the 3D view once, then picture several things.
1. Edit with a floor plan in front. Name the plan by its id; a name shared with a ceiling plan is refused (recipe (d)).
    views_list {"kind":"Floor Plan"}
    view_activate {"view":"<floor plan id>"}
2. Show the 3D view once. It answers `{"kind":"3D View","view":"{3D}"}`.
    view_activate {"view":"{3D}"}
3. Set Display Options, with the 3D view in front. A new template's 3D view opens in the `Hidden` style (white faces, black lines). The Realistic style draws black edge lines by default: `Show Edges=no` and `Silhouette Edges=no` switch the edge lines off. UNION answered with every field read back and `'OK' pressed; the dialog closed`. The options are kept in the model and travel in the saved file. The dialog's fields, keys and limits: `get_guide {"part":"reference > Dialogs > Display Options"}`.
    steps_run {"steps":["ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; Soft Shadows=yes; Backdrop=Sky; OK= · expect —"]}
4. Frame the view. `fit` takes the whole model; `ids` frames those elements and changes no selection. Azimuth in model axes: 90 puts the camera at -y looking +y, 180 at +x, 0 at -x, 270 at +y. `view_camera` takes `azimuth`, `pitch`, `fit` and `ids`.
    view_camera {"fit":true,"azimuth":125,"pitch":-24}
    view_camera {"view":"{3D}","ids":["<id>","<id>"],"azimuth":97,"pitch":-38}
5. Take the picture. It is the whole UNION window (ribbon and panels included); the model is about two thirds of it. Width up to 2048. Send it with no `view` named.
    view_image {"window":"main","width":2048}
A 3D picture can answer "still building its model" without end while UNION is idle: the main window is minimised or hidden behind the UNION AI window. The call above, with no `view`, returns the picture as it stands. Tell the person the main window is hidden and to bring it up.
6. A cutaway in the live view. The box outline and its handles are drawn in the picture.
    selection_set {"ids":["<id>","<id>"]}
    commands_run {"name":"Clip Box"}
    ops_run {"lines":["op:set id=view-3d key=\"Section Box\" value=no"]}
A view's own rows are read with `element_get {"id":"view-3d"}` and written with `op:set`; `param_set` refuses a view.
7. Pale materials go grey on faces away from the sun: give them `glow` (recipe (o)).
8. Black lines labelled Roof, Level 1 and Ground across the picture are the level lines. Hide them and the grid lines in the live 3D view; they were gone from the next picture:
    ops_run {"name":"hide level lines in 3D","lines":["op:set view view=view-3d hide=Levels,Grids"]}

## (o) Materials on a wall type and on blocks
A material is a file material: a name, then one key a line. Native walls, floors and roofs take it from their type; a block takes it from its element's `Material` row. Judge a material by the picture (recipe (n)).
1. Define the materials in one `ops_run`. The keys seen to change the Realistic view: `texture`, `texture_size` (mm), `texture_rotation`, `render_colour`, `roughness`, `metallic`, `bump`, `transparency`, `glow`. A wrong key lists all 33 keys a material keeps:
    op:set material name="Play White" key=zzz value=1
UNION answered `cannot proceed: a material keeps no 'zzz' (its keys: density, elastic_modulus, poisson_ratio, yield_strength, rigidity_modulus, tensile_strength, compressive_strength, thermal_expansion, heat_conductivity, render_colour, texture, texture_size, texture_rotation, roughness, metallic, bump, transparency, glow, relief_depth, relief_shadow, height_gain, cut_pattern, surface_pattern, shading_colour, surface_pattern_angle, surface_pattern_follows, description, material_class, material_keynote, material_mark, material_comments, manufacturer, cost)`. `shading_colour` also played. A repeat `op:add material` of a held name is refused, and the refusal holds the words `already carries`: filter on those words.
    ops_run {"name":"BLOCK MATERIALS: define","lines":["op:add material name=\"Blk Plain\"","op:set material name=\"Blk Plain\" key=render_colour value=#ffffff","op:set material name=\"Blk Plain\" key=glow value=0.2","op:add material name=\"Blk Timber\"","op:set material name=\"Blk Timber\" key=texture value=timber_oak","op:set material name=\"Blk Timber\" key=render_colour value=#ffffff","op:set material name=\"Blk Timber\" key=glow value=0.1","op:add material name=\"Blk Roof Tile\"","op:set material name=\"Blk Roof Tile\" key=texture value=roof_tile_concrete","op:set material name=\"Blk Roof Tile\" key=render_colour value=#ffffff","op:set material name=\"Blk Roof Tile\" key=texture_size value=1800"]}
2. A texture set from the library comes with its ready-made graph. 67 sets ship; the names are in part 7 (Materials). A name the library does not hold: `cannot proceed: the library holds no texture set named 'zinc_standing_seam'; nothing was written`.
    op:add material library=copper name="Play Copper"
Textures are photographs and show in their own colours; `render_colour` leaves their colours as they are. Nine sets draw brightness only and take their colour from `render_colour`, so `library=lawn_mown` is grey until given a green: lawn_mown, roof_tile_concrete, paving_stone, box_profile, precast_panel, brick_grey, brick_cream, steel_plate_painted, steel_sheet_worn.
3. A wall type: duplicate a layered type, then set the material of EVERY layer. A wall, floor or roof type draws the material of its structure layer in the Realistic view. `types_list {"category":"Walls"}` reads each type's layers. The value is a file material or a block-library word. The reply holds `layers` read back. The call:
    type_duplicate {"category":"Walls","type":"Precast 150 + Lining","name":"Precast White"}
    type_set {"category":"Walls","type":"Precast White","key":"Layer 1 Material","value":"Precast White"}
If the `type` of the duplicate's reply differs from the name sent, use the reply's name. The same `type_set` on the template's own type, with a material made in step 1:
    type_set {"category":"Walls","type":"Generic 200mm","key":"Layer 1 Material","value":"Play White"}
UNION answered `{"category":"Walls","id":"3043cea2-...","key":"Layer 1 Material","layers":[{"function":"Structure","layer":1,"material":"Play White","thickness":200}],"type":"Generic 200mm","value":"Play White"}`. `add wall`, `add column` and `add beam` take `type=`, not a material.
To put an existing wall on a type, write the row `@type` with `param_set`. It answered `{"changed":1,"elements":1}` and `element_get` then read `"family":"Block 190 Core-filled","type":"Block 190 Core-filled"`:
    param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}
The same call on a roof, with `"value":"Terracotta Tile Battens 90"`, gave the same answer. `op:set id=<id> key=Type value=...` is refused (`A Roof has no parameter 'Type'`). So: `type_duplicate`, `type_set` `Layer n Material`, then `param_set` `@type` on the wall ids.
4. Blocks: one texture for the whole element, from its `Material` row, each part's colour coming from its material word (part 8, Blocks). `id=` takes several ids with commas and no space; 40 ids a line was played. One wrong id refuses the whole line: send those ids one by one. Doors and windows took it too (29 doors and 113 windows were set to a plain white file material). A Structural Framing block: set the material on the member's type (part 7).
    op:set id=<id>,<id>,<id> key=Material value="Blk Plain"
Find the ids with `elements_query {"category":"<category>","limit":1000}`: block rows hold `"kind":"BlockInstance"` and `family`.
5. A block with no `Material` takes its category's default finish: Furniture and Doors draw a grey wood grain over every part, so white doors, pictures and fabric look like dirty timber. Give painted and manufactured blocks a plain file material (`render_colour #ffffff`, `glow 0.2`), timber pieces a timber set, roof tile blocks `roof_tile_concrete`, board blocks a timber floor set with `roughness 0.85`.
6. Pale materials go grey away from the sun: `glow` 0.2 to 0.45 keeps them pale. Relief on flat paint reads as dirt. The repeat of a texture shows on large surfaces.
7. Look: recipe (n). A Form takes the `Material` row too; a plain colour material showed (recipe (p)).

## (p) A freeform surface: three curves, a loft, panels, a material
Played on a copy of the Architectural template. The element categories are `Freeform Curve` and `Form`. Safe course: send the curve calls with a floor plan in front (recipe (d) gives the id form); the Revolve call of step 4 was played so. An answer with `changed` empty wrote nothing: keep a plan in front and end any standing tool first. A tool left standing is ended by a carrier step with `keys Escape Escape` (step 5). The commands are on the Freeform tab's Form panel (the command list files them under tab `Structural`, panel `Form`). Step keys: `ribbon:Massing & Site:Revolve` pressed the tool and UNION answered "Click the axis start". A draw mode, where a tool has several, is set on the options strip in its ribbon step (recipe (t)).
1. Curve 1. Options: `Degree` 1, 2 or 3 (default 3); `Interpolate` yes (the curve passes through the points) or no (they are control points); `Level` (label Storey); `Offset` (mm above the level). The tool's prompt is "Click control point 1 of at least 4". The answer is `{"changed":[{"category":"Freeform Curve","id":"deea7bc2...","kind":"insert","table":"element"}],"text":"Freeform Curve: 5 point(s)"}`. (The first play sent each point with a third number 0, `[0,0,0]`; two-number points were played with other coordinates.)
    commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true},"points":[[0,0],[3000,1500],[6000,-1000],[9000,800],[12000,0]],"finish":true}
2. Curve 2 at Level 1 (drew at 3000), and curve 3 at Level Ground with Offset 1500. Height is set with `Level` and `Offset`. Level Ground with Offsets 2400, 3400 and 2700, five points each, was also played, and the three curves lofted into one Form.
    commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true,"Level":"Level 1"},"points":[[0,4000],[3000,6500],[6000,3500],[9000,5200],[12000,4000]],"finish":true}
    commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true,"Level":"Ground","Offset":1500},"points":[[0,8000],[3000,9000],[6000,7500],[9000,9200],[12000,8000]],"finish":true}
Read back: `element_get {"id":"<curve id>"}` answers `"params":{"Control Points":5,"Degree":3,"Interpolate":true,...}`; `elements_query {"category":"Freeform Curve"}` lists them.
3. Loft: select the curves in order, then run it. Points do not pick curves: with no selection the call answers `cannot proceed: Select the Freeform Curves to loft through, in order, then press Enter`.
    selection_set {"ids":["<curve 1>","<curve 2>","<curve 3>"]}
    commands_run {"name":"Loft"}
Read `document_info {"categories":true}` (`"Form": 1`) or `elements_query {"category":"Form"}`; do not send the call twice. `element_get` on the Form: `"params":{"Control Net U":3,"Control Net V":7,...}`; three curves at Offsets 2400, 3400 and 2700 read V 5. The net size depends on the point count of the curves.
4. Revolve and Sweep. The axis points are the start and end of the axis; with the profile selected and no points the call answers `Revolve: 0 point(s)` and writes nothing. With no selection: `cannot proceed: Select the profile curve to revolve, then press Enter` and `cannot proceed: Select the rail curve, then the section curve, then press Enter`. Loft, Sweep and Revolve also name Make-tab block-editor commands; `commands_run` by name ran the Freeform ones.
    selection_set {"ids":["<profile curve>"]}
    commands_run {"name":"Revolve","options":{"Angle":360},"points":[[20000,-2000],[20000,2000]],"finish":true}
    selection_set {"ids":["<rail curve>","<section curve>"]}
    commands_run {"name":"Sweep"}
5. Panels. Options of the command: U (12), V (20), U Grid, V Grid, Pattern (rect, diamond, hex), Inset (20), Max Warp (20). The tool stayed standing and took the next drawing call's points: end it with the zoom step, which ends any standing tool.
    selection_set {"ids":["<form id>"]}
    commands_run {"name":"Form Panels","options":{"U":8,"V":12,"Pattern":"diamond"}}
    steps_run {"steps":["chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —"]}
6. A material on a Form. The Form takes the `Material` row (`element_get` then shows `"Material":"Play White"`). A plain colour material showed in the Realistic view. Look at the picture before you say what a Form shows. (A block, door or window takes a texture through its Material row: recipe (o).)
    ops_run {"name":"materials","lines":["op:add material name=\"Play White\"","op:set material name=\"Play White\" key=render_colour value=#f4f1ea","op:set material name=\"Play White\" key=glow value=0.2","op:add material library=copper name=\"Play Copper\"","op:set id=<form id> key=Material value=\"Play White\""]}
7. The picture: `view_activate {"view":"{3D}"}`, the Display Options step and `view_camera {"fit":true,"azimuth":125,"pitch":-24}` of recipe (n), then `view_image {"window":"main"}`.

## (s) A gable roof on four walls (Roof tool, Pick Walls, Defines Slope)
Played on a copy of the Architectural template. Four walls stand on Ground (a rectangle 8000 x 5000), a plan view is in front, and one `steps_run` call picks the walls with the Roof tool in its Pick Walls draw mode. The picture shows a gable roof: two sloping planes over the long walls, a 400 overhang, upright open gable ends over the short walls.
1. The walls: four `op:add wall` lines round the corners (30000,20000) (38000,20000) (38000,25000) (30000,25000), each `op:add wall from=<point> to=<point> level=Ground height=2700`. `height` is the wall's own height in mm, measured from its level: a wall on Level 1 with `height=2700` starts at 3000.
2. The plan in front, by its id (a name two views share is refused, recipe (d)):
    views_list {"kind":"Floor Plan"}
    view_activate {"view":"<Ground floor plan id>"}
3. One call, four steps. Pick the walls IN LOOP ORDER, one pick on each wall's line, and switch the slope on the options strip for each edge: an edge with Defines Slope=no does not slope, which makes a gable end.
    steps_run {"steps":[
     "ribbon:Architecture:Roof · picks (34000,20000) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=400 · expect —",
     "chrome:Canvas Zoom to Fit · picks (38000,22500) · keys — · fields Options Strip: Defines Slope=no · expect —",
     "chrome:Canvas Zoom to Fit · picks (34000,25000) · keys — · fields Options Strip: Defines Slope=yes · expect —",
     "chrome:Canvas Zoom to Fit · picks (30000,22500) · keys Return · fields Options Strip: Defines Slope=no · expect Roofs +1"]}
Every step green. The last: `keys: Return (tool Roof -> no tool) | expect 'Roofs +1': [green] Roofs 0 -> 1 (+1, expected +1)`. The first step presses Roof; the strip's fields are applied BEFORE the picks of the same step. Steps 2 to 4 are carrier steps: while a tool stands, `chrome:Canvas Zoom to Fit` carries more picks, keys and strip fields to it and leaves it standing. The Pick Walls options are `Defines Slope`, `Overhang` and `Extend to wall core`.
4. Loop order. Picked in another order (the two long walls first, then the two short ones) the sketch did not close: `cannot proceed: the sketch is not closed -- its open end is at (30000, 19500) mm`. Pick the walls round the loop.
5. Lift and pitch. The roof is made at its level (Base Offset 0). Lift it and set its pitch afterwards. The roof's base is its eave edge, out at the overhang, so lift by the wall height LESS Overhang x tan(Slope): 400 mm at 35 degrees is about 280 mm. Played: with `by=(0,0,2700)` and Slope 35 `element_get` read `"Base Offset": 2700, "Slope": 35`, and in the picture the roof stood about 280 mm above the 2700 walls; with Base Offset 2500 it sat on the walls with no gap seen. The call for the lift that sat:
    ops_run {"name":"lift roof","lines":["op:move id=<roof id> by=(0,0,2500)","op:set id=<roof id> key=Slope value=35"]}
A Roofs element has the rows Slope, Lower Slope, Upper Slope, Break Height, Form (read only), Rafter or Truss, Base Offset, Cutoff Level.
6. A roof from a sketched footprint, with no walls: the first point repeated closes it.
    commands_run {"name":"Roof","points":[[30000,20000],[38000,20000],[38000,25000],[30000,25000],[30000,20000]],"finish":true}
UNION answered `{"changed":[{"category":"Roofs","id":"roof-0acc339c...","kind":"insert","table":"element"},...],"text":"Roof: 5 point(s)"}`. An open sketch answered `cannot proceed: the sketch is not closed -- its open end is at (30000, 19500) mm`. `op:delete id=<roof id>` removed a roof (`state: changed`).
7. Before a picture, finish the roof sketch, or end the tool with the carrier step that sends `keys Escape Escape` (recipe (t), step 5).

## (t) A curved wall and a spline line (draw modes on the options strip)
A tool's draw mode (Line, Rectangle, Circle, the arcs, Spline, Pick Lines, Pick Walls ...) is one of the `draw_modes` that `commands_list {"name":"<command>"}` lists. It is set on the options strip INSIDE the ribbon step that presses the tool, as `fields Options Strip: Draw=<mode>`. The strip's fields are applied BEFORE the picks of the same step: put the mode in the step, never after the picks.
1. A curved wall: `Wall: Architectural` (step `ribbon:Architecture:Wall`) in the Start-End-Radius Arc mode, three picks (start, end, a point on the arc). The draw modes listed for `Wall` are: Line, Rectangle, Inscribed Polygon, Circumscribed Polygon, Start-End-Radius Arc, Ellipse, Partial Ellipse, Pick Lines, Pick Faces.
    steps_run {"steps":["ribbon:Architecture:Wall · picks (50000,6000) (56000,6000) (53000,8000) · keys Escape Escape · fields Options Strip: Draw=Start-End-Radius Arc · expect Walls +1"]}
Green: `fields: Draw=Start-End-Radius Arc set | picks: ... presses to the tool 3` and `changed=Walls 5>6`.
2. A spline line: Model Line in the Spline mode (the command list calls this tool `3D Line`). The picks are points the spline passes through; `keys Return` ends it.
    steps_run {"steps":["ribbon:Setout:Model Line · picks (50000,12000) (52000,13500) (54000,11000) (56000,12500) · keys Return Escape Escape · fields Options Strip: Draw=Spline · expect —"]}
Green: `fields: Draw=Spline set ... presses to the tool 4` and `changed=Lines 0>1`.
3. A draw mode is set in the tool's ribbon step. Sent as an option of `commands_run`, it is refused in these words:
    commands_run {"name":"Roof","options":{"Draw Mode":"Pick Walls"}}
`cannot proceed: Roof has no option Draw Mode; nothing was written`. An option of another mode answers `cannot proceed: Defines Slope is in Pick Walls mode; the options strip is in Line mode. Set Draw first with steps_run: plan:noop · fields Options Strip: Draw=Pick Walls.` The step that answer names is refused: `plan:noop` answers `plan: plan:noop is not an inventory process`. Set `Draw=` in the tool's own ribbon step instead (step 1 or 2, and recipe (s)).
4. A wrong strip field lists the strip's fields. On the Roof tool in its Line mode:
    fields Options Strip: Nonsense=1
UNION answered `fields: the options strip has no 'Nonsense' (its options: Offset, Radius)`: those are the Line mode's fields.
5. To end a standing tool: `chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —`.

## (u) A spiral stair between two levels
Played on a copy of the Architectural template. A stair by tool takes TWO points, and the Ground floor plan must be in front (the plan's id: recipe (d)).
1. A spiral: the first point is the centre, the second sets where the stair starts. `Multistorey Top Level` gives the rise: the stair climbs from Ground to Level 1.
    commands_run {"name":"draw-stair","options":{"Shape":"spiral","Width":1000,"Inner Radius":200,"Sweep":360,"Level":"Ground","Multistorey Top Level":"Level 1"},"points":[[4000,14000],[5200,14000]],"finish":true}
UNION answered `{"changed":[{"category":"Stairs","id":"stair-1b8c7fdd096539a1","kind":"insert","table":"element"},...],"text":"draw-stair: 2 point(s)"}`.
2. Read it back with `element_get {"id":"<stair id>"}`. It read `"Stair Shape":"spiral","Actual Number of Risers":18,"Actual Riser Height":166.67,"Actual Run Width":1000,"Base Level":"Ground","Top Level":"Level 1","Multistorey Top Level":"Level 1"`, with its location point at [4000,14000]. The picture showed a spiral stair. `elements_query {"category":"Stairs"}` lists the stairs.
3. The command's options: Shape (straight, L, U, winderL, winderU, spiral, sketched), Turn (left, right), Width, Location Line, Offset, Riser, Going, Gap, Inner Radius, Sweep, Begin with Riser, End with Riser, Level, Height, Multistorey Top Level.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
