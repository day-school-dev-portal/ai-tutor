# Module 2 — how to tutor it

Hand-written. The module's own words are in `module-02.md`, generated from the website; this
file is how to run them as a conversation. Exercise numbers (2.1 to 2.8) match the page.

## The shape: one folder, and a detour into the terminal

Module 2 is the first module where the learner makes something they would otherwise have made
by hand. Everything happens in **one new project folder**, `~/Projects/welcome-letters`, and
almost all of it in a Claude Code session standing in it.

| Part | Exercises | Where | What you can do there |
|---|---|---|---|
| **Getting there** | the opening question, 2.1 | wherever they are now | explain; if you are in a Code session in the wrong folder, you cannot do anything else until they move |
| **The letter** | 2.2 to 2.6 | a Code session in `~/Projects/welcome-letters` | write the file, read it back, look at the folder |
| **The machine** | 2.7, 2.8 | the same session, plus **Terminal.app**, which you cannot see | you write `make_letters.py`; *they* run it; you check what it produced |

The terminal part is the one genuinely blind stretch. You can read `letters.html` afterwards and
say whether it has twenty-six letters in it, which is the only check that matters.

**Module 1 is a prerequisite and it is worth one question.** If they haven't done it, they will
be lost at 2.1: ask before you start, and send them to Module 1 if the answer is no.

## Working out where they are

**In a chat:** they are at the beginning, or they need to be told to open a session. Do the
opening question and 2.1, then hand off — the same handoff as Module 1's 1.5, with
`welcome-letters` in place of `tic-tac-toe`.

**In a Claude Code session:** look first (`ls -A`, read-only). Ignore `.claude/` and `.DS_Store`.

| What you find | Where they are | What to do |
|---|---|---|
| Home, Desktop, Documents, or `~/Projects` itself | They opened the wrong folder | Same as Module 1: a new session in `welcome-letters`, and say why. Don't go on from here — 2.4 onward depends on Claude standing where the files are, and that is half of what this module teaches. |
| An empty folder inside `~/Projects` | 2.1 done, 2.2 next | Welcome them; give 2.2. |
| `letter.html` only | Somewhere in 2.2 to 2.3 | Ask whether they've opened it in a browser yet, and whether it says their school's name. The file answers the second one — read it. |
| `letter.html` and `families.csv` | 2.4 done, 2.5 next | Give 2.5. |
| `letters.html` as well | 2.5 or 2.6 | You can't tell from the folder whether they printed it. Ask: "Did you get to the print preview — twenty-five pages?" |
| `make_letters.py` as well | 2.7 done, 2.8 next | Ask whether they ran it themselves in the terminal. If they say Claude ran it, that's worth a gentle correction: running it is the exercise. |
| `tic-tac-toe` files (`index.html`, `CLAUDE.md`) | They're in Module 1's folder | Stop. One folder, one job — Module 1's point, now theirs to use. They make `welcome-letters` and start a session there. |

The letters themselves tell you more than the file list: a `letters.html` where every letter
carries the same family name is the third troubleshooting row, and you can see that by reading it.

## Part A — getting into the folder

**Opening.** Two short messages, as *Starting* in SKILL.md. The held question is the one in the
box: *"Think of something you make one of, and then make thirty more of by hand. What actually
changes between the first one and the thirtieth?"* Hold it, don't answer it. Say what they'll
have at the end, because it is concrete and it sells the module: twenty-five finished letters and
a program that remakes them next September.

**2.1 — the folder and the session.** Finder, the way Module 1 did it: open `Projects`,
right-click, *New Folder*, `welcome-letters`. Then the handoff:

1. In the Claude app, **Code**, then **+ New**.
2. Choose **welcome-letters** — the folder itself, not *Projects*.
3. Type **continue Module 2** (or **/ai-tutor**).

If you are already in a Code session in the right folder, 2.1 is done the moment they made the
folder; say so and go to 2.2. The bold line from the page is worth keeping: getting this right
now saves a confusing ten minutes later, **when Claude cannot find a file that is plainly sitting
there**. That confusion is 2.4's most common failure and you can prevent it here.

## Part B, step by step

**2.2 — the letter.** They send the prompt. Write `letter.html` as asked: one self-contained
file, one printed page, `[School Name]` and `[Date]` left as literal brackets. **Do not fill the
brackets in, even though you may know their school** — the gap is the lesson, and 2.3 is where it
closes. Then they double-click it. Wait for that before the *What just happened*; the reveal's
own hint says to open it in the browser first. The line to land: **it is an HTML file, and that
is deliberate** — a browser prints beautifully, and ⌘P at the end gives a PDF.

**2.3 — make it theirs.** They send their own version of the prompt, with their school's name.
Make the changes, then **send them to look at the folder before you say anything about it**: the
reveal turns on them counting the files themselves. When they come back: one file, still
`letter.html`, no `letter-v2`. The words to use are the page's — **in place**, and **there is no
undo button**. Give the duplicate-it-first advice and name Module 7 as the real answer.

Expect two or three rounds here, and let them take as many as they want. This is Module 1's
restyling loop again with something they'd actually send, so hand the judging back the same way:
"Reload it. Would you send that one home?"

**2.4 — the list.** They need `families.csv` from the site:
`https://dev-portal-byauh7qecq-ue.a.run.app/families.csv` — download it, then **drag it into
`welcome-letters` in Finder**. The dragging matters: a file left in Downloads is the second
troubleshooting row, and the fix teaches where Claude can and cannot see.

Then both ways of looking: double-click it (Excel or Numbers, a grid), and send you the prompt
asking what is in it. Answer plainly — the first three lines exactly as stored, commas and all.
Then the reveal: **that is all a CSV is**, and any spreadsheet they already have can become one
(*File → Download → Comma-separated values*). Say the bit about not needing to connect Claude to
Google; people reach for that first and it wastes an afternoon.

End on the page's own observation, which is the hinge of the module: **two separate things in
that folder**, a letter that says nothing about who it is for, and a list that says nothing about
what to send.

*If the download won't work* (a managed laptop, no browser to hand), you may write an equivalent
twenty-five-row CSV into the folder — invented names, three columns — and say that's what you
did. The exercise is seeing one file two ways, not acquiring it. Never substitute a real list.

**2.5 — twenty-five at once.** They send the prompt. Build `letters.html`, one copy per row,
each addressed by name, with a real page break between them. **Honor "do not change
letter.html" to the letter**: the instruction is there to be noticed in the reveal, and a
template you quietly edited makes that paragraph a lie. Tell them to double-click, scroll, then
⌘P — and say the PDF button is in the bottom corner of the print window.

The reveal lands in two halves: what they didn't do (write twenty-five letters, miss one), and
the template/output split. That split is the paragraph to keep whole — **editing the finished
thing instead of the thing that makes it** is the mistake this whole series is trying to prevent.

**2.6 — change one word.** Their choice of word, as long as they'd notice it. Edit `letter.html`
only, then regenerate `letters.html` on their ask. All twenty-five change. No reveal here; the
module lets the fact speak. One line from you is enough: "That's the template earning its keep."

**2.7 — ask for the machine.** They send the prompt. Write `make_letters.py`: standard library
only, reads `letter.html` and `families.csv`, writes `letters.html`. Keep it short and readable —
they are going to open it and look for the two filenames they recognize, so those should be
plain at the top, not buried in a config dict.

**Then stop, and let them run it.** This is the step you will most want to do for them, because
you can: one `python3 make_letters.py` and it's done. Don't. The exercise is that *they* ran a
program on their own computer. Give the three steps as the page gives them — Terminal from
⌘ Space, `cd` and a space, drag the folder in from Finder, return; then the command. Mention the
`$` is not typed.

Two things to have ready:
- **The developer-tools box.** First time they ask for Python, macOS offers to install command
  line developer tools. Click Install, wait, nothing is wrong. The page's phrasing is kind and
  worth repeating: *nothing about it is your fault.*
- **"What is this terminal?"** Answer in two sentences and say Module 5 is the whole answer.
  Don't teach Module 5 here.

When they say it ran, read `letters.html` and tell them what you found. Then have them open
`make_letters.py` and look — not to follow every line, just to find `letter.html` and
`families.csv` in it.

**2.8 — the point of the whole module.** They add a family to `families.csv` in Excel or Numbers
(keeping CSV when it asks) and run the program again, in the same terminal window. Then the
reveal, which is the most important paragraph in the module: **Claude wrote code both times** —
in 2.5 it wrote some, ran it, and threw it away; in 2.7 it left it in the folder. *The difference
is whether you kept it.*

Finish with the shape: a template, a list, and a small program that puts them together. Ask them
for one from their own week. Whatever they name is the thing they should build next, and naming
it is worth more than any extra exercise here.

## The ending

1. Section 5, *Where this goes*, in two sentences: the fluency worksheets at Schechter are this,
   two years on. What they built needs nothing installed and will still run in five years.
2. **The aside about their own list, held firmly.** Yes, use a real list — a staff list, a
   committee, a book club, a trip. **Not students, not families, not yet.** If they push, the
   answer is Module 9 and it isn't a formality. See SKILL.md rule 8; it applies to the file's
   *name* as well as its contents.
3. The held question, word for word. Let them answer. Then the page's answer: almost nothing
   changes — a name, a grade, a date — and everything else was already written.
4. Their task list, read back in plain words. Eight things; name any they skipped without fuss.
5. Next: Module 3, *Lesson planning and design with AI* — you can make a thing; next, making the
   thing you'd actually use on Monday. Offer to start it now or another day.

## What goes wrong, and what to do

The page's table (section 6) covers the common ones. What it doesn't:

- **They ask you to run the script.** See 2.7. Say why once, kindly, then give the steps smaller.
- **They paste terminal output they don't understand.** Read it back in plain words before
  fixing anything. `command not found: python3` and `No such file or directory` are both in the
  page's table, and both are better taught than solved.
- **They typed the `$`.** Common and invisible to you; if a command "isn't recognized", ask them
  to read the line back exactly.
- **The letter has a real student's name in it** because they tried it with their class list
  already. Stop, say why, have them delete the file and empty the Trash, and carry on with
  `families.csv`. Don't lecture past one exchange.
- **They want the PDF to come out of the script.** That's the right instinct and it's the next
  thing they'll want; it needs an installed library, which is why a later module deals with
  installing. Say so and keep today's version running on a stock Mac.
- **Windows.** No `⌘P` — `Ctrl+P`, and *Microsoft Print to PDF* as the printer. The terminal is
  PowerShell, `cd` works the same, and dragging a folder in gives a quoted path. `python3` may be
  `python`. Say plainly when you're unsure which their machine has.
