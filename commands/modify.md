# UNION commands: Modify

77 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## Align

A UNION command on the Modify tab, Modify panel. It asks: "Click the reference element".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify
- Works in views: drafting, plan, section_or_elevation, sheet_or_schedule, three_d

Worked example: press **Align** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Align · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Align' on Modify's Modify panel (through its fold): the tool 'Align' stands | keys: Escape (tool Align -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Lock | yesno | false |  | all |
| Multiple Alignment | yesno | false |  | all |
| Prefer | choice | Wall Faces | Wall Faces, Wall Centerlines, Faces of Core, Center of Core | all |
| Space Evenly | yesno | false |  | all |

Played in these jobs:

- [6035. The east wall sits 300 mm out of line with the west wall: align it to the west wall's line.](../examples/change-modify-and-freeform.md)

## Anchor

A UNION command on the Modify tab, Modify panel. Also known as Pin. It asks: "Click to pin the selected elements".

### Pin

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Edit

Worked example: press **Anchor** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Pin · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Pin' on Modify's Edit panel (through its fold): it refused in words: cannot proceed: Select the elements first, then press Pin

Played in these jobs:

- [6041. Pin the surveyed boundary wall so nobody moves it, then unpin it and move it 500 mm.](../examples/change-modify-and-freeform.md)

## Array

A UNION command on the Modify tab, Modify panel. It asks: "Click a base point, then click to place the array".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify
- Works in views: drafting, plan, section_or_elevation, sheet_or_schedule, three_d
- Draw modes: Line

Worked example: press **Array** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Array · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Array' on Modify's Modify panel (through its fold): the tool 'Array' stands | keys: Escape (tool Array -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Group And Associate | yesno | true |  | all |
| Move To | choice | 2nd | 2nd, Last | all |
| Number | number | 2 |  | all |

Played in these jobs:

- [1028. Draw one column and array it five times at 7.2 m along the frontage.](../examples/setting-out-and-structure.md)
- [1029. Draw one 8 m secondary beam on the first floor and array it five times at 3 m centres.](../examples/setting-out-and-structure.md)
- [1057. Draw one 250UC89.5 column and array it into a colonnade of eight at 3.6 m along the front of the building.](../examples/setting-out-and-structure.md)
- [6006. Array this 3 m wall four times at 2 m centres for the cubicle partitions.](../examples/change-modify-and-freeform.md)
- [6019. Repeat this column five times at 3 m centres along the grid line.](../examples/change-modify-and-freeform.md)
- [6030. Repeat the 6 m cold water branch four times at 2.5 m centres for the four bathrooms.](../examples/change-modify-and-freeform.md)
- [6033. Repeat the distribution board four times at 2.5 m centres along the plant wall.](../examples/change-modify-and-freeform.md)
- [6066. Repeat the 8 m beam four times at 3 m centres for the floor framing.](../examples/change-modify-and-freeform.md)

### Array › Linear

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify > Array

Worked example: press **Array** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Array › Linear · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Array › Linear' on Modify's Modify panel (through its fold) (through its parent 'Array''s arrow, the row 'Linear'; the press stood 478 ms (the menu stood at 24 ms; its row ran 452 ms; it made 0 child widgets native)): the tool 'Array › Linear' stands | keys: Escape (tool Array › Linear -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Array by Count

A UNION command on the Modify tab, Modify panel.

### modify-array

- Tab: Modify
- Panel: Modify
- Ribbon: Modify > Modify

Worked example: press **Array by Count** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:modify-array · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'modify-array' on Modify's Modify panel (through its fold) (through its parent 'Array''s arrow, the row 'Array by Count'; the press stood 58 ms (the menu stood at 18 ms; its row ran 29 ms; it made 0 child widgets native)): the command 'modify-array' ran; status 'Select elements to array, then press Enter' | keys: Escape (tool Array -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Array Radial

A UNION command on the Modify tab, Modify panel. Also known as Radial. It asks: "Click a centre, then click a point on the array".

### Array › Radial

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify > Array

Worked example: press **Array Radial** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Array › Radial · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Array › Radial' on Modify's Modify panel (through its fold) (through its parent 'Array''s arrow, the row 'Radial'; the press stood 101 ms (the menu stood at 16 ms; its row ran 70 ms; it made 0 child widgets native)): the tool 'Array › Radial' stands | keys: Escape (tool Array › Radial -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Angle | angle | 0 |  | all |
| Group And Associate | yesno | true |  | all |
| Move To | choice | 2nd | 2nd, Last | all |
| Number | number | 2 |  | all |

## Array Settings

A UNION command on the Modify tab, Modify panel.

### modify-array-dialog

- Tab: Modify
- Panel: Modify
- Ribbon: Modify > Modify

Worked example: press **Array Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:modify-array-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'modify-array-dialog' on Modify's Modify panel (through its fold) (through its parent 'Array''s arrow, the row 'Array Settings'; the press stood 112 ms (the menu stood at 20 ms; its row ran 92 ms; the window's first paint at 92 ms in union_shell::ShellDialogWindow, dialog 'Array'; the dialog stood 697 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Array' opened and stood; closed by the player | inside the modal 'Array' | keys: Escape (no tool, dialog 'Array' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Break

A UNION command on the Modify tab, Modify panel. Also known as Split.

### Split

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Edit

Worked example: press **Break** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Split · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Split' on Modify's Edit panel (through its fold): the command 'Split' ran; status 'Click an element to break it there' | keys: Escape (tool Break -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6038. Split the 8 m wall at its middle and delete the east half.](../examples/change-modify-and-freeform.md)

## Break Gap

A UNION command on the Modify tab, Modify panel. Also known as Split with Gap.

### Split › Split with Gap

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Edit > Split

Worked example: press **Break Gap** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Split › Split with Gap · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Split › Split with Gap' on Modify's Edit panel (through its fold) (through its parent 'Split''s arrow, the row 'Split with Gap'; the press stood 131 ms (the menu stood at 21 ms; its row ran 91 ms; it made 0 child widgets native)): the command 'Split › Split with Gap' ran; status 'Click an element to break it with a gap' | keys: Escape (tool Break Gap -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6039. Break the 8 m wall in two with a gap at the movement joint.](../examples/change-modify-and-freeform.md)

## Copy

A UNION command on the Modify tab, Modify panel. It asks: "Click a base point".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify
- Works in views: drafting, plan, section_or_elevation, sheet_or_schedule, three_d

Worked example: press **Copy** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Copy · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Copy' on Modify's Modify panel (through its fold): the tool 'Copy' stands | keys: Escape (tool Copy -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Constrain | yesno | false |  | all |
| Multiple | yesno | false |  | all |

Played in these jobs:

- [3015. Draw a 6 m supply duct with three diffusers, then copy the whole run 3 m north for the next room.](../examples/building-services.md)
- [3087. Draw a 450 mm cable tray 10 m long and copy it 1 m north.](../examples/building-services.md)
- [6002. Copy this 6 m wall 3.6 m north to make the other side of the corridor.](../examples/change-modify-and-freeform.md)
- [6016. Put a window in the north wall and copy it 3 m along for the second bay.](../examples/change-modify-and-freeform.md)
- [6028. Copy the 6 m supply duct 3 m north for the second room and mark it SA-2.](../examples/change-modify-and-freeform.md)
- [6034. Copy distribution board DB-1 3 m east and mark the copy DB-2.](../examples/change-modify-and-freeform.md)
- [6042. Draw a spline model line through four points for the garden path edge, then copy it 3 m north for the other edge.](../examples/change-modify-and-freeform.md)
- [6068. Move, copy and turn the wall, take the three changes back one by one, then redo the first.](../examples/change-modify-and-freeform.md)

## Copy (to Clipboard)

A UNION command on the Modify tab, Clipboard panel.

### Press it

- Tab: Modify
- Panel: Clipboard
- Ribbon: Modify > Clipboard

Worked example: press **Copy (to Clipboard)** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Copy (to Clipboard) · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Copy (to Clipboard)' on Modify's Clipboard panel (through its fold): it refused in words: cannot proceed: nothing is selected to copy

## Copy Type

A UNION command on the Modify tab, Modify panel. Also known as Match Type. It asks: "Click the source element".

### Match Type

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Clipboard

Worked example: press **Copy Type** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Match Type · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Match Type' on Modify's Clipboard panel (through its fold): the tool 'Match Type' stands | keys: Escape (tool Match Type -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Corner

A UNION command on the Modify tab, Modify panel. Also known as Trim/Extend. It asks: "Click the first element".

### Trim/Extend

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Edit

Worked example: press **Corner** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Trim/Extend · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Trim/Extend' on Modify's Edit panel (through its fold): the tool 'Trim/Extend' stands | keys: Escape (tool Trim/Extend -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Create Parts

A UNION command on the Modify tab, Create panel.

### Press it

- Tab: Modify
- Panel: Create
- Ribbon: Modify > Create

Worked example: press **Create Parts** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Create Parts · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Create Parts' on Modify's Create panel (through its fold): it refused in words: cannot proceed: nothing is selected

## Cut

A UNION command on the Modify tab, Geometry panel. Also known as Cut Geometry. It asks: "Click the first element".

### Press it

- Tab: Modify
- Panel: Geometry
- Kind: tool
- Ribbon: Modify > Geometry

Worked example: press **Cut** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Cut · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Cut' on Modify's Geometry panel (through its fold): the tool 'Cut' stands | keys: Escape (tool Cut -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Multiple Cut | yesno | false |  | all |

## Cut › Cut Geometry

A UNION command on the Modify tab, Geometry panel. Also known as Cut Geometry. It asks: "Click the first element".

### Press it

- Tab: Modify
- Panel: Geometry
- Kind: tool
- Ribbon: Modify > Geometry > Cut

Worked example: press **Cut › Cut Geometry** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Cut › Cut Geometry · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Cut › Cut Geometry' on Modify's Geometry panel (through its fold) (through its parent 'Cut''s arrow, the row 'Cut Geometry'; the press stood 351 ms (the menu stood at 23 ms; its row ran 326 ms; it made 0 child widgets native)): the tool 'Cut › Cut Geometry' stands | keys: Escape (tool Cut › Cut Geometry -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Multiple Cut | yesno | false |  | all |

## Cut › Uncut Geometry

A UNION command on the Modify tab, Geometry panel.

### Press it

- Tab: Modify
- Panel: Geometry
- Ribbon: Modify > Geometry > Cut

Worked example: press **Cut › Uncut Geometry** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Cut › Uncut Geometry · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Cut › Uncut Geometry' on Modify's Geometry panel (through its fold) (through its parent 'Cut''s arrow, the row 'Uncut Geometry'; the press stood 314 ms (the menu stood at 22 ms; its row ran 265 ms; it made 0 child widgets native)): the tool 'Cut › Uncut Geometry' stands | keys: Escape (tool Cut › Uncut Geometry -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Cut to Clipboard

A UNION command on the Modify tab, Clipboard panel. It asks: "Select elements, then press Cut to Clipboard".

### Press it

- Tab: Modify
- Panel: Clipboard
- Kind: tool
- Ribbon: Modify > Clipboard

Worked example: press **Cut to Clipboard** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Cut to Clipboard · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Cut to Clipboard' on Modify's Clipboard panel (through its fold): it refused in words: cannot proceed: nothing is selected to copy

## Delete

A UNION command on the Modify tab, Modify panel. It asks: "Click to delete the selected elements".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Edit

Worked example: press **Delete** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Delete · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Delete' on Modify's Edit panel (through its fold): the tool 'Delete' stands | keys: Escape (tool Delete -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [3016. Draw two supply ducts 2 m apart, then delete the lower one because it was drawn in the wrong place.](../examples/building-services.md)
- [3045. Draw two cold water pipes 1 m apart and delete the upper one.](../examples/building-services.md)
- [3086. Run two conduits 500 mm apart and delete the lower one.](../examples/building-services.md)
- [6007. Delete the store wall, then undo it, then redo it.](../examples/change-modify-and-freeform.md)
- [6008. Delete the south and north walls together, then take it back.](../examples/change-modify-and-freeform.md)
- [6011. Touch the south and middle walls with a crossing box and delete them, keeping the north wall.](../examples/change-modify-and-freeform.md)
- [6021. Delete the corner column, bring it back with undo, then delete it again with redo.](../examples/change-modify-and-freeform.md)
- [6029. Turn the 5 m return duct a quarter turn about its centre, then delete the 2 m stub.](../examples/change-modify-and-freeform.md)
- [6038. Split the 8 m wall at its middle and delete the east half.](../examples/change-modify-and-freeform.md)
- [6063. Draw a trial curve, decide against it and delete it.](../examples/change-modify-and-freeform.md)
- [6069. Delete the door from the north wall, then undo the delete to bring it back.](../examples/change-modify-and-freeform.md)
- [6074. Window-select the whole east bay of the frame, delete it, then undo the delete.](../examples/change-modify-and-freeform.md)

## Demolish

A UNION command on the Modify tab, Geometry panel.

### Press it

- Tab: Modify
- Panel: Geometry
- Ribbon: Modify > Geometry

Worked example: press **Demolish** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Demolish · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Demolish' on Modify's Geometry panel (through its fold): the tool 'Demolish' stands | keys: Escape (tool Demolish -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Disassemble Assembly

A UNION command on the Modify tab, Create panel.

### Press it

- Tab: Modify
- Panel: Create
- Kind: action
- Ribbon: Modify > Create

Worked example: press **Disassemble Assembly** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Disassemble Assembly · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Disassemble Assembly' on Modify's Create panel (through its fold): it refused in words: cannot proceed: nothing is selected to disassemble

## Drag Elements on Selection

A UNION command on the Modify tab, Select panel.

### Press it

- Tab: Modify
- Panel: Select
- Kind: action
- Ribbon: Modify > Select

Worked example: press **Drag Elements on Selection** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Drag Elements on Selection · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Drag Elements on Selection' on Modify's Select panel: the command 'Drag Elements on Selection' ran; status 'Drag Elements on Selection: off' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Exclude

A UNION command on the Modify tab, Group panel.

### Press it

- Tab: Modify
- Panel: Group
- Kind: action
- Ribbon: Modify > Create

Worked example: press **Exclude** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Exclude · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Exclude' on Modify's Create panel (through its fold): it refused in words: cannot proceed: nothing is selected to exclude

## Export Group

A UNION command on the Modify tab, Group panel.

### Press it

- Tab: Modify
- Panel: Group
- Kind: action
- Ribbon: Modify > Create

Worked example: press **Export Group** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Export Group · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Export Group' on Modify's Create panel (through its fold): it refused in words: cannot proceed: the project has no group types

## Filter

A UNION command on the Modify tab, Select panel.

### Refine Selection

- Tab: Modify
- Panel: Select
- Ribbon: Modify > Select

Worked example: press **Filter** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Refine Selection · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Refine Selection' on Modify's Select panel (the window's first paint at 137 ms in union_shell::ShellDialogWindow, dialog 'Refine Selection'): the dialog 'Filter' opened and stood; closed by the player | inside the modal 'Filter' | keys: Escape (no tool, dialog 'Filter' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Join

A UNION command on the Modify tab, Geometry panel. Also known as Join Geometry. It asks: "Click the first element".

### Press it

- Tab: Modify
- Panel: Geometry
- Kind: tool
- Ribbon: Modify > Geometry

Worked example: press **Join** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Join · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Join' on Modify's Geometry panel (through its fold): the tool 'Join' stands | keys: Escape (tool Join -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Join Type | choice | Mitre | Mitre, Butt, Square | all |
| Multiple Join | yesno | false |  | all |

### Join › Join Geometry

- Tab: Modify
- Panel: Geometry
- Kind: tool
- Ribbon: Modify > Geometry > Join

Worked example: press **Join** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Join › Join Geometry · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Join › Join Geometry' on Modify's Geometry panel (through its fold) (through its parent 'Join''s arrow, the row 'Join Geometry'; the press stood 474 ms (the menu stood at 10 ms; its row ran 463 ms; it made 0 child widgets native)): the tool 'Join › Join Geometry' stands | keys: Escape (tool Join › Join Geometry -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6076. Join the slab to the wall that stands on it so the slab edge follows the wall.](../examples/change-modify-and-freeform.md)

## Join › Switch Join Order

A UNION command on the Modify tab, Geometry panel. Also known as Switch Join Order. It asks: "Click the first element".

### Press it

- Tab: Modify
- Panel: Geometry
- Kind: tool
- Ribbon: Modify > Geometry > Join

Worked example: press **Join › Switch Join Order** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Join › Switch Join Order · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Join › Switch Join Order' on Modify's Geometry panel (through its fold) (through its parent 'Join''s arrow, the row 'Switch Join Order'; the press stood 175 ms (the menu stood at 8 ms; its row ran 154 ms; it made 0 child widgets native)): the tool 'Join › Switch Join Order' stands | keys: Escape (tool Join › Switch Join Order -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Multiple Switch | yesno | false |  | all |

## Join › Unjoin Geometry

A UNION command on the Modify tab, Geometry panel.

### Press it

- Tab: Modify
- Panel: Geometry
- Ribbon: Modify > Geometry > Join

Worked example: press **Join › Unjoin Geometry** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Join › Unjoin Geometry · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Join › Unjoin Geometry' on Modify's Geometry panel (through its fold) (through its parent 'Join''s arrow, the row 'Unjoin Geometry'; the press stood 196 ms (the menu stood at 18 ms; its row ran 162 ms; it made 0 child widgets native)): the tool 'Join › Unjoin Geometry' stands | keys: Escape (tool Join › Unjoin Geometry -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Load Group

A UNION command on the Modify tab, Group panel.

### Press it

- Tab: Modify
- Panel: Group
- Kind: action
- Ribbon: Modify > Create

Worked example: press **Load Group** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Load Group · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Load Group' on Modify's Create panel (through its fold) (the window's first paint at 72 ms in union_shell::ShellDialogWindow, dialog 'Browse IFC'): the dialog 'Load Group' opened and stood; closed by the player | inside the modal 'Load Group' | keys: Escape (no tool, dialog 'Load Group' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Make Assembly

A UNION command on the Modify tab, Create panel. Also known as Create Assembly.

### Create Assembly

- Tab: Modify
- Panel: Create
- Kind: dialog
- Ribbon: Modify > Create

Worked example: press **Make Assembly** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Create Assembly · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create Assembly' on Modify's Create panel (through its fold) (the window's first paint at 72 ms in union_shell::ShellDialogWindow, dialog 'Make Assembly'): the dialog 'Make Assembly' opened and stood; closed by the player | inside the modal 'Make Assembly' | keys: Escape (no tool, dialog 'Make Assembly' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Make Group

A UNION command on the Modify tab, Create panel. Also known as Create Group.

### Create Group

- Tab: Modify
- Panel: Create
- Kind: dialog
- Ribbon: Modify > Create

Worked example: press **Make Group** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Create Group · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create Group' on Modify's Create panel (through its fold) (the window's first paint at 95 ms in union_shell::ShellDialogWindow, dialog 'Make Group'): the dialog 'Make Group' opened and stood; closed by the player | inside the modal 'Make Group' | keys: Escape (no tool, dialog 'Make Group' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Measure

A UNION command on the Modify tab, Measure panel. It asks: "Click two points to measure the distance".

### Press it

- Tab: Modify
- Panel: Measure
- Kind: tool
- Ribbon: Modify > Measure
- Draw modes: Line

Worked example: press **Measure** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Measure · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Measure' on Modify's Measure panel (through its fold): the tool 'Measure' stands | keys: Escape (tool Measure -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Measure › Measure Between Two References

A UNION command on the Modify tab, Measure panel.

### Press it

- Tab: Modify
- Panel: Measure
- Ribbon: Modify > Measure > Measure

Worked example: press **Measure › Measure Between Two References** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Measure › Measure Between Two References · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Measure › Measure Between Two References' on Modify's Measure panel (through its fold) (through its parent 'Measure''s arrow, the row 'Measure Between Two References'; the press stood 406 ms (the menu stood at 14 ms; its row ran 390 ms; it made 0 child widgets native)): the command 'Measure › Measure Between Two References' ran; status 'Click two points to measure the distance' | keys: Escape (tool Measure -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Measure Along An Element

A UNION command on the Modify tab, Measure panel.

### Measure › Measure Along An Element

- Tab: Modify
- Panel: Measure
- Kind: tool
- Ribbon: Modify > Measure > Measure

Worked example: press **Measure Along An Element** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Measure › Measure Along An Element · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Measure › Measure Along An Element' on Modify's Measure panel (through its fold) (through its parent 'Measure''s arrow, the row 'Measure Along An Element'; the press stood 30 ms (the menu stood at 13 ms; its row ran 4 ms; it made 0 child widgets native)): the command 'Measure › Measure Along An Element' ran; status 'Click a member to read the length' | keys: Escape (tool Measure Along An Element -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Measure Area

A UNION command on the Modify tab, Measure panel.

### Measure › Measure Area

- Tab: Modify
- Panel: Measure
- Kind: tool
- Ribbon: Modify > Measure > Measure

Worked example: press **Measure Area** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Measure › Measure Area · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Measure › Measure Area' on Modify's Measure panel (through its fold) (through its parent 'Measure''s arrow, the row 'Measure Area'; the press stood 227 ms (the menu stood at 9 ms; its row ran 207 ms; it made 0 child widgets native)): the command 'Measure › Measure Area' ran; status 'Click the corners, then press Enter to read the area' | keys: Escape (tool Measure Area -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Measure Area of an Object

A UNION command on the Modify tab, Measure panel.

### Measure › Measure Area of an Object

- Tab: Modify
- Panel: Measure
- Kind: tool
- Ribbon: Modify > Measure > Measure

Worked example: press **Measure Area of an Object** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Measure › Measure Area of an Object · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Measure › Measure Area of an Object' on Modify's Measure panel (through its fold) (through its parent 'Measure''s arrow, the row 'Measure Area of an Object'; the press stood 41 ms (the menu stood at 18 ms; its row ran 8 ms; it made 0 child widgets native)): the command 'Measure › Measure Area of an Object' ran; status 'Click inside a closed shape to read its area' | keys: Escape (tool Measure Area of an Object -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Mirror Pick

A UNION command on the Modify tab, Modify panel. Also known as Mirror. It asks: "Click the start of the axis".

### Mirror

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify
- Draw modes: Line

Worked example: press **Mirror Pick** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Mirror · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Mirror' on Modify's Modify panel (through its fold): the tool 'Mirror' stands | keys: Escape (tool Mirror -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Copy | yesno | true |  | all |

### Mirror › Draw Axis

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify > Mirror

Worked example: press **Mirror Pick** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Mirror › Draw Axis · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Mirror › Draw Axis' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Draw Axis'; the press stood 37 ms (the menu stood at 17 ms; its row ran 7 ms; it made 0 child widgets native)): the tool 'Mirror › Draw Axis' stands | keys: Escape (tool Mirror › Draw Axis -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6004. Mirror the 4 m entrance wall across a centre line at y = 5000 so the lobby is symmetrical.](../examples/change-modify-and-freeform.md)
- [6020. Mirror the column and its beam across the centre line at y = 6000.](../examples/change-modify-and-freeform.md)
- [6073. Select the two walls of the L-shaped wing with a window and mirror them across the line at x = 16000.](../examples/change-modify-and-freeform.md)

### Mirror › Pick Axis

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify > Mirror

Worked example: press **Mirror Pick** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Mirror › Pick Axis · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Mirror › Pick Axis' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Pick Axis'; the press stood 564 ms (the menu stood at 13 ms; its row ran 550 ms; it made 0 child widgets native)): the tool 'Mirror › Pick Axis' stands | keys: Escape (tool Mirror › Pick Axis -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6005. Mirror the north wing wall across the corridor wall.](../examples/change-modify-and-freeform.md)
- [6031. Mirror the 100 mm sprinkler branch to the other side of the 8 m main.](../examples/change-modify-and-freeform.md)

## Mirror Selection

A UNION command on the Modify tab, Modify panel.

### modify-mirror

- Tab: Modify
- Panel: Modify
- Ribbon: Modify > Modify

Worked example: press **Mirror Selection** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:modify-mirror · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'modify-mirror' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Mirror Selection'; the press stood 59 ms (the menu stood at 27 ms; its row ran 9 ms; it made 0 child widgets native)): the tool 'modify-mirror' stands | keys: Escape (tool modify-mirror -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Modify

A UNION command on the Modify tab, Select panel.

### Modify/Modify

- Tab: Modify
- Panel: Select
- Ribbon: Modify > Select

Worked example: press **Modify** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Modify · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Modify' on Modify's Select panel: the command 'Modify' ran; status 'Modify: no tool' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Move

A UNION command on the Modify tab, Modify panel. It asks: "Click a base point".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify
- Works in views: drafting, plan, section_or_elevation, sheet_or_schedule, three_d

Worked example: press **Move** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Move · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Move' on Modify's Modify panel (through its fold): the tool 'Move' stands | keys: Escape (tool Move -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Constrain | yesno | false |  | all |
| Disjoin | yesno | false |  | all |

Played in these jobs:

- [6001. Move the partition wall 1.5 m to the north.](../examples/change-modify-and-freeform.md)
- [6009. Select the whole 6 x 4 m meeting room with a window and move it 3 m north.](../examples/change-modify-and-freeform.md)
- [6015. Put a door in the south wall, mark it D01 and slide it 2.5 m along the wall.](../examples/change-modify-and-freeform.md)
- [6041. Pin the surveyed boundary wall so nobody moves it, then unpin it and move it 500 mm.](../examples/change-modify-and-freeform.md)
- [6067. Select one bay of the frame, two columns and the beam between them, and move it 2 m north.](../examples/change-modify-and-freeform.md)
- [6068. Move, copy and turn the wall, take the three changes back one by one, then redo the first.](../examples/change-modify-and-freeform.md)

## Offset

A UNION command on the Modify tab, Modify panel. It asks: "Click the element to offset".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify
- Works in views: drafting, plan, section_or_elevation, sheet_or_schedule, three_d

Worked example: press **Offset** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Offset · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Offset' on Modify's Modify panel (through its fold): the tool 'Offset' stands | keys: Escape (tool Offset -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Chain | yesno | false |  | all |
| Copy | yesno | true |  | all |
| Placement Line | choice | Wall Centerline | Wall Centerline, Core Centerline, Finish Face: Exterior, Finish Face: Interior, Core Face: Exterior, Core Face: Interior | all |
| Offset value | length | 100 |  | all |
| Pick Lines | yesno | false |  | all |
| Offset Mode | choice | Graphical | Graphical, Numerical | all |

Played in these jobs:

- [6032. Offset the 6 m main 1.2 m north to run the parallel return.](../examples/change-modify-and-freeform.md)
- [6040. Offset the 8 m facade wall 1.5 m inward to start the inner leaf.](../examples/change-modify-and-freeform.md)

## Paint

A UNION command on the Modify tab, Geometry panel.

### Press it

- Tab: Modify
- Panel: Geometry
- Ribbon: Modify > Geometry

Worked example: press **Paint** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Paint · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Paint' on Modify's Geometry panel (through its fold) (the window's first paint at 62 ms in QDialog#MaterialsWindow): the tool 'Paint' stands | inside the modal 'Materials' | keys: Escape (no tool, dialog 'Materials' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Parallel Offset

A UNION command on the Modify tab, Modify panel.

### modify-offset

- Tab: Modify
- Panel: Modify
- Ribbon: Modify > Modify

Worked example: press **Parallel Offset** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:modify-offset · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'modify-offset' on Modify's Modify panel (through its fold) (through its parent 'Offset''s arrow, the row 'Parallel Offset'; the press stood 81 ms (the menu stood at 18 ms; its row ran 63 ms; the window's first paint at 63 ms in union_shell::ShellDialogWindow, dialog 'Offset'; the dialog stood 708 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Offset' opened and stood; closed by the player | inside the modal 'Offset' | keys: Escape (no tool, dialog 'Offset' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Paste

A UNION command on the Modify tab, Clipboard panel.

### Press it

- Tab: Modify
- Panel: Clipboard
- Ribbon: Modify > Clipboard

Worked example: press **Paste** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Paste · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Paste' on Modify's Clipboard panel (through its fold): the tool 'Paste' stands | keys: Escape (tool Paste -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Paste (from Clipboard)

A UNION command on the Modify tab, Clipboard panel.

### Press it

- Tab: Modify
- Panel: Clipboard
- Ribbon: Modify > Clipboard

Worked example: press **Paste (from Clipboard)** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Paste (from Clipboard) · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Paste (from Clipboard)' on Modify's Clipboard panel (through its fold) (through its parent 'Paste''s arrow, the row 'Paste (from Clipboard)'; the press stood 390 ms (the menu stood at 32 ms; its row ran 357 ms; it made 0 child widgets native)): the tool 'Paste (from Clipboard)' stands | keys: Escape (tool Paste (from Clipboard) -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Paste › Aligned to Current View

A UNION command on the Modify tab, Clipboard panel.

### Press it

- Tab: Modify
- Panel: Clipboard
- Ribbon: Modify > Clipboard > Paste

Worked example: press **Paste › Aligned to Current View** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Paste › Aligned to Current View · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Paste › Aligned to Current View' on Modify's Clipboard panel (through its fold) (through its parent 'Paste''s arrow, the row 'Aligned to Current View'; the press stood 47 ms (the menu stood at 21 ms; its row ran 8 ms; it made 0 child widgets native)): the command 'Paste › Aligned to Current View' ran; status 'Copy elements first, then paste them' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Paste › Aligned to Picked Level

A UNION command on the Modify tab, Clipboard panel.

### Press it

- Tab: Modify
- Panel: Clipboard
- Ribbon: Modify > Clipboard > Paste

Worked example: press **Paste › Aligned to Picked Level** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Paste › Aligned to Picked Level · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Paste › Aligned to Picked Level' on Modify's Clipboard panel (through its fold) (through its parent 'Paste''s arrow, the row 'Aligned to Picked Level'; the press stood 55 ms (the menu stood at 24 ms; its row ran 12 ms; it made 0 child widgets native)): the tool 'Paste › Aligned to Picked Level' stands | keys: Escape (tool Paste › Aligned to Picked Level -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Paste › Aligned to Same Place

A UNION command on the Modify tab, Clipboard panel.

### Press it

- Tab: Modify
- Panel: Clipboard
- Ribbon: Modify > Clipboard > Paste

Worked example: press **Paste › Aligned to Same Place** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Paste › Aligned to Same Place · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Paste › Aligned to Same Place' on Modify's Clipboard panel (through its fold) (through its parent 'Paste''s arrow, the row 'Aligned to Same Place'; the press stood 43 ms (the menu stood at 21 ms; its row ran 4 ms; it made 0 child widgets native)): the command 'Paste › Aligned to Same Place' ran; status 'Copy elements first, then paste them' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Paste › Aligned to Selected Levels

A UNION command on the Modify tab, Clipboard panel.

### Press it

- Tab: Modify
- Panel: Clipboard
- Ribbon: Modify > Clipboard > Paste

Worked example: press **Paste › Aligned to Selected Levels** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Paste › Aligned to Selected Levels · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Paste › Aligned to Selected Levels' on Modify's Clipboard panel (through its fold) (through its parent 'Paste''s arrow, the row 'Aligned to Selected Levels'; the press stood 38 ms (the menu stood at 16 ms; its row ran 8 ms; it made 0 child widgets native)): the command 'Paste › Aligned to Selected Levels' ran; status 'Copy elements first, then paste them aligned to levels' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Paste › Aligned to Selected Views

A UNION command on the Modify tab, Clipboard panel.

### Press it

- Tab: Modify
- Panel: Clipboard
- Ribbon: Modify > Clipboard > Paste

Worked example: press **Paste › Aligned to Selected Views** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Paste › Aligned to Selected Views · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Paste › Aligned to Selected Views' on Modify's Clipboard panel (through its fold) (through its parent 'Paste''s arrow, the row 'Aligned to Selected Views'; the press stood 32 ms (the menu stood at 14 ms; its row ran 5 ms; it made 0 child widgets native)): the command 'Paste › Aligned to Selected Views' ran; status 'Copy elements first, then paste them aligned to views' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Pick-Axis Mirror

A UNION command on the Modify tab, Modify panel.

### modify-mirror-pick

- Tab: Modify
- Panel: Modify
- Ribbon: Modify > Modify

Worked example: press **Pick-Axis Mirror** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:modify-mirror-pick · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'modify-mirror-pick' on Modify's Modify panel (through its fold) (through its parent 'Mirror''s arrow, the row 'Pick-Axis Mirror'; the press stood 46 ms (the menu stood at 11 ms; its row ran 21 ms; it made 0 child widgets native)): the tool 'modify-mirror-pick' stands | keys: Escape (tool modify-mirror-pick -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Place Group

A UNION command on the Modify tab, Create panel. It asks: "Click to place the group".

### Press it

- Tab: Modify
- Panel: Create
- Kind: tool
- Ribbon: Modify > Create

Worked example: press **Place Group** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Place Group · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Place Group' on Modify's Create panel (through its fold): the tool 'Place Group' stands | keys: Escape (tool Place Group -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Properties

A UNION command on the Modify tab, Properties panel.

### Press it

- Tab: Modify
- Panel: Properties
- Kind: action
- Ribbon: Modify > Properties

Worked example: press **Properties** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Properties · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Properties' on Modify's Properties panel: the command 'Properties' ran; status 'Attributes hidden' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

### User Interface › Properties

- Tab: Modify
- Panel: Properties
- Kind: action
- Ribbon: Views > Windows > User Interface

Worked example: press **Properties** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:View:User Interface › Properties · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'User Interface › Properties' on View's Windows panel (through its fold) (through its parent 'User Interface''s arrow, the row 'Properties'; the press stood 65 ms (the menu stood at 33 ms; its row ran 13 ms; it made 0 child widgets native)): the command 'User Interface › Properties' ran; status 'Attributes shown' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Radial Array by Count

A UNION command on the Modify tab, Modify panel.

### modify-array-radial

- Tab: Modify
- Panel: Modify
- Ribbon: Modify > Modify

Worked example: press **Radial Array by Count** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:modify-array-radial · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'modify-array-radial' on Modify's Modify panel (through its fold) (through its parent 'Array''s arrow, the row 'Radial Array by Count'; the press stood 205 ms (the menu stood at 27 ms; its row ran 162 ms; it made 0 child widgets native)): the command 'modify-array-radial' ran; status 'Select elements to array, then press Enter' | keys: Escape (tool Array › Radial -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Release

A UNION command on the Modify tab, Modify panel. Also known as Release (Share panel, UNION addition), Unpin. It asks: "Click to unpin the selected elements".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Manage > Share

Worked example: press **Release** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:Release · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Release' on Manage's Share panel (through its fold): the command 'Release' ran; status 'Release: this model is not shared -- it has no central file to work with.' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

### Unpin

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Edit

Worked example: press **Release** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Unpin · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Unpin' on Modify's Edit panel (through its fold): it refused in words: cannot proceed: Select the elements first, then press Unpin

Played in these jobs:

- [6041. Pin the surveyed boundary wall so nobody moves it, then unpin it and move it 500 mm.](../examples/change-modify-and-freeform.md)

## Remove from Group

A UNION command on the Modify tab, Group panel.

### Press it

- Tab: Modify
- Panel: Group
- Kind: action
- Ribbon: Modify > Create

Worked example: press **Remove from Group** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Remove from Group · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Remove from Group' on Modify's Create panel (through its fold): the tool 'Remove from Group' stands | keys: Escape (tool Remove from Group -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Remove Paint

A UNION command on the Modify tab, Geometry panel.

### Press it

- Tab: Modify
- Panel: Geometry
- Ribbon: Modify > Geometry

Worked example: press **Remove Paint** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Remove Paint · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Remove Paint' on Modify's Geometry panel (through its fold) (through its parent 'Paint''s arrow, the row 'Remove Paint'; the press stood 276 ms (the menu stood at 13 ms; its row ran 249 ms; it made 0 child widgets native)): the tool 'Remove Paint' stands | keys: Escape (tool Remove Paint -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Restore All Excluded

A UNION command on the Modify tab, Group panel.

### Press it

- Tab: Modify
- Panel: Group
- Kind: action
- Ribbon: Modify > Create

Worked example: press **Restore All Excluded** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Restore All Excluded · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Restore All Excluded' on Modify's Create panel (through its fold): it refused in words: cannot proceed: no group instance selected

## Restyle Line

A UNION command on the Modify tab, View panel. Also known as Linework. It asks: "Select lines, then click to restyle".

### Linework

- Tab: Modify
- Panel: View
- Kind: tool
- Ribbon: Modify > View

Worked example: press **Restyle Line** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Linework · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Linework' on Modify's View panel: the tool 'Linework' stands | keys: Escape (tool Linework -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Becomes | choice | As It Is | As It Is, 3D Line, 2D Line | all |
| Line Style | choice | Thin Lines |  | all |

## Rotate

A UNION command on the Modify tab, Modify panel. It asks: "Click the center of rotation".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify

Worked example: press **Rotate** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Rotate · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Rotate' on Modify's Modify panel (through its fold): the tool 'Rotate' stands | keys: Escape (tool Rotate -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Angle | angle | 0 |  | all |
| Center of Rotation | choice | Default | Place, Default | all |
| Copy | yesno | false |  | all |
| Disjoin | yesno | false |  | all |

Played in these jobs:

- [6003. Turn the 5 m wall a quarter turn about its centre so it runs north to south.](../examples/change-modify-and-freeform.md)
- [6029. Turn the 5 m return duct a quarter turn about its centre, then delete the 2 m stub.](../examples/change-modify-and-freeform.md)
- [6068. Move, copy and turn the wall, take the three changes back one by one, then redo the first.](../examples/change-modify-and-freeform.md)
- [6071. Turn the 6 m roof beam a quarter turn about its centre to run it north to south.](../examples/change-modify-and-freeform.md)

## Same Again

A UNION command on the Modify tab, Modify panel. Also known as Create Similar. It asks: "Click to place the new element".

### Create Similar

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Create

Worked example: press **Same Again** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Create Similar · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create Similar' on Modify's Create panel (through its fold): the tool 'Create Similar' stands | keys: Escape (tool Create Similar -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Scale

A UNION command on the Modify tab, Modify panel. It asks: "Click an origin point to scale from".

### Press it

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Modify

Worked example: press **Scale** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Scale · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Scale' on Modify's Modify panel (through its fold): the tool 'Scale' stands | keys: Escape (tool Scale -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Numerical | yesno | false |  | all |
| Scale | number | 2 |  | all |

Played in these jobs:

- [6075. Scale the 6 m boundary wall up from its west end to 9 m.](../examples/change-modify-and-freeform.md)

## Select Elements by Face

A UNION command on the Modify tab, Select panel.

### Press it

- Tab: Modify
- Panel: Select
- Kind: action
- Ribbon: Modify > Select

Worked example: press **Select Elements by Face** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Select Elements by Face · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Select Elements by Face' on Modify's Select panel: the command 'Select Elements by Face' ran; status 'Select Elements by Face: off' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Select Links

A UNION command on the Modify tab, Select panel.

### Press it

- Tab: Modify
- Panel: Select
- Kind: action
- Ribbon: Modify > Select

Worked example: press **Select Links** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Select Links · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Select Links' on Modify's Select panel: the command 'Select Links' ran; status 'Select Links: off' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Select Pinned Elements

A UNION command on the Modify tab, Select panel.

### Press it

- Tab: Modify
- Panel: Select
- Kind: action
- Ribbon: Modify > Select

Worked example: press **Select Pinned Elements** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Select Pinned Elements · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Select Pinned Elements' on Modify's Select panel (the window's first paint at 4731 ms in QWidget#SheetsRenderHost): the command 'Select Pinned Elements' ran; status 'Select Pinned Elements: off' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Select Underlay Elements

A UNION command on the Modify tab, Select panel.

### Press it

- Tab: Modify
- Panel: Select
- Kind: action
- Ribbon: Modify > Select

Worked example: press **Select Underlay Elements** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Select Underlay Elements · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Select Underlay Elements' on Modify's Select panel: the command 'Select Underlay Elements' ran; status 'Select Underlay Elements: off' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Show Controls

A UNION command on the Modify tab, Measure panel. Also known as Activate Controls and Dimensions.

### Activate Controls and Dimensions

- Tab: Modify
- Panel: Measure
- Kind: tool
- Ribbon: Modify > Measure

Worked example: press **Show Controls** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Activate Controls and Dimensions · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Activate Controls and Dimensions' on Modify's Measure panel (through its fold): the command 'Activate Controls and Dimensions' ran; status 'Show Controls off' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Show Related Warnings

A UNION command on the Modify tab, Warning panel.

### Press it

- Tab: Modify
- Panel: Warning
- Kind: action
- Ribbon: Modify > Warning

Worked example: press **Show Related Warnings** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Show Related Warnings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Show Related Warnings' on Modify's Warning panel: it refused in words: cannot proceed: nothing is selected

## Split › Split Element

A UNION command on the Modify tab, Edit panel.

### Press it

- Tab: Modify
- Panel: Edit
- Ribbon: Modify > Edit > Split

Worked example: press **Split › Split Element** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Split › Split Element · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Split › Split Element' on Modify's Edit panel (through its fold) (through its parent 'Split''s arrow, the row 'Split Element'; the press stood 393 ms (the menu stood at 20 ms; its row ran 372 ms; it made 0 child widgets native)): the command 'Split › Split Element' ran; status 'Click an element to break it there' | keys: Escape (tool Break -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Split Face

A UNION command on the Modify tab, Geometry panel.

### Press it

- Tab: Modify
- Panel: Geometry
- Ribbon: Modify > Geometry

Worked example: press **Split Face** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Split Face · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Split Face' on Modify's Geometry panel (through its fold): the command 'Split Face' ran; status 'Split Face: click a face of an element, then the corners of the region (Enter finishes, Esc cancels).' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Trim Many

A UNION command on the Modify tab, Modify panel. Also known as Trim/Extend Multiple Elements.

### Trim/Extend › Trim/Extend Multiple Elements

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Edit > Trim/Extend

Worked example: press **Trim Many** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Trim/Extend › Trim/Extend Multiple Elements · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Trim/Extend › Trim/Extend Multiple Elements' on Modify's Edit panel (through its fold) (through its parent 'Trim/Extend''s arrow, the row 'Trim/Extend Multiple Elements'; the press stood 150 ms (the menu stood at 16 ms; its row ran 120 ms; it made 0 child widgets native)): the tool 'Trim/Extend › Trim/Extend Multiple Elements' stands | keys: Escape (tool Trim/Extend › Trim/Extend Multiple Elements -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Trim Single

A UNION command on the Modify tab, Modify panel. Also known as Trim/Extend Single Element.

### Trim/Extend › Trim/Extend Single Element

- Tab: Modify
- Panel: Modify
- Kind: tool
- Ribbon: Modify > Edit > Trim/Extend

Worked example: press **Trim Single** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Trim/Extend › Trim/Extend Single Element · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Trim/Extend › Trim/Extend Single Element' on Modify's Edit panel (through its fold) (through its parent 'Trim/Extend''s arrow, the row 'Trim/Extend Single Element'; the press stood 50 ms (the menu stood at 22 ms; its row ran 8 ms; it made 0 child widgets native)): the tool 'Trim/Extend › Trim/Extend Single Element' stands | keys: Escape (tool Trim/Extend › Trim/Extend Single Element -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6037. Extend the 5 m partition east until it meets the boundary wall.](../examples/change-modify-and-freeform.md)

## Trim/Extend › Trim/Extend to Corner

A UNION command on the Modify tab, Edit panel.

### Press it

- Tab: Modify
- Panel: Edit
- Ribbon: Modify > Edit > Trim/Extend

Worked example: press **Trim/Extend › Trim/Extend to Corner** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Trim/Extend › Trim/Extend to Corner · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Trim/Extend › Trim/Extend to Corner' on Modify's Edit panel (through its fold) (through its parent 'Trim/Extend''s arrow, the row 'Trim/Extend to Corner'; the press stood 393 ms (the menu stood at 26 ms; its row ran 366 ms; it made 0 child widgets native)): the tool 'Trim/Extend › Trim/Extend to Corner' stands | keys: Escape (tool Trim/Extend › Trim/Extend to Corner -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6036. Trim the south wall and the east wall to meet in a clean corner.](../examples/change-modify-and-freeform.md)

## Trim/Extend Settings

A UNION command on the Modify tab, Edit panel.

### modify-trim-settings

- Tab: Modify
- Panel: Edit
- Ribbon: Modify > Edit

Worked example: press **Trim/Extend Settings** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:modify-trim-settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'modify-trim-settings' on Modify's Edit panel (through its fold) (through its parent 'Trim/Extend''s arrow, the row 'Trim/Extend Settings'; the press stood 148 ms (the menu stood at 15 ms; its row ran 133 ms; the window's first paint at 133 ms in union_shell::ShellDialogWindow, dialog 'Trim/Extend Settings'; the dialog stood 760 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Trim/Extend Settings' opened and stood; closed by the player | inside the modal 'Trim/Extend Settings' | keys: Escape (no tool, dialog 'Trim/Extend Settings' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Type Properties

A UNION command on the Modify tab, Properties panel.

### Press it

- Tab: Modify
- Panel: Properties
- Ribbon: Modify > Properties

Worked example: press **Type Properties** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Type Properties · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Type Properties' on Modify's Properties panel: it refused in words: cannot proceed: Select an element to see its type settings.

## Ungroup

A UNION command on the Modify tab, Group panel.

### Press it

- Tab: Modify
- Panel: Group
- Kind: action
- Ribbon: Modify > Create

Worked example: press **Ungroup** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Ungroup · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Ungroup' on Modify's Create panel (through its fold): it refused in words: cannot proceed: nothing selected is in a group

## Unpack Import

A UNION command on the Modify tab, Create panel.

### Press it

- Tab: Modify
- Panel: Create
- Kind: action
- Ribbon: Modify > Create

Worked example: press **Unpack Import** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Unpack Import · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Unpack Import' on Modify's Create panel (through its fold): it refused in words: cannot proceed: nothing selected is an imported drawing

## Wall Joins

A UNION command on the Modify tab, Geometry panel. It asks: "Pick a wall end at the junction".

### Press it

- Tab: Modify
- Panel: Geometry
- Kind: tool
- Ribbon: Modify > Geometry

Worked example: press **Wall Joins** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Modify:Wall Joins · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall Joins' on Modify's Geometry panel (through its fold): the tool 'Wall Joins' stands | keys: Escape (tool Wall Joins -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
