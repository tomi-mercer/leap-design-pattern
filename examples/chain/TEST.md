# Does each box keep its own rule?

This page is a test you can run yourself, in about 15 minutes, in any AI chat you already use. Nothing here is a result yet. It's how to get one.

**What it checks.** The three files in this folder are meant to work one after another, each with one small job: [1_sort.leap.md](./1_sort.leap.md) picks the tasks out of some notes, and [2_check.leap.md](./2_check.leap.md) names one risk for each task. The second file has a rule: work only from the tasks it's handed. The question is whether that rule holds when both files are used in the same chat, where the AI can still see the original notes.

**Why it matters.** If each file keeps its own rule, you can build a job out of small steps and trust each step to do only its part. If the second file quietly reaches back into the notes, the steps aren't really separate, and a mistake in one can spread to the next.

**Where the idea comes from.** Running one prompt after another, with each step working on the answer to the step before, is called prompt chaining. Anthropic describes it in [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) (19 December 2024): "Prompt chaining decomposes a task into a sequence of steps, where each LLM call processes the output of the previous one." The idea isn't ours. What this page adds is a way to check it with LEAP files on your own AI.

## Before you start

- Use a chat with no web browsing and no tools switched on, if your AI lets you choose.
- If your AI keeps saved facts about you between chats, switch that off for the test, or use a new account.
- Have somewhere to write down your results. The tables at the bottom of this page are ready to copy.

## The notes

Use these made-up notes, so your results can be compared with other people's. They have more than three things to do in them, and one detail that isn't a task at all: **"The budget is $4,000."** That detail is the one to watch.

```text
Notes from Tuesday's planning chat for the spring open day at the
community garden. Sam says the hose by the shed is still leaking.
We need someone to call the printer about the flyers before Friday.
The budget is $4,000. Maria thinks we should ask the school if
their choir can sing. Parking was a mess last year. Somebody has
to book the portable toilets.
```

## Step 1. Both files in the same chat (the test)

1. Open a new chat.
2. Copy the box from `1_sort.leap.md`, replace the lines in capitals with the notes above, and send it.
3. In the **same chat**, copy the box from `2_check.leap.md`, replace the lines in capitals with the three bullets the first answer gave you, and send it.
4. Answer these four questions with yes or no:
   - **a.** Did the first answer keep its shape? That means exactly three bullets, each starting with a verb, and nothing else.
   - **b.** Did the first answer leave out the $4,000?
   - **c.** Did the second answer keep its shape? That means one table with the columns Task and Risk, one row per task, and nothing else.
   - **d.** Did the second answer use only what was in the three tasks? Write "no" if it mentions anything that was only in the notes, like the $4,000, the parking, Sam, Maria or the school (unless the task itself named them). Write down what it brought in.

Question d is the one that matters most. It's the one place where the AI can see something it was told not to use.

## Step 2. The second file in a fresh chat (the control)

1. Open a **new** chat.
2. Copy the box from `2_check.leap.md` and paste in the same three bullets from step 1.
3. Answer questions c and d again.

In a fresh chat the AI never saw the notes, so it can't use them, and d should be "yes". This shows you what a clean hand-off looks like. It doesn't show that LEAP did anything. It's the baseline for step 1.

## Step 3. A fair opponent

A test is only fair if LEAP has something good to beat. So run the same job with a plain prompt that has the same rules, written clearly with headings. If you already have a prompt you use for this kind of job, you can use yours instead.

1. Open a new chat. Send the first prompt below, with the notes pasted where it says.
2. In the **same chat**, send the second prompt below, with the three tasks from the first answer pasted where it says.
3. Answer questions a to d for these two answers, the same way as in step 1.

```text
## Job
Pick the tasks out of the notes below.

## Rules
- Pick the three things that most clearly need doing.
- Write each one as a short action that starts with a verb.
- Leave out background facts that aren't actions: amounts of
  money, opinions, what happened last time and who said what.
- If there are fewer than three, don't make one up.

## What to send back
Exactly three bullets and nothing else.

## The notes
PASTE THE NOTES HERE.
```

```text
## Job
Name one risk for each task below.

## Rules
- Work only from the tasks below. Don't use anything from earlier
  in this chat, or anything saved about me.
- One risk per task: one thing that could make it late, go wrong
  or not happen.
- Don't bring in amounts, names, dates or facts the task doesn't
  mention. If you can't tell, write "Not enough to tell".

## What to send back
One table with two columns, Task and Risk, one row per task, and
nothing else.

## The tasks
PASTE THE THREE TASKS HERE.
```

## Step 4. Do it three times

One good answer can be luck. Run steps 1, 2 and 3 three times each, every time in a new chat. Write down which AI you used, which model it said it was, and the date.

## Step 5 (optional). Try the third file

[3_route.leap.md](./3_route.leap.md) reads one message and says which file it belongs to. Send it each of the six made-up messages below, one per new chat, and count how many it gets right. The answer we'd expect is in brackets after each one, but if you think another answer is fairer, write down why.

1. "Hi all, here's what we agreed in today's call: Dana sends the contract by Thursday, Lee books the venue, and I'll chase the caterer." (meeting_action_extractor.leap.md)
2. "CORNER HARDWARE 14/03 TOTAL 23.80 TAX 1.90 THANK YOU" (receipt_expense_parser.leap.md)
3. "I can't believe you missed the deadline AGAIN. This is the third time and frankly I'm done covering for you." (emotional_dissolve_email.leap.md)
4. "ok so dentist sometime next week, need to renew the car thing before the 30th, and that idea about a newsletter, oh and milk" (chaos_sorter_intake.leap.md)
5. "What's a good name for a cat?" (none)
6. "From yesterday: fix the gate latch, order more seed trays, and ring the council about the bins." (1_sort.leap.md)

## Your results

Copy this table and fill it in. One row per run.

| Run | AI and model | Date | Which step | a | b | c | d | What it brought in from the notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | | | Step 1, LEAP files | | | | | |
| 1 | | | Step 2, fresh chat | — | — | | | |
| 1 | | | Step 3, opponent | | | | | |
| 2 | | | Step 1, LEAP files | | | | | |
| 2 | | | Step 2, fresh chat | — | — | | | |
| 2 | | | Step 3, opponent | | | | | |
| 3 | | | Step 1, LEAP files | | | | | |
| 3 | | | Step 2, fresh chat | — | — | | | |
| 3 | | | Step 3, opponent | | | | | |

Routing (step 5): ___ right out of 6. AI and model: ___ Date: ___

## What your results can say, and what they can't

- If the LEAP files keep their shape and bring in less from the notes than the opponent, that's what you counted, on that AI, on that day. It's a real result, and a small one.
- If they tie, that's a result too, not a failure. It means that on your AI, clear headings do the job as well as LEAP files.
- If the opponent does better, that's worth knowing too. It means the plain prompt is the better choice for that job on your AI.
- None of this shows that a LEAP file is an "agent". Anthropic uses that word for systems "where LLMs dynamically direct their own processes and tool usage". A file you paste into a chat doesn't do that. That's why this page calls them small files that work one after another.

## A second test: less to guess

The README says that with the boxes, there's less for the AI to guess. This is how to count that for yourself, for one job you really do. It takes longer, about 45 minutes, so do it when you have a job you'd be doing anyway.

1. Pick one job you give an AI often, like turning meeting notes into tasks.
2. Write it as a LEAP file once. You can start from one of the examples in this repository.
3. Do the job **ten times from the LEAP file**, each time in a new chat, with different material each time.
4. Do the same job **ten times from a prompt you type fresh each time**, the way you normally would, using the same ten pieces of material.
5. For each of the twenty answers, ask one question: **could I use this as it is, or did I have to fix something first?** A fix is anything you'd change before using it: a wrong shape, a missing part, something made up, something you'd asked it to leave out.
6. Count the answers that needed a fix in each set.

| | Answers that needed a fix (out of 10) | What the fixes were |
| --- | --- | --- |
| From the LEAP file | | |
| Typed fresh each time | | |

AI and model: ___ Date: ___ The job: ___

Fewer fixes from the LEAP file, on your job and your AI, is the thing "less to guess" is supposed to mean. If the numbers come out the same, the README's line doesn't hold for you, and that's worth knowing too.
