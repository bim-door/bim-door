# UNION commands: Structural

49 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## 3D Line

A UNION command on the Structural tab, Model panel. Also known as Model Line. It asks: "Click to start the model line".

### Model Line

- Tab: Structural
- Panel: Model
- Kind: tool
- Ribbon: Setout > Reference
- Draw modes: Line, Rectangle, Inscribed Polygon, Circumscribed Polygon, Circle, Start-End-Radius Arc, Center-ends Arc, Ellipse, Pick Lines, Spline, Partial Ellipse

Worked example: press **3D Line** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Setout:Model Line · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Model Line' on Setout's Reference panel: the tool 'Model Line' stands | keys: Escape (tool Model Line -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Chain | yesno | true |  | Line |
| Sides | number | 6 |  | Inscribed Polygon, Circumscribed Polygon |

Played in these jobs:

- [6042. Draw a spline model line through four points for the garden path edge, then copy it 3 m north for the other edge.](../examples/change-modify-and-freeform.md)
- [6043. Draw the 6 x 4 m pavilion footprint as a rectangle of model lines.](../examples/change-modify-and-freeform.md)
- [6044. Draw the fountain as a model line circle of 2.5 m radius.](../examples/change-modify-and-freeform.md)
- [6045. Draw the L-shaped setting-out line as three connected model lines.](../examples/change-modify-and-freeform.md)
- [6046. Draw the curved bench back as a model line arc, 6 m chord with a 2.5 m rise.](../examples/change-modify-and-freeform.md)

## 3D Text

A UNION command on the Structural tab, Model panel. Also known as Model Text. It asks: "Click to place the text, then type it".

### Model Text

- Tab: Structural
- Panel: Model
- Kind: tool
- Ribbon: Setout > Reference
- Draw modes: Line

Worked example: press **3D Text** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Setout:Model Text · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Model Text' on Setout's Reference panel: the tool 'Model Text' stands | keys: Escape (tool Model Text -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Abbreviations

A UNION command on the Structural tab, Reinforcement panel.

### Reinforcement Settings › Abbreviations

- Tab: Structural
- Panel: Reinforcement
- Kind: action
- Ribbon: Manage > Settings > Reinforcement Settings

Worked example: press **Abbreviations** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:Reinforcement Settings › Abbreviations · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Reinforcement Settings › Abbreviations' on Manage's Settings panel (through its fold) (through its parent 'Structural Settings''s arrow, the row 'Abbreviations'; the press stood 139 ms (the menu stood at 43 ms; its row ran 96 ms; the window's first paint at 96 ms in union_shell::ShellDialogWindow, dialog 'Abbreviations'; the dialog stood 706 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Abbreviations' opened and stood; closed by the player | inside the modal 'Abbreviations' | keys: Escape (no tool, dialog 'Abbreviations' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Area

A UNION command on the Structural tab, Reinforcement panel. Also known as Area Reinforcement. It asks: "Click a floor, a foundation slab or a wall, then sketch the boundary of the area reinforcement".

### Press it

- Tab: Structural
- Panel: Reinforcement
- Kind: tool
- Ribbon: Structural > Reinforcement
- Draw modes: Line, Rectangle, Circle, Pick Lines

Worked example: press **Area** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Area · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Area' on Structure's Reinforcement panel (through its fold) (through its parent 'Rebar''s arrow, the row 'Area'; the press stood 345 ms (the menu stood at 23 ms; its row ran 320 ms; it made 0 child widgets native)): the tool 'Area' stands | keys: Escape (tool Area -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Bar Diameter | length | 16 |  | all |
| Layer | choice | Top and Bottom | Top, Bottom, Top and Bottom | all |
| Spacing | length | 200 |  | all |

## Bar Coupler

A UNION command on the Structural tab, Reinforcement panel. Also known as Rebar Coupler. It asks: "Pick a bar end, or two bar ends to join".

### Rebar Coupler

- Tab: Structural
- Panel: Reinforcement
- Kind: tool
- Ribbon: Structural > Reinforcement
- Draw modes: Line

Worked example: press **Bar Coupler** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Rebar Coupler · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Rebar Coupler' on Structure's Reinforcement panel (through its fold) (through its parent 'Rebar''s arrow, the row 'Rebar Coupler'; the press stood 48 ms (the menu stood at 22 ms; its row ran 7 ms; it made 0 child widgets native)): the tool 'Rebar Coupler' stands | keys: Escape (tool Rebar Coupler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Brace on Form

A UNION command on the Structural tab, Form panel. It asks: "Click the first point on the Form surface".

### Press it

- Tab: Structural
- Panel: Form
- Kind: tool
- Ribbon: Freeform > Form

Worked example: press **Brace on Form** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Brace on Form · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Brace on Form' on Massing & Site's Form panel: the tool 'Brace on Form' stands | keys: Escape (tool Brace on Form -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Bracing

A UNION command on the Structural tab, Elements panel. Also known as Brace. It asks: "Click the start attachment".

### Brace

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Structural > Framing
- Draw modes: Line

Worked example: press **Bracing** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Brace · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Brace' on Structure's Framing panel: it refused in words: cannot proceed: Brace works in a plan, section or elevation view

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| End Level | level | Level 1 |  | all |
| End Level Offset | length | 0 |  | all |
| Start Level | level | Level 1 |  | all |
| Start Level Offset | length | 0 |  | all |
| Structural Usage | choice | Vertical Bracing | Vertical Bracing, Kicker Bracing, Web, Other | all |

## Column

A UNION command on the Structural tab, Elements panel. It asks: "Click to place a column, or drag a window across grid intersections".

### Press it

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Structural > Structure

Worked example: press **Column** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Column · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Column' on Structure's Structure panel: the tool 'Column' stands | keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| 3D Snapping | yesno | false |  | all |
| At Columns | yesno | false |  | all |
| At Grids | yesno | false |  | all |
| Base Offset | length | 0 |  | all |
| Direction | choice | Height | Depth, Height | all |
| Storey | level | Level 1 |  | all |
| Top Level | choice | Level 2 | Level 2, Unconnected | all |
| Rotate after placement | yesno | false |  | all |
| Slanted Column | yesno | false |  | all |
| Tag on Placement | yesno | false |  | all |
| Top Offset | length | 0 |  | all |
| Unconnected Height | length | 3000 |  | all |

Played in these jobs:

- [1011. Set out a square column grid, three bays each way at 8 m, lettered across and numbered up, with a column at every crossing.](../examples/setting-out-and-structure.md)
- [1012. The building sits skew to the boundary: set out a 7.5 x 6 m grid and swing the whole grid 30 degrees, then put columns on the crossings.](../examples/setting-out-and-structure.md)
- [1013. Set out a fan-shaped grid for an auditorium: five lines splayed 10 degrees apart from the stage point, cut by one cross line, with a column at each crossing.](../examples/setting-out-and-structure.md)
- [1014. Set out the plant room grid with uneven bays of 6.0, 7.5, 9.0, 7.5 and 6.0 m and two rows 12 m apart, with a column at every crossing.](../examples/setting-out-and-structure.md)
- [1021. Click in two grid lines each way for a 6 x 6 m bay and put columns where they cross.](../examples/setting-out-and-structure.md)
- [1025. Click in six columns along the south wall line, 4.5 m apart.](../examples/setting-out-and-structure.md)
- [1037. Set out a portal-frame shed: five frames 7.5 m apart, 24 m span, columns at every frame and an eaves beam down each side.](../examples/setting-out-and-structure.md)
- [1042. Set out the column grid for a warehouse: six 9 m bays along its length, three 10 m bays across, a column at every crossing.](../examples/setting-out-and-structure.md)
- [1043. Lay out the column grid of a car-park deck: four bays of 8.1 m and two rows of columns 16.2 m apart.](../examples/setting-out-and-structure.md)
- [1044. Add a basement car park 3.2 m down and put its columns on a 8.1 x 16.2 m grid, up to the ground floor.](../examples/setting-out-and-structure.md)
- [1045. Set out a mezzanine at 3 m on its own grid, three lines 7.5 m apart by two lines 6 m apart, with a beam along each grid line.](../examples/setting-out-and-structure.md)
- [1047. Stack the columns of a two-deck car park: decks at 2.9 m and 5.8 m, eight columns on each deck, on a 8.1 x 16.2 m grid.](../examples/setting-out-and-structure.md)

### Column: Architectural › Column: Structural

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Architectural > Build > Column: Architectural

Worked example: press **Column** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Column: Architectural › Column: Structural · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Column: Architectural › Column: Structural' on Architecture's Build panel (through its parent 'Column: Architectural''s arrow, the row 'Column: Structural'; the press stood 2693 ms (the menu stood at 362 ms; its row ran 2329 ms; it made 0 child widgets native)): the tool 'Column' stands | keys: Escape (tool Column -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Column on Form

A UNION command on the Structural tab, Form panel. It asks: "Click the first point on the Form surface".

### Press it

- Tab: Structural
- Panel: Form
- Kind: tool
- Ribbon: Freeform > Form

Worked example: press **Column on Form** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Column on Form · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Column on Form' on Massing & Site's Form panel: the tool 'Column on Form' stands | keys: Escape (tool Column on Form -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Construction Plane

A UNION command on the Structural tab, Work Plane panel. Also known as Ref Plane, Reference Plane, Reference Plane (family). It asks: "Click to start the reference plane".

### Ref Plane

- Tab: Structural
- Panel: Work Plane
- Kind: tool
- Ribbon: Setout > Work Plane
- Draw modes: Line, Pick Lines

Worked example: press **Construction Plane** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Setout:Ref Plane · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Ref Plane' on Setout's Work Plane panel: the tool 'Ref Plane' stands | keys: Escape (tool Ref Plane -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Lock | yesno | false |  | Pick Lines |
| Offset | length | 0 |  | all |

## Cover

A UNION command on the Structural tab, Reinforcement panel.

### Reinforcement Settings › Cover

- Tab: Structural
- Panel: Reinforcement
- Kind: tool
- Ribbon: Structural > Reinforcement > Reinforcement Settings

Worked example: press **Cover** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Reinforcement Settings › Cover · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Reinforcement Settings › Cover' on Structure's Reinforcement panel (through its fold) (through its parent 'Reinforcement Settings''s arrow, the row 'Cover'; the press stood 610 ms (the menu stood at 19 ms; its row ran 589 ms; it made 0 child widgets native)): the tool 'Cover' stands | keys: Escape (tool Cover -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## draw-ceiling

A UNION command on the Structural tab, Elements panel. It asks: "Click points to sketch the ceiling boundary".

### Press it

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Architectural > Build
- Draw modes: Automatic Ceiling, Sketch Ceiling

Worked example: press **draw-ceiling** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:draw-ceiling · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'draw-ceiling' on Architecture's Build panel: the tool 'draw-ceiling' stands | keys: Escape (tool draw-ceiling -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Grid | choice | 600x1200 | 600x1200, 600x600, none | all |
| Height Offset From Level | length | 2700 |  | all |
| Type | choice |  |  | all |

Played in these jobs:

- [2017. Ceiling the reception at 2700 and the meeting room at 2400 with a 600 x 600 grid, by clicking in each room.](../examples/architecture.md)

## draw-ramp

A UNION command on the Structural tab, Elements panel. It asks: "Click points to sketch the ramp path".

### Press it

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Architectural > Circulation
- Works in views: plan, three_d
- Draw modes: Line

Worked example: press **draw-ramp** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:draw-ramp · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'draw-ramp' on Architecture's Circulation panel: the tool 'draw-ramp' stands | keys: Escape (tool draw-ramp -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Base Level | level |  |  | all |
| Gradient | number | 14 |  | all |
| Maximum Rise | length | 750 |  | all |
| Shape | choice | straight | straight, switchback | all |
| Top Level | level |  |  | all |
| Width | length | 1200 |  | all |

Played in these jobs:

- [2038. Draw a 10 m long, 1200 wide access ramp up from Ground and put a handrail along each side.](../examples/architecture.md)

## draw-stair

A UNION command on the Structural tab, Elements panel. It asks: "Click points to sketch the stair run".

### Press it

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Architectural > Circulation
- Works in views: plan, three_d
- Draw modes: Line, Rectangle

Worked example: press **draw-stair** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:draw-stair · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'draw-stair' on Architecture's Circulation panel: the tool 'draw-stair' stands | keys: Escape (tool draw-stair -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Begin with Riser | yesno | true |  | all |
| End with Riser | yesno | true |  | all |
| Gap | length | 100 |  | all |
| Going | length | 280 |  | all |
| Height | length | 0 |  | all |
| Inner Radius | length | 100 |  | all |
| Base Level | level |  |  | all |
| Location Line | choice | Run: Center | Run: Center, Run: Left, Run: Right | all |
| Multistorey Top Level | level |  |  | all |
| Offset | length | 0 |  | all |
| Maximum Riser | length | 175 |  | all |
| Shape | choice | straight | straight, L, U, winderL, winderU, spiral, sketched | all |
| Sweep | angle | 360 |  | all |
| Turn | choice | left | left, right | all |
| Width | length | 1000 |  | all |

Played in these jobs:

- [2035. Put a 1000 wide spiral stair from Ground to Level 1 inside a 3.4 m square stairwell.](../examples/architecture.md)
- [2036. Draw an L-shaped stair from Ground to Level 1 in the 3 x 5 m stair hall.](../examples/architecture.md)
- [2037. Draw a U-shaped stair 1100 wide from Ground to Level 1 in the stair core of the walk-up.](../examples/architecture.md)
- [6056. Put a 1 m wide spiral stair in the corner of the atrium, Ground up to Level 1.](../examples/change-modify-and-freeform.md)
- [6057. Draw a 1.2 m wide spiral stair turning left through three quarters of a turn to the mezzanine at Level 1.](../examples/change-modify-and-freeform.md)

## Fabric Area

A UNION command on the Structural tab, Reinforcement panel. It asks: "Sketch the fabric area boundary".

### Press it

- Tab: Structural
- Panel: Reinforcement
- Kind: tool
- Ribbon: Structural > Reinforcement
- Draw modes: Line, Rectangle, Circle, Pick Lines

Worked example: press **Fabric Area** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Fabric Area · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Fabric Area' on Structure's Reinforcement panel (through its fold) (through its parent 'Rebar''s arrow, the row 'Fabric Area'; the press stood 86 ms (the menu stood at 43 ms; its row ran 16 ms; it made 0 child widgets native)): the tool 'Fabric Area' stands | keys: Escape (tool Fabric Area -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Fabric Sheet | choice | A393 | A142, A193, A252, A393, SL52, SL62, SL72, SL81, SL82, SL92, SL102, RL718, RL818, RL918, RL1018, RL1118, RL1218 | all |

## Fabric Sheet

A UNION command on the Structural tab, Reinforcement panel. It asks: "Click a floor or a wall to lay a fabric sheet on it".

### Press it

- Tab: Structural
- Panel: Reinforcement
- Kind: tool
- Ribbon: Structural > Reinforcement

Worked example: press **Fabric Sheet** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Fabric Sheet · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Fabric Sheet' on Structure's Reinforcement panel (through its fold) (through its parent 'Rebar''s arrow, the row 'Fabric Sheet'; the press stood 268 ms (the menu stood at 20 ms; its row ran 226 ms; it made 0 child widgets native)): the tool 'Fabric Sheet' stands | keys: Escape (tool Fabric Sheet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Fabric Sheet | choice | A393 | A142, A193, A252, A393, SL52, SL62, SL72, SL81, SL82, SL92, SL102, RL718, RL818, RL918, RL1018, RL1118, RL1218 | all |

## Face Cut-out

A UNION command on the Structural tab, Opening panel. Also known as By Face. It asks: "Sketch the opening, then Finish".

### By Face

- Tab: Structural
- Panel: Opening
- Kind: tool
- Ribbon: Architectural > Opening
- Works in views: plan, section_or_elevation, three_d
- Draw modes: Line, Rectangle

Worked example: press **Face Cut-out** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:By Face · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'By Face' on Architecture's Opening panel (through its fold): the tool 'By Face' stands | keys: Escape (tool By Face -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Floor: Structural

A UNION command on the Structural tab, Elements panel. It asks: "Sketch the floor boundary, then Finish".

### Floor: Architectural › Floor: Structural

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Architectural > Build > Floor: Architectural
- Draw modes: Line, Rectangle, Inscribed Polygon, Circumscribed Polygon, Circle, Spline, Partial Ellipse, Pick Lines, Pick Walls, Start-End-Radius Arc, Center-ends Arc, Tangent End Arc, Fillet Arc, Ellipse

Worked example: press **Floor: Structural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Floor: Architectural › Floor: Structural · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Floor: Architectural › Floor: Structural' on Architecture's Build panel (through its parent 'Floor: Architectural''s arrow, the row 'Floor: Structural'; the press stood 448 ms (the menu stood at 12 ms; its row ran 435 ms; it made 0 child widgets native)): the command 'Floor: Structural' ran; status 'Sketch the floor boundary, then Finish' | keys: Escape (tool Floor -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Extend into wall | yesno | false |  | all |
| Height Offset at Head | number | 0 |  | all |
| Height Offset at Tail | number | 0 |  | all |
| Offset | length | 0 |  | all |
| Radius | length | 0 |  | all |
| Sides | number | 6 |  | Inscribed Polygon, Circumscribed Polygon |
| Slope Arrow | choice |  |  | all |
| Span Direction | angle | 0 |  | all |

### Press it

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Structural > Structure

Worked example: press **Floor: Structural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Floor · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Floor' on Structure's Structure panel: the tool 'Floor' stands | keys: Escape (tool Floor -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Framing

A UNION command on the Structural tab, Elements panel. Also known as Beam. It asks: "Click to start the beam".

### Beam

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Structural > Framing
- Draw modes: Line, Pick Lines, Start-End-Radius Arc, Center-ends Arc

Worked example: press **Framing** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Beam · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Beam' on Structure's Framing panel: the tool 'Beam' stands | keys: Escape (tool Beam -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| 3D Snapping | yesno | false |  | Line |
| Chain | yesno | false |  | Line |
| On Grids | yesno | false |  | Line |
| Placement Plane | level | Level 1 |  | all |
| Structural Usage | choice | Girder | Girder, Joist, Purlin, Other, Horizontal Bracing, Kicker Bracing | all |

Played in these jobs:

- [1030. Frame a four-storey steel building 9 x 6 m: four columns full height and a ring of beams at each floor.](../examples/setting-out-and-structure.md)
- [1032. Click a ring of beams round a 12 x 9 m bay at the first floor, 3.6 m up.](../examples/setting-out-and-structure.md)
- [1056. Frame the roof of a 12 x 8 m building in steel: four columns Ground to the Roof, a ring beam by clicks and one purlin across the middle.](../examples/setting-out-and-structure.md)

## Framing Layout

A UNION command on the Structural tab, Elements panel. Also known as Beam System. It asks: "Click in a bay, or click the first corner".

### Beam System

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Structural > Framing
- Draw modes: Line, Pick Lines

Worked example: press **Framing Layout** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Beam System · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Beam System' on Structure's Framing panel: the tool 'Beam System' stands | keys: Escape (tool Beam System -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Automatic | yesno | true |  | all |
| Justification | choice | Center | Beginning, Center, End | all |
| Layout Rule | choice | Fixed Number | Fixed Distance, Fixed Number, Maximum Spacing, Clear Spacing | all |
| Spacing or Number | number | 4 |  | all |
| Tag on Placement | yesno | false |  | all |
| Walls Define Slope | yesno | false |  | all |

## Freeform Curve

A UNION command on the Structural tab, Form panel. It asks: "Click control point 1 of at least 4".

### Press it

- Tab: Structural
- Panel: Form
- Kind: tool
- Ribbon: Freeform > Form
- Draw modes: Line

Worked example: press **Freeform Curve** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Freeform Curve · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Freeform Curve' on Massing & Site's Form panel: the tool 'Freeform Curve' stands | keys: Escape (tool Freeform Curve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Degree | choice | 3 | 1, 2, 3 | all |
| Interpolate | yesno | true |  | all |
| Storey | level |  |  | all |
| Offset | length | 0 |  | all |

Played in these jobs:

- [6048. Draw a faceted degree 1 curve through five points for the folded-plate edge.](../examples/change-modify-and-freeform.md)
- [6049. Draw the fascia line as a degree 2 curve driven by control points rather than passing through them.](../examples/change-modify-and-freeform.md)
- [6050. Draw the balustrade top-rail curve on Level 1, 500 mm above the floor.](../examples/change-modify-and-freeform.md)
- [6051. Loft a canopy surface between the front edge curve and the raised back edge curve.](../examples/change-modify-and-freeform.md)
- [6052. Loft the shell through three section curves and divide it into hexagonal panels.](../examples/change-modify-and-freeform.md)
- [6053. Revolve the profile curve 360 degrees about a vertical axis to make the column vase.](../examples/change-modify-and-freeform.md)
- [6054. Revolve the profile 180 degrees to make the half-round apse surface.](../examples/change-modify-and-freeform.md)
- [6055. Sweep the small section curve along the rail curve to model the curved handrail.](../examples/change-modify-and-freeform.md)
- [6058. Loft a roof shell through two curves on Level 1 for the stadium canopy study.](../examples/change-modify-and-freeform.md)
- [6062. Loft the two curves, take the loft back with undo, then put it back with redo.](../examples/change-modify-and-freeform.md)
- [6063. Draw a trial curve, decide against it and delete it.](../examples/change-modify-and-freeform.md)

## Gridline

A UNION command on the Structural tab, Datums panel. Also known as Grid. It asks: "Click point 1 of 2".

### Grid

- Tab: Structural
- Panel: Datums
- Kind: tool
- Ribbon: Setout > Datum
- Draw modes: Line, Start-End-Radius Arc, Center-ends Arc, Pick Lines, Multi-Segment

Worked example: press **Gridline** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Setout:Grid · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Grid' on Setout's Datum panel: the tool 'Grid' stands | keys: Escape (tool Grid -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | Line, Pick Lines |

Played in these jobs:

- [1021. Click in two grid lines each way for a 6 x 6 m bay and put columns where they cross.](../examples/setting-out-and-structure.md)

## Lap Bars

A UNION command on the Structural tab, Reinforcement panel. It asks: "Click a bar where it is to be lapped".

### Press it

- Tab: Structural
- Panel: Reinforcement
- Kind: tool
- Ribbon: Structural > Reinforcement

Worked example: press **Lap Bars** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Lap Bars · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Lap Bars' on Structure's Reinforcement panel (through its fold) (through its parent 'Rebar''s arrow, the row 'Lap Bars'; the press stood 90 ms (the menu stood at 12 ms; its row ran 64 ms; it made 0 child widgets native)): the tool 'Lap Bars' stands | keys: Escape (tool Lap Bars -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Split At | choice | Press | Press, Line, Stock Length | all |
| Stock Length | length | 12000 |  | all |

## Loft

A UNION command on the Structural tab, Form panel. Also known as Blend. It asks: "Click a Freeform Curve to loft through, in pick order".

### Press it

- Tab: Structural
- Panel: Form
- Kind: tool
- Ribbon: Freeform > Form

Worked example: press **Loft** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Loft · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Loft' on Massing & Site's Form panel: the tool 'Loft' stands | keys: Escape (tool Loft -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6051. Loft a canopy surface between the front edge curve and the raised back edge curve.](../examples/change-modify-and-freeform.md)
- [6052. Loft the shell through three section curves and divide it into hexagonal panels.](../examples/change-modify-and-freeform.md)
- [6058. Loft a roof shell through two curves on Level 1 for the stadium canopy study.](../examples/change-modify-and-freeform.md)
- [6062. Loft the two curves, take the loft back with undo, then put it back with redo.](../examples/change-modify-and-freeform.md)

## Member Opening

A UNION command on the Structural tab, Opening panel. It asks: "Click where the opening starts along the beam or brace".

### Press it

- Tab: Structural
- Panel: Opening
- Kind: tool
- Ribbon: Structural > Opening
- Draw modes: Rectangle

Worked example: press **Member Opening** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Member Opening · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Member Opening' on Structure's Opening panel (through its fold): the tool 'Member Opening' stands | keys: Escape (tool Member Opening -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Corner Fillet | length | 0 |  | all |
| Opening Bottom | length | 0 |  | all |
| Opening Top | length | 0 |  | all |

## Pad Footing

A UNION command on the Structural tab, Foundation panel. Also known as Isolated. It asks: "Click to place a foundation".

### Isolated

- Tab: Structural
- Panel: Foundation
- Kind: tool
- Ribbon: Structural > Foundation

Worked example: press **Pad Footing** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Isolated · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Isolated' on Structure's Foundation panel (through its fold): the tool 'Isolated' stands | keys: Escape (tool Isolated -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Pile Columns | number | 0 |  | all |
| Pile Diameter | number | 300 |  | all |
| Pile Length | number | 6000 |  | all |
| Pile Rows | number | 0 |  | all |
| Pile Spacing | number | 900 |  | all |

## Path

A UNION command on the Structural tab, Reinforcement panel. It asks: "Click the start and end points of the path".

### Press it

- Tab: Structural
- Panel: Reinforcement
- Kind: tool
- Ribbon: Structural > Reinforcement

Worked example: press **Path** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Path · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Path' on Structure's Reinforcement panel (through its fold) (through its parent 'Rebar''s arrow, the row 'Path'; the press stood 71 ms (the menu stood at 13 ms; its row ran 45 ms; it made 0 child widgets native)): the tool 'Path' stands | keys: Escape (tool Path -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Bar Diameter | length | 16 |  | all |
| Bar Length | length | 1500 |  | all |
| Hook at End | text |  |  | all |
| Hook at Start | text |  |  | all |
| Layer | choice | Top | Top, Bottom, Top and Bottom | all |
| Short Bar Length | length | 0 |  | all |
| Spacing | length | 200 |  | all |

## Plate

A UNION command on the Structural tab, Connection panel. It asks: "Select a steel connection, then press Enter to add a plate".

### Press it

- Tab: Structural
- Panel: Connection
- Kind: tool
- Ribbon: Structural > Framing

Worked example: press **Plate** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Plate · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Plate' on Structure's Framing panel: it refused in words: cannot proceed: Plate works in a plan, section or elevation view

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Face | choice | side.left | side.left, side.right, side.top, side.bottom, web.left, web.right, flange.top, flange.bottom | all |
| Height | length | 200 |  | all |
| Thickness | length | 10 |  | all |
| Width | length | 150 |  | all |

## Raft

A UNION command on the Structural tab, Foundation panel. Also known as Slab. It asks: "Sketch the foundation slab boundary, then Finish".

### Slab

- Tab: Structural
- Panel: Foundation
- Kind: tool
- Ribbon: Structural > Foundation
- Works in views: plan, three_d
- Draw modes: Line, Rectangle, Pick Lines

Worked example: press **Raft** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Slab · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Slab' on Structure's Foundation panel (through its fold) (the window's first paint at 67 ms in QDialog#ScopeBoxViewsPopup, dialog 'Go To View'): the dialog 'Go To View' opened and stood; closed by the player | inside the modal 'Go To View' | keys: Escape (no tool, dialog 'Go To View' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Extend into wall | yesno | false |  | all |
| Offset | length | 0 |  | all |

## Rebar

A UNION command on the Structural tab, Reinforcement panel. It asks: "Click a column, a beam or a floor to reinforce it".

### Press it

- Tab: Structural
- Panel: Reinforcement
- Kind: tool
- Ribbon: Structural > Reinforcement

Worked example: press **Rebar** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Rebar · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Rebar' on Structure's Reinforcement panel (through its fold): the tool 'Rebar' stands | keys: Escape (tool Rebar -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Bar Diameter | length | 16 |  | all |
| Bar Shape | choice | Straight | Straight, L Bar, U Bar, Hooked Bar, Link | all |
| Cover | length | 40 |  | all |
| Hook at End | text |  |  | all |
| Layout | choice | Cage | Cage, Single | all |
| Spacing | length | 200 |  | all |

## Rebar Cover Settings

A UNION command on the Structural tab, Reinforcement panel.

### Reinforcement Settings › Cover Settings

- Tab: Structural
- Panel: Reinforcement
- Kind: action
- Ribbon: Structural > Reinforcement > Reinforcement Settings

Worked example: press **Rebar Cover Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Reinforcement Settings › Cover Settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Reinforcement Settings › Cover Settings' on Structure's Reinforcement panel (through its fold) (through its parent 'Reinforcement Settings''s arrow, the row 'Rebar Cover Settings'; the press stood 79 ms (the menu stood at 12 ms; its row ran 67 ms; the window's first paint at 67 ms in union_shell::ShellDialogWindow, dialog 'Rebar Cover Settings'; the dialog stood 764 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Rebar Cover Settings' opened and stood; closed by the player | inside the modal 'Rebar Cover Settings' | keys: Escape (no tool, dialog 'Rebar Cover Settings' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

### Reinforcement Settings › Rebar Cover Settings

- Tab: Structural
- Panel: Reinforcement
- Kind: action
- Ribbon: Manage > Settings > Reinforcement Settings

Worked example: press **Rebar Cover Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:Reinforcement Settings › Rebar Cover Settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Reinforcement Settings › Rebar Cover Settings' on Manage's Settings panel (through its fold) (through its parent 'Structural Settings''s arrow, the row 'Rebar Cover Settings'; the press stood 78 ms (the menu stood at 16 ms; its row ran 62 ms; the window's first paint at 62 ms in union_shell::ShellDialogWindow, dialog 'Rebar Cover Settings'; the dialog stood 1164 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Rebar Cover Settings' opened and stood; closed by the player | inside the modal 'Rebar Cover Settings' | keys: Escape (no tool, dialog 'Rebar Cover Settings' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Reinforcement Numbers

A UNION command on the Structural tab, Reinforcement panel.

### Reinforcement Settings › Reinforcement Numbers

- Tab: Structural
- Panel: Reinforcement
- Kind: action
- Ribbon: Manage > Settings > Reinforcement Settings

Worked example: press **Reinforcement Numbers** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:Reinforcement Settings › Reinforcement Numbers · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Reinforcement Settings › Reinforcement Numbers' on Manage's Settings panel (through its fold) (through its parent 'Structural Settings''s arrow, the row 'Reinforcement Numbers'; the press stood 121 ms (the menu stood at 19 ms; its row ran 102 ms; the window's first paint at 102 ms in union_shell::ShellDialogWindow, dialog 'Reinforcement Numbers'; the dialog stood 695 ms more after it painted (all that ran in it, the player's waits included); it made 0 child widgets native)): the dialog 'Reinforcement Numbers' opened and stood; closed by the player | inside the modal 'Reinforcement Numbers' | keys: Escape (no tool, dialog 'Reinforcement Numbers' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Reinforcement Settings

A UNION command on the Structural tab, Reinforcement panel.

### Press it

- Tab: Structural
- Panel: Reinforcement
- Kind: action
- Ribbon: Structural > Reinforcement

Worked example: press **Reinforcement Settings** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Reinforcement Settings · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Reinforcement Settings' on Structure's Reinforcement panel (through its fold) (the window's first paint at 301 ms in union_shell::ShellDialogWindow, dialog 'Reinforcement Settings'): the dialog 'Reinforcement Settings' opened and stood; closed by the player | inside the modal 'Reinforcement Settings' | keys: Escape (no tool, dialog 'Reinforcement Settings' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Revolve

A UNION command on the Structural tab, Form panel. Also known as Revolve (family).

### Press it

- Tab: Structural
- Panel: Form
- Kind: tool
- Ribbon: Freeform > Form

Worked example: press **Revolve** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Revolve · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Revolve' on Massing & Site's Form panel: the tool 'Revolve' stands | keys: Escape (tool Revolve -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6053. Revolve the profile curve 360 degrees about a vertical axis to make the column vase.](../examples/change-modify-and-freeform.md)
- [6054. Revolve the profile 180 degrees to make the half-round apse surface.](../examples/change-modify-and-freeform.md)

## Roof Cut-out

A UNION command on the Structural tab, Opening panel. Also known as Dormer. It asks: "Sketch the dormer opening in the roof".

### Dormer

- Tab: Structural
- Panel: Opening
- Kind: tool
- Ribbon: Architectural > Opening
- Works in views: plan, section_or_elevation, three_d
- Draw modes: Rectangle, Line

Worked example: press **Roof Cut-out** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Dormer · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Dormer' on Architecture's Opening panel (through its fold): the tool 'Dormer' stands | keys: Escape (tool Dormer -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Sketch Ceiling

A UNION command on the Structural tab, Elements panel. It asks: "Sketch the ceiling boundary, then Finish".

### Press it

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Architectural > Build
- Works in views: plan, three_d
- Draw modes: Line, Rectangle, Circle, Spline, Partial Ellipse, Pick Lines, Pick Walls, Inscribed Polygon, Circumscribed Polygon, Start-End-Radius Arc, Center-ends Arc, Tangent End Arc, Fillet Arc, Ellipse

Worked example: press **Sketch Ceiling** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Sketch Ceiling · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Sketch Ceiling' on Architecture's Build panel (through its parent 'draw-ceiling''s arrow, the row 'Sketch Ceiling'; the press stood 3784 ms (the menu stood at 1557 ms; its row ran 2225 ms; it made 0 child widgets native)): the tool 'Sketch Ceiling' stands | keys: Escape (tool Sketch Ceiling -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Extend into wall | yesno | false |  | Pick Walls |
| Offset | length | 0 |  | all |
| Radius | length | 0 |  | all |
| Sides | number | 6 |  | Inscribed Polygon, Circumscribed Polygon |

## Slab Edge

A UNION command on the Structural tab, Structure panel. It asks: "Pick a floor edge".

### Floor: Architectural › Slab Edge

- Tab: Structural
- Panel: Structure
- Kind: tool
- Ribbon: Architectural > Build > Floor: Architectural
- Draw modes: Line

Worked example: press **Slab Edge** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Floor: Architectural › Slab Edge · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Floor: Architectural › Slab Edge' on Architecture's Build panel (through its parent 'Floor: Architectural''s arrow, the row 'Slab Edge'; the press stood 1152 ms (the menu stood at 397 ms; its row ran 752 ms; it made 0 child widgets native)): the tool 'Slab Edge' stands | keys: Escape (tool Slab Edge -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

### Press it

- Tab: Structural
- Panel: Structure
- Kind: tool
- Ribbon: Structural > Structure

Worked example: press **Slab Edge** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Slab Edge · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Slab Edge' on Structure's Structure panel: the tool 'Slab Edge' stands | keys: Escape (tool Slab Edge -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Steel Connection

A UNION command on the Structural tab, Connection panel. It asks: "Select the members, then click to place the connection".

### Press it

- Tab: Structural
- Panel: Connection
- Kind: tool
- Ribbon: Structural > Framing

Worked example: press **Steel Connection** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Steel Connection · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Steel Connection' on Structure's Framing panel: the tool 'Steel Connection' stands | keys: Escape (tool Steel Connection -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Hole Depth | length | 0 |  | all |
| Hole Kind | choice | Round | Round, Slotted, Oversized | all |
| Hole Size | length | 22 |  | all |
| Joint Type | choice | Shear Plate | Shear Plate, Splice, Moment | all |

## Storey

A UNION command on the Structural tab, Datums panel. Also known as Level. It asks: "Click to start the level line".

### Level

- Tab: Structural
- Panel: Datums
- Kind: tool
- Ribbon: Setout > Datum
- Draw modes: Line

Worked example: press **Storey** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Setout:Level · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Level' on Setout's Datum panel: the tool 'Level' stands | keys: Escape (tool Level -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Make Plan View | yesno | true |  | all |
| Offset | length | 0 |  | all |
| Plan View Types | choice |  |  | all |

Played in these jobs:

- [1061. Click in a new level at 4.5 m with the Level tool, then stand a column from Level 1 up to Level 2.](../examples/setting-out-and-structure.md)

## Strip Footing

A UNION command on the Structural tab, Foundation panel. Also known as Wall (foundation). It asks: "Select a wall to host the foundation".

### Wall (foundation)

- Tab: Structural
- Panel: Foundation
- Kind: tool
- Ribbon: Structural > Foundation

Worked example: press **Strip Footing** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Wall (foundation) · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall (foundation)' on Structure's Foundation panel (through its fold): the tool 'Wall (foundation)' stands | keys: Escape (tool Wall (foundation) -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Sweep

A UNION command on the Structural tab, Form panel. Also known as Sweep (family).

### Press it

- Tab: Structural
- Panel: Form
- Kind: tool
- Ribbon: Freeform > Form

Worked example: press **Sweep** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Massing \u0026 Site:Sweep · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Sweep' on Massing & Site's Form panel: the tool 'Sweep' stands | keys: Escape (tool Sweep -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [6055. Sweep the small section curve along the rail curve to model the curved handrail.](../examples/change-modify-and-freeform.md)

## Truss

A UNION command on the Structural tab, Elements panel. It asks: "Click to start the truss layout".

### Press it

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Structural > Framing
- Draw modes: Line, Pick Lines

Worked example: press **Truss** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Truss · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Truss' on Structure's Framing panel: the tool 'Truss' stands | keys: Escape (tool Truss -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Number Panels | number | 4 |  | all |
| Truss Height | length | 1000 |  | all |

## Vertical Cut-out

A UNION command on the Structural tab, Opening panel. Also known as Shaft. It asks: "Click one corner of the shaft footprint".

### Shaft

- Tab: Structural
- Panel: Opening
- Kind: tool
- Ribbon: Architectural > Opening
- Works in views: plan, three_d
- Draw modes: Rectangle, Pick Lines

Worked example: press **Vertical Cut-out** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Shaft · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Shaft' on Architecture's Opening panel (through its fold): the tool 'Shaft' stands | keys: Escape (tool Shaft -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [2031. Sketch a 1.2 x 0.8 m service riser opening through the first floor slab.](../examples/architecture.md)

## Wall Cut-out

A UNION command on the Structural tab, Opening panel. Also known as Wall (opening). It asks: "Click one corner of the opening on the wall face".

### Wall (opening)

- Tab: Structural
- Panel: Opening
- Kind: tool
- Ribbon: Architectural > Opening
- Draw modes: Rectangle

Worked example: press **Wall Cut-out** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Wall (opening) · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall (opening)' on Architecture's Opening panel (through its fold): the tool 'Wall (opening)' stands | keys: Escape (tool Wall (opening) -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Head Height | length | 0 |  | all |
| Sill Height | length | 0 |  | all |

## Wall Framing

A UNION command on the Structural tab, Elements panel. Also known as wall-framing.

### wall-framing

- Tab: Structural
- Panel: Elements
- Kind: action
- Ribbon: Structural > Framing

Worked example: press **Wall Framing** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:wall-framing · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'wall-framing' on Structure's Framing panel: it refused in words: cannot proceed: select a wall on Ground first

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Double Top Plate | yesno | false |  | all |
| Noggin Height | length | 1350 |  | all |
| Spacing | length | 450 |  | all |
| Stud | text | 90x45 |  | all |

## Wall Framing › Remove Framing

A UNION command on the Structural tab, Framing panel.

### wall-framing › Remove Framing

- Tab: Structural
- Panel: Framing
- Ribbon: Structural > Framing > wall-framing

Worked example: press **Wall Framing › Remove Framing** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:wall-framing › Remove Framing · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'wall-framing › Remove Framing' on Structure's Framing panel (through its parent 'wall-framing''s arrow, the row 'Remove Framing'; the press stood 802 ms (the menu stood at 377 ms; its row ran 423 ms; it made 0 child widgets native)): it refused in words: cannot proceed: select a wall first

## Wall Reveal

A UNION command on the Structural tab, Structure panel. It asks: "Click a wall to place a Wall Reveal".

### Press it

- Tab: Structural
- Panel: Structure
- Kind: tool
- Ribbon: Structural > Structure

Worked example: press **Wall Reveal** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Wall Reveal · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall Reveal' on Structure's Structure panel (through its parent 'Wall Sweep''s arrow, the row 'Wall Reveal'; the press stood 837 ms (the menu stood at 335 ms; its row ran 500 ms; it made 0 child widgets native)): the tool 'Wall Reveal' stands | keys: Escape (tool Wall Reveal -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Profile | text | 20x20 |  | all |

### Wall: Architectural › Wall Reveal

- Tab: Structural
- Panel: Structure
- Kind: tool
- Ribbon: Architectural > Build > Wall: Architectural

Worked example: press **Wall Reveal** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Wall: Architectural › Wall Reveal · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall: Architectural › Wall Reveal' on Architecture's Build panel (through its parent 'Wall: Architectural''s arrow, the row 'Wall Reveal'; the press stood 840 ms (the menu stood at 336 ms; its row ran 503 ms; it made 0 child widgets native)): the tool 'Wall Reveal' stands | keys: Escape (tool Wall Reveal -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Wall Sweep

A UNION command on the Structural tab, Structure panel. It asks: "Click a wall to place a Wall Sweep".

### Press it

- Tab: Structural
- Panel: Structure
- Kind: tool
- Ribbon: Structural > Structure

Worked example: press **Wall Sweep** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Wall Sweep · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall Sweep' on Structure's Structure panel: the tool 'Wall Sweep' stands | keys: Escape (tool Wall Sweep -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Apply To | choice | This Wall | This Wall, Whole Type | all |
| Offset | length | 0 |  | all |
| Profile | text | 50x50 |  | all |

### Wall: Architectural › Wall Sweep

- Tab: Structural
- Panel: Structure
- Kind: tool
- Ribbon: Architectural > Build > Wall: Architectural

Worked example: press **Wall Sweep** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Wall: Architectural › Wall Sweep · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall: Architectural › Wall Sweep' on Architecture's Build panel (through its parent 'Wall: Architectural''s arrow, the row 'Wall Sweep'; the press stood 753 ms (the menu stood at 360 ms; its row ran 392 ms; it made 0 child widgets native)): the tool 'Wall Sweep' stands | keys: Escape (tool Wall Sweep -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Wall: Structural

A UNION command on the Structural tab, Elements panel. It asks: "Click to start the wall".

### Wall: Architectural › Wall: Structural

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Architectural > Build > Wall: Architectural
- Works in views: plan, three_d
- Draw modes: Line, Rectangle, Inscribed Polygon, Circumscribed Polygon, Start-End-Radius Arc, Ellipse, Partial Ellipse, Pick Lines

Worked example: press **Wall: Structural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Wall: Architectural › Wall: Structural · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall: Architectural › Wall: Structural' on Architecture's Build panel (through its parent 'Wall: Architectural''s arrow, the row 'Wall: Structural'; the press stood 426 ms (the menu stood at 11 ms; its row ran 414 ms; it made 0 child widgets native)): the command 'Wall: Structural' ran; status 'Click to start the wall' | keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Chain | yesno | true |  | all |
| Direction | choice | Height | Height, Depth | all |
| Height | choice | Level 2 | Level 1, Level 2, Level 3, Unconnected | all |
| Join Status | choice | Allow | Allow, Disallow | all |
| Storey | level | Level 1 |  | all |
| Placement Line | choice | Wall Centerline | Wall Centerline, Core Centerline, Finish Face: Exterior, Finish Face: Interior, Core Face: Exterior, Core Face: Interior | all |
| Offset | length | 0 |  | all |
| Radius | length | 0 |  | all |
| Sides | number | 6 |  | Inscribed Polygon, Circumscribed Polygon |
| Unconnected Height | length | 3000 |  | all |

### Press it

- Tab: Structural
- Panel: Elements
- Kind: tool
- Ribbon: Structural > Structure
- Works in views: plan, three_d

Worked example: press **Wall: Structural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Wall · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall' on Structure's Structure panel: the tool 'Wall' stands | keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [4008. I have an office with a front door and a back door; give me a door list sorted by mark and put it on the schedules sheet.](../examples/views-sheets-and-schedules.md)
- [4011. List the windows of my 8 by 6 m cottage by sill height, highest first, and put the list on the schedules sheet.](../examples/views-sheets-and-schedules.md)
- [4021. Make a plan for the brickie that shows the walls only, with no doors or windows, for my 9 by 6 m house.](../examples/views-sheets-and-schedules.md)
- [4048. Hide all the 900 x 2100 doors in the Ground plan with a view filter.](../examples/views-sheets-and-schedules.md)
- [4063. Count my doors by level, one row a level, with the count for each.](../examples/views-sheets-and-schedules.md)
- [4070. Make a drawing set for my 8 by 6 m cottage: a plan, a section, an elevation and the door list, all on one sheet.](../examples/views-sheets-and-schedules.md)

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
