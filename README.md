# L.E.A.P. (Logically Engineered AI Prompts)

**Stop chatting with AI... Start operating the machine.**

Most of us experience the exact same exhaustion every single day: we dump our messy thoughts and raw data into a massive paragraph in an AI chat box and assume the AI will sort it out. Instead, we spend our time correcting hallucinations and writing endless follow-up prompts just to herd the machine back on track.

### The Philosophy: Simple Made Easy
Following the Rich Hickey philosophy, we believe that complexity is a choice. We choose the "slippery, thread-the-needle" path of simplicity. L.E.A.P. doesn't fix AI by adding more code; it fixes the interaction by changing the physical shape of your intent.

### The Solution: The Bento Box
Instead of a messy, conversational paragraph, L.E.A.P. relies on isolating your instructions into strict compartments. We call this the **Bento Box**. When you stop writing paragraphs and start using isolated compartments, the AI stops trying to guess your intent in a "chat" and simply fills the space you provided. It becomes a deterministic computer.

#### Bento Box Lite (Everyday Tool)
Wrap your prompts in these simple brackets to see an immediate 10x improvement in clarity:

**[CONTEXT]**
Who you are and what the background situation is.
**[/CONTEXT]**

**[RULES]**
Exactly how the AI must behave and what it must ignore.
**[/RULES]**

**[INPUT]**
The raw data, messy notes, or transcript to process.
**[/INPUT]**

---

### Advancing to .LEAP (The Steel Mold)
Once you realize that AI responds perfectly to isolated context, you can scale this logic to build autonomous digital workers using **`.leap` files**. A `.leap` file is a strict XML container—a "Steel Mold"—that guarantees a pristine, exact output every single time.

### The Domino Standard (Agentic Logic)
For complex, multi-step workflows, we use the **Domino Standard**. This structure allows the AI to understand the sequence of operations, the fuel (data) required, and the internal machinery (logic) to execute.

*   **`<DOMINO>`**: The wrapper for the entire logic unit.
*   **`<FUEL>`**: The input data, context, or triggers required for the machine to run.
*   **`<THE_MACHINE>`**: The specific instructions, rules, and transformation logic.
*   **`<THE_DESTINATION>`**: The exact format and location of the final output.

### Obvious Utility (HILOU) Examples
Explore the `examples/` directory to see L.E.A.P. in action for high-friction daily tasks:
*   **[Chaos Sorter (Task Intake)](./examples/chaos_sorter_intake.leap.md)**: Dump your messy thoughts; get back real tasks, filed into life buckets with honest dates — the schema-enforced sorting pattern.
*   **[Meeting Action Extractor](./examples/meeting_action_extractor.leap.md)**: Convert messy transcripts into strict JSON task lists.
*   **[Receipt Expense Parser](./examples/receipt_expense_parser.leap.md)**: Extract merchant, date, and total from raw OCR text.
*   **[Emotional Dissolve Email](./examples/emotional_dissolve_email.leap.md)**: Refactor angry drafts into perfectly professional responses.

#### Developer Integration (Copy-Paste Examples)
You can embed L.E.A.P. logic directly into your existing codebase.

**Python Example:**
```python
leap_prompt = f"""
<LEAP_FILE type="data_cleaner">
<MAP>
    <FUEL>{raw_input_data}</FUEL>
    <THE_MACHINE>Execute regex cleaning and JSON formatting.</THE_MACHINE>
    <THE_DESTINATION>Return a valid JSON object only.</THE_DESTINATION>
</MAP>
</LEAP_FILE>
"""
response = client.chat.completions.create(messages=[{"role": "user", "content": leap_prompt}])
```

---

### The Open-Source Handshake
*   **Visibility**: Everything is open to read and fork.
*   **Licensing**: MIT covers the copyright in this spec and its examples; see [PATENTS.md](./PATENTS.md) for the patent notice (belt-and-suspenders — MIT is silent on patents).
*   **Contribution**: Pull requests must pass the HILOU^3 logic test (Highest Immediate Logical Obviously Useful).
*   **Communication**: Don't shout in the void of GitHub Issues. Meet the community of AI Operators at [AutomatedWith.tech](https://automatedwith.tech)—that's where the real machinery moves.

### Dual-Bridge Navigation
*   **Watch the Face**: See the "Casual Magic" in action on YouTube at [@ThisIsYourMindOnAI](https://youtube.com/@ThisIsYourMindOnAI).
*   **See the Gears**: Join the community and build the future of AI-Native Operating Networks at [AutomatedWith.tech](https://automatedwith.tech).

### Get the Engine (The NDK)
This repository provides the manual framework — the pattern you drive by hand. The **Nitwyt Developing Kit (NDK)** is the factory: a private repository you open in an IDE with an AI dev agent beside it. It carries the runnable **Nitwyt OS** studio — a local-first Chrome extension where you catch stray thoughts in **The Net** and organize them in **the Idea Garden**, with no server, no account, and your ideas never leaving your machine — plus the living blueprints and `.leap` spec brain that build it. When the artifact needs a fix, the factory fixes it; you watch each fix arrive through a blueprint.

[**Purchase the NDK ($500)**](https://nitwyt.ai)

**AI First... Always Human.**
