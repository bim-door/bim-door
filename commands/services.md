# UNION commands: Services

60 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## Board

A UNION command on the Services tab, Electrical panel. Also known as Electrical Equipment. It asks: "Click to place the electrical equipment".

### Electrical Equipment

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Board** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Electrical Equipment · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Electrical Equipment' on Systems's Electrical panel (through its fold): the tool 'Electrical Equipment' stands | keys: Escape (tool Electrical Equipment -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Distribution System | text | Single Phase |  | all |
| Leader | yesno | false |  | all |
| Number of Phases | number | 1 |  | all |
| Number of Poles | number | 12 |  | all |
| Offset | length | 0 |  | all |
| Tag on Placement | yesno | true |  | all |
| Voltage | number | 230 |  | all |
| Leader Length | length | 0 |  | all |

Played in these jobs:

- [3073. Put a distribution board on the wall and run three 25 mm conduits from it to the first three outlet positions.](../examples/building-services.md)
- [3074. Draw a 6 x 4 m switchboard room and put a main switchboard against the east wall.](../examples/building-services.md)
- [3079. Put the fire alarm panel at the entry and five detection points down the corridor.](../examples/building-services.md)
- [3081. Wire the distribution board to the outlet 3 m away.](../examples/building-services.md)
- [3082. Run a 600 x 100 cable tray 10 m to the main switchboard at its end.](../examples/building-services.md)
- [4074. Put the switchboard in the plant room on Level 1 with two conduit runs and a conduit schedule.](../examples/views-sheets-and-schedules.md)

## Check Air

A UNION command on the Services tab, Check Systems panel. Also known as Check Duct Systems.

### Check Duct Systems

- Tab: Services
- Panel: Check Systems
- Kind: action
- Ribbon: Building Services > Check Systems

Worked example: press **Check Air** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Check Duct Systems · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Check Duct Systems' on Systems's Check Systems panel (through its fold) (the window's first paint at 22 ms in QDialog#servicesCheckReport:Check Duct Systems): the command 'Check Duct Systems' ran; status 'Check Duct Systems: none found' | keys: Escape (no tool, dialog 'Check Duct Systems' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [3023. Draw a supply duct with two diffusers and run the duct system check.](../examples/building-services.md)

## Check Circuits

A UNION command on the Services tab, Check Systems panel.

### Press it

- Tab: Services
- Panel: Check Systems
- Kind: action
- Ribbon: Building Services > Check Systems

Worked example: press **Check Circuits** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Check Circuits · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Check Circuits' on Systems's Check Systems panel (through its fold) (the window's first paint at 50 ms in QDialog#servicesCheckReport:Check Circuits): the command 'Check Circuits' ran; status 'Check Circuits: none found' | keys: Escape (no tool, dialog 'Check Circuits' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Check Pipework

A UNION command on the Services tab, Check Systems panel. Also known as Check Pipe Systems.

### Check Pipe Systems

- Tab: Services
- Panel: Check Systems
- Kind: action
- Ribbon: Building Services > Check Systems

Worked example: press **Check Pipework** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Check Pipe Systems · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Check Pipe Systems' on Systems's Check Systems panel (through its fold) (the window's first paint at 27 ms in QDialog#servicesCheckReport:Check Pipe Systems): the command 'Check Pipe Systems' ran; status 'Check Pipe Systems: none found' | keys: Escape (no tool, dialog 'Check Pipe Systems' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [3046. Draw a cold water main with two branches and run the pipe system check.](../examples/building-services.md)
- [3062. Run a sprinkler main with a branch and check the pipe systems.](../examples/building-services.md)

## Circuit › Communication

A UNION command on the Services tab, Electrical panel. Also known as Create System › Communication.

### Create System › Communication

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Communication** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Communication · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Communication' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Communication'; the press stood 34 ms (the menu stood at 16 ms; its row ran 6 ms; it made 0 child widgets native)): the command 'Create System › Communication' ran; status 'Select the devices to put on a Communication circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Circuit › Control

A UNION command on the Services tab, Electrical panel. Also known as Create System › Control.

### Create System › Control

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Control** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Control · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Control' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Control'; the press stood 49 ms (the menu stood at 25 ms; its row ran 12 ms; it made 0 child widgets native)): the command 'Create System › Control' ran; status 'Select the devices to put on a Control circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Circuit › Data

A UNION command on the Services tab, Electrical panel. Also known as Create System › Data.

### Create System › Data

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Data** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Data · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Data' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Data'; the press stood 348 ms (the menu stood at 19 ms; its row ran 328 ms; it made 0 child widgets native)): the command 'Create System › Data' ran; status 'Select the devices to put on a Data circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Circuit › Fire Alarm

A UNION command on the Services tab, Electrical panel. Also known as Create System › Fire Alarm.

### Create System › Fire Alarm

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Fire Alarm** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Fire Alarm · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Fire Alarm' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Fire Alarm'; the press stood 45 ms (the menu stood at 21 ms; its row ran 7 ms; it made 0 child widgets native)): the command 'Create System › Fire Alarm' ran; status 'Select the devices to put on a Fire Alarm circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Circuit › Nurse Call

A UNION command on the Services tab, Electrical panel. Also known as Create System › Nurse Call.

### Create System › Nurse Call

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Nurse Call** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Nurse Call · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Nurse Call' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Nurse Call'; the press stood 52 ms (the menu stood at 23 ms; its row ran 9 ms; it made 0 child widgets native)): the command 'Create System › Nurse Call' ran; status 'Select the devices to put on a Nurse Call circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Circuit › Power

A UNION command on the Services tab, Electrical panel. Also known as Create System › Power.

### Create System › Power

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Power** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Power · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Power' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Power'; the press stood 315 ms (the menu stood at 13 ms; its row ran 301 ms; it made 0 child widgets native)): the command 'Create System › Power' ran; status 'Select the devices to put on a Power circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Circuit › Security

A UNION command on the Services tab, Electrical panel. Also known as Create System › Security.

### Create System › Security

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Security** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Security · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Security' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Security'; the press stood 27 ms (the menu stood at 12 ms; its row ran 4 ms; it made 0 child widgets native)): the command 'Create System › Security' ran; status 'Select the devices to put on a Security circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Circuit › Switch

A UNION command on the Services tab, Electrical panel. Also known as Create System › Switch.

### Create System › Switch

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Switch** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Switch · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Switch' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Switch'; the press stood 328 ms (the menu stood at 16 ms; its row ran 311 ms; it made 0 child widgets native)): the command 'Create System › Switch' ran; status 'Select the devices to put on a Switch circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Circuit › Telephone

A UNION command on the Services tab, Electrical panel. Also known as Create System › Telephone.

### Create System › Telephone

- Tab: Services
- Panel: Electrical
- Kind: action
- Ribbon: Building Services > Electrical > Create System

Worked example: press **Circuit › Telephone** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Create System › Telephone · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Create System › Telephone' on Systems's Electrical panel (through its fold) (through its parent 'Create System''s arrow, the row 'Telephone'; the press stood 337 ms (the menu stood at 17 ms; its row ran 319 ms; it made 0 child widgets native)): the command 'Create System › Telephone' ran; status 'Select the devices to put on a Telephone circuit, then press Create System' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Comms Point

A UNION command on the Services tab, Devices panel. Also known as Communication Device. It asks: "Click a face to place the comms point".

### Press it

- Tab: Services
- Panel: Devices
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Comms Point** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Comms Point · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Comms Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Comms Point'; the press stood 1384 ms (the menu stood at 16 ms; its row ran 1328 ms; it made 0 child widgets native)): the tool 'Comms Point' stands | keys: Escape (tool Comms Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |

## Conduit

A UNION command on the Services tab, Electrical panel. It asks: "Click to start the conduit".

### Press it

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical
- Draw modes: Line

Worked example: press **Conduit** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Conduit · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Conduit' on Systems's Electrical panel (through its fold): the tool 'Conduit' stands | keys: Escape (tool Conduit -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Bend Radius | number | 1.5 |  | all |
| Diameter | length | 20 |  | all |
| Lock | yesno | false |  | all |
| Offset | length | 300 |  | all |

Played in these jobs:

- [3073. Put a distribution board on the wall and run three 25 mm conduits from it to the first three outlet positions.](../examples/building-services.md)
- [3080. Run 20, 25 and 32 mm conduits 8 m long side by side, 200 mm apart.](../examples/building-services.md)
- [3086. Run two conduits 500 mm apart and delete the lower one.](../examples/building-services.md)
- [4043. Put three power outlets and a conduit run on Level 1 and make an electrical sheet for the plan.](../examples/views-sheets-and-schedules.md)
- [4074. Put the switchboard in the plant room on Level 1 with two conduit runs and a conduit schedule.](../examples/views-sheets-and-schedules.md)

## Conduit Bank

A UNION command on the Services tab, Electrical panel. Also known as Parallel Conduits. It asks: "Click a conduit to start the conduit bank".

### Parallel Conduits

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical
- Draw modes: Line

Worked example: press **Conduit Bank** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Parallel Conduits · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Parallel Conduits' on Systems's Electrical panel (through its fold): the tool 'Parallel Conduits' stands | keys: Escape (tool Parallel Conduits -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Horizontal Number | number | 1 |  | all |
| Horizontal Offset | length | 0 |  | all |
| Vertical Number | number | 0 |  | all |
| Vertical Offset | length | 0 |  | all |

## Conduit Fitting

A UNION command on the Services tab, Electrical panel. It asks: "Select the segments, then click to place the conduit fitting".

### Press it

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Conduit Fitting** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Conduit Fitting · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Conduit Fitting' on Systems's Electrical panel (through its fold): the tool 'Conduit Fitting' stands | keys: Escape (tool Conduit Fitting -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Data Point

A UNION command on the Services tab, Devices panel. Also known as Data Device. It asks: "Click a face to place the data point".

### Press it

- Tab: Services
- Panel: Devices
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Data Point** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Data Point · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Data Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Data Point'; the press stood 278 ms (the menu stood at 24 ms; its row ran 229 ms; it made 0 child widgets native)): the tool 'Data Point' stands | keys: Escape (tool Data Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |

Played in these jobs:

- [3078. Put three light switches and three data points along the corridor wall.](../examples/building-services.md)

## Device

A UNION command on the Services tab, Electrical panel. It asks: "Click a face to place the device".

### Press it

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Device** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Device · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Device' on Systems's Electrical panel (through its fold): the tool 'Device' stands | keys: Escape (tool Device -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |
| Tag on Placement | yesno | true |  | all |

## Diffuser

A UNION command on the Services tab, Air panel. Also known as Air Terminal. It asks: "Click a face to place the air terminal".

### Air Terminal

- Tab: Services
- Panel: Air
- Kind: tool
- Ribbon: Building Services > HVAC

Worked example: press **Diffuser** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Air Terminal · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Air Terminal' on Systems's HVAC panel: the command 'Air Terminal' ran; status 'Click a face to place the air terminal' | keys: Escape (tool Diffuser -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Orientation | choice | Horizontal | Horizontal, Vertical | all |
| Leader | yesno | false |  | all |
| Offset | length | 0 |  | all |
| Rotate after placement | yesno | false |  | all |
| Tags | yesno | false |  | all |
| Leader Length | length | 6 |  | all |

Played in these jobs:

- [3024. Use the Duct tool to draw a 500 x 250 supply duct at 2700 mm and a diffuser on it.](../examples/building-services.md)
- [3025. Draw a supply duct and a return duct with the Duct tool, 2 m apart, each with a diffuser.](../examples/building-services.md)
- [4040. Run a supply duct with a diffuser along the corridor on Level 1 and put the plan on a sheet.](../examples/views-sheets-and-schedules.md)
- [5053. Run a supply duct with one air terminal on it and tag the duct.](../examples/annotation-details-and-materials.md)

## Duct

A UNION command on the Services tab, Air panel. It asks: "Click to start the duct".

### Press it

- Tab: Services
- Panel: Air
- Kind: tool
- Ribbon: Building Services > HVAC
- Draw modes: Line

Worked example: press **Duct** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Duct · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duct' on Systems's HVAC panel: the tool 'Duct' stands | keys: Escape (tool Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Apply | button |  |  | all |
| Diameter | length | 300 |  | all |
| End Offset | length | 2400 |  | all |
| Height | length | 200 |  | all |
| Storey | level | Level 1 |  | all |
| Lock | yesno | false |  | all |
| Middle Elevation | length | 2400 |  | all |
| Start Offset | length | 2400 |  | all |
| System Type | choice | Supply Air | Supply Air, Return Air, Exhaust Air | all |
| Width | length | 400 |  | all |

Played in these jobs:

- [3024. Use the Duct tool to draw a 500 x 250 supply duct at 2700 mm and a diffuser on it.](../examples/building-services.md)
- [3025. Draw a supply duct and a return duct with the Duct tool, 2 m apart, each with a diffuser.](../examples/building-services.md)
- [4040. Run a supply duct with a diffuser along the corridor on Level 1 and put the plan on a sheet.](../examples/views-sheets-and-schedules.md)
- [4055. Schedule the ducts on Level 1 by system type and put the list on its own sheet.](../examples/views-sheets-and-schedules.md)
- [5053. Run a supply duct with one air terminal on it and tag the duct.](../examples/annotation-details-and-materials.md)

## Duct Accessory

A UNION command on the Services tab, Air panel. It asks: "Click a duct to place the accessory".

### Press it

- Tab: Services
- Panel: Air
- Kind: tool
- Ribbon: Building Services > HVAC

Worked example: press **Duct Accessory** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Duct Accessory · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duct Accessory' on Systems's HVAC panel: the tool 'Duct Accessory' stands | keys: Escape (tool Duct Accessory -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Rotate after placement | yesno | false |  | all |

Played in these jobs:

- [3017. Draw a 5 m branch duct 400 x 250 and place a duct accessory in it at 2 m.](../examples/building-services.md)

## Duct Fitting

A UNION command on the Services tab, Air panel. It asks: "Click a duct to cap the open end".

### Press it

- Tab: Services
- Panel: Air
- Kind: tool
- Ribbon: Building Services > HVAC

Worked example: press **Duct Fitting** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Duct Fitting · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duct Fitting' on Systems's HVAC panel: the tool 'Duct Fitting' stands | keys: Escape (tool Duct Fitting -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Rotate after placement | yesno | false |  | all |

## Duct Legend

A UNION command on the Services tab, Check Systems panel. It asks: "Click to place the duct legend".

### Press it

- Tab: Services
- Panel: Check Systems
- Kind: tool
- Ribbon: Building Services > Check Systems

Worked example: press **Duct Legend** with the view **Ground Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Duct Legend · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duct Legend' on Systems's Check Systems panel (through its fold): the tool 'Duct Legend' stands | keys: Escape (tool Duct Legend -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [3022. Show the supply and the return duct on the plan and drop a duct legend beside them.](../examples/building-services.md)

## Fire Alarm Point

A UNION command on the Services tab, Devices panel. Also known as Fire Alarm Device. It asks: "Click a face to place the fire alarm point".

### Press it

- Tab: Services
- Panel: Devices
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Fire Alarm Point** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Fire Alarm Point · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Fire Alarm Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Fire Alarm Point'; the press stood 50 ms (the menu stood at 19 ms; its row ran 11 ms; it made 0 child widgets native)): the tool 'Fire Alarm Point' stands | keys: Escape (tool Fire Alarm Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |
| Tag on Placement | yesno | false |  | all |

Played in these jobs:

- [3079. Put the fire alarm panel at the entry and five detection points down the corridor.](../examples/building-services.md)
- [3083. Put four emergency luminaires in the corridor and two fire alarm call points at the exits.](../examples/building-services.md)

## Fire Pump

A UNION command on the Services tab, Pipework panel. It asks: "Click to place the fire pump".

### Press it

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Fire Pump** with the view **Ground Copy 1 Copy 1 (dependent) Copy 1** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Fire Pump · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Fire Pump' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Fire Pump'; the press stood 73 ms (the menu stood at 33 ms; its row ran 16 ms; it made 0 child widgets native)): the tool 'Fire Pump' stands | keys: Escape (tool Fire Pump -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Tag on Placement | yesno | false |  | all |

Played in these jobs:

- [3057. Put the fire pump in the pump room and connect a 150 mm suction pipe on one side and a 100 mm discharge pipe on the other.](../examples/building-services.md)

## Flex Duct

A UNION command on the Services tab, Air panel. It asks: "Click to start the flex duct".

### Press it

- Tab: Services
- Panel: Air
- Kind: tool
- Ribbon: Building Services > HVAC
- Draw modes: Line

Worked example: press **Flex Duct** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Flex Duct · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Flex Duct' on Systems's HVAC panel: the tool 'Flex Duct' stands | keys: Escape (tool Flex Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Diameter | length | 300 |  | all |
| Storey | level | Level 1 |  | all |
| Offset | length | 2400 |  | all |

Played in these jobs:

- [3018. Run a 6 m supply duct and connect a flexible duct from its end to a diffuser 1.5 m away.](../examples/building-services.md)

## Flex Pipe

A UNION command on the Services tab, Pipework panel. It asks: "Click point 1, or Finish".

### Press it

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping
- Draw modes: Line

Worked example: press **Flex Pipe** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Flex Pipe · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Flex Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Flex Pipe' stands | keys: Escape (tool Flex Pipe -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Diameter | length | 100 |  | all |
| End Offset | length | 0 |  | all |
| Storey | level | Level 1 |  | all |
| Offset | length | 0 |  | all |
| Start Offset | length | 0 |  | all |

Played in these jobs:

- [3067. Run a 32 mm cold water pipe 5 m along the wall and connect a flexible pipe from its end to a basin 800 mm away.](../examples/building-services.md)

## Hose Reel

A UNION command on the Services tab, Pipework panel. It asks: "Click a face to place the hose reel".

### Press it

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Hose Reel** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Hose Reel · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Hose Reel' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Hose Reel'; the press stood 39 ms (the menu stood at 15 ms; its row ran 6 ms; it made 0 child widgets native)): the tool 'Hose Reel' stands | keys: Escape (tool Hose Reel -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |
| Tag on Placement | yesno | false |  | all |

Played in these jobs:

- [3056. Run a 50 mm fire supply pipe down a 20 m corridor and put three hose reels on it.](../examples/building-services.md)
- [3063. Run a 150 mm fire main 16 m along the loading dock, put two hydrants on it and two hose reels on the wall behind.](../examples/building-services.md)

## Hydrant

A UNION command on the Services tab, Pipework panel. It asks: "Click a face to place the hydrant".

### Press it

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Hydrant** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Hydrant · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Hydrant' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Hydrant'; the press stood 415 ms (the menu stood at 25 ms; its row ran 389 ms; it made 0 child widgets native)): the tool 'Hydrant' stands | keys: Escape (tool Hydrant -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |
| Tag on Placement | yesno | false |  | all |

Played in these jobs:

- [3055. Lay a 150 mm hydrant ring main around the building, 30 x 20 m, with a hydrant at each corner.](../examples/building-services.md)
- [3063. Run a 150 mm fire main 16 m along the loading dock, put two hydrants on it and two hose reels on the wall behind.](../examples/building-services.md)

## Luminaire

A UNION command on the Services tab, Electrical panel. Also known as Lighting Fixture. It asks: "Click a face to place the lighting fixture".

### Lighting Fixture

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Luminaire** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Lighting Fixture · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Lighting Fixture' on Systems's Electrical panel (through its fold): the tool 'Lighting Fixture' stands | keys: Escape (tool Lighting Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |
| Tag on Placement | yesno | true |  | all |

Played in these jobs:

- [3075. Lay out six luminaires on a 3 m grid in a 9 x 6 m office, three across and two down.](../examples/building-services.md)
- [3076. Put a luminaire every 3 m down a 24 m corridor.](../examples/building-services.md)
- [3083. Put four emergency luminaires in the corridor and two fire alarm call points at the exits.](../examples/building-services.md)
- [3085. Put four luminaires in a room and schedule them by type with a count.](../examples/building-services.md)
- [3088. Run a 300 mm cable tray down a 20 m corridor, hang six luminaires under it and put two light switches at the ends.](../examples/building-services.md)
- [3094. Draw a 9 x 6 m office with a ceiling at 2700 mm and put six luminaires in it on a 3 m grid.](../examples/building-services.md)
- [3098. Draw an 8 x 6 m office with a ceiling at 2800 mm and put four luminaires and four sprinklers in it, alternating on a 2 m by 3 m grid.](../examples/building-services.md)
- [4072. Lay out four light fittings and a cable tray on Level 1 and list the fittings.](../examples/views-sheets-and-schedules.md)

## Make Flexible

A UNION command on the Services tab, HVAC panel. Also known as Convert to Flex Duct.

### Convert to Flex Duct

- Tab: Services
- Panel: HVAC
- Kind: action
- Ribbon: Building Services > HVAC

Worked example: press **Make Flexible** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Convert to Flex Duct · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Convert to Flex Duct' on Systems's HVAC panel (through its parent 'Flex Duct''s arrow, the row 'Convert to Flex Duct'; the press stood 996 ms (the menu stood at 374 ms; its row ran 622 ms; it made 0 child widgets native)): the tool 'Convert to Flex Duct' stands | keys: Escape (tool Convert to Flex Duct -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Length | length | 1500 |  | all |

## Make Full Size

A UNION command on the Services tab, HVAC panel. Also known as Convert Placeholder.

### Convert Placeholder

- Tab: Services
- Panel: HVAC
- Kind: action
- Ribbon: Building Services > HVAC

Worked example: press **Make Full Size** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Convert Placeholder · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Convert Placeholder' on Systems's HVAC panel: the command 'Convert Placeholder' ran; status 'Select a single-line duct or pipe to make full size' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Nurse Call Point

A UNION command on the Services tab, Devices panel. Also known as Nurse Call Device. It asks: "Click a face to place the nurse call point".

### Press it

- Tab: Services
- Panel: Devices
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Nurse Call Point** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Nurse Call Point · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Nurse Call Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Nurse Call Point'; the press stood 55 ms (the menu stood at 29 ms; its row ran 11 ms; it made 0 child widgets native)): the tool 'Nurse Call Point' stands | keys: Escape (tool Nurse Call Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |

## Open Ends

A UNION command on the Services tab, Check Systems panel. Also known as Show Disconnects.

### Show Disconnects

- Tab: Services
- Panel: Check Systems
- Kind: action
- Ribbon: Building Services > Check Systems

Worked example: press **Open Ends** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Show Disconnects · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Show Disconnects' on Systems's Check Systems panel (through its fold) (the window's first paint at 16 ms in QDialog#servicesCheckReport:Show Disconnects): the command 'Show Disconnects' ran; status 'Show Disconnects: none found' | keys: Escape (no tool, dialog 'Show Disconnects' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Outlet

A UNION command on the Services tab, Devices panel. Also known as Electrical Fixture. It asks: "Click a face to place the outlet".

### Press it

- Tab: Services
- Panel: Devices
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Outlet** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Outlet · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Outlet' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Outlet'; the press stood 356 ms (the menu stood at 26 ms; its row ran 329 ms; it made 0 child widgets native)): the tool 'Outlet' stands | keys: Escape (tool Outlet -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |

Played in these jobs:

- [3073. Put a distribution board on the wall and run three 25 mm conduits from it to the first three outlet positions.](../examples/building-services.md)
- [3077. Draw an 8 m wall and put six power outlets along it at 300 mm from the floor line.](../examples/building-services.md)
- [3081. Wire the distribution board to the outlet 3 m away.](../examples/building-services.md)
- [4043. Put three power outlets and a conduit run on Level 1 and make an electrical sheet for the plan.](../examples/views-sheets-and-schedules.md)

## Phone Point

A UNION command on the Services tab, Devices panel. Also known as Telephone Device. It asks: "Click a face to place the phone point".

### Press it

- Tab: Services
- Panel: Devices
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Phone Point** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Phone Point · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Phone Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Phone Point'; the press stood 41 ms (the menu stood at 17 ms; its row ran 9 ms; it made 0 child widgets native)): the tool 'Phone Point' stands | keys: Escape (tool Phone Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |

## Pipe

A UNION command on the Services tab, Pipework panel. It asks: "Click to start the pipe".

### Press it

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping
- Draw modes: Line

Worked example: press **Pipe** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Pipe · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Pipe' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe' stands | keys: Escape (tool Pipe -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Apply | button |  |  | all |
| Chain | yesno | true |  | all |
| Diameter | length | 100 |  | all |
| End Offset | length | 0 |  | all |
| Storey | level | Level 1 |  | all |
| Lock | yesno | false |  | all |
| Middle Elevation | length | 0 |  | all |
| Slope | number | 0 |  | all |
| Start Offset | length | 0 |  | all |
| System Classification | choice | Domestic Cold Water | Domestic Hot Water, Domestic Cold Water, Sanitary, Hydronic Supply, Hydronic Return, Fire Protection Wet, Fire Protection Dry, Fire Protection Pre-Action, Fire Protection Other, Vent, Other | all |
| System Type | choice | Domestic Cold Water | Domestic Hot Water, Domestic Cold Water, Sanitary, Hydronic Supply, Hydronic Return, Fire Protection Wet, Fire Protection Dry, Fire Protection Pre-Action, Fire Protection Other, Vent, Other | all |

Played in these jobs:

- [3032. Draw a hydronic heating flow pipe and return pipe around a 6 x 4 m room with the Pipe tool, 50 mm, each turning one corner.](../examples/building-services.md)
- [3033. Run a 100 mm sanitary drain 8 m long at 1 per cent fall and put three fixtures along it.](../examples/building-services.md)
- [3038. Take a 100 mm cold water pipe up 3 m from the floor in a riser, then carry it 5 m east along the ceiling void.](../examples/building-services.md)
- [3040. Run a 150 mm stormwater pipe 12 m long at a 1.5 per cent fall.](../examples/building-services.md)
- [3044. Draw a 100 mm hot water riser up to 3000 mm, take it back, then bring it back again.](../examples/building-services.md)
- [3049. Draw 100, 65 and 40 mm cold water pipes 1 m apart with the Pipe tool.](../examples/building-services.md)
- [3064. Draw a 100 mm sprinkler main with the Pipe tool and a 40 mm branch off it, then add two sprinklers on the branch.](../examples/building-services.md)
- [4041. Run a 50 mm cold water pipe along the north wall on Level 1, schedule the pipes and put the plan on a sheet.](../examples/views-sheets-and-schedules.md)
- [4042. Lay out four sprinkler heads on a branch pipe on Level 1 and list the heads.](../examples/views-sheets-and-schedules.md)
- [4073. Place three fixtures on a 50 mm supply pipe on Level 1 and list the fixtures.](../examples/views-sheets-and-schedules.md)
- [4076. Run a sprinkler branch on Level 1, make a sheet for it and put the Level 1 plan on it at 1:100.](../examples/views-sheets-and-schedules.md)

## Pipe Bank

A UNION command on the Services tab, Plumbing & Piping panel. Also known as Parallel Pipes. It asks: "Click to start the pipe bank".

### Parallel Pipes

- Tab: Services
- Panel: Plumbing & Piping
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping
- Draw modes: Line

Worked example: press **Pipe Bank** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Parallel Pipes · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Parallel Pipes' on Systems's Plumbing & Piping panel (through its fold): the tool 'Parallel Pipes' stands | keys: Escape (tool Parallel Pipes -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Horizontal Number | number | 1 |  | all |
| Horizontal Offset | length | 0 |  | all |
| Vertical Number | number | 0 |  | all |
| Vertical Offset | length | 0 |  | all |

## Pipe Fitting

A UNION command on the Services tab, Pipework panel. It asks: "Click a pipe to place the fitting".

### Press it

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Pipe Fitting** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Pipe Fitting · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Pipe Fitting' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe Fitting' stands | keys: Escape (tool Pipe Fitting -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [3037. Draw a 65 mm pipe 6 m long, put a valve in it at 1.5 m and a pipe fitting at 4.5 m.](../examples/building-services.md)

## Pipe Legend

A UNION command on the Services tab, Check Systems panel. It asks: "Click to place the pipe legend".

### Press it

- Tab: Services
- Panel: Check Systems
- Kind: tool
- Ribbon: Building Services > Check Systems

Worked example: press **Pipe Legend** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Pipe Legend · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Pipe Legend' on Systems's Check Systems panel (through its fold): the tool 'Pipe Legend' stands | keys: Escape (tool Pipe Legend -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [3041. Draw the cold water and the hot water pipes and put a pipe legend beside them.](../examples/building-services.md)

## Plant Item

A UNION command on the Services tab, Plant panel. Also known as Mechanical Equipment. It asks: "Click to place the mechanical equipment".

### Mechanical Equipment

- Tab: Services
- Panel: Plant
- Kind: tool
- Ribbon: Building Services > Mechanical

Worked example: press **Plant Item** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Mechanical Equipment · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Mechanical Equipment' on Systems's Mechanical panel: the command 'Mechanical Equipment' ran; status 'Click to place the Mechanical Equipment' | keys: Escape (tool Plant Item -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Orientation | choice | Horizontal | Horizontal, Vertical | all |
| Leader | yesno | false |  | all |
| Tags | yesno | false |  | all |
| Leader Length | length | 6 |  | all |

## Plumbing Plant

A UNION command on the Services tab, Pipework panel. Also known as Plumbing Equipment. It asks: "Click to place the plumbing equipment".

### Plumbing Equipment

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Plumbing Plant** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Plumbing Equipment · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Plumbing Equipment' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Equipment' stands | keys: Escape (tool Plumbing Equipment -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Tag on Placement | yesno | false |  | all |

## Sanitaryware

A UNION command on the Services tab, Pipework panel. Also known as Plumbing Fixture. It asks: "Click a face to place the fixture".

### Plumbing Fixture

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Sanitaryware** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Plumbing Fixture · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Plumbing Fixture' on Systems's Plumbing & Piping panel (through its fold): the tool 'Plumbing Fixture' stands | keys: Escape (tool Plumbing Fixture -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Leader | yesno | false |  | all |
| Tag on Placement | yesno | false |  | all |
| Leader Length | length | 0 |  | all |

Played in these jobs:

- [3033. Run a 100 mm sanitary drain 8 m long at 1 per cent fall and put three fixtures along it.](../examples/building-services.md)
- [3036. Run a 32 mm cold water pipe 7 m along the wall and put four basins on the other side of it.](../examples/building-services.md)
- [3043. Place three plumbing fixtures and schedule them by type with a count.](../examples/building-services.md)
- [3048. Put a row of three basins along the north wall and a row of three along the south wall of a 6 m washroom.](../examples/building-services.md)
- [3067. Run a 32 mm cold water pipe 5 m along the wall and connect a flexible pipe from its end to a basin 800 mm away.](../examples/building-services.md)
- [3095. Draw a 6 x 4 m toilet block, put four fixtures along the north wall and run a 100 mm sanitary pipe behind them.](../examples/building-services.md)
- [4073. Place three fixtures on a 50 mm supply pipe on Level 1 and list the fixtures.](../examples/views-sheets-and-schedules.md)

## Security Point

A UNION command on the Services tab, Devices panel. Also known as Security Device. It asks: "Click a face to place the security point".

### Press it

- Tab: Services
- Panel: Devices
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Security Point** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Security Point · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Security Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Security Point'; the press stood 367 ms (the menu stood at 27 ms; its row ran 299 ms; it made 0 child widgets native)): the tool 'Security Point' stands | keys: Escape (tool Security Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |

## Set Plane

A UNION command on the Services tab, Work Plane panel. Also known as Set.

### Set

- Tab: Services
- Panel: Work Plane
- Kind: tool
- Ribbon: Setout > Work Plane

Worked example: press **Set Plane** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Setout:Set · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Set' on Setout's Work Plane panel (the window's first paint at 88 ms in union_shell::ShellDialogWindow, dialog 'Work Plane'): the dialog 'Work Plane' opened and stood; closed by the player | inside the modal 'Work Plane' | keys: Escape (no tool, dialog 'Work Plane' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Name | choice | Level 1 | Level 1, Level 2, Level 3 | all |

## Show Plane

A UNION command on the Services tab, Work Plane panel. Also known as Show.

### Show

- Tab: Services
- Panel: Work Plane
- Kind: tool
- Ribbon: Setout > Work Plane

Worked example: press **Show Plane** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Setout:Show · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Show' on Setout's Work Plane panel: the command 'Show' ran; status 'Work plane shown' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Single-Line Duct

A UNION command on the Services tab, HVAC panel. Also known as Duct Placeholder. It asks: "Click to start the single-line duct".

### Duct Placeholder

- Tab: Services
- Panel: HVAC
- Kind: tool
- Ribbon: Building Services > HVAC
- Draw modes: Line

Worked example: press **Single-Line Duct** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Duct Placeholder · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Duct Placeholder' on Systems's HVAC panel: the tool 'Duct Placeholder' stands | keys: Escape (tool Duct Placeholder -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Played in these jobs:

- [3069. Rough in a supply duct run as a single-line placeholder duct 12 m long before it is sized.](../examples/building-services.md)

## Single-Line Pipe

A UNION command on the Services tab, Plumbing & Piping panel. Also known as Pipe Placeholder. It asks: "Click to start the single-line pipe".

### Pipe Placeholder

- Tab: Services
- Panel: Plumbing & Piping
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping
- Draw modes: Line

Worked example: press **Single-Line Pipe** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Pipe Placeholder · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Pipe Placeholder' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe Placeholder' stands | keys: Escape (tool Pipe Placeholder -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Space

A UNION command on the Services tab, Air panel. It asks: "Click inside an enclosed region to place the space".

### Press it

- Tab: Services
- Panel: Air
- Kind: tool
- Ribbon: Building Services > Spaces & Zones
- Draw modes: Line, Rectangle, Pick Lines

Worked example: press **Space** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Space · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Space' on Systems's Spaces & Zones panel (through its fold): the tool 'Space' stands | keys: Escape (tool Space -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Condition Type | choice | Heated | Heated, Cooled, Heated and cooled, Unconditioned, Vented, Naturally vented | all |
| Lighting Load | number | 0 |  | all |
| Limit Offset | length | 0 |  | all |
| People | number | 0 |  | all |
| Power Load | number | 0 |  | all |
| Upper Limit | length | 2400 |  | all |

Played in these jobs:

- [3029. Draw a 5 x 4 m server room and place a cooled space in it with four people and a 4000 power load.](../examples/building-services.md)
- [3068. Draw a 6 x 4 m office, place a space in it and put a thermostat on the wall beside the door position.](../examples/building-services.md)
- [3089. Draw a 6 x 5 m meeting room and place a space in it that is heated and cooled for twelve people.](../examples/building-services.md)
- [3090. Draw an 8 x 6 m office, run a supply duct through it with two diffusers and place a space.](../examples/building-services.md)

## Space Naming

A UNION command on the Services tab, Check Systems panel. It asks: "Select the spaces, then click to number them".

### Press it

- Tab: Services
- Panel: Check Systems
- Kind: tool
- Ribbon: Building Services > Spaces & Zones

Worked example: press **Space Naming** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Space Naming · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'Space Naming' on Systems's Spaces & Zones panel (through its fold): it refused in words: cannot proceed: Space Naming needs at least one real Space already selected

## Space Separator

A UNION command on the Services tab, Air panel. It asks: "Click to start the space separator".

### Press it

- Tab: Services
- Panel: Air
- Kind: tool
- Ribbon: Building Services > Spaces & Zones
- Draw modes: Line

Worked example: press **Space Separator** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Space Separator · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Space Separator' on Systems's Spaces & Zones panel (through its fold): the tool 'Space Separator' stands | keys: Escape (tool Space Separator -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Sprinkler

A UNION command on the Services tab, Pipework panel. It asks: "Click a face to place the sprinkler".

### Press it

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Sprinkler** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Sprinkler · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Sprinkler' on Systems's Plumbing & Piping panel (through its fold): the tool 'Sprinkler' stands | keys: Escape (tool Sprinkler -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Leader | yesno | false |  | all |
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |
| Tag on Placement | yesno | false |  | all |
| Leader Length | length | 0 |  | all |

Played in these jobs:

- [3050. Run a 100 mm wet sprinkler main 9 m long with three 40 mm branches at 1.5, 4.5 and 7.5 m, and put four sprinklers on each branch.](../examples/building-services.md)
- [3051. Lay out sprinklers for a 12 x 9 m office at 3 m spacing, three branch lines off a riser main on the west wall.](../examples/building-services.md)
- [3052. Put sprinklers every 3 m down a 24 m corridor on a 65 mm pipe at 3000 mm.](../examples/building-services.md)
- [3053. Run a 100 mm wet main for the offices and a 100 mm dry main for the car park, 5 m apart, and give each three sprinklers.](../examples/building-services.md)
- [3054. Run a pre-action sprinkler pipe through a 6 x 4 m server room and put four sprinklers on it.](../examples/building-services.md)
- [3058. Put three pendant sprinklers at 2800 mm below the ceiling and three upright sprinklers at 3300 mm in the ceiling void on the same pipe.](../examples/building-services.md)
- [3059. Put six sprinklers on a branch line and schedule them by type with a count.](../examples/building-services.md)
- [3060. Put three sprinklers on a pipe, then take the last one back out with Undo.](../examples/building-services.md)
- [3061. Run a 100 mm wet main on each floor, 10 m long, and put two sprinklers on the Level 1 main.](../examples/building-services.md)
- [3064. Draw a 100 mm sprinkler main with the Pipe tool and a 40 mm branch off it, then add two sprinklers on the branch.](../examples/building-services.md)
- [3093. Draw a 9 x 6 m office with a ceiling at 3000 mm and put six sprinklers in it on a 3 m grid with a branch line above.](../examples/building-services.md)
- [3098. Draw an 8 x 6 m office with a ceiling at 2800 mm and put four luminaires and four sprinklers in it, alternating on a 2 m by 3 m grid.](../examples/building-services.md)

## Switch Point

A UNION command on the Services tab, Devices panel. Also known as Lighting Device. It asks: "Click a face to place the switch point".

### Press it

- Tab: Services
- Panel: Devices
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Switch Point** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Switch Point · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Switch Point' on Systems's Electrical panel (through its fold) (through its parent 'Device''s arrow, the row 'Switch Point'; the press stood 151 ms (the menu stood at 23 ms; its row ran 97 ms; it made 0 child widgets native)): the tool 'Switch Point' stands | keys: Escape (tool Switch Point -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Placement Plane | choice | Level | Level, Face, Work Plane | all |

Played in these jobs:

- [3078. Put three light switches and three data points along the corridor wall.](../examples/building-services.md)
- [3088. Run a 300 mm cable tray down a 20 m corridor, hang six luminaires under it and put two light switches at the ends.](../examples/building-services.md)

## Tank

A UNION command on the Services tab, Pipework panel. It asks: "Click to place the tank".

### Press it

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Tank** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Tank · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Tank' on Systems's Plumbing & Piping panel (through its fold) (through its parent 'Plumbing Equipment''s arrow, the row 'Tank'; the press stood 99 ms (the menu stood at 36 ms; its row ran 62 ms; it made 0 child widgets native)): the tool 'Tank' stands | keys: Escape (tool Tank -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Offset | length | 0 |  | all |
| Tag on Placement | yesno | false |  | all |

Played in these jobs:

- [3035. Place a water tank, run a 50 mm outlet pipe 6 m from it and put an isolating valve in the pipe.](../examples/building-services.md)
- [3047. Place a hot water tank and run a 40 mm hot water flow and return pair 8 m out from it, with a valve in the flow pipe.](../examples/building-services.md)

## Tray

A UNION command on the Services tab, Electrical panel. Also known as Cable Tray. It asks: "Click to start the cable tray".

### Cable Tray

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical
- Draw modes: Line

Worked example: press **Tray** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Cable Tray · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Cable Tray' on Systems's Electrical panel (through its fold): the tool 'Cable Tray' stands | keys: Escape (tool Cable Tray -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Bend Radius | number | 1.5 |  | all |
| Height | length | 100 |  | all |
| Lock | yesno | false |  | all |
| Offset | length | 3000 |  | all |
| Width | length | 300 |  | all |

Played in these jobs:

- [3070. Run a 300 x 100 cable tray 15 m down the corridor at 3000 mm.](../examples/building-services.md)
- [3071. Run a 450 mm main cable tray 12 m long and branch a 300 mm tray off it at 6 m going north for 5 m.](../examples/building-services.md)
- [3072. Run a 450 mm power tray at 3000 mm and a 150 mm data tray at 2700 mm side by side down a 15 m corridor.](../examples/building-services.md)
- [3082. Run a 600 x 100 cable tray 10 m to the main switchboard at its end.](../examples/building-services.md)
- [3084. Draw a 300 mm cable tray, take it back, then bring it back again.](../examples/building-services.md)
- [3087. Draw a 450 mm cable tray 10 m long and copy it 1 m north.](../examples/building-services.md)
- [3088. Run a 300 mm cable tray down a 20 m corridor, hang six luminaires under it and put two light switches at the ends.](../examples/building-services.md)
- [3099. Draw a 20 m corridor with its two walls and stack a duct, a pipe and a cable tray down it at different heights.](../examples/building-services.md)
- [4072. Lay out four light fittings and a cable tray on Level 1 and list the fittings.](../examples/views-sheets-and-schedules.md)

## Tray Fitting

A UNION command on the Services tab, Electrical panel. Also known as Cable Tray Fitting. It asks: "Select the segments, then click to place the cable tray fitting".

### Cable Tray Fitting

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical

Worked example: press **Tray Fitting** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Cable Tray Fitting · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Cable Tray Fitting' on Systems's Electrical panel (through its fold): the tool 'Cable Tray Fitting' stands | keys: Escape (tool Cable Tray Fitting -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Valve

A UNION command on the Services tab, Pipework panel. Also known as Pipe Accessory. It asks: "Click a pipe to place the accessory".

### Pipe Accessory

- Tab: Services
- Panel: Pipework
- Kind: tool
- Ribbon: Building Services > Plumbing & Piping

Worked example: press **Valve** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Pipe Accessory · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Pipe Accessory' on Systems's Plumbing & Piping panel (through its fold): the tool 'Pipe Accessory' stands | keys: Escape (tool Pipe Accessory -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Tag on Placement | yesno | false |  | all |

Played in these jobs:

- [3035. Place a water tank, run a 50 mm outlet pipe 6 m from it and put an isolating valve in the pipe.](../examples/building-services.md)
- [3037. Draw a 65 mm pipe 6 m long, put a valve in it at 1.5 m and a pipe fitting at 4.5 m.](../examples/building-services.md)
- [3047. Place a hot water tank and run a 40 mm hot water flow and return pair 8 m out from it, with a valve in the flow pipe.](../examples/building-services.md)

## Wire

A UNION command on the Services tab, Electrical panel. It asks: "Select the devices, then click to tie them with a wire; or click a device, then the next".

### Press it

- Tab: Services
- Panel: Electrical
- Kind: tool
- Ribbon: Building Services > Electrical
- Draw modes: Arc

Worked example: press **Wire** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Wire · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Wire' on Systems's Electrical panel (through its fold): the tool 'Wire' stands | keys: Escape (tool Wire -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Number of Poles | number | 1 |  | all |
| Voltage | number | 230 |  | all |
| Wiring Type | text | TPS 2.5mm2 |  | all |

Played in these jobs:

- [3081. Wire the distribution board to the outlet 3 m away.](../examples/building-services.md)

## Zone

A UNION command on the Services tab, Air panel. It asks: "Click a space to add it to the zone, then Finish".

### Press it

- Tab: Services
- Panel: Air
- Kind: tool
- Ribbon: Building Services > Spaces & Zones

Worked example: press **Zone** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Systems:Zone · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'Zone' on Systems's Spaces & Zones panel (through its fold): the tool 'Zone' stands | keys: Escape (tool Zone -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
