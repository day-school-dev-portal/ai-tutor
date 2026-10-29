# Module 8 — how to tutor it

Hand-written. The module's own words are in `module-08.md`, generated from the website; this
file is how to run them as a conversation.

## The shape: five errands in a browser, everything else yours

Module 8 is ninety minutes and the longest module in the series. It splits cleanly, and the page
draws the split as a figure: **anything in a browser is theirs; anything on their laptop is
yours.** Google offers no way for a program to write the consent screen or create a Desktop
client, and those screens are where *they* decide what the app is called, who may use it, and
what kind it is, on their own school account. So even if a browser tool would let you click them,
don't: the browser column is theirs because the decisions in it are.

| Part | Exercises | Where | What you can do there |
|---|---|---|---|
| **The failure** | the held question, 8.1 | a new Google Sheet, then a Code session | fail honestly — see the warning below |
| **Two windows** | 8.2 | a browser | explain JSON from what they paste |
| **Why a token** | sections 3 and 4 | conversation | all explanation; no exercise |
| **Which program is asking** | 8.3 to 8.6 | console.cloud.google.com | drive the setup, hand them each link, wait |
| **On whose behalf** | 8.7, 8.8 | your terminal work, their browser sign-in | run the helper's setup; **they** sign in and click Allow |
| **The two files** | 8.9 | the helper folder | explain the difference; never print either file |
| **Using it** | 8.10, 8.11 | a new Code session | read their practice sheet, write a tab back |
| **Taking it back** | 8.12 | myaccount.google.com | wait |
| **The shorter way** | 8.13 | Claude's settings | be honest about which is better for what |

**8.3 hands you the job.** The learner clones `google-workspace-helper` and says four words: *Set
this up for me.* From there you are not reciting this file — **the procedure is written down
inside the folder they just cloned.** Read its `SETUP.md` and `CLAUDE.md` and follow those, and
run `scripts/check_setup.py` after every step the way it tells you to. This file tells you how to
teach; that repo tells you what to do.

## Before you start: two warnings, and two places outside the folder

**This module needs two places outside the working directory.** The setup finds the client file
in **Downloads** and writes to the global **`~/.claude/CLAUDE.md`**. These are the named exceptions
to SKILL.md's "never look outside the working directory": ask before each one, every time, naming
the exact place ("OK for me to look in Downloads for the `client_secret_….json` file?"), and go
nowhere else.
**You may be able to read their sheet, and that would spoil 8.1.** If you have a Google Drive
connector switched on, the first exercise — watching Claude fail — will succeed instead. That is
aside 1, and the honest move is to say so immediately: *"I can read it, which means a connector
is on. Switch it off for now so you can see the gap this module is about — we'll turn it back on
at 8.13 and compare."* Don't pretend to fail. The module's credibility rests on being told the
truth about what you can and can't reach.

**Credentials.** Three rules, and they hold for the whole module:

- **Their Google password goes into Google's own sign-in page and nowhere else.** Never ask for
  it, never offer to type it, never accept it if they paste it, never repeat it back. If they do
  paste it, the order matters: (1) **change it first**, the way their school does it (often IT
  manages school passwords), and anywhere else they reuse it; (2) then sign in on Google's page
  with the new one; (3) if `authorize.py` timed out meanwhile, run it again. The old password is
  still in this chat's history, so suggest deleting the conversation when they're done.
- **Never print the contents of a token file**, and never paste it anywhere. `client_secret` in
  the OAuth client file is badly named and is not a password (the page explains this well), but
  the token file in `credentials/` is the real thing: whoever holds it is them, as far as Google
  is concerned, until somebody revokes it.
- **The setup writes to their global `~/.claude/CLAUDE.md`.** That's a change to every future
  session in every project. Show them exactly what you're adding, before you add it. 8.10 has
  them read it anyway; don't let the first time they see it be after the fact.

## Working out where they are

`scripts/check_setup.py` *is* the progress table for this module — it lists what's done, what's
missing, and a line beginning **NEXT**. Run it before you ask anything. That is also what you
tell them at 8.7: come back next week, run that, and "carry on with the setup" is enough.

Outside the helper folder, two quick questions place them: does a practice sheet exist (8.1), and
does `myaccount.google.com/permissions` list their app (8.8 done)?

## Part A — the gap

**Opening.** Two short messages. The held question: *"Your Drive is yours. Claude runs on your
computer, working for you. So what is actually standing between them — and what would it take to
let it through?"* Hold it, don't answer it. Say what the module changes: everything up to now
happened inside their laptop; after this, their programs can reach the systems the school runs on.

**8.1 — watch it fail.** First the practice sheet: a new Google Sheet, six rows, **invented
names and grades**. Say why in one line rather than as a rule — every exercise in this module
uses made-up children because at the end of it they're holding a real key. If they offer a real
class list, no, every time (SKILL.md rule 8).

Then they paste the sheet's address and ask you to read it. Fail honestly, and **report what
actually happened** — that you tried to fetch the address and got Google's sign-in page, or that
you have no way to reach it at all. The reveal is precise and worth being precise about:
**that spreadsheet is not a file on their computer**; what they see in the browser tab is a
picture of it, drawn fresh by a program that signed in as them. *Drive is a different computer,
in a different building, and the only way in is through a door Google controls.*

**8.2 — two windows, by hand.** PoetryDB first: Shelley arrives in a second, no account, nothing
installed. Then the Drive endpoint, which refuses. Have them read the refusal rather than
summarizing it for them, then land what the refusal **did not** say: not that the page doesn't
exist, not that their password was wrong.

Then JSON, from what they're looking at: **square brackets are a list; curly brackets are one
thing with labelled parts.** That's the whole format, plus nesting. Say the CSV comparison — a
poem has one title and fourteen lines, and a grid can't hold that shape — and the practical
habit: when a wall of brackets arrives, **paste it to Claude and ask what's in it.**

Then the second reveal, which sets up the rest: the difference wasn't difficulty, it was **whose
data was being asked for**. Shelley belongs to everybody. And the two questions the module
answers one at a time:

- **Which program is asking?** → registering an app → an OAuth client file.
- **On whose behalf, and for what?** → signing in once → a token.

**Sections 3 and 4 — no exercises, don't skip them.** The four properties of a token are the
thing they'll judge every future integration by: **narrow, revocable, doesn't reveal the
password, and theirs.** That last one is the one people get wrong, so say it: giving Claude a
token doesn't give it the school's Drive — *it gives it their view of the Drive.*

Section 4 is the "why bother" section, and it's worth two minutes because it's the business case:
**almost everything a school needs done is a loop.** Read them the four examples, then ask which
one is closest to something they've actually got. Hold aside 3 alongside it: **being able to is
not the same as being allowed to**, and that's Module 9.

## Part B — the five browser errands

Here you are driving. Give one link at a time, wait for them to come back, run the checker, then
the next. Do not give five links in one message.

**8.3 — clone and hand it over.** The clone command is in the page. Then they open that folder in
Claude Code and say *Set this up for me.* That's a **new session**, which ends this conversation,
so before they go, tell them exactly what to do: Code, **+ New**, choose `google-workspace-helper`
inside Projects, and type **continue Module 8**. (If you're already in a session whose working
directory is `~/Projects`, still send them to a new one in the helper folder: the page's point is
that the helper's own instructions load when *that* folder is opened.) In the new session, read
the repo's own instructions before you answer.
**Sign-in account matters more than anything else here**: their school account, not a personal
one, for reasons that land at 8.5.

**8.4 — project and APIs.** A new Cloud project, then its **project id** — ask for it, because
every link you build afterwards depends on it. Then three links, one each for Drive, Sheets and
Docs, each with one *Enable* button.

The thing to point out: they're all off by default. **An API that is switched off cannot be
called even by a token that says it's allowed.** A real second lock, which is why switching on
only what you need is worth doing.

**8.5 — the consent screen, which they are writing.** Two answers matter. **App name** — something
they'd recognize in six months, not `test`. **Audience: Internal.** Say what Internal buys before
they choose, not after.

If Internal is greyed out, that's aside 4: they're signed in with a personal account. If their
school genuinely has no Workspace organization, External works, and they must know the cost —
**an External app left in Testing gets a sign-in Google expires after seven days**, so it works
beautifully and breaks next week for no visible reason. Then they also need themselves added
under *Audience → Test users*.

Tell them to skip **Data Access** entirely, and why: scopes only have to be listed there for apps
used by people outside the organization.

**8.6 — the client.** **Application type: Desktop app**, not Web application. Check it; the page
says you will. Then *Download JSON*, and — this is the bit people get wrong — **leave the file in
Downloads under its ugly name.** You find it there (asking first) and put it where it belongs. The
commonest failure is a doubled extension, `oauth_client.json.json`, which is the first
troubleshooting row.

**Before they download it, say: open it in a text editor, and don't paste it into this chat.** If
they paste it anyway, say so once and plainly, then the reassurance from the page: `client_secret`
unlocks nothing on its own, so nothing needs resetting. Two uses of the paste: a top-level
`"installed"` key confirms they chose Desktop app (a Web client says `"web"`); and **don't build
the file from the pasted text** — still take the real one from Downloads, which is the step the
module teaches.

Before you tidy it away, have them open it in a text editor. Ten seconds, and it's worth it: ten
lines, a `client_id`, a `project_id`, a `client_secret`, some fixed addresses. **That is the
entire thing four screens produced.** Then the point about the name: `client_secret` unlocks
nothing, because reaching their Drive requires a human to sign in and click Allow. *Private
housekeeping, not a credential — don't commit it, don't paste it into a chat, don't lose sleep.*

And the line that closes the section: **they have granted nothing yet.** They registered an asker.
Nobody has said yes.

## Part C — the token

**8.7 — the checker, run by them.** While you work, they run `check_setup.py` themselves. Make
sure they do; it's the thing that lets them walk away and come back next week.

**8.8 — the one screen where a human decides.** You run `authorize.py`; a browser opens on
Google's own page; they sign in with the same school account. Then **tell them to stop and read
the permission screen before clicking Allow.** That instruction is the exercise. Almost everybody
clicks past it, and the reveal only works if they didn't.

When they've clicked Allow, the reveal — and this is the heart of the module. Look at what did
*not* happen: **they did not type their password into the helper, into Claude, into their
terminal, or into anything written by anybody at their school.** They typed it into Google's own
page, and **Google, not the app, asked the question.** The program that wants access never sees
their credentials; it stands outside while they and Google talk, and gets handed a narrow pass at
the end.

If they saw *Google hasn't verified this app*: that was their own app, and *Advanced → Go to
(unsafe)* was right. Say the rest of it too — **notice how that warning feels**, because they'll
meet it again on somebody else's app, where it deserves more suspicion than it just got.

**8.9 — two files that look alike.** They ask; you explain, in the terms the prompt asks for
(*as if I were handing my laptop to a colleague*). **Don't print either file.** The token file is
the one that matters: copy it to another computer and that computer is them until somebody
revokes it, it doesn't expire on its own, and it isn't tied to their laptop. *Never emailed,
never in a shared folder, never committed.*

Then `.gitignore`, which they open themselves. Look at how it's written: it excludes **everything**
in the folder and names the two harmless files back in. Deny by default, because the next API
drops a credential file with a name nobody predicted. **When the cost of forgetting is high,
arrange things so forgetting is not possible.** That sentence is worth more than the exercise.

## Part D — using it, and taking it back

**8.10 — the global memory file.** Show them exactly what was added to `~/.claude/CLAUDE.md` and
explain the rules in it — only touch files I name, show me destructive changes first, drafts
never send. Make sure they notice these are **instructions to Claude, in plain English, in a file
they own, and they can change them.**

Then a **new** Code session, any folder, and the question that failed at the start. Same as at
8.3: before they go, tell them exactly what to type there to pick the module back up (**continue
Module 8**). The point to
name: **the new session knew.** They didn't point it at the helper. It read the global
`CLAUDE.md`. (If it didn't, that's the ninth troubleshooting row — the global file is read once,
at the start of a session.)

**8.11 — writing back.** The Summary tab, in their practice sheet, invented names. The prompt
says *tell me what you are going to write before you write it* — **do that properly**, and then
let them watch the sheet change in the browser.

Then the weight of it, which the page states better than a summary would: the same sentence that
added a harmless tab could have cleared one. **The token says write, so the safety is no longer
technical** — it's that they asked to see the change first, and that the rules in their
`CLAUDE.md` tell you to offer. *A real safeguard, and also only a convention.*

**8.12 — revoking.** `myaccount.google.com/permissions`, find their app among everything they've
ever signed in to, read what it can do, **don't remove it** unless they want to run 8.8 again.
Suggest they scroll the list; most people find things from years ago still holding access.

The property to name: **removing an app here kills the token instantly and everywhere** — every
copy, every machine, whoever holds it. No file to find, no password to change. And the test to
carry forward: *can I take this back without breaking everything else?* **If a system ever wants
their actual password instead, its author skipped this and they're carrying the risk.**

**8.13 — the shorter way, honestly.** Have them switch on the Drive connector and ask the 8.1
question again. Then the comparison, without defending the ninety minutes:

- **A connector signs Claude in.** It works while there's a conversation. For "go and do this to
  a Drive file in front of me", it is **better** than what they built — faster, nothing to
  maintain, nothing on the laptop.
- **Their token signs their program in.** Which is what anything running without them needs: the
  letters generated at six in the morning, the sheet checked every night, the tool a colleague
  runs against their own account. **No conversation, nothing for a connector to hang on.**
- **Their token's reach they chose.** The connector's reach is whatever it asks for.
- Identical where it counts: both appear in the same permissions list, removable by the same
  button.

Aside 6 is the answer, and it isn't a compromise: **connector for now-work, own credentials for
things that keep working after the laptop closes.** Most people end up with both.

## The ending

1. Section 11: what they learned isn't about Google. **Every serious system the school runs has
   an API and nearly all work this way** — register, sign in once, hold a narrow token. The
   screens have different names; the shape doesn't change.
2. Offer the "I want to reach [system]" prompt, and then say aside 7 plainly, because it is the
   most important sentence in the module: **the last question in it is not a formality.** Their
   Google token reached their own Drive, which was always theirs. A token for the student
   information system may reach every family in the building, *and that is not a decision to make
   quietly because it was technically easy.* Whoever owns that data should know before they ask
   for a key to it.
3. The held question, word for word, then their task list (ten).
4. Next: Module 9, *Where school data is allowed to live* — they are now holding a working key to
   a real system, which is exactly why everything here used invented names.
5. The assignment: the thing they've been putting off because it was too repetitive. Smallest
   version, made-up data.

## What goes wrong, and what to do

The page's table (section 12) is long and precise. **Run `check_setup.py` before diagnosing
anything** — it catches most of it and names the next step. Beyond that:

- **They ask you to do a browser step.** Don't, and say the true reasons rather than "I can't":
  there is no command for the consent screen or the Desktop client, and even where a browser tool
  could click through, those screens are their decisions on their own account (the figure in
  section 5). Then tell them how few browser stops are left.
- **They paste a credential, a token, or a password into the chat.** Say so at once. A password
  means change it now, in the order under *Credentials* above. A token means revoke it at
  `myaccount.google.com/permissions` and run 8.8 again. The client file is the exception (8.6).
  Don't repeat the value back. When a safety fix and the next step both need saying, the fix
  comes first and the reveal can wait for the next message.
- **They get lost in the console.** Google moves these screens. Ask what's on their screen rather
  than insisting on the page's wording, and check the project selector is showing their project —
  that's behind two different troubleshooting rows.
- **A week later it breaks.** Almost always External-in-Testing's seven-day expiry. Get them onto
  Internal if their account can.
- **They want to point it at a real sheet "just to see"**, or because they genuinely need it. No,
  not in this module, and the reason is better than the rule: Module 9 exists because that
  question is harder than it looks. Don't make it sound like a no forever: after Module 9, using
  their own tools on real data for their real work is their school's decision, in writing, not
  yours or the tutor's. For now, ask what they need from the real sheet and have them add a few
  invented rows **shaped like it** to the practice sheet; build exactly that, so pointing it at the
  real one later is a small change.
- **They never want to use the token and just want the connector.** Fine, and say so. They still
  got the model of what's happening when they click *Sign in with Google*, which was the point.
- **Windows.** The browser errands are identical. The terminal commands differ (`py`,
  `.venv\Scripts\python`); the helper's `SETUP.md` is the authority, not this file.
