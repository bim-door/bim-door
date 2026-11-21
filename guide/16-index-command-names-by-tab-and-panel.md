# 16. Index: command names by tab and panel


In this part: the command names `commands_list` gave, grouped by the tab and panel the list files them
under, so one read shows whether UNION has a command for what you want. `*` after a name: a tool that takes points. `=`: it
opens a dialog. No mark: an action. The names under "no tab" are real commands
too: sub-tools (written with the fold arrow), contextual buttons, file types (`file-import:<type>`, `file-export:<type>`) and
program tiles. A few names are not here: file exchanges named after the program they exchange with:
`commands_list {"name":"<that program's name>"}` finds one, and `commands_list {"brief":true}` lists every name.

Read one in full (prompt, options, draw modes): `commands_list {"name":"<name>"}`. Run one: `commands_run {"name":"<name>"}`, part 5
(Commands, steps and dialogs). `commands_list {"name":...}` also answers some common trade names (`Level` finds `Storey`). The tab
words here are the list's own; the ribbon a person sees reads Setout, Architectural, Structural, Building Services, Detailing,
Freeform, Views, Manage, Add-Ins, Modify, Insert, Interoperability.

**Tab Structural (50)**
- Datums: Storey*; Gridline*
- Work Plane: Construction Plane*
- Elements: Wall*; Wall: Structural*; Column*; Framing*; Bracing*; Floor*; Floor: Structural*; Truss*; Framing Layout*; draw-stair*; draw-ramp*; draw-ceiling*; Sketch Ceiling*; Wall Framing
- Foundation: Pad Footing*; Strip Footing*; Raft*
- Opening: Face Cut-out*; Wall Cut-out*; Member Opening*; Vertical Cut-out*; Roof Cut-out*
- Model: 3D Line*; 3D Text*
- Form: Freeform Curve*; Loft*; Sweep*; Revolve*; Column on Form*; Brace on Form*
- Structure: Slab Edge*; Wall Sweep*; Wall Reveal*
- Reinforcement: Rebar*; Path*; Area*; Cover*; Fabric Area*; Fabric Sheet*; Bar Coupler*; Lap Bars*; Reinforcement Settings; Rebar Cover Settings; Reinforcement Numbers; Abbreviations
- Connection: Steel Connection*; Plate*

**Tab Services (64)**
- Work Plane: Set Plane*; Show Plane*; Construction Plane*
- Pipework: Pipe*; Flex Pipe*; Sanitaryware*; Valve*; Pipe Fitting*; Plumbing Plant*; Sprinkler*; Hydrant*; Hose Reel*; Fire Pump*; Tank*; mep-pipesize*
- Air: Duct*; Diffuser*; Flex Duct*; Duct Fitting*; Duct Accessory*; Space*; Zone*; Space Separator*
- Plant: Plant Item*
- Electrical: Tray*; Conduit*; Conduit Bank*; Tray Fitting*; Conduit Fitting*; Board*; Device*; Luminaire*; Wire*; Disconnect Board; Circuit › Power; Circuit › Switch; Circuit › Data; Circuit › Telephone; Circuit › Fire Alarm; Circuit › Nurse Call; Circuit › Communication; Circuit › Control; Circuit › Security
- HVAC: Single-Line Duct*; Make Full Size; Make Flexible
- Plumbing & Piping: Single-Line Pipe*; Pipe Bank*
- Check Systems: Check Air; Check Pipework; Check Circuits; Open Ends; Duct Legend*; Pipe Legend*; Space Naming*
- Devices: Outlet*; Comms Point*; Data Point*; Fire Alarm Point*; Switch Point*; Nurse Call Point*; Security Point*; Phone Point*
- Power: mep-trayfill

**Tab Setout (1)**
- Work Plane: Plane View

**Tab Modify (139)**
- Grids: Propagate Extents
- View: Restyle Line*; Clip Box
- Floors: Edit Boundary*; Modify Sub Elements*; Add Point*; Add Split Line*; Pick Supports*; Reset Shape
- Roofs: Edit Footprint*
- Ceilings: Edit Boundary (ceiling)*
- Roof Soffits: Edit Boundary (roof soffit)*
- Openings: Edit Sketch (opening)*
- Detail Items: Edit Boundary (region)*
- Stairs: Edit Stairs*
- Structural Framing: Justification Points*; Edit Work Plane; Pick New*; Attach Top/Bottom*; Detach Top/Bottom; Edit Profile (truss)*
- Structural Beam Systems: Edit Boundary (beam system)*; Release Beam System; Run Direction (beam system)*
- Modify: Move*; Copy*; Mirror Pick*; Rotate*; Offset*; Corner*; Trim Single*; Trim Many*; Array*; Scale*; Anchor*; Release*; Delete*; Align*; Break*; Mirror Draw*; Copy Type*; Same Again*; Array Radial*; Break Gap*
- Select: Select Pinned Elements; Select Links; Select Underlay Elements; Select Elements by Face; Drag Elements on Selection; Select All
- Clipboard: Cut to Clipboard*
- Geometry: Cut*; Cut › Cut Geometry*; Join*; Join › Switch Join Order*; Wall Joins*
- Create: Make Group=; Make Assembly=; Disassemble Assembly; Unpack Import; Place Group*
- Measure: Measure Along An Element*; Interference Check=; Show Controls*; Measure*; Measure Area*; Measure Area of an Object*
- Tags: Pick New Host*; Select Host; Edit Tag; Select Leaders to Show
- Text Notes: Add Straight Leader*; Remove Last Leader
- Draw Order: Raise to Top; Lower to Bottom; Bring Forward; Send Backward
- Parts: Divide Parts*
- Viewports: Activate View; Positioning and View
- Views: Edit Crop*; Reset Crop; Size Crop=
- Dimensions: Edit Witness Lines*
- Warning: Show Related Warnings
- Pipes: Pipe Sizing (Pipes)=; Justify (Pipes); Cap Open Ends (Pipes); Slope (Pipes); Add Insulation (Pipes)
- Analysis: Duct Sizing=; Pipe Sizing=
- Ducts: Duct Sizing (Ducts)=; Justify (Ducts); Cap Open Ends (Ducts); Add Insulation (Ducts); Add Lining (Ducts)
- Properties: Properties
- Structural Columns: Attach Top/Base*; Detach
- Edit panel: Cap Open Ends; Justify
- Walls: Detach Top/Base*; Edit Profile*; Reset Profile; Attach Top/Base (wall)*
- Mode: Edit Family; Edit In-Place
- Duct Insulation panel: Add Insulation
- Duct Lining panel: Add Lining
- Electrical: Select Panel*
- Visibility: Form Showing=
- Group: Exclude; Restore All Excluded; Ungroup; Export Group; Load Group; Remove from Group
- Structural Area Reinforcement: Remove Reinforcement System
- Insulation and Lining: Edit Insulation; Remove Insulation; Edit Lining; Remove Lining
- Create Systems: Duct System; Piping System; Edit System
- System Tools: Divide System; Add to System; Remove from System; Reapply Type
- Connect: Connect Into*; Take Elevation*; Take Size*
- Electrical Circuits: Edit Circuit; Add to Circuit; Remove from Circuit
- Layout: Generate Placeholder
- Model: Mass Floors
- (no panel): Modify/Modify

**Tab View (45)**
- Graphics: Outline; Hidden line; Shaded; Hide*; Hide category*; Hide element*; Isolate*; Reset temporary hide/isolate; Reveal hidden; View Presets*; Visibility; Filters; Thin Lines*; Hidden Lines On*; Hidden Lines Off*; Cut Shape*
- Zoom: Zoom region*; Zoom out; Zoom to fit; Zoom all; Previous zoom; Next zoom
- Create: Model View; Section*; Enlargement*; Plans; Elevation*; 2D View*; Copy View; Legends; Schedules*; Extent Box*; Area Boundary*
- Sheet Composition: Drawing*; Border*; Revisions=; Layout Grid*; Matchline*; Placed View*
- Windows: Switch; Close Others; Tabs; Tile; Cascade
- Context Menu: Find Referring Views

**Tab Architecture (17)**
- Build: Wall: Architectural*; Column: Architectural*; Floor: Architectural*; Curtain Grid*; Mullion*; Door*; Window*; Roof*; Roof Soffit*; Model In-Place; Roof: Fascia*; Roof: Gutter*
- Room & Area: Room Tag*; Room*; Room Separator*; Area (area plan)*
- Circulation: Railing*

**Tab Annotate (51)**
- Dimension: Aligned*; Linear*; Dimension Continue*; Dimension Baseline*; Dimension Ordinate*; Quick Dimension*; Dimension Break*; Angular*; Radial*; Diameter*; Arc Length*; Spot Level*; Spot Coordinate*; Spot Fall*
- Detail: 2D Line*; Hatch*; 2D Block*; Cloud*; 2D Group*; Define Attribute*; Edit Attribute*; Insulation*; Fillet*; Chamfer*; Trim*; Extend*; Lengthen*; Center Mark*; Centerline*; Multileader*; Overkill*; Polyline Edit*; Repeating Detail Component*; Legend Component*; Save to Detail Library=
- Text: Table*; Text*; Find*; Spelling*
- Tag: Tag*; Area Tag*; Tag All*; Any Tag*; Material Tag*; Keynote*; View Reference*
- Symbol: Symbol*; Feature Control Frame*; Datum Feature*; Surface Texture*; Span Direction*

**Tab Home (1)**
- Layers: Viewport Layer*

**Tab Manage (45)**
- Settings: Materials=; Category Styles=; Snapping=; Project Details=; Project Fields=; Shared Fields=; Global Fields=; Copy Standards=; Save Schedule Layout; Load Schedule Layout; Purge; Units=; Structural Setup=; More Settings=; Resolution=; Assembly Code=; Multiple Values Indication=; views-area-types
- Project Location: Site=; Acquire Coordinates; Publish Coordinates; Specify Coordinates at a Point; Place Project Base Point*; Relocate Project; Rotate True North; Rotate Project North; Mirror Project
- Design Options: Options Sets=
- Phasing: Stages=
- Selection: Save Selection=; Load Selection=; Edit Selection=
- Inquiry: Show IDs; Pick by ID; Warnings
- Share: Synchronise; Borrow; Release; Reload Latest
- Info: About=; Licence=
- Redline: Redline
- Services Settings: Load Classes; Demand Factors; Building and Space Types

**Tab Insert (15)**
- Link: Project Files=; Link RVT=; Link IFC; Link DWG; Link PDF=; Link Image=; Link Point Cloud=; Links Manager=; Copy/Monitor
- Import: Import DWG=; Import Image; Import PDF=
- Load from Library: Load Block=; Detail Library=; Insert 2D Elements from File

**Tab Systems (1)**
- Mechanical: Mechanical Control Device*

**Tab Make (23)**
- Forms: Extrude*; Loft*; Revolve*; Sweep*; Swept Loft*; Cut Forms*; Cut Forms › Extrude*; Cut Forms › Loft*; Cut Forms › Revolve*; Cut Forms › Sweep*; Cut Forms › Swept Loft*
- Datum: Construction Plane*; Construction Line*
- Text: Parameter Text*
- Ports: Power Port*; Duct Port*; Pipe Port*; Tray Port*; Conduit Port*
- Properties: Block Category and Fields=; Block Types=; Send to Project; Send and Close

**Tab Structure (1)**
- Model: Group

**Tab File (18)**
- (no panel): New; Open; Save; Save As; Export=; Analytical Formats; STEP; Print=; Close; Preferences=; Recent; Open Windows; Exit; Feedback=; Edit Skin; Push; Compare With Saved File; Import=

**Tab Views (16)**
- Render: render-sun; render-textures; Render Lights; render-panorama; Render Queue; render-print; Entourage*
- Display: views-depth-cue; views-silhouette; views-colourfill; view-templates; View Filters
- Drawings: sheets-render
- New View: views-legend; views-areas; views-autosections

**Tab External (6)**
- Imports: IFC Property Sets; ifc-types; ifc-classes; ifc-openings; IFC Materials; ifc-assemblies

**Tab Setup (15)**
- Site: ifc-georef
- Inspect: ifc-compare; ifc-ids; model-compare
- Share: bcf; export-cobie; Transmit; export-cutlist
- Project: bcf-import; Parameter Formulas*; param-formulas-dialog=
- Options Sets: design-options; design-options-add-to-set
- Stages: view-phases*; view-phases-dialog=

**Tab Freeform (17)**
- Site: LANDXML; CITYJSON; GEOJSON; Toposurface*; Building Pad*; Property Line*; Property Line Distances; Toposolid*; Sub-Divide*; Convert to Toposolid; Label Contours*
- Form: Form Panels*; Reference Point*
- Model by Face: Floor by Face*; Roof by Face*; Wall by Face*; Curtain System*

**Tab Add-Ins (1)**
- External Tools: External Tools

**Tab Tools (1)**
- Adjust: modify-trim

**Tab Detailing (1)**
- Dimensions: annotate-autodim

**Tab (no tab) (472)**
- (no panel): redline_open_pdf; muleAddAnother; muleRead; muleBack; muleNext; muleConvert; muleCancel; muleDone; muleOrigin; muleLocation; muleSave; muleItem; muleStep; Select All Instances; Go to View; Override Graphics in View By Element; Analysis and MEP; export_window; gbXML; IFC (MEP); CIS/2; IFC Structural; SAF; Undo; Redo; Hide selection (viewer toolbar, UNION addition); Show all objects (viewer toolbar, UNION addition); Ghost mode and transparency slider (viewer, UNION addition); Isolate category; Temporary Hide/Isolate; Clip plane menu (viewer, UNION addition): Horizontal; Clip plane menu (viewer, UNION addition): Vertical; Clip plane menu (viewer, UNION addition): Flip; Snapping of clip planes (viewer, UNION addition); Clip plane (viewer, UNION addition); Section plane from a face (viewer); Section remove (viewer); Section box off (viewer); Remove section (viewer); Measure (viewer, UNION addition); Clear measure (viewer, UNION addition); Measure distance between points (viewer); Measure distance between faces (viewer); Measure angle between points (viewer); Measure area (viewer); Measure what the snap shows (viewer); Measure angle between faces (viewer); Finish area measurement (viewer); Markup menu (viewer, UNION addition); Arrow markup (viewer, UNION addition); Freehand markup (viewer, UNION addition); Cloud markup (viewer, UNION addition); Markups (viewer panel, UNION addition); Export current view as image (viewer, UNION addition); Datum point X Y Z (viewer); Datum surface RL (viewer); Edit Label=; Vertical; MSPACE; PSPACE; Finish; Cancel; Close Shape; Slope Arrow; Undo Last Point; Line; Show Mass; Apply temporary hide/isolate; PDF; Type Properties; Type Settings; Edit Type; Help; Trim/Extend › Trim/Extend to Corner; Copy (to Clipboard); Paste; Paste (from Clipboard); Paste › Aligned to Same Place; Paste › Aligned to Current View; Paste › Aligned to Selected Levels; Paste › Aligned to Picked Level; Paste › Aligned to Selected Views; Measure › Measure Between Two References; Refine Selection; Filter; Allow Join; Disallow Join; Join › Unjoin Geometry; Cut › Uncut Geometry; Split › Split Element; Detail Line › Finish; Detail Line › Line; Detail Line › Rectangle; Detail Line › Inscribed Polygon; Detail Line › Circumscribed Polygon; Detail Line › Circle; Detail Line › Start-End-Radius Arc; Detail Line › Center-ends Arc; Detail Line › Tangent End Arc; Detail Line › Fillet Arc; Detail Line › Spline; Detail Line › Ellipse; Detail Line › Partial Ellipse; Detail Line › Pick Lines; Detail Line › Polyline; Region › Filled Region; Region › Masking Region; Region › Finish; Region › Close Shape; Remove Fabric Area System; Symbolic Line; Flip Structural Framing Ends; Remove Truss Family; Create Parts; Exclude Parts; Restore Parts; Merge Parts; Unmerge Parts; Edit Division; User Interface; Close Inactive Views; User Interface › Project Browser; User Interface › Browser Organization; Report Shared Coordinates; Location; Mouse scheme; View Templates › Manage View Templates; View Templates › View Preset Sync; Callout › Rectangle; Callout › Sketch; Legends › Legend; Legends › Keynote Legend; MEP Settings › Mechanical Settings; MEP Settings › Piping Settings; MEP Settings › Electrical Settings; Edit Path; Edit Zone; Place Spaces Automatically; Component; 3D View › Default 3D View; Plan Views › Structural Plan; Plan Views › Floor Plan; Plan Views › Reflected Ceiling Plan; Plan Views › Area Plan; Duplicate View › Duplicate; Duplicate View › Duplicate with Detailing; Duplicate View › Duplicate as Dependent; Elevation › Framing Elevation; Plan Views › Plan Region; Edit Crop Region; Panel Schedules; Schedules › Material Takeoff; Schedules › Sheet List; Schedules › View List; Schedules › Graphical Column Schedule; Schedules › Graphical Wall Schedule; Schedules › Note Block; Schedules › Steel Take-off; Schedules › Schedule/Quantities; Panel Schedule Templates; Board Schedule Layouts; Update Panel Schedules; Share Model; Pending merges; My pending pushes; Split Face; Paint; Remove Paint; gooseClicked; albatrossClicked; redlineClicked; viewerClicked; view3DClicked; modelSpaceClicked; terminalClicked; Terminal; buildClicked; playstationClicked; muleClicked; unionClicked; edit_skin; User Interface › System Browser; Render Settings; Top; Bottom; Front; Back; Left; Right; Isometric; Perspective; Orthographic; Orbit; Pan; Save As Template; Reset to 3D Extents; Maximize 3D Extents; New Block › Furniture; New Block › Casework; New Block › Generic Model; New Block; Open Block; Save Block As; Save All Blocks; file-import:auto; file-export:3DM; file-import:3DM; file-export:AI; file-import:AI; file-export:DGN; file-import:DGN; file-export:DWG; file-import:DWG; file-export:DXF; file-import:DXF; file-export:DXF3D; file-import:DXF3D; file-export:EMF; file-import:EMF; file-export:EPS; file-import:EPS; file-export:PDF; file-import:PDF; file-export:SVG; file-import:SVG; file-export:U2D; file-import:U2D; file-export:ADSK; file-import:ADSK; file-export:IGES; file-import:IGES; file-export:IGS; file-import:IGS; file-export:SAT; file-import:SAT; file-export:STEP; file-import:STEP; file-export:STP; file-import:STP; file-export:VDA; file-import:VDA; file-export:3MF; file-import:3MF; file-export:AMF; file-import:AMF; file-export:FBX; file-import:FBX; file-export:GTS; file-import:GTS; file-export:LWO; file-import:LWO; file-export:OBJ; file-import:OBJ; file-export:OFF; file-import:OFF; file-export:PLY; file-import:PLY; file-export:RAW; file-import:RAW; file-export:SLC; file-import:SLC; file-export:STL; file-import:STL; file-export:3DS; file-import:3DS; file-export:DAE; file-import:DAE; file-export:GLB; file-import:GLB; file-export:GLTF; file-import:GLTF; file-export:SKP; file-import:SKP; file-export:UNIONBUILD; file-import:UNIONBUILD; file-export:UNIONPLAY; file-import:UNIONPLAY; file-export:USD; file-import:USD; file-export:USDC; file-import:USDC; file-export:USDZ; file-import:USDZ; file-export:VRML; file-import:VRML; file-export:WRL; file-import:WRL; file-export:XAML; file-import:XAML; file-export:CITYJSON; file-import:CITYJSON; file-export:GEOJSON; file-import:GEOJSON; file-export:GSM; file-import:GSM; file-export:IFC; file-import:IFC; file-export:IFC2X3; file-import:IFC2X3; file-export:IFC4; file-import:IFC4; file-export:IFCZIP; file-import:IFCZIP; file-export:LANDXML; file-import:LANDXML; file-export:PLN; file-import:PLN; file-export:PUSH; file-import:PUSH; file-export:RVT; file-import:RVT; file-export:UNION; file-import:UNION; file-export:CSV; file-import:CSV; file-export:E57; file-import:E57; file-export:GDF; file-import:GDF; file-export:JPG; file-import:JPG; file-export:KMZ; file-import:KMZ; file-export:PNG; file-import:PNG; file-export:PTS; file-import:PTS; file-export:TIFF; file-import:TIFF; file-export:TXT; file-import:TXT; file-export:XYZ; file-import:XYZ; Create System; Switch System; Add to Switch System; Remove from Switch System; Additional Settings › Arrowheads=; Additional Settings › Line Styles=; Additional Settings › Line Weights=; Additional Settings › Line Patterns=; Additional Settings › Dimension Types; MEP Settings; Additional Settings › Fill Patterns=; Additional Settings › Halftone/Underlay=; Review Warnings=; Display Options=; Reload Link; Unload Link; Bind Link; Graphics; Additional Settings › Temporary Dimensions=; Additional Settings › Sun Settings=; analytical-window; annotate-autodim-dialog; annotate-revision-dialog; Audit; bcf-issues; CITYJSON Settings; Command Aliases; Count; Join Lines; Match Properties; Stretch; draw-ceiling-rcp; draw-ceiling-dialog; draw-ramp-settings; draw-stair-settings; draw-topo-graded; draw-topo-settings; Toposolid › Finish; Toposolid › Cancel; Explode; export-cutlist-settings; file-transmit-settings; form-panels-dialog; geojson-settings; ifc-compare-clear; ifc-compare-settings; ifc-materials-dialog; Merge IFC Files (viewer); ifc-openings-dialog; Save Selection as IFC (viewer); Insert Views from File; Layer Current; Layer Make Current; Layer Off; Layer Freeze; Layer Lock; Layer Isolate; Layer All On; Layer Match; Layer Freeze In View; Layer Thaw All In View; Layer Manager; Layer States; Loaded Tags; mep-pipesize-settings; model-compare-next; model-compare-previous; modify-array; modify-array-radial; modify-array-dialog; modify-mirror; modify-mirror-pick; modify-mirror-settings; modify-offset; modify-trim-settings; Property Line › Finish; Property Line › Cancel; render-entourage-settings; render-lights-settings; render-view; render-sun-dialog; render-textures-settings; sheets-render-refresh; sheets-render-settings; Drawing Settings; sun-hours; Demolish; view-templates-manage; Add Model (viewer); Place Model (viewer); Remove Model (viewer); area-computations; views-areas-schedule; views-areas-settings; views-autosections-dialog; views-colourfill-dialog; views-depth-cue-dialog; views-silhouette-dialog; wall-framing-remove; wall-framing-settings; windClicked; windRun; windStop; windFly; windFetchSurroundings; windSettings; windSiteSettings; windDirectionSettings; windTimeSettings; windResolutionCoarse; windResolutionMedium; windResolutionFine; windRunOnGpu; windRunOnCpu; windEnclosed; windShowMean; windShowPeak; windShowPressure; windShowSurroundings; windShowSection; windShowPlan; windShowVectors; windShowPanels; windExportTable; Zoom to Selection; Save Behaviour=; Arrowheads=; Line Widths=; Fill Patterns=; Additional Settings › Keynote Table=; Keynote Table=; Faint Plan=; Temporary Dimensions=; Sunlight=; Line Types=; Dash Patterns=; feedback; New 2D Drawing; Home

**Tab Doors (2)**
- (no panel): Doors/Flip Facing; Doors/Flip Hand

**Tab Windows (2)**
- (no panel): Windows/Flip Facing; Windows/Flip Hand

**Tab Ceilings (1)**
- (no panel): Ceilings/Slope Arrow

Look it up: `commands_list {"tab":"<tab>"}` gives one tab's commands in full; `commands_list {}` gives the tabs and their counts.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
