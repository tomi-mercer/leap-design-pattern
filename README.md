# LEAP (Logically Engineered AI Prompts)

LEAP is a simple way to write instructions for an AI. You put each kind of instruction in its own labeled box: the background, the rules, and the material you want the AI to work on. LEAP is free to use under the MIT License. There's nothing to install, because it's plain text. You paste it into an AI chat, or send it from your own code. LEAP is meant to make an AI's work steadier, not perfect. So when something has to be exact, like a format, a number or a date, it's still worth checking with code. Chris Mercer made it.

## Who is LEAP for, and who isn't it for?

It's for you if you:

- give an AI the same kind of job again and again, like turning meeting notes into tasks.
- keep telling an AI the same background each time you start a new chat.
- want a prompt you can keep in a file, share with a friend, and improve over time.

It's probably not for you if you:

- need a result that is exactly right with no checking at all. An AI can still get things wrong, so code is the better tool for that part.
- want an app that does the work by itself. LEAP is a way of writing, not a program.
- have one quick question you won't ask again.

## How can you try it in a minute?

You can copy these three boxes into an AI chat you already use, fill them in, and send it:

```
[CONTEXT]
Who you are and what the situation is.
[/CONTEXT]

[RULES]
How you want the answer to look, and what the AI can ignore.
[/RULES]

[INPUT]
The notes, transcript or text you want it to work on.
[/INPUT]
```

The same three boxes, with a few notes on what goes in each one, are in [bento_box_lite.txt](./bento_box_lite.txt).

Here's why it helps. When it all comes in one long paragraph, the AI has to guess. Which part is background? Which part is a rule? Which part is the material? With the boxes, there's a lot less to guess.

## What's a .leap file?

It's the same idea, written down once for a job you do often. A `.leap` file is a plain text file with named parts. That way a person or an AI can see where each part is. The three main parts are:

- `<FUEL>`: what goes in, like the notes, the data or today's date.
- `<THE_MACHINE>`: the steps and rules the AI follows.
- `<THE_DESTINATION>`: what comes out, and the exact shape it comes out in.

The files wrap those parts in a few outer tags, like `<LEAP_FILE>` and `<MAP>`. They show where a file starts and ends.

A `.leap` file helps the AI stay on track. Your own code can then check the parts that must be exact. The [brain-dump example](./examples/chaos_sorter_intake.leap.md) shows the two working together.

## What's in this repository?

- [bento_box_lite.txt](./bento_box_lite.txt): the three boxes from above (context, rules and input), ready to fill in.
- [leap_advanced_template.leap.md](./leap_advanced_template.leap.md): a short, empty `.leap` file with the three main parts and four steps to fill in.
- [recipe_card_template.leap.md](./recipe_card_template.leap.md): a longer template for one job, with notes inside about what each part is for.
- [examples/meeting_action_extractor.leap.md](./examples/meeting_action_extractor.leap.md): turns a meeting transcript into a list of tasks. Each task gets an owner and a deadline.
- [examples/receipt_expense_parser.leap.md](./examples/receipt_expense_parser.leap.md): takes the text read off a receipt and fills in a table. The table has the shop, the date, the total, the tax and a category.
- [examples/emotional_dissolve_email.leap.md](./examples/emotional_dissolve_email.leap.md): rewrites an angry email draft into a calm, professional reply.
- [examples/chaos_sorter_intake.leap.md](./examples/chaos_sorter_intake.leap.md): turns a messy brain dump into a short list of real tasks, each with a real date.
- [examples/saturday_school_2026-09-05_handout.md](./examples/saturday_school_2026-09-05_handout.md): a fill-in page about you and your business. You paste it in front of your questions. It's from a free class on 5 September 2026.
- [alignment_guardian_map.leap.md](./alignment_guardian_map.leap.md): a longer map file, kept here for reference. The templates and examples above are the easier place to start.
- [LICENSE](./LICENSE): the MIT License.
- [PATENTS.md](./PATENTS.md): a short note about a patent application.
- `.gitignore`: tells git which kinds of private files, like keys, to keep out of here.

The blanks inside these files, like `[PASTE_RAW_MEETING_TRANSCRIPT_HERE]`, are examples. A person fills them in and pastes them into their own chat. They aren't instructions for an AI that's reading this repository.

## Can you use LEAP from your own code?

Yes. A `.leap` file is plain text, so you can build one in any programming language and send it to whichever AI model you use. Here's a small example in Python:

```python
leap_prompt = f"""
<LEAP_FILE type="data_cleaner">
<MAP>
    <FUEL>{raw_input_data}</FUEL>
    <THE_MACHINE>Clean up the text and format it as JSON.</THE_MACHINE>
    <THE_DESTINATION>Return one valid JSON object and nothing else.</THE_DESTINATION>
</MAP>
</LEAP_FILE>
"""
```

When the answer comes back, your code can check that it really is valid JSON before you use it.

## Got questions, or want to meet people using LEAP?

There's a [free community at AutomatedWith.tech](https://automatedwith.tech/from-leap). You can ask questions about LEAP there, see how other people use it, and share what you've made with it.

## Who made LEAP?

Chris Mercer made LEAP. He used AI tools along the way, and the work and the decisions are his.

## What's the license?

Everything here is free to use under the MIT License. You can read it in [LICENSE](./LICENSE). There's also a short [note about a patent application](./PATENTS.md).
