<LEAP_FILE type="leaplet_example_sorter">
<!--
THE PATTERN (read this once, then use the mold below)

This is the "Chaos Sorter": you hand the machine a messy brain-dump — half sentences,
pasted links, three ideas and a grocery item — and it returns a strict, sorted list of
real tasks, each filed into one of your life's buckets with an honest date.

Five moves make it deterministic instead of chatty:

1. ONE GOVERNING FRAME. The machine gets a single job description ("you sort chaos into
   tasks"), not a personality conversation. If your API supports a system-instruction
   field, put the frame there and keep the dump clean in the user slot.

2. THE FRAME COMPARTMENT OUTRANKS THE DUMP. If the dump belongs to a project with rules
   ("everything here is for the March launch"), put those rules in their own fenced
   compartment marked highest priority. Compartments beat paragraphs: the machine applies
   the frame to every task it extracts, without you repeating it.

3. REAL DATES ONLY. Inject today's actual date into the prompt so "by Friday" becomes a
   date that stays true tomorrow. Never let the machine store the word "tomorrow."

4. THE DESTINATION IS A SCHEMA, NOT A WISH. When you call a model API directly, pass the
   output shape as a real JSON schema (most modern APIs accept one and will refuse to
   drift from it). Begging for "valid JSON please" in prose is the old world.

5. NOTHING IS EVER LOST. In your own code, wrap the call so that on any failure the raw
   dump is kept somewhere safe and said so plainly. A sorter that can drop your words
   while failing politely is worse than no sorter.

Works with any schema-capable model API. One more honesty rule for builders: put the
API call behind one small adapter function in your codebase, so the day you change
models you change one constant — not twelve call sites.
-->
<DOMINO>
    <TEMPLATE>
        <RECIPE_CARD>
            <MAP>
                <FUEL>
                    <!-- [TODAY_IS: YYYY-MM-DD] -->
                    <!-- [PASTE_RAW_BRAIN_DUMP_HERE] -->
                </FUEL>

                <THE_FRAME priority="highest">
                    <!-- OPTIONAL. Rules that govern every task below, e.g.:
                         "All of this is for the March launch. Deadlines earlier than
                          March 1 are mistakes — flag them, don't file them." -->
                </THE_FRAME>

                <THE_MACHINE>
                    <LOGIC>
                        1. **Dissolve**: Read the raw dump as material, not conversation. Ignore greetings, mood, and filler.
                        2. **Extract**: Pull out every distinct, genuinely actionable task. Cap at 5 — a sorter that returns 40 items has sorted nothing.
                        3. **File**: Assign each task to exactly one bucket: 'work', 'school', 'personal', or 'community'. One task, one bucket, no "misc".
                        4. **Date honestly**: Resolve every relative date ("Friday", "next week") against TODAY_IS into a real YYYY-MM-DD, or use "TBD". Never output a relative word as a date.
                        5. **Obey the Frame**: If THE_FRAME is present, its rules override anything conflicting in the dump.
                        6. **Hold the mold**: Output must match the Destination schema exactly — no commentary, no extra fields.
                    </LOGIC>
                </THE_MACHINE>

                <THE_DESTINATION>
                    <OUTPUT_FORMAT>
                        {
                          "tasks": [
                            {
                              "bucket": "work | school | personal | community",
                              "title": "Short imperative title",
                              "description": "One or two sentences of the real substance",
                              "who": "Owner or 'me'",
                              "dueDate": "YYYY-MM-DD or TBD",
                              "why": "The one-line reason this matters"
                            }
                          ]
                        }
                    </OUTPUT_FORMAT>
                </THE_DESTINATION>
            </MAP>
        </RECIPE_CARD>
    </TEMPLATE>
</DOMINO>
</LEAP_FILE>
