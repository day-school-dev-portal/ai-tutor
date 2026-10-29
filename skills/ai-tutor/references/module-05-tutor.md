# Module 5 — how to tutor it

Hand-written. The module's own words are in `module-05.md`, generated from the website; this
file is how to run them as a conversation.

## The shape: one window, and you are not in it

Module 5 is the first module of Sequence 2 and the first that happens almost entirely somewhere
you cannot see — **Terminal.app**, with the Claude app beside it. There is no project folder,
nothing gets built, and nothing needs publishing. The learner types, reads what comes back, and
pastes it to you when it surprises them.

| Part | Exercises | Where | What you can do there |
|---|---|---|---|
| **Do it before you understand it** | the opening question, 5.1 | Terminal, then Finder | wait; read what they paste |
| **Where am I, what's here** | 5.2 to 5.6 | Terminal and Finder together | read their `pwd` and `ls` output, and tell them what it means |
| **Programs and extensions** | 5.7, 5.8 | Terminal | same |
| **Making things** | 5.9, 5.10 | Terminal, checked in Finder | same |
| **Taking the first line apart** | section 6 | conversation | this is the payoff; it's all explanation |

**A chat is the right place for this module.** If you're in a Claude Code session instead, that
is fine, but it brings one serious temptation, below.

**Never run these commands yourself.** You can. `pwd`, `ls`, `mkdir ~/Desktop/my-first-folder` —
all of it is one tool call away, and every one of them would delete the module. The entire point
is that *they* typed something and their own computer answered. If they ask you to just do it,
say why in one line and give the command to paste. (In a sandboxed session `open` won't work for
you anyway, which is a convenient way to say the same thing.)

What you *should* do with what they paste: read it back. A learner who pastes
`/Users/rwong/Desktop` and gets "that's your Desktop, two folders down from the root — `Users`,
then `rwong`, then `Desktop`" is getting the thing the page can't give them.

## Working out where they are

There is no folder to inspect, so ask — but ask about results, not about progress:

- "What did `pwd` print?" tells you whether they're at 5.2 and whether they're lost.
- "Is `hello-terminal` still on your desktop?" tells you whether 5.1 happened.
- "Does your Finder window have a strip along the bottom?" tells you whether 5.5 happened.

If they say "continue" and can't remember, start at 5.4 — the walk. It re-establishes everything
earlier and costs five minutes.

## Part A, step by step

**Opening.** Two short messages. The held question: *"You open your computer and look at your
desktop. You click the word doc you've been working on and it opens. What is actually happening
inside your computer?"* Hold it, don't answer it.

Say the two things aside 1 says, because they set the whole tone and they lower the stakes:
**they are not going to become a person who lives in the terminal**, and Sequence 1 was already
enough if documents in folders is all they want. What this hour buys is not being *surprised*
when Claude says *run this* — knowing where they're standing, what it's about to touch, and
roughly what it will do. **Tell them not to memorize anything.**

**5.1 — do it before you understand it.** The six-line paste. Three things to say before they run
it, and none after:

- The prompt symbol on their Mac is `%`; the page writes `$`; **neither is ever typed**, and
  Copy leaves it out. This confuses more people than anything else in the module.
- They are not expected to understand a word of it. That's the design.
- A Finder window will open by itself. Go into all three folders and open all three files.

Then the reveal, and keep its last line whole: **the terminal is not a different computer. It is
a different way of talking to the same one.** Promise the ending — every word of that paste gets
taken apart in section 6 — and move on. Don't explain `mkdir -p` now; you'll spend the payoff.

**Core vocabulary.** Mention once that twelve terms are there if they want them, and that they'll
meet each one by doing something. Don't read them out.

**Section 2, briefly.** The UI is a picture; the terminal is a more direct interface onto the
same machine. Two or three sentences. Then 5.2.

**5.2 — `pwd`.** Have them **type** it rather than paste — the page says so, and typing three
letters is the point. Read their answer back as a path: the folder with their name on it, inside
`Users`. Name the words as they arrive: **directory**, **working directory**, **path**, **home
directory**.

**5.3 — `ls`.** Then the line that does the work: *your UI shows documents in folders; your
terminal shows files in directories.* **Nothing was converted or translated.** Offer the hidden
files aside only if they ask why Finder shows fewer things.

**5.4 — the walk.** Six steps, and they come back between each one. Do not give all six at once,
however much it looks like a list: the rhythm *is* the lesson, because `cd` prints nothing and
`pwd` is what proves it moved. If they run ahead and paste the lot, that's fine — go back and ask
what `cd Desktop` printed, and let them notice it printed nothing.

The three questions are the thing to land, and they're worth saying as a set at the end:
**`pwd` — where am I? `cd` — where I want to go. `ls` — what is here?** Then: when they get lost
later, and they will, the way out is `pwd`, then `ls`, then decide.

Finish with the hand-built path: their `pwd` output, a slash, a filename from their own `ls`.
They assembled a full path out of two things on their screen.

**5.5 — Option-copy.** Finder's path bar on (*View → Show Path Bar*), then right-click, hold ⌥,
*Copy "name" as Pathname*. They paste it to you. **Compare it against the path they built in
5.4** — that comparison is the exercise, so ask for both.

The reveal is the module's best moment: Finder handed them *the same text, character for
character*. Then why it matters: from here on they constantly need to tell a program, or you,
exactly which file they mean. "The spreadsheet on my desktop" is ambiguous;
`/Users/name/Desktop/roster.csv` is not.

**Careful here.** They are about to paste a path into a chat, and a path contains a filename. If
they've picked something with a child's or a family's name in it, ask for a different file
before they paste it, not after. SKILL.md rule 8 — the name alone is the data.

**5.6 — ⌘⇧G.** The reverse trick. `/Users`, then one of their own paths, then `~/Desktop`. Short.

**5.7 — extensions.** One question, one answer. The sentence to keep: Finder hides extensions to
look tidy, `ls` always shows the full name — **that is the terminal telling you the truth about
your computer.**

**5.8 — `cat`.** They need a `.txt` file; one from 5.1 will do. Then the reveal, which is the
conceptual heart of the section: `cat` **is** a program, and typing `cat notes.txt` is running a
program and handing it a file — *which is exactly what a double-click does. The double-click just
picks the program for you.* Encourage the `cat` on a PDF; a screenful of nonsense is the right
result and Control-C gets out.

**5.9 and 5.10 — making things.** `mkdir`, then `touch`. Both times: **go and look at the actual
desktop.** Then the two keepers: `~` works from anywhere, and **silence in the terminal usually
means success** — unnerving for about a week.

## Section 6 — the payoff

This is the module's ending and it deserves real time. Go back to the six lines from 5.1 and take
them apart in order, letting them tell you the ones they already know. By now they own `cd`, `~`,
`mkdir`, `ls`. You supply four things:

- `-p` — make any folders needed along the way, which is how one command made four folders.
- `echo` — print whatever you're given.
- `>` — **put it in this file instead of printing it to the screen**, creating the file if it
  isn't there. That one character is how a command's output becomes something you can keep.
- `;` — *and then*, which is why six lines ran from one paste.
- `open` — a program like `cat`, whose job is to hand something to the Mac and let the Mac
  decide. Hand it a folder, get a Finder window.

Then the line that closes it: **forty minutes ago it was noise.**

**Tidying up.** Drag both folders to the trash. Say what aside 4 says and don't improve on it:
there is a command for deleting things, this module isn't teaching it, it doesn't ask "are you
sure?", and there is no trash to fish things out of. If they ask what it is, name `rm` and say
it's the one command worth being slow with — then move on.

## Section 7 — working with you

The last section is about the thing they'll actually do forever: describe what they want, get a
command, paste it, press return. Two prompts on the page are for you, so answer them properly
when they come:

- The `school-data` folder one. Give the commands, explain each part, and make them run it and
  **check the result in Finder.** That habit — *every time your AI changes something, go and look
  at it* — is the one to name out loud.
- The "explain this command piece by piece" one. When they bring you a line, say what it does
  **and whether it changes or deletes anything.** Aside 5 is the rule of thumb: a command that
  only reads (`pwd`, `ls`, `cat`) can't hurt anything; one that writes or deletes can. Tell them
  that's a fair question to ask every time.

## The ending

1. The held question, word for word. Let them answer; it will be a much longer answer than an
   hour ago, and that's the point of asking twice.
2. Their task list (nine), read back in plain words.
3. Then what the page says to notice: what still feels unclear is the most useful thing they
   could ask in the next five minutes.
4. Next: Module 6, *Coding with AI* — borrowing a library somebody else wrote, so they can make
   things that would be impossible by hand.

## What goes wrong, and what to do

The page's table (section 8) covers the common errors. What it doesn't:

- **They ask you to run it.** The temptation of this whole module. One line of why, then the
  command to paste.
- **They typed the `%` or the `$`.** Invisible to you; if a command "isn't found", ask them to
  read the whole line back exactly as they typed it.
- **Smart quotes.** Copying from somewhere that curls quotation marks breaks `echo "…"`. If a
  line fails with an unexpected error, ask them to use the page's Copy button rather than
  selecting the text.
- **They're in the wrong directory and everything fails.** `pwd`, then `ls`, then decide. Say it
  every time rather than diagnosing it for them — that's the habit the module is building.
- **`Permission denied`, and they've found `sudo` online.** Don't. `cd ~` and start again, and
  ask what's going on. The page says this and it's worth repeating firmly.
- **They want to delete something with a command.** Not today. The trash works.
- **They get interested and want more commands.** Good sign, wrong module. Point them at asking
  you for a command whenever they want one — that's section 7 — and at Module 6 for the thing
  commands are *for*.
- **Windows.** This module is genuinely Mac-specific in its details. PowerShell: `pwd` and `ls`
  work, `cd` works, `mkdir` works, `touch` doesn't (use `New-Item`), `cat` works, `open` is
  `Invoke-Item` or `start`, and the path separator is `\`. Finder's Option-copy is
  Shift-right-click → *Copy as path*, and ⌘⇧G is typing the path into the address bar. Say
  plainly when you're unsure which their version does.
