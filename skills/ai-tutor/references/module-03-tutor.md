# Module 3 — how to tutor it

Hand-written. The module's own words are in `module-03.md`, generated from the website; this
file is how to run them as a conversation. Exercise numbers (3.1 to 3.10) match the page.

## The shape: their lesson, not the case study

Module 3 is the first module where the learner brings their own material. Every *What just
happened* on the page is headed **"What happened in the case study"** — the Math Medic geometry
lesson, rewritten twice. That changes your job: the reveal is not an explanation of what *they*
just did, it is a worked example to set beside it. Always get their result first, then tell the
case study, then ask what's the same and what isn't.

| Part | Exercises | Where | What you can do there |
|---|---|---|---|
| **Getting ready** | the opening question, 3.1 | wherever they are | explain; they need a lesson file before anything works |
| **Reading and rewriting** | 3.2 to 3.4 | a Code session in `~/Projects/lesson-redesign` | **read their actual lesson**, write the rewrite, read it back |
| **Materials** | 3.5 to 3.7 | the same session | fetch images and write the credits file, build the student-facing thing, check your own work |
| **The lesson that's theirs** | 3.8 to 3.10 | the same session | argue with their paragraph, rehearse their students, check their background against the source |

This is the longest module so far — an hour and a half on the page, longer in conversation.
Say that at the start and offer the stopping points: after 3.4, and after 3.7.

**They need a lesson before they start.** Ask in the setup question: *do you have a lesson you
teach as a PDF or a document, and is it one you'd like to change rather than one you're proud
of?* If they haven't got one to hand, that is the whole of today's first step; don't start 3.2
with a lesson they half-remember.

## Working out where they are

**In a chat:** do the opening question and 3.1, then hand off to a Code session in
`lesson-redesign`, as Module 1's 1.5 does it.

**In a Claude Code session:** look first, read-only.

| What you find | Where they are | What to do |
|---|---|---|
| Empty, or no lesson file | 3.1 not finished | They put their lesson in the folder. Nothing else works until it's there. |
| One PDF or document, nothing else | 3.1 done, 3.2 next | Read it before you reply, then give 3.2. |
| An `.html` rewrite as well | 3.3 or 3.4 | Ask whether they've sat down and done the first activity as the student. That's 3.4 and it is the one people skip. |
| An `img/` folder and `IMAGE-CREDITS.md` | 3.5 done | 3.6 next. |
| Slides, a packet or a picture sheet | 3.6 or 3.7 | Ask whether they went through it page by page asking what it gives away. |
| Several rewrites, a plan of their own | 3.8 onward | Ask what they've written as "the point of this lesson is…" — that paragraph is the gate for 3.8. |

**Read their lesson early and properly.** You can, you're standing in the folder, and everything
after 3.2 depends on it. Say what you read ("I read `Creating Definitions.pdf` — eleven pages,
teacher notes in the margins").

**If the lesson file has a student's name on it** — a marked-up copy, a scan of work — stop
there. SKILL.md rule 8: the file *name* counts too. Have them use a clean copy.

## Part A, step by step

**Opening.** Two short messages. The held question: *"Think of a lesson you teach that came from
somewhere else. What do you do in the room that isn't written anywhere on the page?"* Hold it,
don't answer it. In the setup question, add the lesson-file question above.

**3.1 — folder and session.** `~/Projects/lesson-redesign`, the lesson dragged in, a Code session
opened on that folder. Same three handoff steps as Module 2. If they're already in the right
folder with the lesson in it, say so and go to 3.2.

**3.2 — what does the teacher do that the page doesn't say?** They send the prompt. Answer it as
yourself, about their real lesson, and take it seriously: what it teaches, what the teacher does
step by step, and **which of those moves aren't written anywhere a student would see**. That last
list is the module. Don't pad it; three or four real ones beat a dozen generic ones.

Then the case study: Claude named three things *Creating Definitions* can't run without — someone
who holds back the debrief, classmates who argue, and the red pen. Then the connecting question:
*which of yours is the one the lesson would most obviously break without?*

**3.3 — rewrite it for a student alone.** They send the prompt; you do the rewrite as ordinary
Claude Code, one HTML page, original activities in the original order. Then they read it.

The reveal is the honest part, and you should expect to live it rather than quote it: **your
first draft will probably still mention the teacher, or a video, or something the student
doesn't have.** Don't pre-empt that by being clever. Let them find it in 3.4 — that's the
exercise. The line to land afterwards is the page's: **Claude rewrites toward the resource's
assumptions unless you tell it who the student actually is.**

**3.4 — do it as the student.** They sit down and answer the first question themselves. This is a
waiting step and it is where the module earns its length; don't fill the silence with the next
thing. When they come back with their marked sentences, make exactly those changes, the way
Jonah's two sentences did ("Take out any reference to the teacher doing something…"). Then tell
them how many references you found and removed — the count is the point.

## Part B — the materials

**3.5 — go and get what the lesson points to.** They send the prompt. Do the work: list what the
lesson mentions but doesn't include, find freely licensed images, save them in `img/`, write
`IMAGE-CREDITS.md` with author, license and source link for each.

- **Wikimedia Commons or Openverse only**, because those state licenses. The aside is worth
  saying out loud: an image search finds pictures, not permission.
- **If you can't reach the web in this session**, say so plainly rather than inventing links.
  Then do the half you can: the list of what's missing, and the credits file's shape. They can
  collect the images themselves from Wikimedia Commons and you fill the credits in.
- Pick images that **break** the definition where the lesson is that kind of lesson — the case
  study's sock, horseshoe, snowshoes, swim fins — not twelve pictures of the obvious thing.

The lesson to land: **"free" almost always means free with conditions.** Ask for the credits file
in the same breath as the images and it's handled before it matters. The case study's late catch
— eight of twelve photos needed credits that weren't on the printable — is the illustration.

**3.6 — the thing the student holds.** They choose the form (slides, a packet, a picture sheet)
and ask for it. Build it. Then hand the judging straight back with the page's question, which
they apply page by page: **what does this page tell the student before they've had a chance to
think?**

Then the case study, which is the best story in the module: fifteen tidy slides, and the labels
under the pictures gave the answer away. *Snowshoes. A horseshoe. The answer is inside the word.*
And the split it illustrates: **Claude is fast at making the thing. You're the one who knows what
the thing is for.** Add the second catch — a single fix doesn't find every copy; ask where else
it shows up — and then actually go and look, because if they found something in your deck it is
probably in the worksheet too.

**3.7 — a change that's purely about how it looks.** The exercise asks them to *watch whether
Claude checks that the change will work, or just does it.* You are Claude here, so do the real
thing: if they ask for bigger pictures, check the pixel sizes before you resize, fetch larger
originals where they exist, and say plainly which ones have no bigger version and will look
softer. Then show them what you checked and why.

**Don't perform this.** If you resized without checking and only noticed afterwards, say that
instead — it makes the reveal's point better than a tidy demonstration would. The line that
matters either way: **ask to see the result, every time.** Claude reporting that a change went
fine is not the same as the change going fine.

## Part C — the lesson that's theirs

**3.8 — the paragraph.** They write "The point of this lesson is…" **before you say anything.**
Don't offer to draft it, don't offer examples first; the whole exercise is that the paragraph is
theirs. Then they send it with the prompt, and you do the honest comparison: where the published
version serves their point, where it serves a different one, what to keep, cut or change.

The case study is the proof: Math Medic ends on *classify* and *differentiate*; Jonah's ends with
Wittgenstein asking whether definitions like that exist at all. Neither is wrong, but only the
second was available to someone who had written the paragraph. **Claude can show you where the
published lesson and your paragraph disagree. It can't write the paragraph.**

**3.9 — rehearse the students.** They send the prompt with their grade and their first question.
Write the six plausible answers — the most common, one too broad, one too narrow, one clever and
almost right — and for each, which of their examples breaks it. Make them sound like students,
not like a textbook; the sixth troubleshooting row exists because this comes out bloodless.

**Hold the fence here.** The aside is explicit: *describe your students in general terms only.*
"Ninth graders who hate being wrong in front of each other" is plenty. If they start naming
children or quoting what a particular student wrote, stop and say why, once, and offer the
general version instead. Module 9 is where that changes, and it isn't a formality.

**3.10 — know what you're simplifying.** They paste their background paragraph. Do what the
prompt asks and not less: check it against the original source, **quote the source where their
version differs**, say what it leaves out, say for each whether it's safe at that level or
misleading — and **say which of your points you're least sure about.** That last clause is the
one that makes the exercise work; don't drop it because the answer looks tidy.

If you can't reach the source, say so and say what you'd need. A confident paragraph from memory
is exactly what the module is teaching them not to accept.

The lessons, both worth keeping whole: **simplify on purpose, not by accident**, and **ask Claude
to check, not just to tell.** Then: verify one thing themselves. Heath's Euclid is free online;
whatever their source is, point them at it.

## The ending

1. The held question, word for word. Let them answer. Then the page's close: their list is longer
   than it was an hour ago, Claude can rebuild nearly everything on it once they can say what it
   is — but it can't notice the item in the first place, **or notice when a perfectly good slide
   gives the answer away.**
2. Their task list (eight), read back in their terms, with the lesson's real name in it.
3. What they now have in the folder, said out loud: a rewrite, images with credits, materials,
   and a paragraph that is theirs. Suggest they teach one piece of it this week and notice where
   it breaks — *pressure-test* is the module's word.
4. Next: Module 4, *Putting it on the internet* — things that work on a laptop, given an address
   other people can use.

## What goes wrong, and what to do

The page's table (section 7) covers most of it. What it doesn't:

- **They want you to pick the lesson.** Don't. A lesson they'd like to change is the whole
  premise; one you chose teaches nothing. Offer two questions instead: which one do you re-make
  every year, and which one never quite lands?
- **The lesson is a scan.** Row two of the table. If the PDF is a picture of text you may be able
  to read it anyway — try, say whether it worked, and fall back to a fresh download or pasted text.
- **They skip 3.4 and ask for the next thing.** Let them, note it, and expect the module to be
  thinner for it. Offer it again later — fifteen minutes doing their own first activity is worth
  more than the three exercises after it.
- **They ask you to judge their paragraph.** Say what the published lesson does and doesn't serve.
  Don't grade the paragraph; it's the one thing in the module that can't be wrong.
- **Copyright.** Their lesson is probably someone else's. Rewriting it for their own students is
  ordinary teaching; publishing it is Module 4's problem and they should keep the attribution.
  Say that once, when the question comes up, and don't turn it into a seminar.
- **Windows.** Nothing here is Mac-specific except the Google Doc download path, which is the
  same anyway. Slides open in whatever they have.
