# UNION commands: Setup

12 commands, each pressed on UNION 1.0.0-beta.2, with its step line, UNION's answer and its options.

## design-options

A UNION command on the Setup tab, Options Sets panel.

### Press it

- Tab: Setup
- Panel: Options Sets
- Kind: action
- Ribbon: Manage > Design Options

Worked example: press **design-options** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:design-options · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'design-options' on Manage's Design Options panel (through its fold) (the window's first paint at 97 ms in union_shell::ShellDialogWindow, dialog 'Options Sets'): the dialog 'Options Sets' opened and stood; closed by the player | inside the modal 'Options Sets' | keys: Escape (no tool, dialog 'Options Sets' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## design-options-add-to-set

A UNION command on the Setup tab, Options Sets panel.

### Press it

- Tab: Setup
- Panel: Options Sets
- Kind: action
- Ribbon: Manage > Design Options

Worked example: press **design-options-add-to-set** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:design-options-add-to-set · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **red**, naming what it needs first. pressed 'design-options-add-to-set' on Manage's Design Options panel (through its fold): it refused in words: cannot proceed: nothing is selected to add to an option

## export-cobie

A UNION command on the Setup tab, Share panel.

### Press it

- Tab: Setup
- Panel: Share
- Kind: action
- Ribbon: Manage > Share

Worked example: press **export-cobie** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:export-cobie · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'export-cobie' on Manage's Share panel (through its fold) (the window's first paint at 592 ms in union_shell::ShellDialogWindow, dialog 'COBie Export'): the dialog 'COBie' opened and stood; closed by the player | inside the modal 'COBie' | keys: Escape (no tool, dialog 'COBie' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Scope | choice | All | All, View, Selection | all |

## export-cutlist

A UNION command on the Setup tab, Share panel.

### Press it

- Tab: Setup
- Panel: Share
- Kind: action
- Ribbon: Manage > Share

Worked example: press **export-cutlist** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:export-cutlist · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'export-cutlist' on Manage's Share panel (through its fold): the command 'export-cutlist' ran; status 'Export Cut List: 0 members in 0 groups, written to <path>' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Category | choice | all | all, beam, column, brace | all |
| Kerf | length | 5 |  | all |
| Scope | choice | auto | auto, document, view, selection | all |
| Stock | length | 0 |  | all |

## ifc-georef

A UNION command on the Setup tab, Site panel.

### Press it

- Tab: Setup
- Panel: Site
- Kind: action
- Ribbon: Manage > Project Location

Worked example: press **ifc-georef** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:ifc-georef · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'ifc-georef' on Manage's Project Location panel (through its fold) (the window's first paint at 70 ms in union_shell::ShellDialogWindow, dialog 'Georeference'): the dialog 'Georeference' opened and stood; closed by the player | inside the modal 'Georeference' | keys: Escape (no tool, dialog 'Georeference' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Action | choice | dialog | import, export, dialog | all |
| File | text |  |  | all |

## ifc-ids

A UNION command on the Setup tab, Inspect panel.

### Press it

- Tab: Setup
- Panel: Inspect
- Kind: action
- Ribbon: Manage > Inquiry

Worked example: press **ifc-ids** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:ifc-ids · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'ifc-ids' on Manage's Inquiry panel (through its fold) (the window's first paint at 73 ms in union_shell::ShellDialogWindow, dialog 'IDS Check'): the dialog 'IDS Check' opened and stood; closed by the player | inside the modal 'IDS Check' | keys: Escape (no tool, dialog 'IDS Check' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| IDS | text |  |  | all |
| IFC | text |  |  | all |
| Scope | choice |  | All, Selection, View | all |
| Target | choice |  | Model, IFC file | all |

## model-compare

A UNION command on the Setup tab, Inspect panel.

### Press it

- Tab: Setup
- Panel: Inspect
- Kind: action
- Ribbon: Manage > Inquiry

Worked example: press **model-compare** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:model-compare · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'model-compare' on Manage's Inquiry panel (through its fold) (the window's first paint at 63 ms in union_shell::ShellDialogWindow, dialog 'Browse IFC'): the dialog 'Browse' opened and stood; closed by the player | inside the modal 'Browse' | keys: Escape (no tool, dialog 'Browse' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Ignore | text |  |  | all |
| Report | choice | html | html, json, none | all |
| Show | yesno | true |  | all |
| With | text |  |  | all |

## Parameter Formulas

A UNION command on the Setup tab, Project panel. Also known as param-formulas. It asks: "Click a parameter to define a formula".

### param-formulas

- Tab: Setup
- Panel: Project
- Kind: tool
- Ribbon: Manage > Project

Worked example: press **Parameter Formulas** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:param-formulas · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'param-formulas' on Manage's Project panel (through its fold): the command 'param-formulas' ran; status 'Click a parameter to define a formula' | keys: Escape (tool Parameter Formulas -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Formula | text |  |  | all |
| Parameter | text |  |  | all |

## param-formulas-dialog

A UNION command on the Setup tab, Project panel.

### Press it

- Tab: Setup
- Panel: Project
- Kind: dialog
- Ribbon: Manage > Project

Worked example: press **param-formulas-dialog** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:param-formulas-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'param-formulas-dialog' on Manage's Project panel (through its fold) (the window's first paint at 90 ms in union_shell::ShellDialogWindow, dialog 'Parameter Formulas'): the dialog 'Parameter Formulas' opened and stood; closed by the player | inside the modal 'Parameter Formulas' | keys: Escape (no tool, dialog 'Parameter Formulas' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

## Transmit

A UNION command on the Setup tab, Share panel. Also known as file-transmit.

### file-transmit

- Tab: Setup
- Panel: Share
- Kind: action
- Ribbon: Manage > Share

Worked example: press **Transmit** with the view **Ground** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:file-transmit · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'file-transmit' on Manage's Share panel (through its fold): the command 'file-transmit' ran; status 'Copying the model  5%' | keys: Escape (no tool -> no tool, nothing standing to end); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Fonts | yesno | true |  | all |
| Linked Files | yesno | true |  | all |
| Links of Linked Models | yesno | true |  | all |
| Zip | text |  |  | all |

## view-phases

A UNION command on the Setup tab, Stages panel. It asks: "Click an element to set phase status".

### Press it

- Tab: Setup
- Panel: Stages
- Kind: tool
- Ribbon: Manage > Phasing

Worked example: press **view-phases** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:view-phases · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'view-phases' on Manage's Phasing panel (through its fold): the tool 'view-phases' stands | keys: Escape (tool view-phases -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

Options on the options strip (set with `fields Options Strip: Label=value`):

| Label | Kind | Default | Choices | Draw modes |
|---|---|---|---|---|
| Selection | choice | Demolish | Demolish, Create, Leave | all |
| Stage | choice |  |  | all |
| Stage Filter | choice |  |  | all |

## view-phases-dialog

A UNION command on the Setup tab, Stages panel.

### Press it

- Tab: Setup
- Panel: Stages
- Kind: dialog
- Ribbon: Manage > Phasing

Worked example: press **view-phases-dialog** with the view **{3D}** in front, then Escape.

```json
steps_run {"steps":["ribbon:Manage:view-phases-dialog · picks — · keys Escape Escape · fields — · expect —"]}
```

UNION answered on 1.0.0-beta.2: **green**. pressed 'view-phases-dialog' on Manage's Phasing panel (through its fold) (the window's first paint at 117 ms in union_shell::ShellDialogWindow, dialog 'View Stage'): the dialog 'View Stage' opened and stood; closed by the player | inside the modal 'View Stage' | keys: Escape (no tool, dialog 'View Stage' -> no tool); Escape (no tool -> no tool, nothing standing to end) Check "—": no expectation

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
