# 1. Connect, permissions, and working beside other agents


Look commands, dialogs and fields up and drive them with `commands_list`, `commands_run` and `steps_run`: part 2.

In this part:
- The tools, one line each, by group.
- What is the person's, not yours: File actions (Save excepted), the working copy, `start:` lines, Undo.
- Busy, unavailable and retry answers.

Look it up: the model's facts and the reference's parts:

    document_info {"categories":true}
    get_guide {"part":"reference"}

## The union tools at a glance

Arguments are the tool descriptions. A reply is read in the reference under the tool's method, its name with the first underscore a dot (`record_start` is `record.start`, `albatross_card_readback` is `albatross.card_readback`; the second for `wall_profile_get` and `line_weights_model`): `get_guide {"part":"reference > Methods"}`. The needs column: R = a read; W = a write. Units are mm. A paged tool takes `after` and answers `more` and `next`.

| tool and arguments | what it does | needs |
|---|---|---|
| **Read the model** | | |
| `document_info {categories?}` | path, name, revision, counts; `categories` adds a count per category | R |
| `elements_query {category, level?, type?, fields?, limit?, after?}` | a page of elements; the category in any spelling the catalogue knows | R |
| `element_get {id}` | one element: columns, parameters, `host`, `location` | R |
| `elements_get {ids}` | up to 200 elements as `element_get`; ids that are no element in `missing` | R |
| `params_schema {category?}` | the parameter rows of a category; none lists the categories | R |
| `types_list {category, limit?, after?}` | the project's types of a category, with layers | R |
| `levels_list {}` | levels by elevation | R |
| `grids_list {limit?, after?}` | grids: id, Name, geometry | R |
| `groups_list {limit?, after?, instances?}` | group definitions with member and instance counts | R |
| `views_list {kind?}` | views: id, name, kind | R |
| `sheets_list {limit?, after?}` | sheets by number with the views placed on each | R |
| `schedule_read {view, limit?, after?}` | a schedule's table as the schedule shows it | R |
| `library_list {category, limit?, after?}` | block names of a category (a category is needed); on a build that lists them, Detail Items and Generic Annotations add the detail components as `Family : Type`; reads no document | R |
| `model_check {limit?, after?}` | the structural analytical model check | R |
| `selection_get {}` | the selection | R |
| `elements_in_box {view?, points}` | ids inside a view's box and those it touches; selects nothing | R |
| `detail_shape {id, kind?}` | the drawing of a detail component, line or tag, in mm | R |
| `redline_marks {}` | the mark-ups beside the open model | R |
| **Write the model** | | |
| `param_set {ids, key, value}` | one parameter on up to 5000 elements, all or none | W |
| `type_duplicate {category, type, family?, name}` | a type copied with its parameters and layers | W |
| `type_set {category, type, family?, key, value}` | one parameter of a type; elements on it follow | W |
| `selection_set {ids}` | replaces the selection; `[]` clears it | W |
| `redline_answer {id, status, words}` | answers one mark-up: Done, Query or Refused | W |
| **Look** | | |
| `view_image {view?, window?, width?}` | a PNG of a UNION window; `window` is main, viewer, active, or a program's window by name; width 64 to 2048; a 3D view in front is waited on up to 20 seconds | R |
| `view_activate {view}` | shows a view or sheet by name or id; a name two views share is refused: send the id from `views_list` | R |
| `view_camera {view?, azimuth?, pitch?, fit?, ids?}` | turns and frames a 3D view, reads its camera | R |
| **Run commands and steps** | | |
| `commands_list {tab?, kind?, built?, name?, brief?}` | the command registry; no argument gives the tabs with counts | R |
| `commands_run {name, options?, points?, finish?}` | one command as its ribbon press; at most 40 points a call | W |
| `ops_run {lines, name?}` | 1 to 500 op lines, one Undo entry `Add-in: <name>` | W |
| `steps_run {steps}` | 1 to 200 step lines, one undo step; a red step ends the call | W |
| `batch {calls}` | up to 100 `param.set`, `selection.set`, `commands.run` calls, one undo step | W |
| **ALBATROSS** | | |
| `albatross_place {kind, at?, inputs?}` | places a card; opens the ALBATROSS window if closed | W |
| `albatross_set {card, input, value}` | sets one input or setting of a card | W |
| `albatross_wire {from, output?, to, input}` | wires an output into an input | W |
| `albatross_delete {card}` | deletes a card and its wires; elements it made stay; opens the ALBATROSS window if closed | W |
| `albatross_graph {limit?, after?}` | the cards and wires; opens the ALBATROSS window if closed | R |
| `albatross_card_readback {card, part, offset?, snapshot?}` | one card's Panel text or ports; a closed canvas answers unavailable | R |
| **Talk with the person** | | |
| `falcon_wait {timeout_ms?}` | takes the person's next prompt; `{none:true}` at the time-out | R |
| `falcon_say {text, done?}` | shows your words in their conversation; `done` ends your answer | R |
| **The guide** | | |
| `get_guide {part?, page?}` | this guide, and the reference by `reference > <section> > <name>`, for example `reference > Commands > Freeform Curve` | R |

## What is the person's, not yours: File actions

File actions are the person's: New, Open, Import, Export; also Save As, Close, Exit, Print and every Export or Import format. Save is the one File action you may press (below).
UNION's own words end the matter, except `busy`: do not retry, tell the person which control to press. Nothing was saved, opened, written or ended.
- A File control, by a step or by `commands_run`: "cannot proceed: 'Save As' is the person's own control, not UNION AI's; ask the person to press it". The word between the quotes is the control. A `batch` holding one stops there.
- A command that is a dialog: "cannot proceed: Print needs a person". Export and Import read the same with their name.
- Save: UNION AI's Save keeps unsaved edits in its own copy, never in the person's file. The copy is `<model> - <UNION AI's name><the model's own suffix>` in UNION AI's folder, `<UNION state folder>/<UNION AI's name>`; a UNION 2D drawing makes a `.u2d` copy. Making that copy leaves the person's file and backups, saved mark, Undo, star and Recent as they were. The status bar says `<UNION AI's name> saved its copy of <model>. Your file is unchanged until you press Save.`; when replacing its earlier copy, it says `<UNION AI's name> replaced '<copy name>'. Your file is unchanged until you press Save.` If a copy already made at the same journal state is still in that folder, Save writes nothing again. If the model has a person's file and nothing unsaved, Save writes nothing.
- Undo and Redo act on the entries your calls made, each named `Add-in: <name>`; as steps: part 5. When the newest change is the person's: "cannot proceed: the newest change is the person's own, not UNION AI's; ask the person to undo it". Nothing is undone.

Unsaved edits live in the working copy; the person's own Save keeps them in the person's file. UNION AI's Save keeps unsaved edits in its own copy, never in the person's file. The copy is `<model> - <UNION AI's name><the model's own suffix>` in UNION AI's folder, `<UNION state folder>/<UNION AI's name>`; a UNION 2D drawing makes a `.u2d` copy. Making that copy leaves the person's file and backups, saved mark, Undo, star and Recent as they were. The status bar says `<UNION AI's name> saved its copy of <model>. Your file is unchanged until you press Save.`; when replacing its earlier copy, it says `<UNION AI's name> replaced '<copy name>'. Your file is unchanged until you press Save.` If a copy already made at the same journal state is still in that folder, Save writes nothing again. The door's answers stay the same as above.

`start:` lines. The recipes of this guide that were played on a fresh template copy begin with a step like this:

    start:Architectural · picks — · keys — · fields — · expect view Ground active

On the person's door the model is the one they have open. Leave every `start:` line out; it is red: "cannot proceed: 'New' is the person's own control, not UNION AI's; ask the person to press it". A red step ends the call, so a recipe that begins with one plays nothing. Read the model instead: `document_info {"categories":true}`, `views_list {}`, `levels_list {}`, and use the names it holds in the recipe's `expect` words (the Structural template opens on Level 1, not Ground).

## Busy, unavailable and retry answers

Retry these. Send the same call again after a short wait.
- One drawing call at a time across callers. A second caller is answered "another AI chat's drawing call is still running in UNION; retry in a moment".
- `busy` from `view_activate`, `view_image` or `view_camera`: the person has a tool or dialog open, or UNION is working or opening a model.
- "cannot proceed: the 3D view is still building its model; ask for the picture again in a moment" (`view_image`, no picture). If it answers so again and again while UNION is idle, the main window is minimised or behind the UNION AI window. Send `view_image {"window":"main"}` with NO `view` named: it returns the picture as it stands.
- `unavailable` "cannot proceed: the Albatross window did not open" (any `albatross_` tool): ask the person to open ALBATROSS, then send the call again.

Do not retry: the answers of the piece on what is the person's (File actions, the person's newest change), except `busy`, which is asked again in a moment. A wrong word is not a retry: UNION's refusal names the fix and lists the valid words: part 13 (UNION's words).

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
