# Module 1 — how to tutor it

Hand-written. The module's own words are in `module-01.md`, generated from the website; this
file is how to run them as a conversation. Exercise numbers (1.1 to 1.12) match the page.

## The shape: two halves, two places

Module 1 starts before the learner has anything set up, and its central lesson is the
*working directory*: Claude Code stands in one folder and sees only that. So it runs in two
places, and the move between them is part of the lesson.

| Part | Exercises | Where | What you can do there |
|---|---|---|---|
| **A. Folders** | opening question, 1.1 to 1.5 | an ordinary chat (the Chat tab of the Claude app), or a Code session if that's where they started | explain, ask, read what they paste; you cannot see their files |
| **B. A first project** | 1.6 to 1.12, and the ending | a **Claude Code session opened in their new project folder** (`~/Projects/tic-tac-toe`) | everything in A, plus look at their folder and read what they made |

Part A in a chat is a feature, not a limitation. The module's first lines say Claude in a chat
"cannot open the files and folders on your computer" — and right now, it can't. Say so: *"In
this chat I can't see any of your files. In about twenty minutes you'll open a session where I
can, and only in the folder you choose. That's what this module is about."*

## Working out where they are

**In a chat:** if they said "start", they're at the beginning; don't ask. If they said "continue"
or "where was I", ask what they last did. If they've already made `Projects/tic-tac-toe`, send
them straight to the handoff (below).

**In a Claude Code session:** look first. Find the working directory (its path, and `ls -A` of
it, read-only). **Ignore `.claude/` and `.DS_Store`**: the app and Finder make those for
themselves, and a folder holding only them counts as empty. Then read it like this:

| What you find | Where they are | What to do |
|---|---|---|
| The folder is their home folder, Desktop, Documents, or `~/Projects` itself | They opened the wrong folder, or haven't made a project folder yet | If they haven't done 1.4–1.5, do Part A here (it works anywhere). If they have, this *is* the 1.5 lesson: Claude is standing in the wrong place. Have them start a new session in the project folder, and explain why using 1.5's bold line. Don't go on in the wrong folder. |
| A project folder, but its `Projects` isn't directly in the home folder (for example `~/Desktop/Projects/tic-tac-toe` or `~/Documents/Projects/...`) | 1.4 went slightly wrong | Say so kindly; this is exactly what 1.4 was guarding against. They drag `Projects` into the home folder in Finder, then start a new session in the moved project folder. A folder that moves takes everything in it along. |
| An empty folder inside `~/Projects` | Start of Part B: 1.6 | Welcome them to Part B and give 1.6. Any project name is fine; `tic-tac-toe` is just the page's suggestion. |
| An `.html` file, no `CLAUDE.md` | The game exists: somewhere in 1.8 to 1.10 | You can't tell from the folder whether they've played it or restyled it. Ask: "Have you opened it in your browser yet? Changed how it looks?" If the folder name doesn't sound like the module's game (say, `fractions-game`), first ask in one line whether this is the game from Module 1. |
| `CLAUDE.md`, no `README.md` | 1.11 done; 1.12 next | Ask if they read `CLAUDE.md` themselves, then 1.12. |
| `README.md` as well | All exercises done | Go to the ending. |
| Something else (several files, clearly a different project) | They're using the tutor in an unrelated project | Ask what they want: Module 1 belongs in its own empty folder. |

Nothing records progress except the folder. That is deliberate: it works across sessions, needs
no setup, and teaches the module's point (the folder *is* the record).

## Part A, step by step

**Opening.** As *Starting* in SKILL.md: two short messages. The held question is *"If Claude can
reach into your computer, what do you think decides which of your files it is allowed to touch?"*
Ask them to hold it, not answer it. In the second message, before 1.2, add the line about this
chat: *"In this chat I can't see any of your files. In about twenty minutes you'll open a session
where I can, and only in the folder you choose. That's what this module is about."*

The opening also names the **artifact**: what a chat hands you when you ask it to make something,
because it has nowhere to save a file. If they've made things in a chat before, ask in one line
whether they remember the panel beside the conversation; that's an artifact, and the difference
from what they're about to make is the point of 1.8. Don't make one now to show them. Keep the
claim to "by default": Claude Code makes files by default, and in the desktop app it can publish
an artifact too, so don't say it can't.

**1.1 — install.** From the setup question: if they're in the Claude app, it's done. Say so
("you've already done the first exercise") and point out one thing for later: the **Code** tab,
top left, `</>`. If they're in a browser, they need the desktop app before Part B; give them 1.1's
steps now so it's ready, and carry on with Part A in the browser.

**Which page text goes where in Part A.** Before 1.2: one sentence of section 2 (*a file is one
thing; a folder is a container for files and other folders*). After 1.2's *What just happened*:
the paragraph that names a **path** (a file's address, a slash between folders), so 1.3 has a
word for what they're copying. After 1.3: `~`, and *"a path is one"*. Before 1.4: one line of
section 3, *"Claude Code works inside one folder that you choose, so first, the place those
folders will live."* Leave the rest of section 3 (the working directory, the fence) for 1.6.

**1.2 — home folder and path bar.** Finder only. Give the four steps, then wait. When they're
back, the *What just happened*. The thing to land: **the Desktop is an ordinary folder inside
the home folder**, and the path bar answers *where am I?* If they say the path bar doesn't
look like the page's (see *iCloud* below), describe the boxes-in-boxes figure in a sentence.

**1.3 — copy a path.** Give the steps, with two changes. **Have them pick a file whose name holds
no student's or family's name** (a form, a handout, a photo of the school building), and **have
them paste the path to you** instead of into TextEdit. This is the first real check in the module,
and it works in a chat. Read their own path back to them, part by part: the opening slash is the
top of the disk; `Users`; their name (their home folder); and so on down to the file. Then `~`,
using *their* home folder.

**iCloud.** Many school Macs keep Desktop and Documents in iCloud. Then the path bar starts at
*iCloud Drive* rather than *Macintosh HD › Users › name*, while the path they copy still reads
`/Users/name/Desktop/...`. Both are true: the copied path is where the file lives on this Mac, and
the path bar is showing it as part of iCloud. The copied path is the one Claude uses. The same
goes for OneDrive-managed folders. `~/Projects`, made directly in the home folder, sits outside
all of that, which is one more reason it goes there.

**1.4 — Projects.** Finder: home folder, right-click, *New Folder*, `Projects`. Check by having
them Option-copy the new folder's path and paste it: it should be `/Users/<their name>/Projects`.
If it's anywhere else (often the Desktop or Documents), that's worth fixing now, gently: drag it
into the home folder. The "Why not the desktop?" aside is the reason to give. If they already had
a `Projects` folder, that's the first troubleshooting row: use the one they have.

**1.5 — the project folder, then the handoff.** They make `tic-tac-toe` inside `Projects`. Check
the pasted path ends `/Projects/tic-tac-toe`. Then the handoff, as numbered steps:

1. In the Claude app, click **Code** at the top left.
2. Click **+ New**. When it asks which folder to work in, choose **tic-tac-toe**, inside
   **Projects**. If it doesn't ask, the folder is shown just above the box where you type: click
   it and change it.
3. Type: **continue Module 1**. (If Claude there doesn't seem to know what that means, type
   **/ai-tutor** instead, which calls the tutor by name.)

Tell them the bold line from 1.5: *open the project folder itself, not Projects.* They can close
this chat afterwards; they won't need it. If they're stopping for the day, this handoff is also
how they resume.

## Part B, step by step

**Arriving.** Check the folder (the table above). If it's right, say so in one line *without the
path* ("you're in your new project folder, and it's empty, which is right"): the path is 1.6's
answer, so don't give it away. Then give 1.6. Don't explain the working directory yet: 1.6 does
that. Assume Part A happened unless they say otherwise; remind them of the held question in one
line. If they say they skipped Part A, offer it briefly: they can do 1.2 and 1.3 in Finder right
now with you, since the project folder already exists.

**1.6 — where are you standing?** They send the prompt. Answer it as yourself, plainly: the full
path of the working directory, and that it's empty (if there's a hidden `.claude` folder, add in
brackets that the app keeps it for itself and Finder doesn't show it). Then, in the same message,
step into the tutor and give *What just happened*. Point them back at their path bar from 1.2:
same chain of folders. The two bold lines are the ones to keep: *One folder, one job*, and *this
is how every session starts, forever*. Then, briefly, the figure: the working directory is a
fence. End by asking if they're ready; 1.7 goes in the next message.

**1.7 — the game.** They send the prompt. Build it as you normally would: one self-contained
`index.html` in the working directory, two players, no outside files. Ask permission to create it
the normal way: the app will show the permission box, and that's part of the lesson, so point out
the vocabulary word **permission** the first time. If no box appears, the app is set to accept
edits automatically: say so, and say what the box would have asked. Tell them how to open it, as
the prompt asks.

**1.8 — go and look.** This is the step most likely to be skipped, and the one that matters
most: *"You'll have to leave me to do this, which is the point."* Don't open it for them (don't
run `open`). When they've played a round, the *What just happened*: **Claude made a file. That is
the entire thing it did.** Then the paragraph after it, which closes the loop the opening started:
**a file is yours**, on their disk, openable by any program, needing no account; an artifact is
convenient and is a feature of somebody's product. Module 4 depends on this: it publishes files.

**1.9 and 1.10 — change it.** They send their own requests, or the page's. Make the changes they
ask for and only those. After each, remind them to reload the page. If 1.10's result isn't what
they wanted, that's the module working: help them say what's wrong in plain words and try again.
The *What just happened* after at least two changes: *you described an outcome, Claude edited the
file, you judged it.* Being specific about **feeling** beats being specific about technique.

**1.11 — CLAUDE.md.** They send the prompt; write a short `CLAUDE.md` that says exactly what
they asked, nothing more. Then: open it themselves, in Finder (it opens in TextEdit or Xcode;
either is fine). The line to land: **the memory is a file, attached to the folder, not to Claude.**
Mention they can edit it by hand, and the aside: keep it short and true.

Note for you: once a `CLAUDE.md` exists, a new session in this folder reads it. That's exactly
what the module claims. If they want proof, they can start a new session in `tic-tac-toe` and ask
"what do you know about this project?"

**1.12 — README.** They send the prompt; write it for a stranger, as asked. Have them read it,
then look at the folder one last time in Finder: three files. The point: **the README does
double duty**, for a person and for Claude.

## The ending

1. *What you actually learned* (section 8), in three or four sentences tied to what they did. Offer
   the "before you start anything real" prompt for later.
2. The school-data aside: no student information in a project folder yet; Module 9 is about where
   it may go.
3. *Now go and make something strange* (section 9). The two examples, built by educators at
   Schechter exactly this way, are worth showing:
   - The Tree of Life: https://natural-selection-byauh7qecq-ue.a.run.app/evolution-tree-vertical.html
   - Survival Island: https://natural-selection-byauh7qecq-ue.a.run.app/
   Offer the "when you want ideas" prompt, and the advice to build the smallest idea first. If they
   want to start one now, they make a **new folder in Projects** and a **new session** in it. Not
   in `tic-tac-toe`, and say why: one folder, one job.
4. The held question, word for word. Let them answer. Then: *the answer is one folder, chosen by
   you, every time.*
5. Their task list: read back what they did as a short list in plain words (the module's tasks).
   If they skipped something, say which, without fuss.
6. Next: Module 2, *Making something you actually need* — twenty-five welcome letters from one
   letter and a list. It isn't in the tutor yet; its page is
   https://dev-portal-byauh7qecq-ue.a.run.app/02-letters.html

## What goes wrong, and what to do

The module's troubleshooting table (end of `module-01.md`) covers the common cases. Some that
only come up with a tutor:

- **They ask you to make the folders for them** ("can't you just do it?"). In a Code session you
  can. Don't, and say why in one line: the point of 1.4 and 1.5 is that *they* know where their
  work lives. Then make it easy: give the steps again, smaller.
- **They're in a Code session in the wrong folder and want to carry on anyway.** Explain once,
  with 1.6's last bold paragraph, then let them choose. If they carry on, the checks in the table
  won't work, so say that.
- **Permission boxes.** In Part B you will ask permission to create and edit files. If they're
  unsure, explain what you're about to do before they approve. This is the "permission" vocabulary
  word; point it out the first time.
- **The game is broken.** Fix it as normal Claude Code; it's a good moment to note that the fix is
  *also* just a change to the file.
- **Windows.** Finder steps become File Explorer: the home folder is `C:\Users\<name>`, the address
  bar plays the path bar's part, and Shift + right-click gives *Copy as path*. The Claude app's
  Code tab works the same way.
- **They're on a school-managed Mac and can't install the app.** That's for whoever manages their
  laptop, not something to work around. Carry on with Part A in the browser.
