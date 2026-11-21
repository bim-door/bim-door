# 9. Forms, freeform curves and surfaces (NURBS, spline, loft, sweep, revolve)


UNION has NURBS modelling. A freeform curve (a spline) has a degree (1, 2 or 3) and control points. Loft, Sweep and Revolve turn curves into a surface: the element `Form`, which has a control net. A Form takes panels and a plain colour material.

The ribbon shows Freeform Curve, Loft, Sweep, Revolve, Column on Form and Brace on Form on tab Freeform, panel Form; the command list files them under tab `Structural`, panel `Form`.

In this part:
- Curves: Freeform Curve, the height rule, 3D Line (Model Line) and its draw modes.
- Surfaces: Loft, Revolve, Sweep, reading a Form back; panels and a material on a Form.
- ALBATROSS curve and surface cards.
- A worked sequence: three curves, a loft, panels, a material, a picture.

Look it up:

    commands_list {"name":"Freeform Curve"}
    get_guide {"part":"reference > Commands > Freeform Curve"}

## Freeform curves: NURBS, spline, control points, degree (Freeform Curve, 3D Line, Model Line)

A Freeform Curve is a NURBS curve through points clicked in a plan. It is the rail or profile that Loft, Sweep and Revolve build a surface from. The element category is `Freeform Curve`; its rows are `Degree`, `Control Points` and `Interpolate`.

`commands_list {"tab":"Freeform"}` lists 17 commands (Form Panels, Toposurface, the by-face tools and more); the curve tools sit on tab `Structural`. Look the curve up by name:

    commands_list {"name":"Freeform Curve"}

`commands_list {"name":"NURBS"}` and `commands_list {"name":"Spline"}` answered `count: 0`. A word that finds nothing is not a missing feature: the NURBS tools are the commands Freeform Curve, Loft, Sweep and Revolve.

Draw one, with a plan view in front:

    commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true},"points":[[0,0],[3000,1500],[6000,-1000],[9000,800],[12000,0]],"finish":true}

UNION answers `{"changed":[{"category":"Freeform Curve","id":"deea7bc2...","kind":"insert","table":"element"}],"text":"Freeform Curve: 5 point(s)"}`. Keep the id.

Options:
- `Degree`: "1", "2" or "3" (default "3").
- `Interpolate`: true (default) = the curve passes through the points; false = the points are control points.
- `Level` (the strip calls it Storey) and `Offset` (mm above the level): the height rule below.
- The prompt reads "Click control point 1 of at least 4".

Control points, degree 2, one level up:

    commands_run {"name":"Freeform Curve","options":{"Degree":"2","Interpolate":false,"Level":"Ground","Offset":1500},"points":[[0,-13500],[-800,-12800],[0,-12000],[800,-11200],[0,-10500]],"finish":true}

The height rule: a curve takes its height from `Level` and `Offset`. `"options":{"Level":"Level 1"}` drew the curve at 3000 (Level 1 stands at 3000 in the template). A third number in a point (`[x,y,z]`) was accepted and the curve was still drawn flat at the level: give the height with `Level` and `Offset`. Three curves drawn with `"Level":"Ground"` and `"Offset"` 2400, 3400 and 2700 were lofted into one Form.

Read back:

    element_get {"id":"<curve id>"}
    elements_query {"category":"Freeform Curve"}

`element_get` answers `"params":{"Control Points":5,"Degree":3,"Interpolate":true,...}`. `elements_query` answers its rows under `rows`.

Plan view: An answer with `changed` empty wrote nothing: keep a plan in front and end any standing tool first. `view_activate {"view":"Ground"}` answered `cannot proceed: 2 views answer to 'Ground': Ground (Floor Plan, id 48660e38...) and Ground (Ceiling Plan, id 5cde2487...); name the one wanted by its id; ...`. Take the id from `views_list {}` and activate the floor plan by it.

- The draw mode of any tool is set on the options strip inside the tool's own ribbon step: on the Roof tool the fields part `Options Strip: Draw=Pick Walls` set the mode, and the strip's fields are applied before the picks of the same step. Choose the draw mode in the step, not in `commands_run`: `"Draw Mode":"Pick Walls"` in `options` answered `cannot proceed: Roof has no option Draw Mode; nothing was written`. A spline through four picks, Model Line with `Draw=Spline`:

        steps_run {"steps":["ribbon:Setout:Model Line · picks (50000,12000) (52000,13500) (54000,11000) (56000,12500) · keys Return Escape Escape · fields Options Strip: Draw=Spline · expect —"]}

  The step was green: `fields: Draw=Spline set ... presses to the tool 4`, and `changed=Lines 0>1`. `keys Return` ends the spline; the two Escapes end the tool. The arc and the other draw modes are reached the same way: the step `Draw=Start-End-Radius Arc` on `ribbon:Architecture:Wall` (it presses `Wall: Architectural`) drew a curved wall. The played recipes are in part 14 (Recipes): (p) a freeform surface, (s) a gable roof on four walls, (t) a curved wall and a spline line.

- A spline in a drawing view is a 2D line, not a model curve: step `ribbon:Annotate:Detail Line › Spline`.

## Surfaces through curves: Loft, Sweep, Revolve (NURBS surface, Form, control net)

Loft, Sweep and Revolve each write one `Form` from Freeform Curves. A Form has the rows `Control Net U`, `Control Net V` and `Material`. Steps: `ribbon:Massing & Site:Revolve`.

Each name belongs to two commands: the Freeform one (tab `Structural`, panel `Form`) and a Block Editor one (tab `Make`, panel `Forms`). `commands_list {"name":"Loft"}` returns both. `commands_run` by name ran the Freeform one each time.

Select the curves first with `selection_set`, then run. Points do not pick curves; they are the axis of a Revolve.

Loft: a smooth surface through the curves, in the order selected:

    selection_set {"ids":["<curve 1>","<curve 2>","<curve 3>"]}
    commands_run {"name":"Loft"}

Three curves gave one `Form` with `"Control Net U":3,"Control Net V":7`. The net size depends on the points of the curves: three five-point curves at `Level` Ground with `Offset` 2400, 3400 and 2700 gave `Control Net V` 5. With nothing selected: `cannot proceed: Select the Freeform Curves to loft through, in order, then press Enter`.

Sweep: the rail curve first, then the section curve. The two curves of that play:

    commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true},"points":[[0,-12000],[4000,-10000],[8000,-13000],[12000,-11000]],"finish":true}
    commands_run {"name":"Freeform Curve","options":{"Degree":"2","Interpolate":false,"Level":"Ground","Offset":1500},"points":[[0,-13500],[-800,-12800],[0,-12000],[800,-11200],[0,-10500]],"finish":true}
    selection_set {"ids":["<rail curve>","<section curve>"]}
    commands_run {"name":"Sweep"}

One more `Form` was written. With nothing selected: `cannot proceed: Select the rail curve, then the section curve, then press Enter`.

Revolve: the profile curve selected, then the two points of the axis. The profile of that play, drawn with three-number points (the z numbers were not used):

    commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true},"points":[[22000,0,0],[23500,0,1500],[22800,0,3000],[23800,0,4500],[22500,0,6000]],"finish":true}
    selection_set {"ids":["<profile curve>"]}
    commands_run {"name":"Revolve","options":{"Angle":360},"points":[[20000,-2000],[20000,2000]],"finish":true}

UNION answers `{"changed":[{"category":"Form","id":"3e554d07...","kind":"insert","table":"element"}],"text":"Revolve: 2 point(s)"}`; the Form read back `Control Net U 9, Control Net V 5`. A plan view was in front. The tool's prompt after the profile is "Click the axis start". With the profile selected and no points the call answers `Revolve: 0 point(s)` and writes nothing: give the axis points. With nothing selected: `cannot proceed: Select the profile curve to revolve, then press Enter`. The ribbon step with the profile selected only starts the tool, which then stands at "Click the axis start":

    steps_run {"steps":["ribbon:Massing & Site:Revolve · picks — · keys Return · fields — · expect —"]}

After either call, read the count and the Form; do not send the call twice:

    document_info {"categories":true}
    elements_query {"category":"Form"}

`document_info` then shows `"Form": 1`. `elements_query` answers `{"category":"Form","count":1,"more":false,"rows":[{"family":"Form","id":"0da7758b...","kind":"Form","level":"","row":7,"type":"Form"}]}`: the row's `id` is the Form's id.

Reading a Form back:

    element_get {"id":"<form id>"}
    params_schema {"category":"Form"}

`element_get` answers `"params":{"Control Net U":3,"Control Net V":7,...}` and, once set, `"Material":"Play White"`. `params_schema` lists 11 rows: Category, Family, Type, Level, GUID, Element Id, Mark, Comments, Design Option, Phase Created, Phase Demolished. The material is written with an op line (next piece).

## On a surface: Form Panels, a material on a Form

Panels on a Form:

    selection_set {"ids":["<form id>"]}
    commands_run {"name":"Form Panels"}

Answer `{"changed":[],"text":"Form Panels: 0 point(s)"}`. A `document_info` sent straight after listed no `Curtain Panels`; they were counted after the next call and the step that ends the tool (below): 240 `Curtain Panels` on the form, a 12 by 20 grid of rectangular panels in the picture. 240 is the DEFAULT 12 x 20. Read the count with `document_info {"categories":true}`.

After Form Panels play this step, which ends any standing tool:

    steps_run {"steps":["chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —"]}

When a command name finds no heading, `commands_list {"name":"<name>"}` gives the same facts.

For many members at computed points, the ALBATROSS gridshell recipe writes braces between points: part 10 (ALBATROSS).

A material on a Form. A Form takes the element `Material` row (`element_get` then shows `"Material":"Play White"`):

    ops_run {"name":"materials","lines":["op:add material name=\"Play White\"","op:set material name=\"Play White\" key=render_colour value=#f4f1ea","op:set material name=\"Play White\" key=glow value=0.2","op:add material library=copper name=\"Play Copper\"","op:set id=<form id> key=Material value=\"Play White\""]}

A plain colour material showed in the Realistic view. `render_colour` and `glow` are among the material keys seen to change the Realistic view; a wrong key lists all 33 keys a material keeps (part 7). Blocks, doors and windows take a texture through their `Material` row (part 8). The set names are the keys of the texture library: `op:add material library=zinc_standing_seam ...` answered `cannot proceed: the library holds no texture set named 'zinc_standing_seam'; nothing was written`. Materials, texture sets and the node graph: part 7 (Materials).

## Geometry by cards: ALBATROSS Curve and Surface groups

ALBATROSS holds cards that make geometry. By the program's own list of card kinds (`albatross_place {"kind":"zzz"}` lists every kind by group): group Curve, 20 kinds (Length, Line, Polyline, Arc, Arc 3Pt, Circle, Curve, Curve Closest Point, Divide, End Points, Evaluate, Explode, Extend, Join, Offset, Point In Curve, Point On Curve, Polygon, Rectangle, Shatter); group Surface, 8 kinds (Area, Boundary, Extrude, Loft, Surface Divide, Surface Evaluate, Surface Offset, Surface Points); group Intersect, 3 kinds (Curve with Curve, Curve with Plane, Solid with Plane). The `Point` card is in the Vector group. `Point` and `Polyline` were placed and wired. Place the card and read its answer. Placing, wiring and the cards that write the model: part 10 (ALBATROSS). `Brace between Points` was played.

## A worked sequence: curves at three heights, a surface, panels, a material, a picture

The net size depends on the point count. Change the points to change the shape.

1. A floor plan in front. Take the plan's id from `views_list {}`:

        views_list {}
        view_activate {"view":"<Ground floor plan id>"}

2. Three curves at Level Ground, at heights 2400, 3400 and 2700. Keep the id from each answer:

        commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true,"Level":"Ground","Offset":2400},"points":[[0,0],[3000,1500],[6000,-1000],[9000,800],[12000,0]],"finish":true}
        commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true,"Level":"Ground","Offset":3400},"points":[[0,4000],[3000,6500],[6000,3500],[9000,5200],[12000,4000]],"finish":true}
        commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true,"Level":"Ground","Offset":2700},"points":[[0,8000],[3000,9000],[6000,7500],[9000,9200],[12000,8000]],"finish":true}

3. Loft them, front to back. The played loft of the three five-point curves read `Control Net U 3, Control Net V 5`:

        selection_set {"ids":["<curve 1>","<curve 2>","<curve 3>"]}
        commands_run {"name":"Loft"}
        elements_query {"category":"Form"}

4. Panels on the Form, then end the standing tool, then read the count (the played run read `"Curtain Panels": 240`):

        selection_set {"ids":["<form id>"]}
        commands_run {"name":"Form Panels"}
        steps_run {"steps":["chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —"]}
        document_info {"categories":true}

5. A material on the Form (the `ops_run` call in "On a surface").

6. The picture. Show the 3D view, set the Realistic look, turn the camera, picture the window (part 6 (See your work)):

        view_activate {"view":"{3D}"}
        steps_run {"steps":["ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; Soft Shadows=yes; Backdrop=Sky; OK= · expect —"]}
        view_camera {"fit":true,"azimuth":125,"pitch":-24}
        view_image {"window":"main"}

Look it up (the first three `commands_list` calls, the Commands call, `params_schema` and `document_info`):

    commands_list {"name":"Freeform Curve"}
    commands_list {"name":"Loft"}
    commands_list {"tab":"Freeform"}
    get_guide {"part":"reference > Commands > Freeform Curve"}
    params_schema {"category":"Form"}
    document_info {"categories":true}

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
