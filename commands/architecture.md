# UNION commands: Architecture

17 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## Area (area plan)

A UNION command on the Architecture tab, Room & Area panel. Also known as Area. It asks: "Click inside a boundary to place an area".

### Press it

- Tab: Architecture
- Panel: Room & Area
- Kind: tool
- Ribbon: Architectural > Room & Area
- Draw modes: Line, Rectangle, Circle, Pick Lines

Worked example: press **Area (area plan)** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Area · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Area' on Architecture's Room & Area panel (through its fold): it refused in words: cannot proceed: the Area tool works on an Area Plan: make one with New Area Plan

## Column: Architectural

A UNION command on the Architecture tab, Build panel. It asks: "Click to place a column, or drag a window across grid intersections".

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build

Worked example: press **Column: Architectural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Column: Architectural · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Column: Architectural' on Architecture's Build panel: the tool 'Column: Architectural' stands | keys: Escape (tool Column: Architectural -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

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

- [2070. Build an entrance portico, 6 x 3 m, on a slab with a column at each corner and a flat roof over it.](../examples/architecture.md)

## Curtain Grid

A UNION command on the Architecture tab, Build panel. It asks: "Click a curtain wall to place a Curtain Grid".

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build

Worked example: press **Curtain Grid** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Curtain Grid · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Curtain Grid' on Architecture's Build panel: the tool 'Curtain Grid' stands | keys: Escape (tool Curtain Grid -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Equal Parts | number | 1 |  | all |
| Height | length | 1200 |  | all |
| Justification | choice | Beginning | Beginning, Center, End | all |
| Orientation | choice | Vertical | Vertical, Horizontal | all |
| Spacing | length | 0 |  | all |

Played in these jobs:

- [2034. Glaze the 8 m front of the shop with an exterior glazing curtain wall and divide it with a vertical grid line.](../examples/architecture.md)

## Door

A UNION command on the Architecture tab, Build panel. It asks: "Click a wall to place the door (Space turns the hand)".

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build

Worked example: press **Door** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Door · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Door' on Architecture's Build panel: the tool 'Door' stands | keys: Escape (tool Door -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Flip | yesno | false |  | all |
| Height | length | 2100 |  | all |
| Leader | yesno | false |  | all |
| Sill Height | length | 0 |  | all |
| Tag on Placement | yesno | false |  | all |
| Orientation | choice | Horizontal | Horizontal, Vertical | all |
| Width | length | 900 |  | all |

Played in these jobs:

- [2003. Click out the walls of a 5 x 4 m store room corner to corner, close the loop and hang a door.](../examples/architecture.md)
- [2004. Draw an 8 x 5 m plant room from two corners, then put a double door in the south wall and a window in the north.](../examples/architecture.md)
- [2027. Put an entry door in the middle of the south wall of the 10 x 6 m cottage with a window either side of it.](../examples/architecture.md)
- [2029. Give the 14 x 8 m hall two 1200 exit doors on the south wall and a 1000 door on the east wall.](../examples/architecture.md)
- [2041. Draw a small three-bedroom house, 12 x 9 m in brick veneer, with a slab, internal walls, a front door, windows, a hip roof and its rooms named.](../examples/architecture.md)
- [2042. Fit out an 8 x 12 m shop unit: glazed shopfront, a stock room at the back with a door, a counter and a ceiling.](../examples/architecture.md)
- [2043. Lay out a 9 x 3 m transportable site office with a slab, a door, two windows, a flat roof and its room.](../examples/architecture.md)
- [2044. Draw an 8 x 4 m ablution block with three toilet cubicles each with its own door, a tiled floor and a ceiling.](../examples/architecture.md)
- [2046. Draw a 6 x 6 m double garage with a 4800 wide roller door in the south wall, a personal door in the east wall and a flat roof.](../examples/architecture.md)
- [2047. Draw a 4 x 3 m park kiosk in brick veneer with a serving window 1800 wide at 1000 sill, a side door and a low hip roof.](../examples/architecture.md)
- [2048. Lay out a 16 x 8 m classroom block: two classrooms on the south side, a 2.2 m corridor on the north, a door from each classroom and a big window to each.](../examples/architecture.md)
- [2049. Draw a 7 x 6 m granny flat: living room, bedroom and bathroom, a front door, two windows and a hip roof.](../examples/architecture.md)

### New Block › Door

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Insert > Load from Library > New Block

Worked example: press **Door** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:New Block › Door · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'New Block › Door' on Insert's Load from Library panel (through its parent 'New Block''s arrow, the row 'Door'; the press stood 916 ms (the menu stood at 470 ms; its row ran 434 ms; the window's first paint at 13 ms in QDialog#BlockEditorWindow, dialog 'Block Editor'; it made 0 child widgets native)): the command 'New Block › Door' ran | keys: Escape (no tool, dialog 'Block Editor · New Door' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Floor: Architectural

A UNION command on the Architecture tab, Build panel. It asks: "Sketch the floor boundary, then Finish".

### Floor › Floor: Architectural

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Structural > Structure > Floor
- Draw modes: Line, Rectangle, Inscribed Polygon, Circumscribed Polygon, Circle, Spline, Partial Ellipse, Pick Lines, Pick Walls, Start-End-Radius Arc, Center-ends Arc, Tangent End Arc, Fillet Arc, Ellipse

Worked example: press **Floor: Architectural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Floor › Floor: Architectural · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Floor › Floor: Architectural' on Structure's Structure panel (through its parent 'Floor''s arrow, the row 'Floor: Architectural'; the press stood 821 ms (the menu stood at 400 ms; its row ran 419 ms; it made 0 child widgets native)): the command 'Floor: Architectural' ran; status 'Sketch the floor boundary, then Finish' | keys: Escape (tool Floor -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

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

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build

Worked example: press **Floor: Architectural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Floor: Architectural · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Floor: Architectural' on Architecture's Build panel: the command 'Floor: Architectural' ran; status 'Sketch the floor boundary, then Finish' | keys: Escape (tool Floor -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [2012. Sketch a floor slab over the walls of a 7 x 5 m classroom.](../examples/architecture.md)
- [2063. Draw a 6 x 6 m pavilion and lay its floor by picking the walls.](../examples/architecture.md)

## Model In-Place

A UNION command on the Architecture tab, Build panel.

### Press it

- Tab: Architecture
- Panel: Build
- Kind: action
- Ribbon: Architectural > Build

Worked example: press **Model In-Place** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Model In-Place · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Model In-Place' on Architecture's Build panel (through its parent 'Component''s arrow, the row 'Model In-Place'; the press stood 843 ms (the menu stood at 412 ms; its row ran 419 ms; the window's first paint at 13 ms in QDialog#BlockEditorWindow, dialog 'Block Editor'; it made 0 child widgets native)): the command 'Model In-Place' ran | keys: Escape (no tool, dialog 'Block Editor · In-Place Generic Model 882b' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Mullion

A UNION command on the Architecture tab, Build panel. It asks: "Click a Curtain Grid to place a Mullion on it".

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build

Worked example: press **Mullion** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Mullion · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Mullion' on Architecture's Build panel: the tool 'Mullion' stands | keys: Escape (tool Mullion -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Place On | choice | Grid Line | Grid Line, All Grid Lines | all |

## Railing

A UNION command on the Architecture tab, Circulation panel. It asks: "Click to start the railing path".

### Press it

- Tab: Architecture
- Panel: Circulation
- Kind: tool
- Ribbon: Architectural > Circulation

Worked example: press **Railing** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Railing · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Railing' on Architecture's Circulation panel: the tool 'Railing' stands | keys: Escape (tool Railing -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Height | length | 1000 |  | all |
| Placement | choice | Sketch Path | Sketch Path, Place on Host | all |

## Roof

A UNION command on the Architecture tab, Build panel. Also known as Roof by Footprint. It asks: "Sketch the roof footprint".

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build
- Works in views: plan, three_d
- Draw modes: Line, Rectangle, Inscribed Polygon, Circumscribed Polygon, Circle, Start-End-Radius Arc, Center-ends Arc, Tangent End Arc, Fillet Arc, Spline, Ellipse, Partial Ellipse, Pick Lines, Pick Walls

Worked example: press **Roof** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Roof · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Roof' on Architecture's Build panel: the tool 'Roof' stands | keys: Escape (tool Roof -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Defines Slope | yesno | true |  | Pick Walls |
| Extend to wall core | yesno | false |  | Pick Walls |
| Offset | length | 0 |  | all |
| Overhang | length | 0 |  | Pick Walls |
| Radius | length | 0 |  | all |
| Sides | number | 6 |  | Inscribed Polygon, Circumscribed Polygon |

Played in these jobs:

- [2020. Roof the 8 x 5 m cottage with a gable roof: slope the long sides, leave the gable ends upright, 400 overhang, sitting on the wall tops.](../examples/architecture.md)
- [2021. Give the 6 x 4 m studio a single-pitch roof that falls to the south wall, drawn on an eaves plan.](../examples/architecture.md)
- [2022. Sketch the roof of the 9 x 6 m machinery shed from its outline on an eaves plan and finish it.](../examples/architecture.md)
- [2060. Roof the 12 x 6 m workshop with a gable roof and hang a gutter on each long eave.](../examples/architecture.md)

## Roof Soffit

A UNION command on the Architecture tab, Build panel. Also known as Roof: Soffit. It asks: "Sketch the roof soffit boundary".

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build
- Works in views: plan, three_d
- Draw modes: Line, Rectangle, Inscribed Polygon, Circumscribed Polygon, Circle, Start-End-Radius Arc, Center-ends Arc, Tangent End Arc, Fillet Arc, Spline, Ellipse, Partial Ellipse, Pick Lines, Pick Walls, Pick Roof Edges

Worked example: press **Roof Soffit** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Roof Soffit · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Roof Soffit' on Architecture's Build panel: the tool 'Roof Soffit' stands | keys: Escape (tool Roof Soffit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Height Offset From Level | length | 0 |  | all |
| Offset | length | 0 |  | all |
| Radius | length | 0 |  | all |
| Sides | number | 6 |  | Inscribed Polygon, Circumscribed Polygon |

## Roof: Fascia

A UNION command on the Architecture tab, Build panel. It asks: "Pick a roof edge".

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build
- Works in views: plan, three_d

Worked example: press **Roof: Fascia** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Roof: Fascia · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Roof: Fascia' on Architecture's Build panel: the tool 'Roof: Fascia' stands | keys: Escape (tool Roof: Fascia -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [2023. Roof the 8 x 5 m community room flat with an extensive green roof, 300 overhang, and run a fascia round all four edges.](../examples/architecture.md)
- [2024. Roof the 10 x 6 m house with a 30 degree hip roof and put a fascia and a gutter on its south eave.](../examples/architecture.md)

## Roof: Gutter

A UNION command on the Architecture tab, Build panel. It asks: "Pick a roof edge".

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build
- Works in views: plan, three_d

Worked example: press **Roof: Gutter** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Roof: Gutter · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Roof: Gutter' on Architecture's Build panel: the tool 'Roof: Gutter' stands | keys: Escape (tool Roof: Gutter -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [2024. Roof the 10 x 6 m house with a 30 degree hip roof and put a fascia and a gutter on its south eave.](../examples/architecture.md)
- [2060. Roof the 12 x 6 m workshop with a gable roof and hang a gutter on each long eave.](../examples/architecture.md)

## Room

A UNION command on the Architecture tab, Room & Area panel. It asks: "Click inside walls to place a room".

### Press it

- Tab: Architecture
- Panel: Room & Area
- Kind: tool
- Ribbon: Architectural > Room & Area

Worked example: press **Room** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Room · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Room' on Architecture's Room & Area panel (through its fold): the tool 'Room' stands | keys: Escape (tool Room -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Limit Offset | length | 0 |  | all |
| Upper Limit | length | 2400 |  | all |

## Room Separator

A UNION command on the Architecture tab, Room & Area panel. It asks: "Click to start the room separator".

### Press it

- Tab: Architecture
- Panel: Room & Area
- Kind: tool
- Ribbon: Architectural > Room & Area
- Draw modes: Line

Worked example: press **Room Separator** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Room Separator · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Room Separator' on Architecture's Room & Area panel (through its fold): the tool 'Room Separator' stands | keys: Escape (tool Room Separator -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [2040. Split the 10 x 5 m open-plan office into a work area and a meeting area with a room separator line and name both rooms.](../examples/architecture.md)

## Room Tag

A UNION command on the Architecture tab, Room & Area panel. It asks: "Click a room to tag it".

### Press it

- Tab: Architecture
- Panel: Room & Area
- Kind: tool
- Ribbon: Architectural > Room & Area

Worked example: press **Room Tag** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Room Tag · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Room Tag' on Architecture's Room & Area panel (through its fold): the tool 'Room Tag' stands | keys: Escape (tool Room Tag -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Show Area | yesno | false |  | all |
| Orientation | choice | Horizontal | Horizontal, Vertical | all |

Played in these jobs:

- [2025. Place a room named Office, number 101, inside the 6 x 4 m office and tag it.](../examples/architecture.md)
- [5016. Make the 6 by 4 m office a named room, "Office 101", and tag it.](../examples/annotation-details-and-materials.md)

## Wall: Architectural

A UNION command on the Architecture tab, Build panel. It asks: "Click to start the wall".

### Wall › Wall: Architectural

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Structural > Structure > Wall
- Works in views: plan, three_d
- Draw modes: Line, Rectangle, Inscribed Polygon, Circumscribed Polygon, Start-End-Radius Arc, Ellipse, Partial Ellipse, Pick Lines

Worked example: press **Wall: Architectural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Structure:Wall › Wall: Architectural · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall › Wall: Architectural' on Structure's Structure panel (through its parent 'Wall''s arrow, the row 'Wall: Architectural'; the press stood 822 ms (the menu stood at 349 ms; its row ran 472 ms; it made 0 child widgets native)): the command 'Wall: Architectural' ran; status 'Click to start the wall' | keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

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

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build
- Works in views: plan, three_d

Worked example: press **Wall: Architectural** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Wall: Architectural · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wall: Architectural' on Architecture's Build panel: the command 'Wall: Architectural' ran; status 'Click to start the wall' | keys: Escape (tool Wall -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Window

A UNION command on the Architecture tab, Build panel. It asks: "Click a wall to place the window (Space turns the hand)".

### New Block › Window

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Insert > Load from Library > New Block

Worked example: press **Window** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Insert:New Block › Window · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'New Block › Window' on Insert's Load from Library panel (through its parent 'New Block''s arrow, the row 'Window'; the press stood 768 ms (the menu stood at 358 ms; its row ran 401 ms; the window's first paint at 10 ms in QDialog#BlockEditorWindow, dialog 'Block Editor'; it made 0 child widgets native)): the command 'New Block › Window' ran | keys: Escape (no tool, dialog 'Block Editor · New Window' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Flip | yesno | false |  | all |
| Height | length | 1200 |  | all |
| Leader | yesno | false |  | all |
| Sill Height | length | 900 |  | all |
| Tag on Placement | yesno | false |  | all |
| Orientation | choice | Horizontal | Horizontal, Vertical | all |
| Width | length | 1200 |  | all |

### Press it

- Tab: Architecture
- Panel: Build
- Kind: tool
- Ribbon: Architectural > Build

Worked example: press **Window** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Architecture:Window · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Window' on Architecture's Build panel: the tool 'Window' stands | keys: Escape (tool Window -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [2004. Draw an 8 x 5 m plant room from two corners, then put a double door in the south wall and a window in the north.](../examples/architecture.md)
- [2027. Put an entry door in the middle of the south wall of the 10 x 6 m cottage with a window either side of it.](../examples/architecture.md)
- [2028. Space four 1500 wide windows evenly along the 12 m north wall of the classroom, sills at 900.](../examples/architecture.md)
- [2041. Draw a small three-bedroom house, 12 x 9 m in brick veneer, with a slab, internal walls, a front door, windows, a hip roof and its rooms named.](../examples/architecture.md)
- [2043. Lay out a 9 x 3 m transportable site office with a slab, a door, two windows, a flat roof and its room.](../examples/architecture.md)
- [2047. Draw a 4 x 3 m park kiosk in brick veneer with a serving window 1800 wide at 1000 sill, a side door and a low hip roof.](../examples/architecture.md)
- [2048. Lay out a 16 x 8 m classroom block: two classrooms on the south side, a 2.2 m corridor on the north, a door from each classroom and a big window to each.](../examples/architecture.md)
- [2049. Draw a 7 x 6 m granny flat: living room, bedroom and bathroom, a front door, two windows and a hip roof.](../examples/architecture.md)
- [2071. Draw a semi-detached pair of 6 x 8 m houses sharing a block party wall, each with its own front door, a rear window and a named room.](../examples/architecture.md)

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
