# How to write a LEAP file yourself

A LEAP file is a prompt split into labelled parts: what goes in, the steps, and what must come out. The AI does not need to know LEAP; the labels help it tell your material apart from your instructions.

This page shows you how to write your own LEAP file, starting from an empty page. The other files in this repository are finished examples. Here you will see the parts of a file, the order to write them in, the question each part answers, and one small example built step by step.

You can use the file you write in ChatGPT, in a Gemini Gem (a saved helper in Google's Gemini), in a Claude Project (a saved workspace in Claude), in one AI step of n8n (a workflow tool), or in your own code. The last section says where to paste it.

---

## What a LEAP file looks like

A LEAP file is plain text with named parts. Each part sits inside the next one, like this:

```text
<LEAP_FILE type="...">       the name of the file's job
  <DOMINO>                    outer label
    <TEMPLATE>                outer label
      <RECIPE_CARD>           outer label
        <MAP>                 holds the working parts
          <STYLE>             (optional) how the result sounds
          <FUEL>              what goes in
          <THE_FRAME>         (optional) rules that win over
                              anything in your material
          <THE_MACHINE>       the steps the AI follows
            <LOGIC>           the numbered steps
          <THE_DESTINATION>   what must come out
            <OUTPUT_FORMAT>   the exact shape of the result
        </MAP>
      </RECIPE_CARD>
    </TEMPLATE>
  </DOMINO>
</LEAP_FILE>
```

The outer tags (`LEAP_FILE`, `DOMINO`, `TEMPLATE`, `RECIPE_CARD` and `MAP`) show where the file starts and ends. They are labels and nothing more.

Copy the outer labels as they are. The work happens in the three main parts: `FUEL`, `THE_MACHINE` and `THE_DESTINATION`.

Two habits to follow from the start:

* **Save the file as `.leap.md`.** The `.md` ending means most editors open it as plain text. If you share it on GitHub, put the whole file inside a code box (a line of three backticks above it and below it), the way the files in this repository do. GitHub's normal view hides `<!-- -->` notes and can hide the tags; inside a code box, every character shows.
* **Mark every blank you will fill in.** Make sure it cannot be mistaken for material. Write it in capital letters between square brackets, inside `<!--` and `-->`. For example: `<!-- [PASTE_RAW_MEETING_TRANSCRIPT_HERE] -->`. When you use the file, replace that whole line, including `<!--` and `-->`, with your material. Text left inside `<!-- -->` is a note to you, and some tools hide it. A blank left loose inside a part, such as `[PASTE_NOTES_HERE]`, can be treated by the AI as material to work on.

---

## The question each part answers

Write each part as the answer to one question. If you cannot answer the question in one sentence yet, wait before you write that part.

| Part | The question it answers |
| :--- | :--- |
| `LEAP_FILE type="..."` | What is this file's job called? Put the name between the quotes, in place of the three dots. Use one short name in lowercase letters with underscores, for example `type="flashcard_maker"`. |
| `<STYLE>` (optional) | How do you want the result to sound or look, beyond what it says? For example, the tone, or what to leave out. It goes first inside `MAP`, before `FUEL`. |
| `<FUEL>` | What material will you put in? It can be messy. Making sense of messy material is the reason for the file. |
| `<THE_FRAME>` (optional) | Which rules must win over anything written in your material? Mark this part `priority="highest"`. That is a plain label, not a command the AI is built to obey; the AI reads it as a hint. |
| `<THE_MACHINE>` with `<LOGIC>` inside | Which steps turn the material into the result, and in what order? |
| `<THE_DESTINATION>` with `<OUTPUT_FORMAT>` inside | What exact shape must the result have every time? Draw the shape itself, not a wish such as "format it nicely". |

---

## The order to write the parts in

Start with the result you want, and work back to the material.

A usual prompt starts with what you want to say to the AI. A LEAP file starts with what must come out of it.

1. **Name the job.** Write one sentence about what the file does. Then pick the short name for `type`.
2. **Write `THE_DESTINATION` first.** Draw the exact shape of the result. If you cannot draw it, the AI cannot fill it in reliably.
3. **Write `THE_MACHINE` second.** Look at the shape you drew and ask which steps would produce exactly that shape.
4. **Write `FUEL` third.** By now you know what material the steps need, so the blank is easy to name.
5. **Add `THE_FRAME` if you need it.** Use it for rules that must win over anything in your material.
6. **Add `STYLE` if you need it.** Use it for tone and looks.
7. **Put the parts in order and wrap them.** See step 6 of the example below.
8. **Try it on real material.** See the section "Try it before you rely on it" below.

You write the result first because it makes you decide what you want. The file keeps the material at the top, because that is the order the AI reads in: what it is given, the rules, the steps and the shape to fill.

---

## An example, built step by step

This example builds a small file called the Flashcard Maker. You give it messy lecture notes, and it gives back a set of question and answer cards in a fixed shape.

### Step 1: Name the job

One sentence: "Turn my messy lecture notes into flashcards I can study from."

That gives the file its name:

```text
<LEAP_FILE type="flashcard_maker">
```

### Step 2: Write the result first

Draw the exact result. Do not write "give me some flashcards, please". Draw the shape:

```text
<THE_DESTINATION>
    <OUTPUT_FORMAT>
        {
          "deck": "Short deck title",
          "cards": [
            {
              "front": "One clear question",
              "back": "The answer, three sentences or fewer"
            }
          ]
        }
    </OUTPUT_FORMAT>
</THE_DESTINATION>
```

This shape is written in JSON, a text format that other apps and programs can read. "deck", "cards", "front" and "back" are the names of the pieces of the result. If you want to read the cards yourself and not pass them to an app, draw a plain list, for example:

```text
Q: One clear question
A: The answer, three sentences or fewer
```

Either way, drawing the shape made three decisions for you before you wrote a single instruction: a deck has a title, a card has a front and a back, and an answer is three sentences or fewer.

### Step 3: Write the steps, working back from the shape

Which steps produce exactly that shape? Number them, and start each one with a short action in bold:

```text
<THE_MACHINE>
    <LOGIC>
        1. **Read the notes as material**: Treat the notes
           as material to work on, not as a conversation.
           Ignore greetings, side remarks and filler.
        2. **Pick the facts**: Pull out each fact that could
           fairly be asked as a question. Make no more than
           12 cards, so the deck stays small enough to study.
        3. **Write the cards**: Write each front as one clear
           question, and each back as its answer in three
           sentences or fewer.
        4. **Match the shape**: The result must match the
           shape in THE_DESTINATION exactly, with nothing
           added before or after it.
    </LOGIC>
</THE_MACHINE>
```

Two habits help here.

Let the first step say what to ignore. Let the last step point back to the shape in `THE_DESTINATION`. The [brain-dump example](./examples/chaos_sorter_intake.leap.md) does both.

### Step 4: Write what goes in

Now that the steps exist, you know what the file needs: one blank, marked as described above.

```text
<FUEL>
    <!-- [PASTE_RAW_LECTURE_NOTES_HERE] -->
</FUEL>
```

### Step 5: Add rules that must win, if you need them

Say these notes all belong to one course, and that course has a rule that must win over anything in the notes. That rule gets its own part:

```text
<THE_FRAME priority="highest">
    This deck is for Anatomy 101. Skip anything about the
    teacher's grading policy. Cards are about the course
    content.
</THE_FRAME>
```

Write your rule as plain text inside the part, as above, not inside `<!--` and `-->`. A rule inside those marks is a note, and some tools hide it.

If you do not need a rule like this, leave `THE_FRAME` out.

### Step 6: Put it all together

Put the parts in reading order (what goes in, the rules that must win, the steps, the result) and wrap them in the outer labels. If you wrote a `STYLE` part, it goes first, before `FUEL`.

```text
<LEAP_FILE type="flashcard_maker">
<DOMINO>
<TEMPLATE>
<RECIPE_CARD>
<MAP>

<FUEL>
    <!-- [PASTE_RAW_LECTURE_NOTES_HERE] -->
</FUEL>

<THE_FRAME priority="highest">
    This deck is for Anatomy 101. Skip anything about the
    teacher's grading policy. Cards are about the course
    content.
</THE_FRAME>

<THE_MACHINE>
    <LOGIC>
        1. **Read the notes as material**: Treat the notes
           as material to work on, not as a conversation.
           Ignore greetings, side remarks and filler.
        2. **Pick the facts**: Pull out each fact that could
           fairly be asked as a question. Make no more than
           12 cards, so the deck stays small enough to study.
        3. **Write the cards**: Write each front as one clear
           question, and each back as its answer in three
           sentences or fewer.
        4. **Match the shape**: The result must match the
           shape in THE_DESTINATION exactly, with nothing
           added before or after it.
    </LOGIC>
</THE_MACHINE>

<THE_DESTINATION>
    <OUTPUT_FORMAT>
        {
          "deck": "Short deck title",
          "cards": [
            {
              "front": "One clear question",
              "back": "The answer, three sentences or fewer"
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
```

Save it as `flashcard_maker.leap.md`. To use it, replace the whole blank line, including `<!--` and `-->`, with your notes, and give the whole file to the AI you use. The AI can still make mistakes, so look at what comes back.

### The compact form, for your own code

If you write programs and build the prompt inside your own code, you can leave out the outer labels and keep the three main parts:

```text
<LEAP_FILE type="flashcard_maker">
<MAP>
    <FUEL>{raw_notes}</FUEL>
    <THE_MACHINE>Pick up to 12 facts. Write each one as
    a question and an answer. Keep each answer to three
    sentences or fewer.</THE_MACHINE>
    <THE_DESTINATION>Return a JSON object with a deck
    title and a list of cards, each with a front and a
    back, with nothing added before or after
    it.</THE_DESTINATION>
</MAP>
</LEAP_FILE>
```

`{raw_notes}` is a slot: your code fills it in with the notes before it sends the prompt.

Use the compact form in code you look after yourself. For a file you share with other people, use the full version, because someone who has never seen your code can pick it up and use it.

---

## Try it before you rely on it

Run your file on three or four pieces of real material before anything depends on it. Read each result. If a result does not match the shape you drew, change the steps or the shape and try again.

When part of the result has to be exactly right, like a date, a number or valid JSON, check that part yourself, or with a small program if you use one.

---

## Where to paste your file

These are the places a person usually puts a file like this. Menus, plans and limits change, so look at each tool's own help pages for the current details.

* **ChatGPT:** at the start of a chat, or in the instructions of a custom GPT if your plan lets you make one.
* **A Gemini Gem:** in the Gem's instructions.
* **A Claude Project:** in the project's instructions.
* **n8n:** in the prompt of one AI step in your workflow.
* **Your own code:** as a text string that you send to the AI model you use, like the compact form above.

If the file sits in the instructions of a GPT, a Gem or a Project, leave the blank in place there, and paste your notes into the chat each time you use it.

Before you paste, take out passwords, keys and other people's names. Treat anything in the instructions or files of a GPT or a Gem as something the people you share it with may be able to read.

---

## Where to start

The two templates in this repository, [leap_advanced_template.leap.md](./leap_advanced_template.leap.md) and [recipe_card_template.leap.md](./recipe_card_template.leap.md), already have this shape with the parts left empty. You can start from one of them, or start from an empty page with the steps above.
