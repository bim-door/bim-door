# 3. The map: what UNION can make and do, from the word you know to UNION's name


In this part: fifteen pieces, one per kind of work. Each line gives the everyday words, UNION's own name for the thing, and the shortest route to it. Read the piece for the work in hand by a word of its heading: `get_guide {"part":"roofs"}`, `get_guide {"part":"NURBS"}`, `get_guide {"part":"schedules"}`.

How to use a line:
1. Take UNION's name from it.
2. Read that command in full, with its prompt, options and draw modes: `commands_list {"name":"<name>"}`.
3. Run it: an op line (part 4), or `commands_run` or a step (part 5).

A word that is in no piece is not a missing feature. Look for it among the command names of part 16, then ask UNION (part 2). This map is long and still not the whole of UNION.

Look it up: `commands_list {}` gives the tabs and their counts; `commands_list {"name":"Level","brief":true}` shows a trade name finding UNION's own (`Storey`).

## Site, levels, grids and setting out (terrain, topo, contours, property line, survey point, true north, storey, landscape, parking, datum)
Levels, plan views, grids, reference planes, terrain, site boundary, location, site imports. Tabs: Setout, Freeform (Site), Views, Manage, Detailing, Insert.

- level, storey, floor level, datum, elevation, RL: `op:add level`, tool `Storey`. Route: ops_run `op:add level elevation=3000 name="Level 2"`; move or rename `op:set id="level-Level 1" key=Elevation value=3600` (id keeps the old name). `commands_list {"name":"Level","brief":true}` answers `Storey`.
- plan view, floor plan, structural plan, reflected ceiling plan, RCP: `op:add view`, `Plans`. Route: ops_run `op:add view kind=plan level="Level 2"` (kind plan, structural, ceiling); step `ribbon:View:Plan Views › Floor Plan · picks — · keys Return · fields New Plan: Levels=Level 2 · expect dialog closed`. Two views share a name (Ground): `view_activate` refuses the name (`cannot proceed: 2 views answer to 'Ground'`) and an op's `view=` takes the floor plan; name the view by its id from views_list, `view=<id>`. North arrow: `op:add symbol at=(-9000,30000) view=<plan id>`.
- typical floor, repeat storey, stack floors, copy up: `op:array`, `Paste › Aligned to Selected Levels`. Route: ops_run `op:array id=<ids> count=12 step=(0,0,3600)`.
- grid, gridline, axis, column grid: `op:add grid`, tool `Gridline`. Route: ops_run `op:add grid from=(0,-2000) to=(0,12000) name=A`.
- curved grid, arc grid, radial grid, grid from lines: `Gridline` modes Line, Start-End-Radius Arc, Center-ends Arc, Pick Lines, Multi-Segment. `Draw=` in the tool's own ribbon step was played on Roof, Wall and Model Line.
- scope box, reference plane, construction plane, work plane: `Extent Box` (Name, Height 3000), `Construction Plane` (Offset), `Set Plane`, `Show Plane`, `Plane View`, dialog `Work Plane`. `commands_list {"name":"Ref Plane"}` answered `Construction Plane`.
- location, latitude, longitude, true north, shared coordinates, base point, georeference: dialog `Location`, `Rotate Project North`, `Rotate True North`, `Mirror Project`, `Specify Coordinates at a Point`, `Acquire Coordinates`, `Publish Coordinates`, `Report Shared Coordinates`, `Relocate Project`, `Place Project Base Point`, `ifc-georef`. `OK=` was played on Display Options.
- roads, footpaths, lawns, verges, driveways: floors on site levels. Route: ops_run `op:add level elevation=<mm> name=<name>`, then `op:add floor boundary=(0,0) (8000,0) (8000,6000) (0,6000) level=<name>`. Name the lowest site level like "Ground": the landscape pad stands there, lower parts are buried.
- trees, shrubs, people, cars, benches, street lights, retaining walls: block categories Planting, Entourage, Parking, Furniture, Lighting Fixtures, Geotechnical, Structural Foundations. Route: library_list {"category":"Planting"}, then `op:place block family=<name> type=<type> at=(x,y) level=<name>`.

Look it up: commands_list {"tab":"Freeform"}, {"tab":"Manage"}, {"name":"Gridline"}; get_guide {"part":"reference > Commands > Toposurface"}; params_schema {"category":"Levels"} (also Grids, Toposolid). Steps: part 5.

## Walls, floors, ceilings, stairs, ramps, railings and rooms (curved wall, arc wall, slab, spiral stair, area, shaft)

- wall, partition: `op:add wall`, `Wall: Architectural`, `Wall: Structural`. Route: ops_run `op:add wall from=(0,0) to=(8000,0) level=Ground`; by picks: `ribbon:Structure:Wall` (`Wall`) and `ribbon:Architecture:Wall` (`Wall: Architectural`), both green.
- wall height, top, base offset, location line: rows Unconnected Height, Base Offset, Top Offset, Location Line. Route: `op:set id=<wall> key="Unconnected Height" value=3120`; set Base Offset after the height. `height=` on `op:add wall` is the wall's own height from its level: with `level="Level 1" height=2700` the wall stands at z = 3000.
- curved wall, arc wall, circular wall, polygon wall: `steps_run {"steps":["ribbon:Architecture:Wall · picks (50000,6000) (56000,6000) (53000,8000) · keys Escape Escape · fields Options Strip: Draw=Start-End-Radius Arc · expect Walls +1"]}` (start, end, a point on the arc).
- wall type, layers, wall colour: types_list {"category":"Walls"}; `type_set {"category":"Walls","type":"Generic 200mm","key":"Layer 1 Material","value":"Play White"}` answers the layers. Set every layer: Realistic draws the structure layer. Change a wall's type: `param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}` answered `{"changed":1,"elements":1}`; `op:set ... key=Type` is refused. A new type: `type_duplicate`, `type_set` first.
- split wall, trim, extend, align, parallel wall, move, copy, mirror, pin, delete: `op:delete`, `op:move`.
- floor, slab: `op:add floor`. Route: ops_run `op:add floor boundary=(0,0) (8400,0) (8400,8400) (0,8400) level="Level 1" type="Concrete Slab 200 + Tile"`; a sketch is step `ribbon:Structure:Floor`, picks round the outline, then `contextual:Finish` (part 5).
- sloping floor: `Slope Arrow`, `Span Direction`, `Add Point`, `Add Split Line`, `Modify Sub Elements`, `Pick Supports`, `Reset Shape`. A floor from `op:add floor` comes out flat.
- ceiling, suspended ceiling: `op:add ceiling`, `draw-ceiling`, `Sketch Ceiling`, `Edit Boundary (ceiling)`, `Ceilings/Slope Arrow`, `draw-ceiling-rcp`. Route: ops_run `op:add ceiling boundary=(0,0) (8000,0) (8000,6000) (0,6000) level="Level 1" height=2500`.
- stair, staircase: `op:add stair`. Route: ops_run `op:add stair from=(0,0) to=(6000,0) level=Ground top="Level 1" width=1200`.
- L-shaped, U-shaped, winder, spiral, sketch stair, riser, going, ramp, switchback: `draw-stair`, `draw-stair-settings` (dialog `Stair`; reference: `Stair Settings`), `Edit Stairs`, `draw-ramp`, `draw-ramp-settings` (dialog `Ramp`). A spiral takes two points, plan in front: `commands_run {"name":"draw-stair","options":{"Shape":"spiral","Width":1000,"Inner Radius":200,"Sweep":360,"Level":"Ground","Multistorey Top Level":"Level 1"},"points":[[4000,14000],[5200,14000]],"finish":true}`; the first point is the centre, the second sets where it starts.
- railing, balustrade, handrail: `op:add railing`, `Railing`. Route: ops_run `op:add railing points=(0,5000) (6000,5000) (6000,8000) level=Ground`; on a stair `op:add railing host=<stair id>` (no level=) answers two rails.
- room, area, space, zone, room tag: `op:add room`, `Room`, `Room Separator`, `Room Tag`, `Area Boundary`, `Area (area plan)`, `views-areas`, `Space`, `Zone`, `Measure Area`. Route: `op:add tag id=<id> view=<plan id> leader=no`.

Look it up: commands_list {"tab":"Structural"}, {"tab":"Architecture"}; get_guide {"part":"reference > Commands > draw-stair"}; params_schema {"category":"Walls"} (also Floors). Steps: part 5.

## Roofs, openings, doors, windows and curtain walls (gable, hip, dormer, skylight, fascia, gutter, mullion, facade, glazing)
- gable roof, gable end, rake, eaves overhang: `Roof` (options `Overhang`, `Defines Slope`, `Extend to wall core`). Four steps, walls picked round the loop; first step: `ribbon:Architecture:Roof · picks (34000,20000) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=400 · expect —`; full call: part 14 (Recipes), recipe (s). Picture: a gable. Lift: the roof's base is its eave edge, out at the overhang: lift by the wall height less Overhang x tan(Slope). Overhang 400, Slope 35: Base Offset 2700 stood about 280 mm above 2700 walls; 2500 sat on them with no gap seen. `commands_list {"name":"Gable"}` answered `count: 0`.
- roof from a drawn outline: `commands_run {"name":"Roof","points":[[30000,20000],[38000,20000],[38000,25000],[30000,25000],[30000,20000]],"finish":true}`.
- hip roof, flat roof, roof deck, parapet roof: `add roof`. `op:add roof boundary=(0,0) (8000,0) (8000,6000) (0,6000) level="Level 1" slope=45`; no `slope` = hip of 30 degrees; `slope=0` = flat. Later: `op:move id=<roof id> by=(0,0,2700)` (the wall height; less with an overhang), `op:set id=<roof id> key=Slope value=35`
- dormer, roof hole, rooflight hole, skylight: `Roof Cut-out` (button Dormer, step `ribbon:Architecture:Dormer`) is a sketch tool; `commands_list {"name":"Dormer"}` finds it and `Skylight` answered `count: 0`; the Dormer step with five picks closing a rectangle and `Draw=Line` pressed the tool and UNION said `cannot proceed: no roof under the click to host the dormer on`, then `contextual:Finish` answered `cannot proceed: sketch has no loops`.
- roof truss, king post, rafter, purlin, ridge beam: `Truss`, `Edit Profile (truss)`, `Attach Top/Bottom`, `Framing Layout`. Rafter: `op:add beam`, `op:set id=<beam> key="Start Level Offset" value=1200`
- roof build-up, tile, metal deck, green roof: `type_set` key `Layer <n> Material` on every layer (Realistic draws the structure layer's). A roof's type changes with `param_set` key `@type`, as a wall's does.
- door, window, doorway: `add door`, `add window`. `op:add door wall=<wall id> at=(2000,0)`; `op:add window wall=<wall id> at=(5000,6000) sill=900 type="1800 x 1800"`. One of `at=` or `offset=`; wall id from the wall line's `made`; `flip=yes`, `hand=yes`.
- door or window by click: `Door`, `Window`. `ribbon:Architecture:Door · picks (2000,0) · keys Escape Escape · fields — · expect Doors +1`; `ribbon:Structure:Opening:Window · picks (5000,6000) · keys Escape Escape · fields — · expect Windows +1`.
- library door block, door colour: `op:place block ... host=<wall>` cuts no opening; `op:add door wall=<wall id> at=(x,y) type=<type>` cuts it. Colour: `op:set id=<id,id> key=Material value="<file material>"`.
- door schedule, repeat windows per floor: `schedule_read {"view":"Door Schedule","limit":50}`; `op:array id=<window id> count=18 step=(0,0,3600)`.
- curtain wall, glass facade, storefront: a wall of a Function-Curtain type (`Exterior Glazing`, `Storefront`; template `Curtain Wall` is not glass). `commands_list {"name":"Curtain Wall"}` answered `count: 0` too. Glass-wall calls: part 4 (Fast ops), piece "Materials and types". Grid and panels come with the wall.
- mullion, glazing bar: `Mullion`, one step per face: `ribbon:Architecture:Mullion · picks (16800,25200) · keys Escape Escape · fields Options Strip: Place On=All Grid Lines · expect —`

Look it up: `commands_list {"tab":"Architecture"}`, `get_guide {"part":"reference > Commands > Roof"}`, `params_schema {"category":"Roofs"}`. Draw modes and steps: part 5.

## Freeform curves and surfaces, masses and solid forms (NURBS, spline, loft, sweep, revolve, panels, control points, dome, canopy)
UNION has NURBS curves (element `Freeform Curve`) and NURBS surfaces (element `Form`); `commands_list {"name":"NURBS"}` and `{"name":"Spline"}` answered `count: 0`. `commands_list {"tab":"Structural"}` files `Freeform Curve`, `Loft`, `Sweep`, `Revolve`, `Column on Form`, `Brace on Form` under panel Form; `{"tab":"Freeform"}` lists the rest. A plan view in front is the played route. Worked surface: part 14 (Recipes), recipe (p).

- spline, NURBS curve, curve through points, control-point curve, rail, profile: `Freeform Curve`. Route: `commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true},"points":[[0,0],[3000,1500],[6000,-1000],[9000,800],[12000,0]],"finish":true}` (the first play sent each point with a third number 0, `[0,0,0]`; two-number points were played with other coordinates). `Degree` 1, 2 or 3; `Interpolate` false = control points; `Level`, `Offset` set the height (a point's z does not).
- loft, skin, surface through sections, tower form, vase: `Loft`. Route: `selection_set {"ids":["<curve 1>","<curve 2>","<curve 3>"]}`, then `commands_run {"name":"Loft"}` (curves in order).
- sweep, pipe along a path, rail and section, handrail form: `Sweep`. Route: `selection_set` the rail curve then the section curve, `commands_run {"name":"Sweep"}`.
- revolve, lathe, dome, surface of revolution: `Revolve`. Route: `selection_set {"ids":["<profile curve>"]}`, `commands_run {"name":"Revolve","options":{"Angle":360},"points":[[20000,-2000],[20000,2000]],"finish":true}` (the points are the axis; without them no Form is written).
- panels on a curved surface, diamond or hex facade: `Form Panels`. `selection_set {"ids":["<form id>"]}`, `commands_run {"name":"Form Panels"}` made 240 `Curtain Panels`. The tool stays standing: `steps_run {"steps":["chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —"]}`.
- colour of a Form: `op:set id=<form id> key=Material value="Play White"` (after `op:add material name="Play White"`): a plain colour material showed in the Realistic view. Blocks, doors and windows take a texture through their Material row (part 7).
- read a form back: `element_get {"id":"<id>"}` gives Form rows `Control Net U`, `Control Net V`, `Material`; Freeform Curve rows `Degree`, `Control Points`, `Interpolate`. `document_info {"categories":true}` counts `Form`.
- model line, 3D line, circle or arc or ellipse in the model, spline line, 3D lettering: Spline: `steps_run {"steps":["ribbon:Setout:Model Line · picks (50000,12000) (52000,13500) (54000,11000) (56000,12500) · keys Return Escape Escape · fields Options Strip: Draw=Spline · expect —"]}`
- curved wall, circular floor, elliptical slab, spline outline: `Wall: Architectural` (step `ribbon:Architecture:Wall`) with `Draw=Start-End-Radius Arc`.
- ALBATROSS curve and surface cards: Curve (Line, Polyline, Arc, Circle, Divide, Offset, Join, Evaluate), Surface (Extrude, Loft, Surface Divide, Surface Points, Boundary), Intersect (Curve with Plane, Solid with Plane). Route: `albatross_place {"kind":"Polyline"}`, `albatross_wire`, `albatross_set`.

Look it up: `commands_list {"tab":"Freeform"}`, `commands_list {"name":"Loft"}` (two commands answer), `get_guide {"part":"reference > Commands > Freeform Curve"}`, `params_schema {"category":"Reference Points"}`. Picture of a Form: `view_camera {"fit":true,"azimuth":125,"pitch":-24}` (part 6).

## Structure: columns, beams, braces, trusses, foundations, reinforcement, loads and analysis (footing, rebar, steel, concrete, connection, slab)

- grid, level, storey, model line, spline line: `Gridline`, `Storey`, `3D Line`. Route: `op:add grid from=(0,-2000) to=(0,12000) name=A`; `op:add level elevation=3000 name="Level 2"`. Spline: `ribbon:Setout:Model Line` with `fields Options Strip: Draw=Spline` and `keys Return Escape Escape`; full call: part 14 (Recipes), recipe (t).
- column, post, raking column: `Column`. Route: `op:add column at=(0,0) level=Ground type=310UC158`.
- beam, girder, joist, purlin, sloped beam: `Framing`. Route: `op:add beam from=(0,0) to=(8400,0) level="Level 1" type=530UB82.0`; slope: `op:set id=<beam> key="Start Level Offset" value=1200`, same for `End Level Offset`.
- slab, deck, sloped slab, slab edge: `Floor: Structural`, `Slab Edge`, `Span Direction`. Route: `op:add floor boundary=(0,0) (8400,0) (8400,8400) (0,8400) level="Level 1" type="Concrete Slab 200 + Tile"`.
- structural wall, shear wall, plinth, reveal: `Wall: Structural`, `Wall Sweep`, `Wall Reveal`. Route: `ribbon:Structure:Wall · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys Escape Escape · fields — · expect Walls +4`; its key presses `Wall`.
- change section, structural material: `type_duplicate`, `type_set`. Route: `type_set {"category":"Structural Framing","type":"323.9x10CHS","family":"Circular Hollow Section - Hot-Finished","key":"Material","value":"Stainless Steel Brushed"}`.
- UB, UC, CHS, RHS, glulam, bored pile: families `Universal Beam`, `Bored Pile`. Place by `op:place block` (part 8, Blocks).
- structural plan, schedule, tag, dimensions: `op:add view kind=structural level=Ground name="Column Setting-Out Plan"`; `op:add schedule category="Structural Columns" fields=Type,Count,Length name="Column Schedule by Type" itemize=no`; `Tag All`, `annotate-autodim`.
- NURBS, loft, sweep, revolve: `Freeform Curve`, `Loft`, `Sweep`, `Revolve`, `Column on Form`, `Brace on Form`. Loft: `selection_set` the curves, then `commands_run {"name":"Loft"}`; full call: part 14 (Recipes), recipe (p).
- gridshell, diagrid, lattice: ALBATROSS `Brace between Points`, `Series`, `Expression`. Route: `albatross_place {"kind":"Brace between Points","at":[960,160]}`, wire, set `run` true.

Look it up: `commands_list {"tab":"Structural"}`, `library_list {"category":"Structural Framing"}`, `params_schema {"category":"Structural Framing"}`, `get_guide {"part":"reference > Commands > Rebar"}`. Detail: parts 4 (Fast ops), 5 (Commands), 9 (Forms), 10 (ALBATROSS).

## Building services: ducts, pipes, cable trays, conduit, equipment, fixtures and systems (HVAC, plumbing, electrical, lighting, sprinkler, mechanical, clash check)

- duct, HVAC, supply air, return air, exhaust: `Duct` (op add duct). Route: `ribbon:Systems:Duct · picks (1000,1000) (5000,1000) · keys Escape Escape · fields — · expect Ducts +1`; sized: `fields Options Strip: Width=300; Height=150; Middle Elevation=2700; System Type=Return Air`.
- diffuser, grille, air handling unit, boiler, thermostat: `Diffuser` (op add terminal), `Plant Item` (op add equipment), `Mechanical Control Device` (Type). Route: `ribbon:Systems:Air Terminal · picks (3000,1000) · keys Escape Escape · fields — · expect Air Terminals +1` on a duct. Ceiling diffuser: `op:place block family="<family>" at=(3000,1000) level=Ground host=<ceiling id>`, the id from `elements_query {"category":"Ceilings","fields":["id","type"],"limit":100}`; part 8 (Blocks), piece "Place a block". A duct runs below it, under the ceiling height.
- count, resize, repeat per floor: `document_info {"categories":true}`.

Look it up: `commands_list {"tab":"Services"}`, `library_list {"category":"Mechanical Equipment"}`, `params_schema {"category":"Ducts"}`, `get_guide {"part":"reference > Commands > Duct"}`. Detail: part 4 (Fast ops), 5 (Commands, steps and dialogs), 10 (ALBATROSS).

## Views: plans, sections, elevations, callouts, 3D views, drafting views, legends, filters and view templates (visibility, hide, isolate, crop, scope box, view range, detail level, scale)

Views tab. Step: `key · picks · keys · fields · expect`; empty part —.

- display style, wireframe, shaded, Realistic, shadows: `Display Options`. `steps_run {"steps":["ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; Soft Shadows=yes; Backdrop=Sky; OK= · expect —"]}`. Full call: part 14 (Recipes), recipe (n). `commands_run {"name":"Shaded"}` sets Display Style to Shaded.
- 3D view, isometric, orbit: `Model View` (`{3D}` in `view_activate`; id `view-3d`). `view_activate {"view":"{3D}"}`, `view_camera {"fit":true,"azimuth":125,"pitch":-24}`. `op:add 3d view`.
- cutaway, section box: `Clip Box`. `selection_set` the elements, then `commands_run {"name":"Clip Box"}`; off: `op:set id=view-3d key="Section Box" value=no`.
- view rows, scale, detail level: `element_get {"id":"view-3d"}` reads. `op:set id=<view id> key=Scale value=1:200`, `op:set id=<view id> key="Detail Level" value=Coarse` write.
- floor plan, structural plan, RCP: `Plans`. `op:add view kind=plan level="Level 8" name="Level 8 Plan"` (kind plan, structural, ceiling); step `ribbon:View:Plan Views › Floor Plan`. Floor and ceiling plans share a name: `view_activate` refuses it with `cannot proceed: 2 views answer to 'Ground': ...; name the one wanted by its id`, and an op's `view=` takes the floor plan; send the id from `views_list`.
- section, elevation: `Section`, `Elevation`. `op:add section from=(50000,-2000) to=(56000,-2000) depth=8000 name="Probe Section" view=48660e38a721430d899d5d8a96df3bec`, `op:add elevation` takes `view=<id>` the same way; full call: part 14 (Recipes), recipe (m).
- auto sections, every grid: `views-autosections`. `view_activate` a plan, then `commands_run {"name":"views-autosections","options":{"Sections":true,"Elevations":true,"Sheets":true,"Grids":"all"}}`.
- drafting view, 2D detail: `2D View`, dialog `New Drafting View`. `op:add drafting view name="Roof Junction" scale=1:10`.
- duplicate view: `Copy View`. `view_activate` the plan, then `commands_run {"name":"Copy View"}`.
- hide category: `op:set view view="Level 8 Plan" hide="Structural Framing,Structural Columns"`; also `show=`, `map=plain:lightgrey`. 3D level and grid lines: `op:set view view=view-3d hide=Levels,Grids`.
- view filter: `View Filters`. Once `steps_run {"steps":["view-filters:add:Braces:Structural Framing;Structural Usage;equals;Other:hide=1 · picks — · keys — · fields — · expect —"]}`, then per open plan `view-filters:apply:Braces`.
- list, open, delete views, zoom, tabs: `views_list {"kind":"Floor Plan"}`, `view_activate {"view":"<floor plan id>"}` (see floor plan, above), `op:delete id=<view id>`.
- picture, put on sheet, crop: `view_image {"window":"main"}`. `op:place view view="Level 8 Plan" sheet=A104 at=(115,140)`, add `scale=1:200 crop=(x0,y0) (x1,y1)`.

Look it up: `commands_list {"tab":"View"}`, `commands_list {"name":"<name>"}`, `get_guide {"part":"reference > Commands > <name>"}`. Detail: parts 6, 14 (m).

## Annotation: dimensions, text, tags, keynotes, symbols, detail lines and filled regions (hatch, leader, note, spot level, insulation, revision cloud)

Detailing tab (door tab `Annotate`, 51 commands). Drawn in one plan, section, elevation or drafting view. Step: `key · picks · keys · fields · expect`; empty part —.

- text, note: `Text` (options Type, Scale, Height, List, Leader). `op:add text at=(0,-10) view="General Notes" text="1. All dimensions are in millimetres."`.
- leader: `ribbon:Annotate:Text · picks (145,-500) (500,-500) · keys S T U D Space 1 4 5 Return Escape · fields Options Strip: Leader=on · expect Text Notes +1`; first pick is the arrow tip.
- dimension, aligned: `Aligned`. `ribbon:Annotate:Aligned · picks (0,-800) (145,-800) (72,-950) · keys Escape Escape · fields — · expect Dimensions +1`; picks on element ends, the third places.
- dimension string, dimension all: `op:add dimension chain points=(0,-1000) (8400,-1000) (16800,-1000) view=<plan id> offset=-3000` (points on live elements); `view_activate` the plan first; `commands_run {"name":"annotate-autodim"}` dimensions a whole plan.
- tag, door tag, mark: `Tag`. `op:add tag id=<element id> view=<plan id> leader=no`. Tag all: `view_activate` the plan, then `commands_run {"name":"Tag All","points":[[16800,12600]]}` with ONE point; if the door stays busy, `chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect nothing selected`.
- north arrow, scale bar, tolerance: `op:add symbol at=(-9000,30000) view=<plan id>`.
- detail line, rectangle, circle, arc, spline: `2D Line`. `ribbon:Annotate:Detail Line › Rectangle · picks (0,-800) (145,-90) · keys Escape Escape · fields — · expect Lines +4`. `op:add detail line points=(x,y) (x,y) view=<view>`; modes Circle, Ellipse, Spline, Pick Lines, Inscribed Polygon, Start-End-Radius Arc: `fields Options Strip: Draw=<mode>` in its ribbon step, part 14 (Recipes), recipe (t): Wall and Model Line.
- hatch, filled region, masking region: `Hatch`. `ribbon:Annotate:Region › Filled Region · picks (-60,-800) (0,-800) (0,-90) (-60,-90) (-60,-800) · keys — · fields — · expect nothing selected`, then `contextual:Finish · picks — · keys — · fields — · expect Filled Regions +1`.
- insulation, batt: `ribbon:Annotate:Insulation · picks (72,-780) (72,-100) · keys Escape Escape · fields Options Strip: Width=100 · expect Detail Items +1`.
- read back: `elements_query {"category":"Dimensions","limit":50}`, `document_info {"categories":true}`.

Look it up: `commands_list {"tab":"Annotate"}`, `commands_list {"name":"<name>"}`, `get_guide {"part":"reference > Commands > <name>"}`. Detail: part 14 (e), (m).

## Blocks, materials, textures and the material node graph (family, furniture, plants, trees, brick, timber, glass, paint, colour, variation, repeat)
Blocks, types, Block Editor, materials, 67 photograph texture sets, Material cards.

- texture on a block, door, window: the element's `Material` row. `ops_run {"lines":["op:set id=<id>,<id> key=Material value=\"<file material>\""]}`. One texture per element. A Structural Framing block: set the material on its type. With no Material, Furniture and Doors draw grey wood grain: use a plain material (`render_colour` #ffffff, `glow` 0.2); recipe (o) of part 14 (Recipes).
- new material, colour, paint, metal, bump, glow: `ops_run {"lines":["op:add material name=\"X\"","op:set material name=\"X\" key=render_colour value=#7E9AAE"]}`. Keys that reach the Realistic view: texture, texture_size, texture_rotation, render_colour, roughness, metallic, bump, transparency, glow. A wrong key lists the 33 keys a material keeps.
- photo texture, brick, timber, concrete, steel, stone, roof tile, lawn, repeat, tiling: 67 sets, photographs in their own colours. `op:add material library=<set> name="X"`. A large wall or lawn shows the texture's tile; `texture_size` (mm) sets it (part 7). Nine sets (names: part 7) draw brightness only: give `render_colour`. Your own set: part 7.
- glass, see-through, wall, floor, roof finish, layers, beam material: `op:set material name="Facade Glass" key=transparency value=0.6` (transparency runs 0 to 1); `type_duplicate {"category":"Walls","type":"Exterior Glazing","name":"Blue-grey glass"}`; `types_list` reads layers. A layer's material: `type_set {"category":"Walls","type":"Generic 200mm","key":"Layer 1 Material","value":"Play White"}` answers the type's `layers`; recipe (o). The STRUCTURE layer is drawn: set every layer.
- change type, retype: `param_set {"ids":["<id>"],"key":"@type","value":"<type name from types_list>"}` answered `{"changed":1,"elements":1}` on a wall and a roof. `op:set id=<id> key=Type` is refused (`A Roof has no parameter 'Type'`). A wall on a new type: `type_duplicate`, `type_set` Layer n Material, `param_set` `@type`.
- place a block, furniture, tree, steel section: `op:place block family="<name>" type=<type> at=(0,-20000) level=Ground rotation=0`; ceiling-hung: `host=<ceiling id>`; an unknown category answers 'load it first'.
- door, window in a wall (cuts the opening): `op:add door wall=<wall id> at=(2000,0)`, `op:add window wall=<wall id> at=(5000,6000)`; tools `Door`, `Window`. `place block ... host=<wall id>` cuts no opening.
- block colour per part, fabric, leather: about 67 material words (Paint - White, Melamine, Leather, Foliage). `type_set` on the block type, key its material parameter. Another word falls to pale timber.
- block instance parameter: `op:set id=<id> key=Length value=<v>` (part 8).
- find a block, library, list placed: `library_list {"category":"Furniture","limit":5}` answers `count`, `more`, `names`, `next`, `total` (204); `library_list {}` answers `library.list needs a category`.
- steel section type: place its block once, `op:delete` the made id; the type stays.
- hatch, fill pattern, object styles: `steps_run {"steps":["ribbon:Manage:Additional Settings › Fill Patterns · picks — · keys Return · fields Fill Patterns: Patterns=Gravel · expect dialog closed"]}`, `ribbon:Manage:Object Styles` (fields Object Styles: Categories=<name>).
- Materials window, IFC materials, procedural texture, import mesh: `Materials`, `IFC Materials`, `render-textures`, `Unpack Import`; Import is the person's press.
- node graph, shader, PBR, normal map, weathering, relief: `albatross_place {"kind":"Real-World Size"}`, `albatross_set`, `albatross_wire`, `albatross_graph`, `albatross_delete`. Cards: Real-World Size, Base Colour Map, Normal Map, Roughness Map, Height Map, AO Map, Multiply Map, Flatten Normal, Shading Colour, Surface Pattern, Cut Pattern, Pattern Colour, Relief, Rock Scatter, Dirt, Edge Wear, Moss and Stain, Wetness, Material Output. Place and wire.

Look it up: `commands_list {"tab":"Make"}`, `params_schema {"category":"<category>"}`, `types_list {"category":"<category>"}`, `library_list {"category":"<category>"}`; `get_guide {"part":"guide > 7"}` (Materials), `guide > 8`, `guide > 10`.

## Pictures, display styles, renders, sun, cameras, PLAY MODE and films (realistic image, shadow, night, walkthrough, video, cutaway, section box)
Ribbon: View tab.

- realistic view, shadows, sky, no black edge lines, wireframe, hidden line: `Display Options`. 3D view in front: `steps_run {"steps":["ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; Soft Shadows=yes; Backdrop=Sky; OK= · expect —"]}`. Style: Outline, Hidden, Shaded, Consistent Colors, Realistic; a new 3D view opens in Hidden; `commands_run {"name":"Shaded"}` sets the 3D view's `visual_style` row to Shaded. Recipe (n) of part 14 (Recipes).
- see-through, sketch lines, depth fade, sun angle: All rows: `get_guide {"part":"reference > Dialogs > Display Options"}`.
- picture, check my work, orbit, zoom to fit: `views_list`, `view_activate {"view":"{3D}"}`, `view_camera {"fit":true,"azimuth":125,"pitch":-24}`, `view_image {"window":"main","width":2048}`. Azimuth 90 puts the camera at -y, 180 at +x, 0 at -x, 270 at +y; `ids` frames elements. 'Still building' for good: `view_image {"window":"main"}` with no view.
- picture at a size, cutaway: `view_image {"window":"main","width":2048}` (the bullet above); the cutaway is the section box bullet below.
- section box, clip box, roof off, see inside: `selection_set {"ids":["<id>"]}` then `commands_run {"name":"Clip Box"}`; off: `op:set id=view-3d key="Section Box" value=no`; read a view's rows: `element_get {"id":"view-3d"}`.
- black lines labelled Roof, Level 1, Ground (level and grid lines): `ops_run {"name":"hide level lines in 3D","lines":["op:set view view=view-3d hide=Levels,Grids"]}` hides them in the live 3D view. Background: add `map=plain:lightgrey` to that line; scale, detail level: the views piece.
- zoom in a plan: `chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —` (also ends any standing tool).
- hide, isolate, filter, override, crop, scope box: `op:set view view="Level 8 Plan" hide="Structural Framing,Structural Columns"`; steps `view-filters:add:<name>:<category>;<parameter>;<operator>;<value>:hide=1`, `view-filters:apply:<name>`.

Look it up: `commands_list {"tab":"View"}`, `commands_list {"tab":"Views"}`, `commands_list {"name":"<command>"}`, `get_guide {"part":"reference > Commands > <name>"}`; `get_guide {"part":"guide > 6"}` (See your work); 3D on a sheet: the sheets piece; save as image, PDF, GLB: the import and export piece.

## Schedules, sheets, title blocks and printing (quantity takeoff, drawing list, door schedule, PDF, plot, paper size)
Views tab: Schedules, Sheet Composition.

- schedule, door/window/column schedule, quantities, count by type: `op:add schedule`. Route: ops_run `op:add schedule category="Structural Columns" fields=Type,Count,Length name="Column Schedule by Type" sortby=Type itemize=no`; no itemize = one row an element. Sheet A501 of the template already carries Door Schedule, Window Schedule and Room Schedule: give a new schedule another name (a taken name is refused).
- read a schedule, list schedules: `schedule_read {"view":"Door Schedule","limit":50}`; `views_list {"kind":"Schedule"}`; CSV: write it from `rows`.
- new sheet, paper size A0-A4, ANSI_B-E, ARCH_C-E1, None, sheet register, look at a sheet: ops_run `op:add sheet number=A104 name="Level 8 Plan" titleblock=A1`; `sheets_list {}`; `view_activate {"view":"A104"}`; `view_image {"view":"A104","window":"main","width":1100}`. Tool `Drawing` (label Sheet) opens New Sheet.
- title block text, project name, client, issue date, status: `steps_run {"steps":["ribbon:Manage:Project Information · picks — · keys — · fields Project Details: Project name=<name>; OK= · expect —"]}`.
- rename sheet, drawn/checked by, sheet issue date, delete sheet, copy a sheet: `steps_run {"steps":["ctx:sheet:Rename · picks — · keys Return · fields Project Tree: view=A104 - Level 8 Plan; Drawing: Drawn By=<initials>; Sheet Issue Date=<date> · expect —"]}`; `op:delete sheet sheet=A000`.
- put a view on a sheet, viewport, crop, 3D, schedule on sheet: `op:place view view="Level 8 Plan" sheet=A104 at=(115,140)`; add `scale=1:100 crop=(-10000,-8000) (40000,32000)`; `view=view-3d`; `table_width=600 text_size=6`.
- remove or move a viewport, swap its view, crop: `op:remove view view="Site Plan" sheet=A100`.
- view scale, copy a view, auto sections and elevations with sheets: `op:set id=<view id> key=Scale value=1:200`; `Copy View` and `views-autosections`: the views piece.
- general notes, cover text: a drafting view with `op:add text`, placed like any view (views and annotation pieces).
- sheet list, drawing register, view list, material takeoff, steel take-off, graphical column/wall schedule, note block: `Schedules › <name>` (also `Schedules › Schedule/Quantities`). Route: `steps_run {"steps":["ribbon:View:Schedules › Sheet List · picks — · keys — · fields — · expect —"]}`.
- print, plot, PDF set, copies, one file per sheet: Print, `PDF` (File › Output), Export: the person's press; UNION says `cannot proceed: Print needs a person`.

Look it up: `commands_list {"tab":"View"}`; the Schedules › names sit on no tab: `commands_list {"name":"Schedules › Sheet List"}`; `get_guide {"part":"reference > Commands > Schedules"}`; export: the import and export piece.

## Import, export and linked files (IFC, DWG, DXF, PDF, images, point clouds, site data, RVT, SKP, 3DM, FBX, OBJ, LandXML, gbXML, STL)
File tab (Import, Export, Print), Insert tab (Import, Link, Load from Library), Manage (Project Location, Share), Freeform (Site), Interoperability. Keys: `file-import:<KEY>` (65, with `auto`), `file-export:<KEY>` (64).

- new, open, save as, close, import, export: the person's press, and so are the keys above. UNION says `cannot proceed: 'Save As' is the person's own control, not UNION AI's; ask the person to press it` (also Open, New, Close, Exit, Print, Export, Import) and `cannot proceed: Print needs a person`; no retry.
- picture of a view, image file at an exact size: `view_image` (the pictures piece, part 3).
- mesh, 3D printing, game and AR files: A GLB holds colour per element and an FBX a diffuse colour per material, no texture image; the model keeps its textures.

Look it up: `commands_list {"name":"<command>"}` (keys and tiles sit on no tab), `get_guide {"part":"reference > Dialogs > Dialog Import"}`; printing: the sheets piece.

## Settings and standards: units, line styles, materials, phases, design options, worksets and parameters (project information, snaps, fill patterns, line weights, purge, transfer standards, shared parameters)
Tabs Manage and Setup. A dialog opens by one step: `steps_run {"steps":["ribbon:Manage:<button> · picks — · keys Return · fields <dialog title>: <field>=<value> · expect dialog closed"]}`; a wrong row lists the valid ones.

- materials, finish, texture, render colour, roughness, glow, library texture set: `Materials`, ops `add material`, `set material`. Route: `ops_run {"lines":["op:add material library=<set> name=\"X\""]}`, then `op:set material name="X" key=<k> value=<v>`; a wrong key answers with all 33 keys a material keeps; seen to change the Realistic view: texture, texture_size, texture_rotation, render_colour, roughness, metallic, bump, transparency, glow. Element: `op:set id=<ids> key=Material value="X"`. Full call: part 14 (Recipes), recipe (o).
- parameters, set parameter, Mark, type parameters, wall layers, duplicate type: `params_schema`, `param_set {"ids":["<door id>"],"key":"Mark","value":"D1"}`, `type_duplicate {"category":"Walls","type":"Exterior Glazing","name":"Blue-grey glass"}`; `type_set {"category":"Walls","type":"Generic 200mm","key":"Layer 1 Material","value":"Play White"}`; then `param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}` puts the wall on the type named in `value`.
- project information, project name, issue date: `Project Details`. Route: `ribbon:Manage:Project Information`, fields `Project Details: Project name=<name>; Client=<name>; Issue Date=<date>`.
- object styles, category line weight, cut weight: `Category Styles` (title Object Styles). Route: `ribbon:Manage:Object Styles`, fields `Object Styles: Categories=Air Terminals` picks a row; columns Projection Line Weight, Cut Line Weight, Line Colour, Line Pattern, Material.
- line styles, dash patterns, hatch, fill patterns, arrowheads: `Line Types`, `Line Widths`, `Dash Patterns`, `Fill Patterns`, `Arrowheads`. Route: `ribbon:Manage:Additional Settings › Line Styles` fields `Line Styles: Styles=Wide Lines` picks a row; likewise `› Line Weights` (`Weights=3`), `› Fill Patterns` (`Patterns=Gravel`), `› Arrowheads` (`Arrowheads=Arrow Filled`).
- display, visibility, view filters, view templates, detail level: calls in the views piece. `Display Options` (3D view in front, fields Style, Show Edges, Silhouette Edges, Shadows, Soft Shadows, Backdrop).

Look it up: `commands_list {"tab":"Manage"}`, `commands_list {"tab":"Setup"}`, `get_guide {"part":"reference > Dialogs > Display Options"}`; parts 5 and 7.

## Change and select: move, copy, rotate, mirror, array, align, trim, join, group, filter and measure (offset, split, extend, pin, delete, undo, redo, scale, stretch, change type, swap type)
Tabs Modify, Manage (Selection, Inquiry), Annotate (Detail). A tool waits for picks: `commands_run {"name":"<tool>","options":{...},"points":[[x,y],...],"finish":true}`

- select, find, pick, selection by id: `elements_query {"category":"Doors"}`; `selection_set {"ids":["<id>"]}` replaces the selection; step `plan:select · picks (-30,-450) · keys — · fields — · expect —`. Cutaway: `selection_set`, then `commands_run {"name":"Clip Box"}`.
- set a value, rename, height, elevation, slope, section box: op `set`. `op:set id="level-Level 1" key=Elevation value=3600`; `op:set id=<wall id> key="Unconnected Height" value=3120`; `op:set id=view-3d key="Section Box" value=no`; `op:set id=<roof id> key=Slope value=35`.
- move, copy, shift, duplicate, paste: ops `move`, `copy`. `ops_run {"lines":["op:move id=<roof id> by=(0,0,2700)"]}`; with an overhang, lift a pitched roof by the wall height less overhang x tan(slope): part 14 (Recipes), recipe (s).
- delete, remove, erase, undo, redo, take back: `Delete`, op `delete`. `ops_run {"lines":["op:delete id=<id,id>"]}`. `steps_run {"steps":["qa:Undo · picks — · keys — · fields — · expect —"]}` takes back your newest call; `qa:Redo · picks — · keys — · fields — · expect —` redoes it; the short `qa:Undo · expect —` is played too.
- array, repeat, pattern: op `array`. `op:array id=<seed> count=5 step=(8400,0,0)`.
- hide, isolate, reveal, zoom to selection: `view_camera {"ids":["<id>"]}` frames them.
- change type, swap type, retype: `param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}`; `element_get` read the new type; a roof took it too. Names: `types_list`. `op:set id=<id> key=Type value=...` is refused (`A Roof has no parameter 'Type'`).
- many changes, node graph: `ops_run`; `batch` makes one undo entry, method names carry a dot (`selection.set`, `param.set`, `commands.run`; full call: part 5, batch).

Look it up: `commands_list {"tab":"Modify"}`, `commands_list {"name":"Break"}` (`{"name":"Level","brief":true}` answered `Storey`; `count: 0` is no missing feature), `get_guide {"part":"reference > Ops grammar"}`; part 4.

## The programs inside UNION: UNION AI and ALBATROSS

Programs open from tiles in the ribbon's app corner; each tile is a command on no tab. Windows: main, viewer, active, build, play, wind, albatross, mule, falcon. Back to the model: `view_activate {"view":"{3D}"}` then `view_image {"window":"main"}`.

- UNION AI window, chat, reply to the person, serve prompts: `gooseClicked`, `falcon_wait`, `falcon_say`. Route: `falcon_wait {"timeout_ms":1000}`. Opened by `commands_run {"name":"gooseClicked"}`, pictured by `view_image {"window":"falcon"}`: tabs CENTRAL and Agents, a box "Ask UNION AI". A refused write: quote UNION's words to the person. Part 11.
- ALBATROSS, parametric, generative design, node editor, gridshell, diagrid: `albatrossClicked`, `albatross_place`, `albatross_set`, `albatross_wire`, `albatross_graph`. Route: `albatross_place {"kind":"series","inputs":{"count":4}}`, then `albatross_graph {}`. Window in front: `view_image` pictures the graph; write `window:"main"` for the model.

Look it up: `commands_list {"name":"<command>"}`; `get_guide {"part":"reference > Commands > muleOrigin"}`. Detail: parts 10, 11.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
