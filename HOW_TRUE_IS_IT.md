# How true is each claim?

This page goes through what the [README](./README.md) says, one claim at a time. For each one it says how sure we are and how you, or your own AI, can check it. Some claims you can check in a minute. Some haven't been shown yet, and for those the page names the test. A claim with nothing behind it doesn't get a row: it gets taken out of the README.

**How to read the middle column.** We use the same few phrases all the way down:

| What the page says | What it means |
| --- | --- |
| You can check it yourself | Open the file or link named in the last column and you'll see it. |
| We counted it | We ran a test that anyone can run, and wrote down the numbers. (Nothing on this page is in this group yet.) |
| Seen, not counted | We've seen it happen, but we haven't counted how often. |
| This is advice | It's a suggestion or a judgement, not a fact that can be tested. |
| Not shown yet | It may be true, but nothing here proves it. The last column names the test. |
| We said it before. It's wrong. | We used to say it. We've changed it. |

This page was written against the README as it stood in November 2026. If the two ever disagree, the README has changed and this page needs to catch up.

## What LEAP is

| The claim | How sure we are | How to check it |
| --- | --- | --- |
| LEAP is a simple way to write instructions for an AI, with each kind of instruction in its own labelled box. | You can check it yourself | Open [bento_box_lite.txt](./bento_box_lite.txt) or any `.leap.md` file and look at the boxes. Whether it's "simple" is for you to judge. |
| It's free to use under the MIT License. | You can check it yourself | Open [LICENSE](./LICENSE). |
| There's nothing to install, because it's plain text. | You can check it yourself | Open any file. There's no program in this repository, only text. |
| You can paste it into an AI chat, or send it from your own code. | You can check it yourself | Paste one into any chat. For code, see the small Python example in the README. |
| It's meant to make an AI's work steadier, not perfect. | Not shown yet | "Meant to" is honest about the aim. Whether it's steadier for you is what the second test in [examples/chain/TEST.md](./examples/chain/TEST.md) counts: ten answers from a LEAP file against ten from a prompt typed fresh each time. |
| When something has to be exact, like a format, a number or a date, it's still worth checking with code. | This is advice | It's widely given advice. AI models can get things wrong, and a few lines of code can check a format or a number every time. |
| Chris Mercer made it. | You can check it yourself | Look at the list of changes (the commit history) on GitHub. Every change is by him. The copyright line in [LICENSE](./LICENSE) names Tomitrader LLC. |

## Who it's for, and who it isn't

| The claim | How sure we are | How to check it |
| --- | --- | --- |
| It's for you if you give an AI the same kind of job again and again, keep repeating the same background, or want a prompt you can keep in a file, share and improve. | This is advice | It's our judgement of who gets the most out of it. A file you keep is easy to reuse and share; that part you can check by saving one. |
| It's probably not for you if you need a result that's exactly right with no checking at all. | This is advice | AI models can still make mistakes, whatever the prompt looks like. |
| It's probably not for you if you want an app that does the work by itself. LEAP is a way of writing, not a program. | You can check it yourself | There's no program in this repository. Nothing here runs until a person pastes it somewhere. |
| It's probably not for you if you have one quick question you won't ask again. | This is advice | Writing a file only pays off if you use it more than once. |

## Trying it, and why the boxes help

| The claim | How sure we are | How to check it |
| --- | --- | --- |
| The same three boxes, with notes on what goes in each, are in bento_box_lite.txt. | You can check it yourself | Open [bento_box_lite.txt](./bento_box_lite.txt). |
| When it all comes in one long paragraph, the AI has to guess which part is background, which is a rule and which is the material. With the boxes, there's a lot less to guess. | Not shown yet | The first half matches what the AI makers themselves advise: [Anthropic](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) and [OpenAI](https://developers.openai.com/api/docs/guides/prompt-engineering) both suggest marking the parts of a prompt with tags or headings. "A lot less" hasn't been counted. The second test in [examples/chain/TEST.md](./examples/chain/TEST.md) is how to count it for your own job. |

## What a .leap file is

| The claim | How sure we are | How to check it |
| --- | --- | --- |
| A `.leap` file is a plain text file with named parts: `<FUEL>` (what goes in), `<THE_MACHINE>` (the steps and rules) and `<THE_DESTINATION>` (what comes out, and its exact shape). | You can check it yourself | Open any file in [examples](./examples/). |
| The files wrap those parts in a few outer tags, like `<LEAP_FILE>` and `<MAP>`. | You can check it yourself | Open any `.leap.md` file. Some of the older files have a few more outer tags than these two. |
| A `.leap` file helps the AI stay on track. | Not shown yet | The test in [examples/chain/TEST.md](./examples/chain/TEST.md) checks one part of this: whether each file keeps its own rule when two are used in the same chat, against a well-written plain prompt with the same rules. |
| Your own code can then check the parts that must be exact, and the brain-dump example shows the two working together. | Partly | The first half you can check: any code can test whether an answer has the right shape. The [brain-dump example](./examples/chaos_sorter_intake.leap.md) explains in words how your code would check the result, but it has no code in it. |

## What's in this repository

| The claim | How sure we are | How to check it |
| --- | --- | --- |
| Each file in the README's list does what its line says (the templates, the meeting, receipt, email and brain-dump examples, the licence and the patent note). | You can check it yourself | Open each one from the README's list. For example, the [meeting example](./examples/meeting_action_extractor.leap.md) asks for an owner and a deadline for every task, and the [receipt example](./examples/receipt_expense_parser.leap.md) asks for the shop, date, total, tax and category. |
| The fill-in page is from the free Saturday class on 5 September 2026. | Seen, not counted | The date is in the file's name. This is our own record of when it was used. |
| `.gitignore` tells git which kinds of private files, like keys, to keep out. | You can check it yourself | Open `.gitignore`. |
| The blanks inside the files are examples for a person to fill in. They aren't instructions for an AI that's reading the repository. | This is how we mean them | Every `.leap.md` file starts with a line telling a person to copy the box and replace the lines in capitals. Before new files go up, we give an AI only this repository's address and check that it describes the files instead of starting to run one. |

## Using LEAP from your own code

| The claim | How sure we are | How to check it |
| --- | --- | --- |
| A `.leap` file is plain text, so you can build one in any programming language and send it to whichever AI model you use. | You can check it yourself | Any language that can build a string of text can build one. The README has a short Python example. |
| When the answer comes back, your code can check that it really is valid JSON before you use it. | You can check it yourself | Most languages can test whether text is valid JSON in a line or two. In Python, for example, `json.loads` raises an error if it isn't. |

## Help, and who made LEAP

| The claim | How sure we are | How to check it |
| --- | --- | --- |
| There's a free community at AutomatedWith.tech, a free class most Saturdays, and a free 20-minute call with Mercer. | You can check it yourself | Open the three links in the README's help section. The class page shows which Saturdays it runs. |
| At AutomatedWith.tech, Mercer helps business owners set up AI for the work they repeat every week. | You can check it yourself | Open [automatedwith.tech](https://automatedwith.tech). |
| He used AI tools along the way, and the work and the decisions are his. | This is Mercer's own account | The commit history lists him as the only author of every change. |

## Something the README doesn't claim

**Labelled boxes aren't LEAP's own idea.** Both [Anthropic](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) and [OpenAI](https://developers.openai.com/api/docs/guides/prompt-engineering) advise separating a prompt's parts with tags or headings. What LEAP adds is a written-down, plain-text file for one job, that anyone can keep, share and paste into any AI.

**A LEAP file isn't an "agent".** The [chain of small files](./examples/chain/TEST.md) works one step after another, but each file only does something when a person pastes it into a chat. Whether each one keeps its own rule is not shown yet; that page is the test.

## Words we've taken back

| What we said before | How sure we are now | How to check it |
| --- | --- | --- |
| That LEAP makes an AI give exactly the same answer every time. | We said it before. It's wrong. | The README now says "steadier, not perfect". An AI can give a different answer to the same prompt. |
| Older notes in two files made security and privacy claims. | We said it before. We've taken it back. Nothing here tested them, so they have been taken out. | The files' history on GitHub shows the change. |
