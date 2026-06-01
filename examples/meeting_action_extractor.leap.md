<LEAP_FILE type="leaplet_example_extractor">
<DOMINO>
    <TEMPLATE>
        <RECIPE_CARD>
            <MAP>
                <FUEL>
                    <!-- [PASTE_RAW_MEETING_TRANSCRIPT_HERE] -->
                </FUEL>

                <THE_MACHINE>
                    <LOGIC>
                        1. **Scan for Intent**: Identify any sentences where a commitment is made (e.g., "I'll handle that," "Let's get this done by Friday").
                        2. **Entity Extraction**: Isolate the task description, the assigned owner, and the specific deadline.
                        3. **Purify**: Remove all conversational "fluff," jokes, and off-topic discussion.
                        4. **Deterministic Mapping**: Transform the findings into the strict JSON array format requested in the Destination.
                    </LOGIC>
                </THE_MACHINE>

                <THE_DESTINATION>
                    <OUTPUT_FORMAT>
                        {
                          "meeting_date": "YYYY-MM-DD",
                          "action_items": [
                            {
                              "task": "Specific description",
                              "owner": "Name",
                              "deadline": "YYYY-MM-DD or TBD"
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
