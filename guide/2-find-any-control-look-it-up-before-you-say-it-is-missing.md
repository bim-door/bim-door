# 2. Find any control: look it up before you say it is missing


In this part: where UNION states its counts; the calls that list its commands, dialogs, fields, parameters, types and blocks; the calls that read the open model; the three routes from a name to a run; how to report a gap.

THE RULE: this guide is not the extent of UNION. UNION does nearly every operation you already know. Your job is to look the control up. A control the guide does not show is one you have not found yet. Say "not found in <the lists searched>" and nothing stronger.

Look it up, in this order:
1. Part 16 (Index): the command names by tab and panel, one read.
2. Part 3 (The map): everyday words mapped to UNION's names.
3. `commands_list` with a `tab` or an exact `name`: the command in full. A keyword goes to items 1 and 2.
4. `get_guide` with `reference`: every command, dialog, field, op kind and parameter, exact.
5. `params_schema`, `types_list`, `library_list`: parameter rows, types, blocks.
6. A wrong word on purpose: UNION's refusal lists the valid words.

Look it up: `get_guide {"part":"reference"}`, `commands_list {}`, `params_schema {}`.

## How much UNION holds: where each count stands

| What | Where to read it | What it counts |
|---|---|---|
| Commands by name | `commands_list {}` answers `count`; a call with `tab`, `kind`, `built` or `name` answers `count` for its rows | What `commands_list` answers and `commands_run` takes. `built` false marks a command with no handler. |
| Commands on a tab | `commands_list {}`: `tabs` as `[{tab, count}]`, and `no_tab` | The commands of each tab. The commands that name no tab are menu entries, viewer, wind, layer, program tiles, dialog openers and the `file-import:` and `file-export:` names. |
| Dialogs | the heading `Dialogs (N)` of `get_guide {"part":"reference > Dialogs"}` | The reference part "Dialogs". The program builds further dialogs in code; they are not among them. |
| Parameter rows | `params_schema {}` answers `count` of the categories and each category's `rows`; the heading `Parameters (N categories)` of the reference | The rows of every category. A category answered with `open: true` stores more than its rows list. |
| Op kinds | the heading `Ops grammar (N kinds)` of the reference | Fast-op line shapes (part 4). |
| Blocks | `library_list {"category":"<category>"}` answers `total` | The blocks of the shipped library (part 8). |

- The reference heading `Commands (N)` counts one entry for each key, not one for each command: it differs from the `count` of `commands_list`. They are views of one list: never add them.
- A count is what was listed, never a limit.

## Look-up calls for UNION's own words: get_guide and the reference

`get_guide`: the guide and the reference.

    get_guide {}
The opening, then one line per `##` heading with its size.

Two ways to name a part of the guide. A bare word finds the first heading that holds it anywhere and names the others: `get_guide {"part":"gable"}`. A path names a part by the START of each heading, number and dot first, and each step is searched inside the one before. A word from the middle of a heading does not match in a path: `guide > 4 > schedule` answered `No part of the guide has ... in its heading`; `guide > 3 > Walls, floors` and `guide > 4 > Roofs, stairs` found their pieces. Words match headings only, never the text. If a path finds nothing, send the bare word. A part of up to 24 KB answers whole; a longer part with pieces answers its opening text and a sized list of its pieces. A piece of any part is read alone by a word of its heading.

No match answers `No part of the guide has "<words>" in its heading. Call get_guide with no part for the guide's contents; the reference is a separate document: part "reference".`. UNION's own words may differ slightly.

    get_guide {"part":"reference"}
Six parts with sizes: Writing a C++ add-in (1.7 KB), Methods (24.4 KB), Commands (357.2 KB), Dialogs (157.8 KB), Ops grammar (6.5 KB), Parameters (59.6 KB).

    get_guide {"part":"reference > Commands > Freeform Curve"}
One command in full.

A command's heading is its `name` as `commands_list` prints it; a few commands are filed under another word. When `get_guide {"part":"reference > Commands > <name>"}` finds no heading, `commands_list {"name":"<name>"}` gives the same facts. `reference > Commands > draw-stair-settings` and `reference > Commands > form-panels-dialog` found no heading. Else try the ribbon word: part 16 (Index) gives the tab and panel.

    get_guide {"part":"reference > Dialogs > Display Options"}
One dialog: Title, Buttons (OK, Cancel, Apply), Actions (Save as View Template), then a table Tab, Group, Field, Key, Kind, Limits, Choices, Notes, with the fields Style, Show Edges, Transparency (0-100), Silhouette Edges, Silhouette Line Style, Shadows and more. A dialog heading begins with the word Dialog, so write the address `reference > Dialogs > Dialog <name>`; `Display Options` worked because no earlier dialog heading holds those words. A dialog's Title line is what UNION prints. `Category Styles` prints `Object Styles`.

## Look-up calls for commands: commands_list

    commands_list {}
`count` 1020, `no_tab` 483, `tabs` as `[{tab, count}]`, and a `more` line on how to ask next.

    commands_list {"brief":true,"tab":"View"}
Short rows: `name`, the other name, `tab`, `panel`, `kind`, `built`. `kind` is `tool`, `action` or `dialog`. Without `brief`, `tab` answers that tab's commands in full.

    commands_list {"name":"Freeform Curve"}
Every command of that exact name. Each row: `name`, the other name, `tab`, `panel`, `kind`, `built`, `key`, `prompt`, `draw_modes`, `options`; each option `{name, label, kind, default, choices, scope, modes?}`. Send an option's `name`, not its `label` (`Level` is labelled Storey). An option with `modes` is offered in those draw modes; one without is offered in every mode.

- Two commands may share a name. `Loft` answers two rows: tab Structural panel Form (curves), and tab Make panel Forms (profiles with a Void option). `commands_run` by that name ran the Freeform one each time.
- A command's tab is the registry's tab, not always the ribbon's. Freeform Curve, Loft, Sweep and Revolve sit on tab Structural, panel Form.
- `name` takes UNION's own name of a command, and some common trade names too: `commands_list {"name":"Level","brief":true}` answered the command `Storey`; `Shaft` answered `Vertical Cut-out`; `Ref Plane` answered `Construction Plane`; `Dormer` answered `Roof Cut-out`. It matches names, not the words of prompts: `Gable`, `Skylight`, `Curtain Wall`, `NURBS` and `Spline` answered `count: 0`. A word that finds nothing is not a missing feature: the gable roof is recipe (s) of part 14 (Recipes); a curtain wall is a wall of a type whose Function is Curtain (part 4, Fast ops); look in part 3 (The map) and part 16 (Index).
- Words found under UNION's names: NURBS work is `Freeform Curve`, `Loft`, `Sweep`, `Revolve`; a spline line is a Model Line (the command list's `3D Line`) with `Draw=Spline`.

## Look-up calls for parameters, types and blocks: params_schema, types_list, library_list, and a wrong word on purpose

`params_schema`, `types_list`, `library_list`: the words of a category.

    params_schema {}
The 29 categories with their row counts.

    params_schema {"category":"Doors"}
`{category, count, rows, open}`. `open: true` means an element stores more than the rows list; `param_set` sets a further parameter by name. A row that begins with `@` is an element column. `param_set` writes `@type` (the element's type) where its row is not `readOnly`, and a floor's `@level` (a level name). It refuses a row marked `readOnly`: `cannot proceed: '<row>' is read-only and cannot be set; nothing was written`. A name the catalogue does not know answers `not_found`.

    param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}
Answered `{"changed":1,"elements":1}`; `element_get` then read the new family and type. The same call on a roof, with a roof type name from `types_list`, answered the same. `op:set id=<id> key=Type value=...` answered `A Roof has no parameter 'Type'`.

    types_list {"category":"Floors"}
`{category, total, count, types:[{id, family, name, layers?}], more, next?}`. `layers` give function, material and thickness in mm.

    library_list {"category":"Furniture","limit":5}
The Block Database's block names of a category, no model read. It answered `{"category":"Furniture","count":5,"more":true,"names":["Armchair","Banquette Booth","Bar Stool","Bed - Bunk","Bed - Double"],"next":5,"total":204}`. `limit` pages it; `next` is the place to go on from. `library_list {}` answers `library.list needs a category`.

A wrong word on purpose: UNION answers with the valid words.

    view_activate {"view":"Ground"}
`cannot proceed: 2 views answer to 'Ground': Ground (Floor Plan, id 48660e38...) and Ground (Ceiling Plan, id 5cde2487...); name the one wanted by its id; ...`.

Other answers of this kind:
- `op:add material library=zinc_standing_seam ...` answered `cannot proceed: the library holds no texture set named 'zinc_standing_seam'; nothing was written`.
- A wrong row, item or option in a step's `fields` lists the valid ones. `table 'Patterns' has no row 'zzz' (its rows: Solid fill, Diagonal crosshatch, ...)` lists a dialog table's rows. `the options strip has no 'Offset' (its options: Storey (Level), Width, Height, Diameter, ...)` lists the strip's options.
- A wrong op kind lists the kinds. The call:

      op:add gable at=(0,0)
  UNION's words: `cannot proceed: 'gable' is not a kind of add (add column, add grid, add level, add beam, add brace, add wall, add floor, add roof, add ceiling, add material, add room, add shaft, add stair, ...)` and goes on through every kind (the list is in part 4, Fast ops).
- A wrong material key lists the 33 keys a material keeps. The call:

      op:set material name="Play White" key=zzz value=1
  UNION's words: `cannot proceed: a material keeps no 'zzz' (its keys: density, elastic_modulus, poisson_ratio, yield_strength, rigidity_modulus, tensile_strength, compressive_strength, thermal_expansion, heat_conductivity, render_colour, texture, texture_size, texture_rotation, roughness, metallic, bump, transparency, glow, relief_depth, relief_shadow, height_gain, cut_pattern, surface_pattern, shading_colour, surface_pattern_angle, surface_pattern_follows, description, material_class, material_keynote, material_mark, material_comments, manufacturer, cost)`. Which keys change the Realistic view: part 7 (Materials).
- A wrong card kind lists every kind: `albatross_place {"kind":"zzz"}` answers `cannot proceed: the Albatross library has no card kind 'zzz'. Kinds by group: Model: Beam, Brace, Column ...` and goes on through every group (part 10, ALBATROSS).

## Look-up calls that read what is drawn

    document_info {"categories":true}
Path, name, revision and counts (of the working copy), and a count for each category present, annotation categories too (Dimensions, Text Notes, Lines, Tags, Keynotes). `elements_query` takes the category names it prints.

    levels_list {}
Levels by elevation. A level's id is `level-<name>`.

    views_list {"kind":"Floor Plan"}
`id`, `name`, `kind` of each view; give `kind` to narrow it. When two views share a name, name the view by its id: `view_activate` refuses a shared name, and an op's `view=` takes the floor plan where a floor plan and a ceiling plan share it.

    elements_query {"category":"Freeform Curve"}
Elements of a category, keyset page. Rows come under `rows`. The category is read under any spelling the catalogue knows; a name that is no category answers `not_found`. `level` and `type` narrow the rows; `fields` chooses the columns. It answers 100 rows unless `limit` is given.

    element_get {"id":"<curve id>"}
One element: its columns, decoded `params` (`"Control Points":5,"Degree":3,"Interpolate":true`), `host` and `location` in mm. A view's id answers the view's rows: `element_get {"id":"view-3d"}`.

## From a name to running it: the three routes

Read the row of the name first (`commands_list {"name":"<name>"}` or the reference), then take the route its row points to.

ROUTE 1: an op line (part 4). Use it when `reference > Ops grammar` has a kind for the work. Two lines of a played batch:

    ops_run {"name":"Walls and floor","lines":["op:add wall from=(0,0) to=(8000,0) level=Ground","op:add floor boundary=(0,0),(8000,0),(8000,6000),(0,6000) level=Ground"]}
Each result holds the new element's id in `made`.

ROUTE 2: `commands_run` with options and points (part 5). Use it for a tool or action command with options and points. Shape: `{name, options?, points?, finish?}`. `options` take the option `name`s of the row; `points` are model x, y in mm; `finish` true presses Finish after the points. Its reply is `commands.run` in the reference.

    commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true},"points":[[0,0],[3000,1500],[6000,-1000],[9000,800],[12000,0]],"finish":true}
Answer: `{"changed":[{"category":"Freeform Curve","id":"deea7bc2...","kind":"insert","table":"element"}],"text":"Freeform Curve: 5 point(s)"}`.

A command that wants a selection first: select, then run. Points do not pick elements.

    selection_set {"ids":["<curve 1>","<curve 2>","<curve 3>"]}
    commands_run {"name":"Loft"}
One `Form` element, a surface through the curves in the order selected. With nothing selected UNION answers `cannot proceed: Select the Freeform Curves to loft through, in order, then press Enter`.

- Played the same way: `Revolve` (select the profile curve; the `points` are the axis start and end, and with none UNION answered `Revolve: 0 point(s)`), `Sweep` (select the rail, then the section) and `Clip Box` (a cutaway box).
- After a command, read back `document_info {"categories":true}` and do not send the call twice.
- A tool left standing swallows the next call's points. Clear it: `steps_run {"steps":["chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —"]}`.
- A tool's draw mode (arc, spline, Pick Walls ...: its `draw_modes`) is set with `fields Options Strip: Draw=<mode>` in the tool's ribbon step, never in `commands_run` options (part 5, Commands, steps and dialogs). Played: Roof with `Draw=Pick Walls`, Wall with `Draw=Start-End-Radius Arc`, Model Line (the command list's `3D Line`) with `Draw=Spline`.

ROUTE 3: a ribbon step with fields (part 5). Use it when the work is a dialog's fields. The chain: the reference row of the command gives `Step:` and `Opens:`; the dialog's table gives the field labels and their choices.

    steps_run {"steps":["ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; Soft Shadows=yes; Backdrop=Sky; OK= · expect —"]}
Every field read back and UNION said `'OK' pressed; the dialog closed`.

- A step is five parts: `<driver>:<control path> · picks <points or —> · keys <keys or —> · fields <Dialog: Field=value; … or —> · expect <words>`. The middle dot separates parts, the em dash is an empty part, the arrow `›` folds a sub-tool: `ribbon:Manage:Additional Settings › Fill Patterns`.
- Name the dialog in `fields` by the title UNION prints, the Title line of the reference.
- End a dialog's fields with `OK=`.
- A `Step:` that starts `contextual:` presses a button of a contextual tab, which stands while its selection or sketch does: `contextual:Finish`.

## Report a gap honestly: what you looked in, what UNION said, two honest forms

Before you write "not found", have done all of these:
1. Part 16 (Index): read the tab groups and the "(no tab)" group for the name and its neighbours.
2. Part 3 (The map): try the everyday word and its neighbours.
3. `commands_list` by exact `name` (singular and plural) and by `tab`.
4. The reference: Commands, Dialogs (a field you want may sit in a dialog), Parameters (a parameter row), Ops grammar.
5. `params_schema`, `types_list`, `library_list` (the work may be a type, a parameter or a block, not a command).
6. A wrong word on purpose, and read UNION's words.

A thing is often found under another word. A command sits on a tab that is not the ribbon's (Freeform Curve is on tab Structural). A dialog's name differs from its title (`Category Styles` prints `Object Styles`).

Two honest forms; use no other:
- UNION's own refusal, quoted exactly.
- "not found in <the lists searched>".

Never turn a failed search into a limit.

Say four things: the lists you searched, the call you tried, UNION's words in quotes, and what you did instead with the next press. A model sentence:

- A refusal: "UNION answered 'cannot proceed: Select the Freeform Curves to loft through, in order, then press Enter'; I selected the three curves and ran Loft again."

Look it up: `get_guide {"part":"reference"}`, `commands_list {}`, `params_schema {}`, `document_info {"categories":true}`, part 16 (Index).

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
