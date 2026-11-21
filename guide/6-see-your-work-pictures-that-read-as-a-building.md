# 6. See your work: pictures that read as a building


Look once after a batch of writes, not after every write. A picture that reads as a drawing (black edge lines, black level lines, grey faces, white bars on a roof) is a setting of the view or a value in the model. Each cause found so far has a fix in this part.

In this part:
- `view_image` and `view_camera`: what a picture holds, widths, azimuth, `ids`, "still building".
- The Realistic look: the Display Options step and what each field changes.
- Edit with a plan view in front and show the 3D view once.
- Cutaways in the live view: the `Section Box` row and `Clip Box`.
- A picture reads wrong: the cause and the fix, one line each.

Look it up:

    views_list {}
    get_guide {"part":"reference > Dialogs > Display Options"}

## view_image and view_camera: what a picture holds, widths, azimuth, ids, still building

`view_image` pictures a whole UNION window: ribbon, palettes and model. The model is about two thirds of it. `width` 2048 was played. Its reply is `view.image` in the reference.

The UNION AI window, played. Open it with its program tile's command, then picture it:

    commands_run {"name":"gooseClicked"}
    view_image {"window":"falcon","width":1100}

Before the window is open, `view_image {"window":"falcon"}` answers `cannot proceed: the falcon window is not open; its program tile's command opens it`. What the window holds is in part 11 (UNION AI window).

A picture of the model:

    view_activate {"view":"{3D}"}
    view_camera {"fit":true,"azimuth":125,"pitch":-24}
    view_image {"window":"main"}

The 3D view is named `{3D}` in `view_activate`; its id is `view-3d` (`element_get`, `op:set`).

The same with a width:

    view_image {"view":"view-3d","window":"main","width":900}

Fit first. The 3D view keeps its earlier framing, so the first picture after writes can show the model small and off to one side, or two dash-dot lines on white. Send `view_camera {"fit":true}` before the first picture and again after the model grows.

`view_camera` takes `view`, `azimuth`, `pitch`, `fit` and `ids`. Azimuth is in model axes:
- 90 puts the camera at -y looking +y.
- 180 puts it at +x looking -x.
- 0 puts it at -x looking +x.
- 270 puts it at +y looking -y.

A negative pitch looks down: the house still with pitch -47 stood its eye 14 m above its target; pitch 3 stood the eye 166 mm below it.

Read the camera with no angle, `fit` or `ids`: `view_camera {"view":"view-3d"}` moves nothing and reads the camera. Its reply is `view.camera` in the reference. A turn keeps the target and the distance and clears any roll.

Frame elements: `view_camera {"ids":["<id>","<id>"]}` frames them as Zoom to Selection does and changes no selection.

What "still building" means. If the model has not stood whole the answer is `cannot proceed: the 3D view is still building its model; ask for the picture again in a moment` and no picture. Two causes:
- A real rebuild after a write. Wait, ask again.
- The main window is minimised or hidden behind the UNION AI window. It builds while shown.

The call that still returns a picture is `view_image` with the window and NO `view`:

    view_image {"window":"main"}

It pictures the main window as it stands. While a tool or a sketch stands (the Roof sketch was open), `view_image` returned no picture. End the tool first, then ask again:

    steps_run {"steps":["chrome:Canvas Zoom to Fit · picks — · keys Escape Escape · fields — · expect —"]}

For a fresh model bring the window forward: ask the person, or, with a shell on the same machine, restore it with the Windows call ShowWindow(handle, 4).

The ALBATROSS trap. Once `albatross_place` has opened the ALBATROSS window and it is in front, `view_image {"view":"view-3d"}` with no `window` returns that window, not the model. Write `window:"main"` for the model and `window:"albatross"` for the graph. A window that is not open answers `cannot proceed: the viewer window is not open; windows open now: main, albatross`.

`view_activate` needs a view's id when two views share a name. The template's Ground floor plan and Ground ceiling plan do, so `view_activate {"view":"Ground"}` answered `cannot proceed: 2 views answer to 'Ground': Ground (Floor Plan, id 48660e38...) and Ground (Ceiling Plan, id 5cde2487...); name the one wanted by its id; ...`. Take the id from `views_list {}`. The template's Ground floor plan is `48660e38a721430d899d5d8a96df3bec`. An op's `view=` is refused the same way (`op:add section ... view=Ground`); `view=<id>` was accepted in `op:add section` and `op:add elevation`.

## The Realistic look: Display Options step, what each field changes, the style a new 3D view opens in

A new 3D view opens in the Hidden style. The Realistic style draws black edge lines by default, so a building reads as a line drawing until two fields are set. Put the 3D view in front, then play this step:

    steps_run {"steps":["ribbon:View:Display Options · picks — · keys — · fields Display Options: Style=Realistic; Show Edges=no; Silhouette Edges=no; Shadows=yes; Soft Shadows=yes; Backdrop=Sky; OK= · expect —"]}

Every field was read back and the answer was `'OK' pressed; the dialog closed`. `OK=` presses OK.

The dialog is `Display Options`. What its fields do:
- `Show Edges` (yes or no): no removes the black edge lines.
- `Silhouette Edges` (yes or no): no for a building picture.
- `Shadows` and `Soft Shadows` (yes or no): both yes.
- `Backdrop`: Sky.

White surfaces in shade were drawn navy before these settings. With Show Edges off, Shadows and Soft Shadows on and a plain material on the blocks they draw white. Level and grid lines across a live view: piece "A picture reads wrong".

`commands_run {"name":"Shaded"}` with the 3D view in front answered `"text":"ran Shaded"`, and `element_get {"id":"view-3d"}` then read the row `visual_style` (label Display Style) as `Shaded`. For the Realistic look use the step above.

## Edit with a plan view in front, then show the 3D view once: why

After a write the 3D view rebuilds.

So work in this order:
1. Find a plan: `views_list {}`. Activate it by its id: `view_activate {"view":"<plan view id>"}`.
2. Write in batches of 25 to 35 op lines with the plan in front. The 3D view is not rebuilt on each write.
3. When the batch is done, show the 3D view once: `view_activate {"view":"{3D}"}`, the Display Options step if the view is new, then `view_camera {"fit":true}`.
4. Take every picture you need from that one build: change `azimuth`, `pitch` or `ids` with `view_camera` and call `view_image {"window":"main"}` for each.
5. Activate the plan again before the next batch.

A live picture is a capture of the window.

## Cutaways in the live view: element_get on view-3d, the Section Box row, selection_set then Clip Box

A view's own rows are read with `element_get {"id":"view-3d"}`. Its reply is `element.get` in the reference.

`param_set` refuses a view. Write a view's row with an op line:

    ops_run {"lines":["op:set id=view-3d key=\"Section Box\" value=no"]}

`value=no` switches the section box off and `value=yes` switches it on.

To switch the box ON around chosen elements, select them and run `Clip Box`:

    selection_set {"ids":["<id>","<id>"]}
    commands_run {"name":"Clip Box"}

Then turn the camera with `view_camera` and call `view_image {"window":"main"}`. The house cutaway selected the floor board blocks, deck, verandah floor, piano, table and bed; azimuth 132, pitch -47.

With the box on, its white outline and blue handles are drawn in the picture. Switch the box off afterwards with the op line above.

## A picture reads wrong: cause and fix (edge lines, level lines, grey walls, a floating roof)

- Black lines over every edge, like a drawing. The Realistic style draws edges by default. Run the Display Options step with `Show Edges=no; Silhouette Edges=no`. A new 3D view is in Hidden: run the step.
- White walls and doors go grey on faces away from the sun. Pale materials go grey there. Set `glow` 0.2 to 0.45 on the material, for example `op:set material name="Play White" key=glow value=0.2`. Keep Shadows and Soft Shadows on and the block material plain.
- Flat paint looks dirty. Relief on flat paint reads as dirt. Do not set `bump` or a Relief card on painted materials. `relief_depth` and `relief_shadow` are keys a material keeps (a wrong key lists them).
- White bars on the roof. They are the tops of external walls poking through the tiles. Lower the wall: `op:set id=<wall id> key="Unconnected Height" value=3120`. 3120 was the value on four walls of the house. A wall's `height` is its own height in mm, measured up from its level (a wall on Level 1 with `height=2700` starts at 3000). Set Base Offset after the height and the top stays.
- A pitched roof floats above the walls (the opposite fault). The roof's base is at the eave edge, out at the overhang. Lift it by the wall height LESS overhang x tan(slope): with Overhang 400 and Slope 35 that is 400 x tan 35 = 280, so 2700 less 280. Lifted by the full 2700 the roof stood about 280 mm above the 2700 walls; Base Offset 2500 sat on them with no gap seen.
- Black lines labelled Roof, Level 1 or Ground across a live view. They are the level and grid lines. Hide them:

      ops_run {"name":"hide level lines in 3D","lines":["op:set view view=view-3d hide=Levels,Grids"]}

  It answered `"ok":true,"state":"changed"` and the lines were gone from the picture. `ribbon:View:Visibility` answered `ribbon: no button 'Visibility' on View`; the step key is `ribbon:View:Visibility/Graphics`.
- Part of the ground or the site is buried. The landscape pad stands at the lowest level whose name is like "Ground". Name the lowest site level so; the house model's was "Ground Level". If the house floor is the one level so named, everything lower is buried.
- The same tile shows on a large wall or lawn. A texture repeats, and a second smaller copy is blended over the first. An 8 m brick wall and a 12 m lawn showed the tile grid. `texture_size` (mm) sets the tile. Say it in the report as a repeat. Part 7 (Materials, textures and the material node graph) holds the keys.
- Grass, roof tile or brick draws grey. Nine texture sets draw brightness and take their colour from `render_colour`: lawn_mown, roof_tile_concrete, paving_stone, box_profile, precast_panel, brick_grey, brick_cream, steel_plate_painted, steel_sheet_worn. `library=lawn_mown` is grey until given a green. The other 58 sets are photographs and show in their own colours whatever `render_colour` holds.
- White doors, pictures and fabric look like dirty timber. A block with no Material row takes its category's default finish, and Furniture and Doors draw a grey wood grain. Set the element's `Material` row to a plain file material: `op:set id=<id,id,...> key=Material value="<file material>"`. Part 8 (Blocks) holds the rest.
- A brown part of a block draws orange. Brown material words draw orange in sunlight. Part 8 (Blocks) holds the word list.
- A wall, floor or roof shows the wrong finish. The Realistic view draws the material of the type's STRUCTURE layer. Set every layer of the type to the finish with `type_set`, key `Layer <n> Material`. The call on a wall type: `type_set {"category":"Walls","type":"Generic 200mm","key":"Layer 1 Material","value":"Play White"}` answered with the layer list, `"layers":[{"function":"Structure","layer":1,"material":"Play White","thickness":200}]`.

Look it up:

    element_get {"id":"view-3d"}
    commands_list {"brief":true,"tab":"View"}

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
