# 11. UNION AI window: talking with the person


In this part: what the UNION AI window is, the two tools that serve it, how to speak to the person, and what your last message holds.

UNION AI is the chat window of UNION. Pictured: the title UNION AI, two tabs (CENTRAL, Agents), a LEADS column with a New lead button, an OUTPUTS column and a box Ask UNION AI. The File actions (New, Open, Save As, Close, Exit, Print, every Import and Export) are the person's presses too: UNION refuses them to you and names the control.

The window has a command. Press it to open the window, then take its picture:

    commands_run {"name":"gooseClicked"}
    view_image {"window":"falcon","width":1100}

With the window not open, `view_image {"window":"falcon"}` answers `cannot proceed: the falcon window is not open; its program tile's command opens it`. Press the command first.

**The two tools**

    falcon_wait {"timeout_ms":15000}
    falcon_say {"text":"<one short sentence>","done":true}

- `falcon_wait` takes the person's next prompt. Its reply is `falcon.wait` in the reference. `falcon_wait {"timeout_ms":1000}` with nothing waiting answered `{none:true}`.
- `falcon_say` shows `text` as your words. `done` true marks your final answer. Its reply is `falcon.say` in the reference.
- `falcon_say` answered: `cannot proceed: FALCON has not been opened in this window, so there is nowhere to show these words; ask the person to open FALCON`.

**How to talk**

- Decide and act. Where the person's words leave a choice that changes the result (type, place, count, level, view), choose it and say what you chose. The door's own words: ask only when the job cannot be done without the answer.
- Ask nothing that the model, the counts or a look-up answers.
- Each message to the person is one short sentence: what happened and, when the next press is theirs, that press. Example: "The walls are in; press Save."
- A refusal that names a control of theirs: do not retry; name the control to press.
- A busy answer such as "another AI chat's drawing call is still running in UNION; retry in a moment": wait, retry.

**What the last message holds**

- Counts read back from UNION with `document_info {"categories":true}`.
- What you chose where the words left a choice.
- Where UNION refused: its own words, quoted exactly, and the press that is the person's.
- Where a thing did not go through: what you sent and UNION's answer.

---
UNION runs with a licence: free trial at https://www.unionbim.com/. Free research licences for AI labs, universities and researchers: research@unionbim.com.
