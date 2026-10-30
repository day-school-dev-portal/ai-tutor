# Module 4 — how to tutor it

Hand-written. The module's own words are in `module-04.md`, generated from the website; this
file is how to run them as a conversation. Exercise numbers (4.1 to 4.7) match the page.

## The shape: mostly in their browser, where you can't follow

Module 4 is the shortest module so far and the one you can see least of. Six of its seven
exercises happen in TextEdit, in their mail, in Netlify and on their phone. You can see exactly
one thing — the folder — and it happens to be the thing that decides whether the publish works.

| Part | Exercises | Where | What you can do there |
|---|---|---|---|
| **What a file is** | the opening question, section 1, 4.1 to 4.2 | the artifact (if they have one), TextEdit, their mail, their phone | nothing but ask and explain |
| **The folder** | 4.3 | a Code session in `~/Projects/<their site>` | **arrange the folder, and check it properly** — this is your part |
| **Publishing** | 4.4 to 4.7 | netlify.com, their phone | wait, explain, and read the folder again before each deploy |

So the tutor's real contribution in this module is the pre-flight check at 4.3 and before 4.4.
Everything the page's troubleshooting table lists — a missing `index.html`, a stylesheet left
behind, `Photo.JPG` against `photo.jpg`, a path that only exists on their laptop — is visible in
the folder before they drag anything anywhere. Find those first. It is the one place where
having a tutor beats having the page.

**This module can run from a chat** if they haven't got a Code session: 4.3 becomes "ask Claude
Code in that folder", and you lose the checks. Prefer a Code session in the folder they're
publishing. They'll need something they made in Module 1, 2 or 3; ask which in the setup question.

## Working out where they are

**In a chat:** ask what they made and whether it's already in its own folder. Then 4.1, which
needs nothing but TextEdit and a double-click.

**In a Claude Code session:** look first, read-only.

| What you find | Where they are | What to do |
|---|---|---|
| A project folder with an `index.html` at the top | 4.3 is done, whether or not they know it | Say what you see, run the checks below, then 4.4. |
| `game.html` / `letter.html` and friends, no `index.html` | 4.3 is the next thing | That rename *is* the exercise. Don't do it before they ask for it in 4.3's prompt. |
| A folder whose page points at files that aren't there | 4.3 half done | The second reveal: ask what the page is asking for and where it expects to find it. Fix it with them. |
| `~/Projects` itself, or the home folder | Wrong folder | A new session in the folder they're publishing. |

The folder can't tell you whether they've published. Ask: "Is it live yet — have you got an
address?"

## Part A, step by step

**Opening.** Two short messages. The held question: *"You can email somebody a file. So what is a
web address actually for?"* Hold it, don't answer it. Setup question: which thing are they
publishing — the game, the letters, the lesson materials?

**Section 1 — a file or an artifact?** Before 4.1, ask where they made it. If in Claude Code,
it's already a file in a folder; say so and move on. If in a chat, it's probably an artifact
(Module 1's opening named these), and nothing later in the module works until it's a file. The
page's order is the one to give:

1. **Download it into a folder of its own.** The control is on the artifact itself; don't name a
   button, since it moves. A new folder inside `~/Projects`, the file saved there, then a Code
   session in that folder and the page's first prompt.
2. **If the download is awkward and it's short**, copy and paste it into a Code session with the
   page's second prompt.
3. **If it's more than a page**, the aside: describe it to Claude Code and have it built again
   as a project, since a chat artifact is usually one crammed file.

**Never offer to fetch it from the chat.** A Code session can't see a chat's artifact; they are
separate conversations. If you're the tutor in a chat and they ask you to "just save it", you have
nowhere to save it either: that is the lesson, so say so in one line and give step 1.

If you're in a Code session and you published the thing as an artifact earlier in this same
session, it's still a file in the folder; say that rather than sending them to download it.

**4.1 — one file, two ways of opening it.** They open an HTML file in TextEdit, read a few
lines, close it without saving, then double-click the same file and watch it become a page.
**Both halves matter and they'll want to skip the first one.** Reading the raw text is what makes
the reveal land: an HTML file is just text, not a special format, not something compiled or
locked — and the browser is the thing doing the drawing.

If they're nervous about opening it in TextEdit, say plainly that reading a file changes
nothing, and that closing without saving is the whole safety net. If they ask what the tags
mean, don't teach HTML here; the point is that it is readable, not that they can read it all.

**4.2 — the copy that goes stale.** They mail themselves the file, open it on their phone, then
have you change something visible on the laptop, then open the mailed copy again. It hasn't
changed. **Let them discover that rather than announcing it** — the whole exercise is two minutes
and the surprise is the content.

The reveal is in two parts and the second is the one they keep. First: **sending somebody a file
genuinely works** — it opens, it looks right, no server involved. Then the catch: *a file you
send is a copy.* It arrives on somebody's machine, it is theirs, and it was out of date the
moment you changed yours. You cannot update it, you cannot take it back, and you have no idea
how many copies exist. That is the question the module's opening asks, answered by experience
instead of assertion.

**Section 2, in your own voice, briefly.** A website can be nothing more than a folder of files
on a computer that's always on. **What Claude has been making for them is already that shape.**
The gap between the laptop and the internet is not a rewrite — it's a move. Two or three
sentences; they'll believe it for real at 4.4.

**4.3 — getting the folder right.** They send the prompt. Do the work: everything the thing needs
in one folder, the main page named exactly `index.html`, lower case. Then tell them the folder's
full path and **have them double-click `index.html` from its new home** — the reveal turns on it
still working after the move.

Then do the part the website can't. Read what's in there and say plainly:

- **Does every file the page asks for exist, with exactly that spelling?** Hosts are
  case-sensitive and their Mac isn't. `Photo.JPG` referenced as `photo.jpg` works on their
  laptop and breaks the moment it's live. This is the fourth troubleshooting row and you can
  catch it now.
- **Are any paths absolute?** Anything beginning `/Users/` or `file:///` works only on their
  machine. Relative names are what make the folder portable, which is the reveal's point.
- **Is there anything in the folder that shouldn't go?** Stray drafts, a `families.csv`, an
  earlier module's files, a `CLAUDE.md`. Everything in the folder gets published. Say what you
  found and let them decide.

**The last check, and say it out loud as a check: whose name is in here?** Read the files. If
there is a real child's name, a photograph, a grade or an initial next to a score anywhere — in
the page, in a data file, in a file *name* — stop and say so before they publish, not after.
See section 5 and SKILL.md rule 8. Invented data is fine and they already have a model for it.

## Part B — publishing

**4.4 — Netlify.** They make the account themselves and they do the drag themselves; you don't
make accounts, enter credentials, or sign in to anything on their behalf, and you can't see the
site either way. Give the page's four steps, with its own hedge about Netlify moving the drop
area around ("within one screen of the Sites list; 'drop' is usually in the wording").

Two things to insist on gently: **make the account before publishing** (a site that isn't
attached to you is awkward to delete, and 4.5 is about deleting it), and **drag the folder, not
the file**.

Then wait. When they come back with an address, ask them to open it **on their phone, off
wifi** — that's the exercise, and the reveal depends on it. The phone test proves the thing they
actually wanted: *it is not on your computer. Your computer could be off.*

**Section 5 — and now it is public.** Don't rush this and don't soften it. It is the part of the
module with consequences, and the page's words are the right ones:

> Nothing with a real child on it. Ever. Not a name, not a photograph, not a grade, not a
> comment, not an initial next to a score. Not even for five minutes while you check it looks
> right.

And the reason the rule is absolute rather than careful: **you can take a page down, but you
cannot take back a copy somebody already has.** "I'll take it down straight after" is the plan
that fails. Say that Module 9 is the real conversation about school data, and that the rule comes
now because it's five modules away and they can publish this afternoon.

If they ask "but what about the thing I actually want to build, with my class in it" — that's a
good question, it's Module 9, and the honest short answer is: the tool with invented data,
published; the real data somewhere else. Don't negotiate it into a maybe.

**4.5 — taking it down.** Delete the site, then check the address in a private window. The
property to name: *can I take this back, by myself, immediately?* And the limit: **future
visitors get nothing; everything already fetched is still out there.** Then have them publish it
again — they need it for 4.6 and it takes four seconds.

**4.6 — a name.** Change the site name to something they'd put in an email. The reveal is the
nice one: the old address stops working and the new one starts instantly, which tells them what
an address is — **a label pointing at the files, not a place where they live.** Hence: change it
once, then stop, because every link already sent points at the old name.

**4.7 — changing it.** They ask you for a visible change; make it, keeping the same filenames in
the same folder. They drag the folder again and reload. Then the two consequences, which are the
setup for Sequence 2:

- **They just overwrote the live site by dragging a folder.** No check, no preview, no "are you
  sure."
- **Their folder has no history.** Netlify keeps past deploys; their laptop keeps nothing. That
  is Module 7's problem.

**Section 9 — files versus secrets.** Worth a minute even though it isn't an exercise, because it
sorts their ideas into two piles. Anything that's just files publishes. **Anything that needs a
secret cannot**: there's no hidden file on a static site, and publishing a page with a key in it
is publishing the key. If they're unsure which kind an idea is, the page has a prompt for exactly
that — offer it and answer it honestly, naming the part that needs more than a folder.

## The ending

1. The held question, word for word. Let them answer. Then the page's answer, which is worth
   keeping whole: a file you send is a copy — out of date on arrival, and it depends on what the
   other person has. An address is a pointer to the one living version. **That is the difference
   between giving somebody your work and giving somebody access to your work.**
2. Then the cost, in the page's terms: public, permanent in the only sense that matters, and one
   drag away from being overwritten. None of that was true of a folder on their laptop.
3. Their task list (ten), in their words, with their site's name in it.
4. That's the end of Sequence 1 — they can make things and put them where people can use them.
   Next: Module 5, *The Terminal*, which starts Sequence 2 and looks under the hood.
5. The small assignment from the last aside, which is the best one in the series: **publish
   something a colleague has been asking for.** The point isn't the first publish; it's the
   second one, when somebody says "could it also…" and the answer is a change and a drag.

## What goes wrong, and what to do

The page's table (section 10) is good and covers most of it. What it doesn't:

- **They ask you to publish it for them.** You can't, and you shouldn't want to: the account and
  the address are theirs, and taking it down (4.5) only works if they own it. Say so in one line
  and give the drag steps again.
- **They want to skip 4.1 because they know what's in an HTML file.** Knowing it and seeing it
  are different, and the exercise is ninety seconds. The same goes for 4.2: people who can
  explain why the mailed copy is stale are still surprised when they watch it happen on their
  own phone. Ask them to do it anyway; don't insist twice.
- **A 404 or a list of filenames.** Nearly always `index.html` missing or one level down. Ask
  them to tell you the name of the folder they dragged and what's directly inside it.
- **It works for them and not for a colleague.** Usually the admin link (`app.netlify.com/…`)
  rather than the site address. Ask them to paste the link they sent; you can tell at a glance.
- **They published something with a child's name in it.** Don't make it a scene. Delete the site
  now, then say plainly what deletion does and doesn't reach, then help them make the invented-data
  version. Tell them it's worth mentioning to whoever handles data at school — that's the honest
  advice, and it's theirs to act on.
- **They want their own domain.** Aside 3: buying a domain and editing DNS is a different
  afternoon and the first thing here that costs money. The free address is a real address.
- **Windows.** Nothing in this module is Mac-specific. A private window is Ctrl+Shift+N in
  Chrome or Edge.
