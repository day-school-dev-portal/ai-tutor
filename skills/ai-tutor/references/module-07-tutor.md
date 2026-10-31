# Module 7 — how to tutor it

Hand-written. The module's own words are in `module-07.md`, generated from the website; this
file is how to run them as a conversation.

The page's title is *Using somebody else's project*, not "GitHub", though the file is
`07-github.html` and people refer to it that way.

## The shape: a stranger's project, on their machine

Module 7 is where the learner stops starting every project in an empty folder. They read a public repo in a browser,
install two programs, clone the repo into `~/Projects`, and then do the real work in a Claude
Code session standing in `group-maker` — which is where you come in.

| Part | Exercises | Where | What you can do there |
|---|---|---|---|
| **Reading in public** | the held question, 7.1 | github.com, in a browser | nothing; wait |
| **Two programs** | 7.2, 7.3 | Terminal, with their Mac password | explain, read output; **never install for them** |
| **Cloning** | 7.4 | Terminal, standing in `~/Projects` | after it lands, you can see everything |
| **Getting your bearings** | 7.5, 7.6 | a Code session in `~/Projects/group-maker` | **this is your module** — you are the interface to the code |
| **Fixing it** | 7.7, 7.8 | the same session, checked in their browser | make the fix, update the README |
| **Whose copy** | 7.9, 7.10 | Terminal, then the session | explain `pull`; read the LICENSE honestly |

**What this module is really teaching is you.** Section 4 says it outright: *from here on, Claude
is your interface to other people's code — the way Finder is your interface to files you never
look inside.* So the way you answer 7.5 and 7.6 is the lesson. Answer them as a competent
colleague who has just read the folder, not as a tutor reciting a page.

## One thing to know before you start

Modules 2 and 4 both promise that **Module 7 is where version history gets solved** — "a way of
keeping every version of every file forever". This module doesn't do that. It clones, and says
the `.git` folder is "a later module". If a learner arrives expecting commits and rollbacks, say
so plainly: today is about getting somebody else's project and changing it; keeping your own
history is the same tool, not yet covered. Don't improvise a commit lesson on top of this one.

## Working out where they are

**In a browser or chat:** 7.1 needs nothing. 7.2 and 7.3 are terminal work you can talk them
through from anywhere.

**In a Claude Code session:** look first.

| What you find | Where they are | What to do |
|---|---|---|
| `~/Projects` itself, with no `group-maker` in it | Before 7.4 | They haven't cloned yet, or it landed elsewhere. Ask what `pwd` said when they ran `git clone`. |
| `group-maker` with `index.html`, `README.md`, `CLAUDE.md`, `LICENSE` | Cloned; somewhere in 7.5 to 7.10 | Read all four files before you say anything, then ask what they've run. |
| `group-maker` cloned, `index.html` modified | 7.7 done | Ask whether they checked thirteen names in groups of four themselves. Then 7.8. |
| A `group-maker` folder with no `.git` inside | They downloaded a ZIP instead of cloning | It will work for everything except 7.9. Say so; offer a clone alongside it if they want the `git pull` exercise. |

The folder tells you a lot here, because it's somebody else's folder and you can read its
`README.md` and `CLAUDE.md` — which is the point of 7.5 and 7.6.

## Part A, step by step

**Opening.** Two short messages. The held question: *"A teacher at another school has already
built the thing you need. How would you get a copy — and what do you think you would actually be
getting?"* Hold it, don't answer it.

**7.1 — go and read a stranger's project.** `github.com/day-school-dev-portal/group-maker`, no
sign-in, click into `index.html`. They are not expected to understand it. The reveal is three
separate facts that beginners run together: **anyone can read it, anyone can copy it, only the
owner can change it.** *You cannot break it.*

**7.2 and 7.3 — Homebrew and git.** If they did Module 6, `brew --version` means skip to 7.3.
Otherwise it's the same install as Module 6, with the same rules: **you never run it**, and the
**password goes into their terminal and nowhere else, invisible as they type**. The page's own
line about the password is the right one to repeat at the end: *a reasonable thing to be asked
once, by something you understood and chose to install, from an address you can read.*

Then `brew install git`, `git --version`. The point to make is how small the second install was:
**that is the whole shape of installing software from now on, and it's the same for the next
hundred things.**

Aside 1 is worth saying before they get confused rather than after: **git is the program on their
computer; GitHub is the website.** Confusing names, everybody just gets used to it.

**7.4 — cloning.** The one thing that decides where it lands is **the folder they're standing in**
— so `cd ~/Projects` and `pwd` to check, *before* the clone. Then `git clone`, then `cd`, `pwd`,
`ls`, and a look in Finder: the folder is really there, next to `tic-tac-toe`.

The reveal has two halves. They got **the whole repository**, not a download of the current
version — every change anyone ever made, in the hidden `.git` folder. And what it is **not**:
not connected, not shared, nothing they do reaches the original. *Like photocopying an entire
book and bringing it home.* That freedom is what makes the rest of the module possible.

Mention the explicit form from aside 2 (`git clone <url> ~/Projects/group-maker`) once — it's the
thing that stops a clone ever landing somewhere confusing again — and the *New Terminal at Folder*
setting if they want it.

## Part B — you as the interface

**7.5 — the first question to ask about any project.** They open a Code session on
`group-maker` and send the prompt. **Answer it properly and specifically**: what the project is,
that it needs nothing installed, that they open `index.html` by double-clicking, and what to
know before changing it — which means the house rules in `CLAUDE.md`, including the one about
class lists never leaving the browser. Read the files first; don't answer from the module.

Then they run it, make some groups, and do the thing that matters: **thirteen names, groups of
four.** Make sure they do that before the reveal; the whole back half of the module depends on
them seeing one child sitting alone with their own eyes.

The reveal's reusable part is the prompt itself — *what is it, what do I need, how do I run it,
what should I be careful of* — and the observation that **the middle question is the one
beginners don't know to ask**: almost every "I couldn't get it working" is a missing
prerequisite. Here the answer was *nothing*, and that was somebody's deliberate choice.

**About the class list.** The page says "paste in a real class list, or use the sample", because
the app keeps everything in the browser and the author wrote that rule down. Hold the series'
line anyway, and say why rather than just forbidding it: typing names into a page on their own
machine is the author's design, but **those names must not come to you in the chat, and they
must not be saved into a file in the folder** — a saved list is school data in a project folder,
which is Module 9's territory. If they'd rather not think about it at all, the sample list is
right there. See SKILL.md rule 8.

**7.6 — house rules.** They ask what rules the project has and where they're written, then **open
`CLAUDE.md` themselves**. Quote it to them when they ask; the exercise says *quote the file*.

Then the payoff, which is the best moment in the module for anyone who did Module 1: `README.md`
and `CLAUDE.md` are the two files they wrote for a hypothetical stranger — **and now they are the
stranger.** The folder explains itself, to them and to you at the same time. Say that this is the
strongest argument for writing those files in their own projects, and that it's hard to feel
until you've been on this side of it.

**7.7 — fix it.** They send the prompt. Make the fix: group sizes differing by at most one, and
**follow `CLAUDE.md`** — one file, no frameworks, nothing leaves the browser, it must print. If
following those rules makes the fix uglier than it would otherwise be, say so and follow them
anyway; that's what house rules are.

Then **make them check**: reload, thirteen names in groups of four, expect 4, 3, 3, 3. Then the
awkward numbers — seven, nine, twenty-two, one name, none. Don't check it for them and don't
report it as done before they've looked.

**7.8 — the README is now a lie.** They ask you to update it. Do it: move the leftover-student
problem out of "Known problem" and describe what it does now. The reveal is worth keeping whole:
**documentation that no longer matches is worse than none**, because the next person — or the
next Claude — will believe it. *Updating it is part of finishing, not a chore afterwards.*

And name the sequence, since it is the method the whole series is building toward: read what the
project says about itself, run it, reproduce the problem with your own eyes, describe the fix in
plain language, check the result yourself instead of believing the report. **None of it required
reading the code.**

## Part C — whose copy is it

**Section 7, then 7.9.** Their version is better; the published one hasn't changed; nothing
travelled. A **fork** and a **pull request** are the door back, and it's a later module — worth
knowing the door exists.

Then the reverse, which is the part that catches people: **the original can change and their copy
will not notice.** `git clone` took a photograph, not a window. Give the table in words: *clone*
is "I don't have this — get me a copy", once ever; *pull* is "I have it — bring me whatever
changed", whenever. And the consequence: trying to clone a second time gets
`destination path already exists`, which is now an error they understand.

7.9 itself is anticlimactic on purpose. `git pull` says `Already up to date.` **That is the
answer to their question, not a failure to do anything** — say so before they ask.

Aside 3 is the good one: they didn't have to say which project or what address. **The folder
remembers where it came from.** That is the real difference between a folder they cloned and a
folder they made; in Finder they look identical, and only one can answer *has the original
changed?*

If a `git pull` ever says something else — a conflict with their own 7.7 edit — that's git being
careful with their work. Have them paste the whole message to you; it looks worse than it is.

**7.10 — the license.** They ask; you answer honestly about the actual `LICENSE` file in the
folder. MIT: use it, change it, share it, even sell it, as long as the copyright notice stays.

Then the part that matters more: **the absence of a license means the opposite.** No LICENSE file
means all rights reserved by default — readable in public, and strictly speaking not yours to
use. Most people ignore it; for something a school will depend on, that's a bad habit. *Two
minutes and one question is the whole cost of knowing.*

## The ending

1. Section 8: they can now take any public project in the world, run it, judge it, and change it
   for their school. **The skill that made it work was not `git clone`** — it was reading the
   README, running the thing, and checking with their own eyes.
2. Offer the "before I clone it" prompt for next time: what it does, what's needed to run it,
   whether it's still maintained, what the license allows.
3. Aside 5, said plainly once: cloning copies somebody's files onto their computer and running
   one runs somebody's instructions. For a single HTML file they can see, that's nothing. For a
   project that wants to install things or asks for a password, **stop and ask first** — the same
   question they'd ask about any command they didn't write.
4. The held question, word for word. The answer: all of it — every file, every change ever made,
   and the right to do what they like with their copy.
5. Their task list (ten), in their words.
6. Next: Module 8, *APIs, tokens and signing in* — somebody else's code, then somebody else's
   data.

## What goes wrong, and what to do

The page's table (section 9) covers the common ones. What it doesn't:

- **The clone landed in the wrong place** because they cloned from the home folder. Third row —
  but the better habit is the one in aside 2: say where it should go, explicitly, every time.
- **They want you to clone it for them.** You could run `git clone` in their folder. Don't; 7.4
  is about *them* knowing where things land. Give the command.
- **They downloaded the ZIP from GitHub's green button.** Everything works except 7.9, because
  there's no `.git`. Say what's missing and why it matters.
- **They're in `~/Projects`, not `group-maker`, in the Code session.** Seventh row of the table.
  You'll notice before they do — say which folder you're standing in and have them reopen.
- **The fix "didn't work" but the browser is showing the old page.** Last row. Reload, hard
  reload if stubborn. Ask what they actually see rather than re-fixing working code.
- **They want to send the fix back to the author.** Good instinct, and the honest answer is that
  forks and pull requests are a later module — but nothing stops them opening an issue on the
  repo and describing what they found. That's a real contribution and it takes five minutes.
- **Windows.** `brew` is macOS; git comes from git-scm.com or winget. Everything after the
  install is identical — `git clone`, `cd`, `ls` (PowerShell has it), `git pull`.
