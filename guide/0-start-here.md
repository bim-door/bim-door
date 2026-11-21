# Start here

UNION is a complete building-modelling and drafting program: walls, floors, roofs and stairs; freeform (NURBS) curves and surfaces; structure and building services; blocks; materials with photographic textures and a node graph; views, schedules, sheets and printing; realistic pictures. An AI works in UNION through the calls in this guide. UNION AI, the AI built into UNION, works this way for the drafter, and AI labs and researchers reach the same calls through UNION's MCP door on a free research licence.

THIS GUIDE. It is written for AI agents. It is the guide that ships inside UNION 1.0.0-beta.2, cut down to what has been played through UNION's AI door: calls not yet played, and the notes on them, are left out. The guide inside UNION holds the rest and is read by part with `get_guide`; the part numbers here are the same as there, so a number missing here is a part kept in the program.

THE RULE. This guide is not the extent of UNION. UNION can do nearly every operation you already know from building-modelling, drafting and 3D programs. Your job is to look the control up, never to decide it is absent. Part 2 says where UNION lists its commands, dialogs, ops and cards. Before you tell the person that UNION lacks a thing, you must have:
1. looked for the everyday word in part 3 (the map) and the name in part 16 (every command);
2. asked UNION itself: `commands_list {"name":"<name>"}` or `commands_list {"tab":"<tab>"}`, and `get_guide {"part":"reference > Commands > <name>"}`;
3. tried it and read UNION's answer: a refusal names its fix and often lists the valid words.
Still not found? Say "I did not find a control for <thing>; I searched <the lists>". Never say "UNION cannot".

HOW TO WORK. Act at once and decide. Ask the person only what neither the model, a look-up nor a sensible choice of yours settles, and say what you chose. Read the model first: `document_info {"categories":true}`, `levels_list`, `views_list`. Write with `ops_run` where an op line exists (part 4), else with `commands_run` or a step (part 5). Look at a picture after each batch of writes (part 6). Read UNION's words in every answer, not only "ok" or "green". File actions (such as New, Open, Save As, Close, Import, Export, Print) are the person's own presses: ask for one in a single short sentence.

READ BY PART. Name a part by the start of its heading, number and dot included: `get_guide {"part":"guide > 4. Fast ops"}`. A part of up to 24 KB answers whole; a longer one answers its opening text and a list of its pieces. Read one piece of any part by a word of its heading: `get_guide {"part":"gable"}` answers the first heading that holds the word and names the others. Words match headings only, never the text: no match means only that no heading holds the word. Read part 2 once, then only what the job needs. The reference (every command, dialog, field and parameter of UNION) is a separate document: `get_guide {"part":"reference"}`.

STANDING. The calls on this page are the ones marked played in UNION's own guide: each was run through UNION's AI door on a UNION build. A played call is true of its build only: send the call and read UNION's answer.

TWO TOWERS. The last part of this page is a worked set of 15 prompts that draws two steel towers, a gridshell round them and a drawing set of 24 sheets, call by call: read `Two Towers > Rules`, then `Two Towers > Prompt <n>`.

On UNION 1.0.0-beta.2 every step line and op line of this guide that needs no id made earlier was played again: 478 lines, 473 green; the five that were not are corrected here from what UNION answered. Every tool the guide names is a method UNION 1.0.0-beta.2 lists in its own reference.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
