# Module 6 — how to tutor it

Hand-written. The module's own words are in `module-06.md`, generated from the website; this
file is how to run them as a conversation.

## The shape: half of it is waiting

Module 6 is ninety minutes and the page is honest that half of that is watching things install.
It runs in the terminal, in Finder, and — for one exercise — in a Claude Code session in
`~/Projects/worksheets`.

| Part | Exercises | Where | What you can do there |
|---|---|---|---|
| **The thing at the end** | the held question, 6.1 | a PDF viewer | nothing; wait |
| **The failure** | 6.2 | Terminal | read the error they paste, and name it |
| **Installing** | 6.3 to 6.7 | Terminal, with their Mac password | explain each step, read output, keep them calm |
| **The payoff** | 6.8 | Terminal, then Finder | **read the generated PDF and the script** |
| **Making it theirs** | 6.9, 6.10 | a text editor, then Claude Code | you do 6.10's edit as ordinary Claude Code |

**Never run the installs.** Homebrew, `brew install python`, the venv, `pip install` — you could
run all of them. Don't. Everything after today depends on those being on *their* machine, in
*their* shell, with their PATH set up, and on them having watched it happen. If a session of
yours installed it, their next terminal window won't have it.

**The password.** 6.3 asks for their Mac login password. They type it into their own terminal and
nowhere else. Never ask for it, never offer to handle it, and don't let them paste it to you. The
thing to tell them: **nothing appears as you type** — not dots, nothing — and it isn't frozen.

## Working out where they are

Ask for the state of two things: the prompt, and the folder.

- "Does your prompt start with `(.venv)`?" → 6.7 happened.
- "What does `brew --version` say?" → 6.3 and 6.4 happened.
- In a Code session in `~/Projects/worksheets`: `make_worksheets.py` and `students.csv` present →
  6.2 reached; `worksheets.pdf` present → 6.8 done; a `.venv/` directory → 6.7 done.

If they're returning after a day, start with the thing that will bite them first: **a venv is
switched off when the terminal closes.** `cd ~/Projects/worksheets`, then
`source .venv/bin/activate`, then look for `(.venv)`.

## Part A, step by step

**Opening.** Two short messages. The held question is unusual — it asks them to hold a *thing*,
not an answer: *"Think of something in your job you have never even considered automating — not
because it is tedious, but because it seemed impossible."* Ask them to hold it. At the end they
go and ask whether a library already exists for the hard part of it.

Say the ceiling this module lifts: Module 2's "use only the standard library" was deliberate, and
everything they've built was made of parts their Mac happened to come with.

**6.1 — look at the end first.** They download and open
`https://dev-portal-byauh7qecq-ue.a.run.app/worksheets-sample.pdf`, look at two pages, then
page 43. Wait for them to come back having compared two sheets.

Then the reveal, and the sentence that carries the module: **nobody could make this by hand.**
Forty-two different worksheets is a lost weekend; forty-two *with a correct answer key* is not
possible, because you'd have to do all 840 sums yourself and you'd get some wrong. *The letters
in Module 2 were tedious by hand. This is impossible by hand.*

**6.2 — watch it fail.** Folder `~/Projects/worksheets`, both files downloaded into it
(`make_worksheets.py`, `students.csv` — same site address), then `cd` and run. **Tell them it is
going to fail and that this is the exercise**; a failure they expected is a different experience
from one that frightens them.

When they paste `ModuleNotFoundError: No module named 'reportlab'`, read it back as a sentence
and land the reveal: **nothing is broken.** The program asked for somebody else's work — a
**dependency** — and it isn't there. *Not a bug. A shopping list.* Tell them this is the most
common error in the whole series and they now know what it means every time.

Have the developer-tools box ready (aside 1), same as Module 2.

**Section 3 — three programs, three jobs.** Give the table in words before any installing, because
it's the thing that stops the confusion rather than fixing it afterwards: **Homebrew installs
programs, pip installs libraries, and they are not interchangeable.** `brew install reportlab`
won't work; `pip install python` is nonsense; everyone tries one of them.

## Part B — installing

**6.3 — Homebrew.** The one-line paste. Tell them what will happen before it does: it explains
itself and waits for a return, it asks for their password (nothing appears), it takes several
minutes. Then wait with them. This is a good moment for their held question, or for whatever they
want to ask — don't fill it with more module.

**6.4 — Next steps, and PATH.** Insist on this one. Homebrew prints two or three commands under
**Next steps** and they must run *the ones their own installer printed*, not the page's, though
they usually match. Then `brew --version` to check.

The reveal is one of the most useful ideas in the series, so give it properly: when they type a
word, the terminal looks for a program by that name **in a short list of folders called PATH**.
Homebrew put itself somewhere not on that list, so `brew` would be "command not found" with the
program sitting right there on the disk. Those lines add it, and `.zprofile` makes it happen in
every future window. *If they skipped them, nothing is damaged — run them now.*

**6.5 — a Python of their own.** `brew install python`, then `python3 --version`. Why: the Mac's
Python belongs to Apple, is usually years old, and system updates can wipe out what you install
into it. **It is there to run your Mac, not your projects.** Then the shape of everything from
here: `brew install` and a name. No download page, no dragging to Applications, no clicking Next
four times.

If it still says 3.9: new terminal window. (Sixth troubleshooting row.)

**6.6 — the refusal.** Have them run `pip3 install reportlab` **knowing it will refuse**. The
exercise is reading `error: externally-managed-environment` and the paragraph underneath it,
which tells them exactly what to do. Ask them to read *what it printed* back to you rather than
explaining it first — a refusal with a reason is a thing worth learning to read.

Then why: Homebrew's Python belongs to Homebrew, and letting every project shove libraries into
it is how one project breaks another.

**6.7 — the venv.** Two commands, then **look at the prompt**: it now begins `(.venv)`. The
sentence to use is the page's, because it ties back to Module 5 — that's the terminal telling
them which Python they're talking to, *the same way it has always told them which folder they're
standing in*. Then `pip install reportlab` (the 3 can go, inside a venv).

**6.8 — the payoff.** `python make_worksheets.py`, then open the folder in Finder. Forty-two
worksheets and a key, about two seconds.

Now use what you can do that the page can't: **read `worksheets.pdf` and tell them what's in it**
— that Ayelet's first problem is different from Noam's, that the key is on the last page. Then
have them open `make_worksheets.py` and see how short it is. The reveal's point, kept whole:
**you did not write the hard part.** Nothing they did today knows how wide a 7 is in Helvetica.
*Learning to write the small part that is yours, on top of the enormous part that is everybody's.*

**Aside 2, said now rather than tomorrow:** the venv switches off when the terminal closes;
`source .venv/bin/activate` first thing, `(.venv)` in the prompt, `deactivate` to switch it off
on purpose. If they forget they get `ModuleNotFoundError`, **which by now they can read.**

## Part C — making it theirs

**6.9 — change two numbers.** They open the file in a text editor, change `PROBLEMS` and
`LOW, HIGH`, save, run. Don't do it for them and don't offer; two numbers in a file they can see
is the whole exercise. Everything downstream follows, which is the point.

**6.10 — ask for something it doesn't do.** They send the prompt in a Code session in that
folder. You do the work as ordinary Claude Code: multiplication instead of addition, the date in
the top right of every sheet, **the answer key still correct**.

Then make them check it: run it, compare the key against a sheet, **do one sum themselves.** Say
that out loud as a habit, not a chore — it's Module 3's *ask to see the result* in a form where a
wrong answer reaches a child.

The reveal is the best detail in the module and you should look for it in the file rather than
quoting it blind: `rng = random.Random(name)`. Same name, same twenty problems, every time. If it
were truly random, re-running would give fresh worksheets and a key for the previous batch — *and
you would not find out until a child did.* **Check that line survived your edit**, say that you
checked, and tell them why you looked. That is exactly the habit the sentence recommends:
*worth noticing when Claude writes things for you.*

**Aside 3, held firmly.** Their real class list would work exactly the same way. **Not yet.**
Module 9 is where that changes. Invented names, or a staff list. SKILL.md rule 8.

## The ending

1. Section 8, briefly: the fluency materials at Schechter are a folder of generators like this
   one. *None of it required learning to draw a PDF. It required knowing that somebody else
   already had.*
2. The question to carry out of the module, which replaces "can I build that?": **has somebody
   already built the hard part of that?** For almost anything, the answer is yes, it's free, and
   it installs in one line.
3. The held question — their impossible thing. Now go and ask: *is there a Python library that
   already does the hard part of this?* Answer it honestly when they ask you, including when the
   answer is "yes, but it's harder than it looks."
4. Their task list (eight), in their words.
5. Next: Module 7, *GitHub* — they've just used somebody else's library; next is somebody else's
   whole project, and a way of keeping every version of their own.

## What goes wrong, and what to do

The page's table (section 9) is thorough. What it doesn't cover:

- **They ask you to install it for them.** See above. One line of why, then the command.
- **They offer you their password.** Decline, plainly, and say where it goes: their terminal,
  nowhere else, invisible as they type.
- **The install hangs, or seems to.** Homebrew is slow and quiet. Several minutes with nothing
  happening is normal; ask what the last line on screen says before assuming it's stuck.
- **A corporate-managed Mac refuses the install.** Not something to work around. That's for
  whoever manages the laptop. They can still do 6.1 and 6.2 and understand the shape.
- **`ModuleNotFoundError` again tomorrow.** The venv. It will happen; it's aside 2, and the point
  is that they can now read the error themselves.
- **They want to use their real class list because it's right there.** Aside 3, firmly, once.
- **Their edit in 6.10 broke something.** Paste the error, fix it as ordinary Claude Code, and
  say what broke. If it's beyond saving they can download `make_worksheets.py` again — that's the
  last troubleshooting row, and losing an edit is a good argument for Module 7.
- **Windows.** Homebrew is macOS (and Linux). On Windows the equivalents are winget or the
  python.org installer, `py` instead of `python3`, and `.venv\Scripts\activate` to switch the
  venv on. Say plainly that this module's commands are the Mac ones and that you're less sure of
  the Windows details.
