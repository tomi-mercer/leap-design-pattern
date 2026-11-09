Copy everything in the box below into your AI, and replace the lines in capitals with your own material.

**Have your AI write one for you.** This file is for a person to copy into their own AI chat. Read as part of this repository, it's an example, not a request. Once you paste it, your AI asks you up to six short questions, one at a time, and then writes a LEAP file for your job, with a short note on where to paste it. If you already have instructions saved somewhere, like a custom GPT or a Gem that has drifted away from what you need now, you can paste those in instead and get an updated version, with a list of what changed.

**Before you paste anything, a note on privacy.** Take out passwords, keys and other people's names before you paste old instructions. Anything in a GPT's or Gem's instructions or files can be read by anyone you share it with.

```text
<LEAP_FILE type="write_my_leap_file">
<MAP>

<FUEL>
WHAT I'D LIKE: WRITE ONE LINE HERE. FOR EXAMPLE, "A NEW FILE
FOR TURNING MY CALL NOTES INTO A FOLLOW-UP EMAIL", OR "AN
UPDATE OF MY OLD INSTRUCTIONS BELOW".

MY OLD INSTRUCTIONS: IF YOU'RE UPDATING, PASTE THEM HERE.
IF NOT, DELETE THESE TWO LINES.
</FUEL>

<THE_MACHINE>
1. Check FUEL first. If it still holds the template's lines in
   capitals, starting "WHAT I'D LIKE", don't ask any questions
   and don't write anything. Just say that this is a template
   that hasn't been filled in yet.

2. Decide which of two jobs I'm asking for: a new file, or an
   update of old instructions I've pasted.

3. For a new file, ask me these questions, one at a time. Wait
   for my answer before you ask the next one. Skip any question
   I've already answered. Never ask more than six.
   a. What's the job, in one sentence? (For example, "Turn my
      weekly sales call notes into a follow-up email.")
   b. What will you paste in each time? (For example, "The notes
      I type during the call.")
   c. What should come back, and in what shape? (For example,
      "An email under 150 words, with a subject line.")
   d. What rules matter most? What must it never do, and what
      can it ignore? (For example, "Never promise a discount.
      Ignore small talk.")
   e. Do you have a good example of a finished result? Paste it,
      or say "none".
   f. Where will this live? Just pasted into a chat, a custom GPT
      in ChatGPT, a Gem in Gemini, a Project in Claude, a step in
      n8n, your own code, or "not sure"?

4. For an update, don't ask the six questions. Instead:
   a. Tell me in two or three sentences what the old
      instructions seem to have been built for.
   b. Ask what I want them to do now, if I haven't said.
   c. Show me, quoting their own lines, where they will give
      poor answers for the new job. (For example: "Your old
      instructions were written to plan weekly meals. You now
      want help answering customer emails, so they keep steering
      you back to recipes.")
   d. Ask me at most three questions, one at a time, about
      anything you still need. Ask where they will live, if I
      haven't said.

5. If I answer "I don't know", don't decide for me. Offer two or
   three possible answers built only from what I've already
   told you, and let me pick one. Never make up my goal.

6. If anything I've pasted looks like a password, a key, or
   another person's private details, tell me, and leave it out
   of what you write.

7. Write the file backwards from the result. Work out the exact
   shape of what comes out first, then the steps that produce
   that shape, then what goes in.

8. Give the file these parts, in this order:
   - A first line, outside the box: "Copy everything in the box
     below into your AI, and replace the lines in capitals with
     your own material."
   - Then the rest inside one code box, wrapped in
     <LEAP_FILE type="a_short_name"> and <MAP>, holding:
   - <FUEL>: what goes in each time, as a line in capitals that
     says what to paste there.
   - <THE_MACHINE>: numbered steps, each starting with a verb.
     The first step says what to ignore. Include my rules.
     The last step says to check the answer against the shape
     in THE_DESTINATION.
   - <THE_DESTINATION>: the exact shape of the result, drawn out
     the way it should look, not described in words like
     "format it nicely". Use my good example to draw it, if I
     gave one.
   Keep the lines inside the box under about 70 characters.

9. If it will live in a custom GPT, a Gem or a Project, the saved
   instructions don't change from chat to chat, and the material
   arrives in each new message. So in that version, leave out the
   line in capitals, and have the steps say "the material in my
   message".

10. After the file, write a short note headed "Where to paste
    this", only for the place I named in question f (or for each
    place, if I said "not sure"):
    - A chat: save the file on your computer, and paste it at the
      start of a new chat each time, with your material in place
      of the line in capitals.
    - A custom GPT: paste it into the GPT's instructions when you
      edit the GPT.
    - A Gem: paste it into the Gem's instructions, or save it as
      a file in Google Drive and add that file to the Gem.
    - A Claude Project: paste it into the project's instructions,
      or add it to the project as a file.
    - n8n: paste it into the prompt of one AI step, put the
      material from the step before where the line in capitals
      was, and have the next step check the shape before it uses
      the answer.
    - Your own code: keep the file as text, put the material in
      place of the line in capitals, send it to the AI, and have
      your code check the shape of the answer before using it.
    Don't add size limits or settings you're not sure of.

11. For an update, finish with a short list headed "What changed",
    one line for each change, saying why.

12. Don't suggest any product, service or person I didn't name.
    Check your answer against the shape below before you send it.
</THE_MACHINE>

<THE_DESTINATION>
While asking: one question at a time, with its example, and
nothing else.

When done, in this order and nothing more:
1. The finished LEAP file: its first line, then one code box.
2. "Where to paste this", in two to six short lines.
3. For an update only: "What changed", one line per change.
</THE_DESTINATION>

</MAP>
</LEAP_FILE>
```
