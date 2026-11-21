# 5. Commands, steps and dialogs: every other control


A person can press any control UNION has. An agent presses it in one of three ways. The fast ops of part 4 are the quick route; this part is the road to the rest.

1. `commands_run`: a command by its name from `commands_list`. Use it when the input is points, options or the selection.
2. `steps_run`: a step line presses a ribbon, contextual or chrome control with picks, keys and dialog fields. Use it for sketches, typed text, draw modes, a control with a `Step:` line, and any press that opens a dialog.
3. A dialog's fields, written inside a step: `fields <Dialog title>: <field>=<value>; <button>=`. Use it for every setting a dialog holds.

Where a reference row gives a `Step:` line, `steps_run` presses it; where `Registered` is `yes`, `commands_run` presses it. A heading is the name `commands_list` prints, or the ribbon word: `draw-stair-settings` found no heading: its heading is `Stair Settings`. Look the control up (part 2); the guide not showing it proves nothing.

In this part: `commands_run`; the step language, draw modes, sketches; dialog fields; `batch`; the rules a model breaks most.

Look it up: `commands_list {"name":"Freeform Curve"}`.
`get_guide {"part":"reference > Dialogs > Dialog <name>"}`.

## commands_run: name, options, points, finish, and commands that read the selection

`commands_run` presses one registered command as its ribbon press does. Arguments: `name` (required), `options`, `points` (model x, y in mm), `finish`.

Names and options come from the command list:

    commands_list {"name":"Freeform Curve"}

The answer gives the prompt ("Click control point 1 of at least 4") and the options: `Degree` (1, 2 or 3; default 3), `Interpolate` (yes or no; default yes), `Level` (label Storey), `Offset` (mm above the level). Send an option by its Option name. The same rows are in `get_guide {"part":"reference > Commands > Freeform Curve"}`.

- `name` also finds some common trade names: `Level` answered `Storey`, `Dormer` answered `Roof Cut-out`. `Gable`, `Skylight` and `Curtain Wall` answered `count: 0`: a word that finds nothing is not a missing feature.
- Loft, Revolve and Sweep share their names with Block Editor commands (tab Make). `commands_run` by name ran the Freeform one every time.

A drawing command:

    commands_run {"name":"Freeform Curve","options":{"Degree":"3","Interpolate":true},"points":[[0,0],[3000,1500],[6000,-1000],[9000,800],[12000,0]],"finish":true}

Answer: `{"changed":[{"category":"Freeform Curve","id":"deea7bc2...","kind":"insert","table":"element"}],"text":"Freeform Curve: 5 point(s)"}`. The height comes from `Level` and `Offset`: `"options":{"Level":"Level 1"}` drew the curve at 3000. A third number in a point was accepted and the curve still drew flat: do not rely on z.

`finish:true` ends the tool after the last point. A roof footprint is finished by it, the first point repeated to close:

    commands_run {"name":"Roof","points":[[30000,20000],[38000,20000],[38000,25000],[30000,25000],[30000,20000]],"finish":true}

Answer: `{"changed":[{"category":"Roofs","id":"roof-0acc339c...","kind":"insert","table":"element"},...],"text":"Roof: 5 point(s)"}`. The roof is made from the sketched footprint. An open footprint answers `cannot proceed: the sketch is not closed -- its open end is at (30000, 19500) mm`.

A second caller is answered "another AI chat's drawing call is still running in UNION; retry in a moment": retry. While a dialog of the person's stands, `ops_run` and `steps_run` answer busy and run nothing.

**Commands that take the selection**

Select first with `selection_set`; points do not pick elements. Loft:

    selection_set {"ids":["<curve 1>","<curve 2>","<curve 3>"]}
    commands_run {"name":"Loft"}

One `Form` is written, through the curves in the order selected. `commands_run` with points and no selection answered `cannot proceed: Select the Freeform Curves to loft through, in order, then press Enter`.

Revolve: the selected profile, then two points for the axis, with a plan view in front:

    selection_set {"ids":["<profile curve>"]}
    commands_run {"name":"Revolve","options":{"Angle":360},"points":[[20000,-2000],[20000,2000]],"finish":true}

Answer: `{"changed":[{"category":"Form","id":"3e554d07...","kind":"insert","table":"element"}],"text":"Revolve: 2 point(s)"}`. With the profile selected and no points: `Revolve: 0 point(s)`, nothing written. With no selection: `cannot proceed: Select the profile curve to revolve, then press Enter`.

Sweep: the rail curve, then the section curve, selected in that order:

    selection_set {"ids":["<rail curve>","<section curve>"]}
    commands_run {"name":"Sweep"}

With no selection: `cannot proceed: Select the rail curve, then the section curve, then press Enter`.

- The prompt and UNION's refusal of Loft, Revolve and Sweep name what to select (their reference rows read `Needs: -`).
- Form Panels takes a selected form: `selection_set {"ids":["<form id>"]}` then `commands_run {"name":"Form Panels"}`.
- A cutaway box: select the elements (floor, deck and furniture blocks were selected on the house model), then `commands_run {"name":"Clip Box"}`. Switch the box off with `op:set id=view-3d key="Section Box" value=no`.

**Reading the answer**

- Its reply is `commands.run` in the reference. Check the count of what you made.
- A tool can be left standing and swallow the next drawing call's points (Form Panels did). The carrier step with `keys Escape Escape` ends any standing tool:

    steps_run {"steps":["chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —"]}

**A view's display style by name**

    commands_run {"name":"Shaded"}

With the 3D view in front the answer was `{"changed":[{"category":"","id":"view-3d","kind":"update","table":"view"}],"text":"ran Shaded"}`. Read it back: `element_get {"id":"view-3d"}` shows the row `visual_style` (label Display Style) = `Shaded`.

## Steps: the five parts, drivers, the options strip and draw modes, expect, typed text, sketches

`steps_run {"steps":[...]}` plays 1 to 200 step lines in order as ONE undo step. Its reply is `steps.run` in the reference.

A step is one line of five parts joined by the middle dot U+00B7; an empty part is the em dash U+2014; a fold is the arrow U+203A:

    <driver>:<control path> · picks <points or —> · keys <keys or —> · fields <Dialog: Field=value; … or —> · expect <words>

Write all five parts. Undo and Redo play in the five-part form, and Undo in the short form too:

    qa:Undo · picks — · keys — · fields — · expect —
    qa:Redo · picks — · keys — · fields — · expect —
    qa:Undo · expect —

A step to press a command is the `Step:` line of its reference row. Play that line; the word after `ribbon:` is the ribbon tab: Setout, Structure, Architecture, Massing & Site, Systems, Annotate, View, Manage, Modify, Insert, Interoperability, File or Add-Ins. A `-` means no step is listed; `commands_run` presses it when `Registered` is `yes`.

Played step line, copied exactly:

    ribbon:View:Drafting View · picks — · keys Return · fields New Drafting View: Name=Timber Eaves Detail; Scale=1:10 · expect view: Drafting View +1

Drivers (the word before the first colon):
- `ribbon:<tab>:<button>`: a press, then picks on the view. A folded sub-tool uses `›`, for example `ribbon:Annotate:Detail Line › Rectangle`.
- `qa:<key>`: Undo, Redo. One `qa:Undo` took back a whole `steps_run` call (`undid 'Add-in: steps.run'`); `qa:Redo` then `redid` it. When the newest change is the person's, UNION refuses and says to ask the person to undo it.
- `chrome:<word>`: window chrome: `chrome:Canvas Zoom to Fit`.
- `plan:<word>`: select, deselect, zoom to fit.
- `ctx:<kind>:<row>`: a right press, then a context row (`ctx:browser:Delete` took a sheet away).
- `dialog:<name>`: the fields of a standing dialog. `contextual:<key>`: a contextual-tab button (Finish).
- `op:<verb> <kind> key=value ...` plays a fast op as a step; use `ops_run` for many (part 4).

`expect` takes these forms: a count (`Walls +4`, `Floors +1`), `view Ground active`, `view: Drafting View +1`, `nothing selected`, `dialog closed`, or an em dash alone ("no expectation"). Sheets are not a counted kind: use `dialog closed`.

Picks are `(x,y)` in the ACTIVE view's own mm, separated by a space, none inside a point. A plan: x east, y north. A drafting view: its own frame. A sheet: sheet mm. Make the plan active first with `view_activate`, a floor plan by its id from `views_list` (`Ground` names a floor plan and a ceiling plan: send the id).

Keys: Return, Escape, and one key per character: letters, digits, Space, `-`, `+`, `.`, `/`, `:`, `&`. Typed text:

    ribbon:Annotate:Text · picks (0,-1250) · keys T I M B E R Space E A V E S Return Escape · fields Options Strip: Leader=off · expect Text Notes +1

A sketch tool is driven by a step: picks that close the loop by repeating the first point exactly, then a separate `contextual:Finish` step. Floor and Filled Region were played so; `Roof Cut-out` is rule 10 of the Rules piece:

    ribbon:Structure:Floor · picks (0,0) (8000,0) (8000,6000) (0,6000) (0,0) · keys — · fields — · expect nothing selected
    contextual:Finish · picks — · keys — · fields — · expect Floors +1

**Tool options and draw modes**

A standing tool ends with `keys Escape Escape`. Tool options go in the fields part as `Options Strip: <option>=<value>` (`Width=100`, `Leader=off`). A tool's draw mode (the `draw_modes` list of `commands_list {"name":"<command>"}`) is `Draw=<mode>` in `fields Options Strip:` of the ribbon step that presses the tool. Three played lines, copied exactly:

    ribbon:Architecture:Roof · picks (34000,20000) (34000,25000) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=400 · expect —
    ribbon:Architecture:Wall · picks (50000,6000) (56000,6000) (53000,8000) · keys Escape Escape · fields Options Strip: Draw=Start-End-Radius Arc · expect Walls +1
    ribbon:Setout:Model Line · picks (50000,12000) (52000,13500) (54000,11000) (56000,12500) · keys Return Escape Escape · fields Options Strip: Draw=Spline · expect —

- The strip's fields are applied BEFORE the picks of the same step. The arc wall takes three picks: start, end, a point on the arc. `keys Return` ends a spline; the command list calls Model Line `3D Line`. A gable roof on four walls is recipe (s) in part 14 (Recipes).
- Both wall step keys are played green: `ribbon:Structure:Wall` presses `Wall`, `ribbon:Architecture:Wall` presses `Wall: Architectural`.
- CARRIER STEP: while a tool stands, `chrome:Canvas Zoom to Fit · picks (38000,22500) (30000,22500) · keys Return · fields Options Strip: Defines Slope=no · expect —` carries more strip fields, picks and keys to it without pressing it again; with `keys Escape Escape` it ends any standing tool.
- A wrong strip field lists the strip's fields: `Nonsense=1` on the Roof tool answered `fields: the options strip has no 'Nonsense' (its options: Offset, Radius)`.
- `commands_run` takes no draw mode: `{"name":"Roof","options":{"Draw Mode":"Pick Walls"}}` answers `cannot proceed: Roof has no option Draw Mode; nothing was written`. An option of another mode answers `cannot proceed: Defines Slope is in Pick Walls mode; the options strip is in Line mode.` Set `Draw=` in the tool's own ribbon step.

## Dialogs: fields lines, tables and rows, the Display Options step, settings dialogs

A dialog is answered in the fields part: `fields <Dialog>: <field>=<value>; <field>=<value>; <button>=`. A button is its name with `=` and nothing after (`OK=`, `Cancel=`). A step can open the dialog and answer it in one line, or `keys Return` presses OK.

The Display Options step, with the 3D view in front:

    steps_run {"steps":["ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; Soft Shadows=yes; Backdrop=Sky; OK= · expect —"]}

UNION read back every field and answered `'OK' pressed; the dialog closed`. A new template's 3D view opens in the `Hidden` style. Realistic draws black edge lines by default; `Show Edges=no` and `Silhouette Edges=no` make a picture read as a building rather than a drawing (part 6).

**Read a dialog's field names**

    get_guide {"part":"reference > Dialogs > Display Options"}

Each dialog prints `Title:`, `Buttons:` and `Actions:`, then a table: Tab, Group, Field, Key, Kind, Limits, Choices, Notes. Display Options answers Buttons OK, Cancel, Apply; Actions Save as View Template; fields Style, Show Edges, Transparency (0-100), Silhouette Edges, Silhouette Line Style, Shadows and more.
- Write the Field column as printed (`Show Edges`, `Soft Shadows`). Kinds: `choice` (a value from Choices), `yesno` (`yes` or `no`), `number`, `integer`, `length`, `text`, `table`, `button`, `image`; the reference also prints `angle`, `colour`, `weight`, `pattern`, `tree`, `view_row`, `view_scale` and `secret`. A `read-only` note marks a row that takes no value.
- A row can carry a `name` note: Display Options prints the Field `Transparency (0-100)` with the note name `Transparency`.
- Notes such as "enabled while `shadows` shows one of (yes)" name a field that depends on another. The played step writes `Shadows=yes` before `Soft Shadows=yes`.
- Limits are `>=` at least, `>` above, `<=` at most, `<` below, `step` a whole multiple, `blank ok` an empty box is taken. A wrong choice names the items: "'System Type' has no item 'zzz' (its items: Supply Air / Return Air / Exhaust Air)".
- The heading of a dialog in the reference is the word Dialog and its key (`Dialog Import`, `Dialog Units`). The `Title:` line is what the screen prints. Played steps used both: the title (`Line Styles`, `Object Styles`, `Display Options`) and the key (`Place View`, whose title is Views). The command list can name the same dialog differently (Line Types for Line Styles).

**Tables and rows**

A table field takes a row name: `fields Fill Patterns: Patterns=Gravel` with `keys Return` and `expect dialog closed`. The row selects it.

To read a table's rows, give a row that is not there. UNION lists the rows, the step is red and nothing changes: "table 'Patterns' has no row 'zzz' (its rows: Solid fill, Diagonal crosshatch, ...)". The Place View table lists views by KIND: `fields Place View: Views=Drafting View`.

A dialog that stands needs its answer in the same step, or UNION closes it: "the step left the modal ... open: closed by the player (a window: "<title>", buttons ...; name the answer in the step's fields as `<title>: <button>=`)". A dialog-kind command opened by `commands_run` is closed as Cancel; open it by its step.

**Settings dialogs**

Opened and read by title. Rows are the first 12 UNION printed.

| step key | title in `fields` | command-list name | table and rows |
|---|---|---|---|
| `ribbon:Manage:Additional Settings › Fill Patterns` | Fill Patterns | Fill Patterns | Patterns: Solid fill, Diagonal crosshatch, Blockwork, Gravel, Insulation, Sand. Buttons New, Delete, Load Patterns, Save Patterns. Field Pattern Type (Drafting, Model). |
| `ribbon:Manage:Additional Settings › Line Styles` | Line Styles | Line Types | Styles: Thin Lines, Medium Lines, Wide Lines, <Sketch>. Button New. |
| `ribbon:Manage:Additional Settings › Line Weights` | Line Weights | Line Widths | Weights: 1 to 12; Width (mm) by view scale; Add View Scale, Delete View Scale. |
| `ribbon:Manage:Additional Settings › Arrowheads` | Arrowheads | Arrowheads | Arrowheads: None, Arrow Filled, Diagonal 3mm, Dot 1.5mm Filled, Arrow 30 Degree. Buttons New, Delete. |
| `ribbon:Manage:Object Styles` | Object Styles | Category Styles | Categories: Air Terminals, Alignment, Anchors, Appliances, Areas. |

The Detail Line `Line Style` option accepted `Wide Lines` and `Medium Lines` and read back the name. `ribbon:Modify:Type Properties` on a Filled Region opens the window "Block Manager · Filled Regions", not `Type Settings`.

## batch: several calls as one Undo step

`batch` applies calls in order as ONE undo step.

The method names inside a batch carry a dot: `selection.set`, `param.set`, `commands.run`. Played, select, set a parameter, clear the selection:

    batch {"calls":[{"method":"selection.set","params":{"ids":["<wall id>"]}},{"method":"param.set","params":{"ids":["<wall id>"],"key":"Comments","value":"probe"}},{"method":"selection.set","params":{"ids":[]}}]}

Answer: `{"applied":3,"calls":[{"index":0,"method":"selection.set","ok":true,"result":{"selected":1}},{"index":1,"method":"param.set","ok":true,"result":{"changed":1,"elements":1}},{"index":2,"method":"selection.set","ok":true,"result":{"selected":0}}],"undo":"Add-in: batch"}`.

- `param_set {"ids":["<door id>"],"key":"Mark","value":"<text>"}` set Mark on one element.
- To change an element's type, `param_set` takes the key `@type`: `param_set {"ids":["<wall id>"],"key":"@type","value":"Block 190 Core-filled"}` answered `{"changed":1,"elements":1}` and `element_get` then read the new family and type. The same call on a roof was played too. `op:set id=<id> key=Type value=...` is refused (`A Roof has no parameter 'Type'`).

## Rules a model breaks most (steps and commands)

Each rule came from a red step or a wrong result.

1. Read UNION's words in every answer, not only the colour.
2. Play 3 to 8 steps a call. Check each step's `expect` and the last step's `counts=`. A red step ends the call.
3. Tidy at the end: `chrome:Canvas Zoom to Fit`, nothing selected, no tool or dialog standing (`keys Escape Escape`).
4. All five parts in every step; an empty part is the em dash. A line missing parts answered "an unknown segment". The short `qa:Undo · expect —` is played too.
5. The model is the person's open model. A `start:<template>` step is red: `cannot proceed: 'New' is the person's own control, not UNION AI's; ask the person to press it`. A step that presses Save As, Open, Close, Exit, Print, Export or Import is refused with the same words and the control's name: do not retry, tell the person which control to press.
6. Take the key from the reference's `Step:` line or a played recipe; write a fold with `›`, never `>`. A guessed name is not a driver and its step does not play: press it with `ribbon:` or `commands_run`. Look the name up (part 2).
7. Quote a name that has a space: `name="Level 2"`. An unquoted second word answers "'9' stands after the kind; every other word is a key=value".
8. `expect` takes the readable forms above. A free-text expect answers "unknown expect form".
9. A dialog that stands needs its answer in the same step: `fields <Dialog>: <field>=<value>` and `keys Return`, or `<button>=`.
10. A sketch ends with `contextual:Finish`; Escape throws it away. Close the loop with the first point exactly. The tool `Roof Cut-out` (ribbon button Dormer, step `ribbon:Architecture:Dormer`; `commands_list {"name":"Dormer"}` finds it) is a sketch tool.
11. Text in a view: `op:add text at=(0,-10) view="General Notes" text="1. All dimensions are in millimetres."` first; typed keys inside a tool with no op. Circles for bar dots: `ribbon:Annotate:Detail Line › Circle`, a centre pick then an edge pick; each counts as a Line (`Lines +1`).
12. Do the plan work before you make a sheet, or `view_activate` the plan first. A sheet in front answers "Duct works in a plan, section or elevation view: a sheet is in front".
13. Pick on real geometry when a tool needs a reference: Aligned and Keynote want a pick on an existing line or element; an Air Terminal wants a pick ON the duct; a duct is two picks, and a third starts a segment Escape throws away. End a standing tool with `keys Escape Escape` before pressing another.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
