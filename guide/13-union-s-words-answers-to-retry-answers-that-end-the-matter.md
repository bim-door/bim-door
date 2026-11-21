# 13. UNION's words: answers to retry, answers that end the matter


Every answer of UNION is in words. A refusal names its fix and often lists the valid words. Read the words, not only the colour: a green step can carry a note.

In this part:
- Answers that mean wait and retry (a drawing call still running, busy, unavailable, still building), and the answers that look like a wait and are not.
- The refusal table. Rows 1 to 28 are step lines, ribbon keys and the options strip. Rows 29 on are the door's tools, ops and ALBATROSS. Row numbers are fixed: other parts quote them.
- A wrong word on purpose: UNION lists the valid words.

Answers that end the matter are rows 31, 32 and 35 (the File band, Undo of the person's change). Do not retry them; tell the person which control to press. For every other answer: read the words, fix the line, send it again.

Look it up:

    commands_list {"name":"<command name>"}
    views_list {}

Both list the valid words.

## Answers that mean wait and retry
Send the same call again after a moment, unchanged, unless the row says to ask the person first.

| UNION's words or state | what it means | next |
|---|---|---|
| "another AI chat's drawing call is still running in UNION; retry in a moment" | one drawing call runs at a time; another AI's call holds it. Not a failure | send the same call again; repeat while it answers so |
| "cannot proceed: the 3D view is still building its model; ask for the picture again in a moment" (`view_image`, no picture) | the 3D view in front has not stood whole after the wait of up to 20 seconds | ask again; if it answers so again, send the call under "Still building without end" |

## Still building without end
The answer "still building" can come while UNION is idle: the main window is minimised or hidden behind the UNION AI window. This call still returns the picture as it stands:

    view_image {"window":"main"}

Name no `view` in it.

Edit with a plan view in front, then show the 3D view once and take several pictures.

    views_list {}
    view_activate {"view":"<floor plan id>"}

Part 6 (See your work) holds the rest.

## Answers that look like a wait and are not
- "cannot proceed: the Albatross window did not open" (row 38): ask the person to open ALBATROSS, then send the call again.

## Refusal table for step lines, ribbon keys and the options strip
A red step changes nothing unless noted. Rows 1, 2 and 28 come from `start:` steps: on the person's door a `start:` step is red with the words of row 31.

| # | UNION's words | what it means | fix |
|---|---|---|---|
| 1 | "start: no New picker in this build" | `start:New` is not a template | `start:Architectural` or another listed template |
| 2 | "no document is open: the ribbon is hidden on the Start page" | a ribbon step before `start:` | `start:<template>` first |
| 3 | "an unknown segment '—' -" | a line without all five parts | five parts, middle dot between, em dash for an empty part. The short step `qa:Undo · expect —` was also played green |
| 4 | "'9' stands after the kind; every other word is a key=value" | `name=Level 9` unquoted | `name="Level 9"` |
| 5 | "the step left the modal ... open: closed by the player (a window: "<title>", buttons ...; name the answer in the step's fields as `<title>: <button>=`)" | a dialog stood with no answer, or a table row was pressed with no OK | `fields <Dialog>: <field>=<value>` and `keys Return` (played green), or the button in fields |
| 6 | (no words) nothing placed after a Filled Region or Floor sketch | Escape instead of Finish | `contextual:Finish` |
| 7 | "cannot proceed: the sketch is not closed -- its open end is at (-600, -410) mm" | the loop did not close | repeat the first point exactly. The Region sketch stays open: `keys Escape Escape` |
| 8 | "unknown expect form 'tool stands'"; "status '' NOT read"; "unknown expect form 'dialog'" | a free-text expect | a count, `nothing selected`, `view … active`, `dialog closed` |
| 9 | `Sheets +1` (any sheet count) reads 0 -> 0 and the step goes red | sheets are not a counted kind | `dialog closed`; UNION's msg "Sheet A150 created" |
| 10 | "the key '195' is not a key this stage knows" | text typed as one word | one key per character |
| 11 | a step that starts `annotate:` or `text:` does not play | a guessed name | `ribbon:Annotate:Text` with keys |
| 12 | "no chrome control 'Ground' (30 words known here)" | a view tab is not a chrome word; the words name `Activate View` on a viewport | do the plan work before the sheet |
| 13 | "an Aligned dimension takes references, and no live element stands within this command's own tolerance of the click" | the pick was off any geometry (26 mm off) | pick endpoints of existing lines |
| 14 | "cannot proceed: nothing under the click to tag" (Keynote) | the pick was on empty space | pick on a real element |
| 15 | "the options strip has no 'Offset' (its options: Storey (Level), Width, Height, Diameter, Middle Elevation, Lock, Apply, Start Offset, End Offset, System Type)" | `Offset` or `Size` sent to a Duct; the words list the strip's options | Width, Height, Middle Elevation |
| 16 | "'System Type' has no item 'zzz' (its items: Supply Air / Return Air / Exhaust Air)" | a wrong choice item | one of the three |
| 17 | "table 'Patterns' has no row 'zzz' (its rows: Solid fill, Diagonal crosshatch, ...)"; the same for Styles, Weights, Arrowheads, Categories | a wrong row | this IS how to read a table's rows |
| 18 | "table 'Views' has no row 'Timber Eaves Detail' (its rows: Ceiling Plan, 3D View, Drafting View, Schedule, Schedule, Schedule)" | Place View lists kinds | name the row as listed: `Views=Drafting View` |
| 19 | "cannot proceed: view already on a sheet: A150" | a standing Viewport tool still holds the placed view, or a second placement | `keys Escape Escape`, then press Viewport again; a view sits on one sheet |
| 20 | "the Viewport tool standing was ended by Modify" | `plan:select` ends a standing tool | use it only after placement |
| 21 | "cannot proceed: Duct works in a plan, section or elevation view: a sheet is in front; use Activate View on one of its viewports to work in that view" | a sheet is the active view | ducts and terminals BEFORE the sheet |
| 22 | Ducts 0 -> 1 after three picks | the third pick starts a segment Escape throws away | two picks per duct |
| 23 | "cannot proceed: a level named Roof already exists" | the template names Ground, Level 1, Roof | another name |
| 24 | "cannot proceed: sheet number exists: A102" | template sheets A000, A100 to A103, A201 ... | a new number |
| 26 | "no contextual tab stands to press 'Cancel' on (waited 0 ms, nothing selected)" | no sketch stood: the step before ended it (a Detail Line press) | press Cancel while the sketch stands |
| 27 | "'Category' has no item 'Detail Items'" (Load Block) | the Category list in that dialog did not hold it | choose an item the list holds |
| 28 | "the active view is 'Level 1' (expected 'Ground')" | the Structural template opens on Level 1, not Ground | `expect view Level 1 active` after `start:Structural` |

## Refusal table for the door's tools, the person's controls, ops and ALBATROSS
Rows 31, 32 and 35 end the matter.

| # | UNION's words | what it means | fix |
|---|---|---|---|
| 29 | "cannot proceed: '@type' is not a parameter name; nothing was written" (`param_set`) | a key that begins with `@` is an element column, not a parameter. `@type` wrote the type of a wall and a roof. | change an element's type: `param_set {"ids":["<id>"],"key":"@type","value":"<type name from types_list>"}` answered `{"changed":1,"elements":1}` on a wall and on a roof, and `element_get` then read the new type. Any other parameter: read it with `element_get`, set it by the name it shows |
| 30 | "cannot proceed: the 3D view is still building its model; ask for the picture again in a moment" (`view_image`, no picture) | the 3D view in front has not stood whole after the wait | ask again; if it never ends, `view_image {"window":"main"}` (see "Still building without end") |
| 31 | "cannot proceed: 'Save As' is the person's own control, not UNION AI's; ask the person to press it" (a red step, or the error of `commands_run`). The word in quotes is the control: Save As, Open, New, Close, Exit, Print, Export, Import or Import IFC for the others, and Save | the File band is the person's | do not retry; tell the person which control to press; nothing was saved, opened or ended |
| 32 | "cannot proceed: Print needs a person" (`commands_run` of Print; Export and Import read the same with their name) | the command is of kind `dialog` | ask the person; a dialog that is not a File control opens by its step |
| 35 | "cannot proceed: the newest change is the person's own, not UNION AI's; ask the person to undo it" (a `qa:Undo` step, or Undo by `commands_run`). Redo: "the change to redo is the person's own ... ask the person to redo it" | the newest entry on the Undo list is the person's; your Undo takes back only your own | do not retry; tell the person; nothing was undone |
| 36 | "kind= wants plan, structural or ceiling; sections, elevations, drafting views and 3D views are made by add section, add elevation, add drafting view and add 3d view" (`add view`) | a view kind other than a plan went to `add view` | the op the words name |
| 37 | "cannot proceed: add railing host= takes no level=: the railing follows the stair" | `host` and `level` written together | `host=` alone, or `points=` with `level=` |
| 38 | `unavailable`: "cannot proceed: the Albatross window did not open" (`albatross_place`, `albatross_graph` or `albatross_delete`) | `albatross_place`, `albatross_graph` and `albatross_delete` open the ALBATROSS window when it is closed; this time it did not open | ask the person to open ALBATROSS, then send the call again |
| 39 | "cannot proceed: the Albatross library has no card kind 'zzz'. Kinds by group: Model: Beam, Brace, Column ..." (`albatross_place`, error `not_found`; the words list every kind of every group, about 3 KB) | a kind the library does not list | one of the kinds the words list |
| 40 | "cannot proceed: 'column (1,1)' is not a kind of add (add column, add grid, ...)" | a second bare point after a one-point key (`at=(0,0) (1,1)`) | one point after `at`, `from`, `to`; a list only after `boundary`, `points`, `axis` |
| 41 | "cannot proceed: add wall takes top= (a level) or height= (mm), not both"; "cannot proceed: add terminal wants level= or duct="; "cannot proceed: no room at this point of Ground and no closed walls round it" (`add ceiling at=` outside the walls) | the keys of the line | the words name the fix |

## Refusal table, further rows
Rows 54 on follow in the next piece.

| # | UNION's words | what it means | fix |
|---|---|---|---|
| 43 | "cannot proceed: Select the Freeform Curves to loft through, in order, then press Enter" | `Loft` with no selection; `points` do not pick curves | `selection_set {"ids":["<curve 1>","<curve 2>","<curve 3>"]}`, then `commands_run {"name":"Loft"}` |
| 44 | "cannot proceed: Select the profile curve to revolve, then press Enter" | `Revolve` with no selection | `selection_set {"ids":["<profile curve>"]}`, then `Revolve` with the axis `points` |
| 45 | "cannot proceed: Select the rail curve, then the section curve, then press Enter" | `Sweep` with no selection | `selection_set {"ids":["<rail curve>","<section curve>"]}`, then `commands_run {"name":"Sweep"}` |
| 46 | "Revolve: 0 point(s)" | the profile was selected and no axis points came; nothing was written | send the two axis points and `"finish":true` |
| 48 | "cannot proceed: 2 views answer to 'Ground': Ground (Floor Plan, id 48660e38...) and Ground (Ceiling Plan, id 5cde2487...); name the one wanted by its id; ..." (`view_activate`) | two views carry the name | send the id from `views_list` |
| 49 | "cannot proceed: the library holds no texture set named 'zinc_standing_seam'; nothing was written" (`op:add material library=`) | the set name is not a key of the texture library | a set name from part 7 (Materials) |

## Refusal table, more new rows: draw mode, roof sketch, strip fields, material keys, library, UNION AI window

| # | UNION's words | what it means | fix |
|---|---|---|---|
| 55 | "cannot proceed: Roof has no option Draw Mode; nothing was written" (`commands_run {"name":"Roof","options":{"Draw Mode":"Pick Walls"}}`) | a draw mode is set on the options strip, not in the options of `commands_run` | set `Draw=` on the options strip in the tool's own ribbon step (row 56) |
| 56 | "cannot proceed: Defines Slope is in Pick Walls mode; the options strip is in Line mode. Set Draw first with steps_run: plan:noop · fields Options Strip: Draw=Pick Walls." and, for that step, "plan: plan:noop is not an inventory process" | an option of another draw mode; the step the words name is refused | `ribbon:Architecture:Roof · picks (34000,20000) · keys — · fields Options Strip: Draw=Pick Walls; Defines Slope=yes; Overhang=400 · expect —`. The strip's fields are applied before the picks of the same step |
| 57 | "cannot proceed: the sketch is not closed -- its open end is at (30000, 19500) mm" (Roof, Pick Walls) | the walls were picked out of loop order | pick the walls round the loop, one pick on each wall's line (part 14, Recipes, gable roof) |
| 58 | "fields: the options strip has no 'Nonsense' (its options: Offset, Radius)" (Roof tool, Line mode) | a wrong strip field; the words list the options of the mode in force (row 15 is the same in a Duct) | a listed option, or `Draw=` first (row 56) |
| 59 | "cannot proceed: a material keeps no 'zzz' (its keys: density, elastic_modulus, poisson_ratio, ... , manufacturer, cost)" (`op:set material name="Play White" key=zzz value=1`) | a wrong material key; the words list all 33 keys | one listed key. Seen to change the Realistic view: texture, texture_size, texture_rotation, render_colour, roughness, metallic, bump, transparency, glow (part 7, Materials) |
| 60 | "library.list needs a category" (`library_list {}`) | the call named no category | `library_list {"category":"Furniture","limit":5}` answered `{"category":"Furniture","count":5,"more":true,"names":["Armchair","Banquette Booth","Bar Stool","Bed - Bunk","Bed - Double"],"next":5,"total":204}` |
| 63 | "cannot proceed: the falcon window is not open; its program tile's command opens it" (`view_image {"window":"falcon"}`) | the UNION AI window is closed | `commands_run {"name":"gooseClicked"}`, then `view_image {"window":"falcon","width":1100}` (part 11, UNION AI window) |
| 64 | "no contextual tab stands to press ..." (`contextual:Finish` with no sketch standing) | UNION names the pages that carry Finish: Create Floor Boundary, Create Property Line and Toposolid | finish a roof sketch with `"finish":true` in `commands_run`, or `keys Return` in the step; row 26 is the same words for Cancel |
| 65 | "A Roof has no parameter 'Type'" (`op:set id=<roof id> key=Type value=...`) | the type of an element is not a parameter row | `param_set {"ids":["<roof id>"],"key":"@type","value":"Terracotta Tile Battens 90"}` answered `{"changed":1,"elements":1}` (row 29) |

## A wrong word on purpose makes UNION list the valid ones
Send an unknown type, view, card kind or table row and UNION answers with the valid words. A refused call writes nothing, so a wrong word costs one call. Send the wrong word alone.

**Views**:

    view_activate {"view":"Ground"}

Answer: `cannot proceed: 2 views answer to 'Ground': Ground (Floor Plan, id 48660e38...) and Ground (Ceiling Plan, id 5cde2487...); name the one wanted by its id; ...` The words give both ids. Send the id wanted.

**ALBATROSS card kinds**:

    albatross_place {"kind":"zzz"}

UNION lists the whole library, every kind by group. Send one of the kinds listed.

The same trick on other words:
- A table row in a step: `table 'Patterns'=zzz` answers with the table's rows (row 17).
- A choice item: "'System Type' has no item 'zzz' (its items: ...)" (row 16).
- A set name: row 49 names the miss and lists no set; the 67 set names are in part 7 (Materials).
- An op kind: `op:add gable at=(0,0)` answers "cannot proceed: 'gable' is not a kind of add (add column, add grid, add level, ...)" and lists every kind, from `add column` to `array`.

Look it up:

    types_list {"category":"<category>"}
    views_list {}
    commands_list {"name":"<command name>"}
    get_guide {"part":"reference > Commands > Freeform Curve"}

The last call reads one command of the reference; replace the name with the command wanted. A few commands are filed in the reference under another word; when a name finds no heading, `commands_list {"name":"<name>"}` gives the same facts.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
