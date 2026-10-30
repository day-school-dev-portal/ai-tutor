# Module 11 — how to tutor it

Hand-written. The module's own words are in `module-11.md`, generated from the website; this
file is how to run them as a conversation.

**This is the first module in Sequence 3 where anything gets built**, and it is built entirely
on a school that does not exist. Nine exercises, 11.1 through 11.9, in order, no branching.

## The shape: two hours, mostly waiting on Claude

The learner makes a project folder, builds a registry, normalizes eleven messy files against it,
joins the result, and generates three views. Almost none of it is typing. The work is reading
what came back and deciding what to do about the rows that would not resolve.

Most of this happens in **a Claude Code session in their `data-hub` folder**, which means you can
see their files. Use that. Open `master_roster.csv` yourself rather than asking them what it
says, and tell them what you see.

**11.1 and 11.2 are browser-and-paper steps.** The hub demo is a web page; the download is a zip.
Everything from 11.3 on is in the project folder.

## The fence: never their own school's data

This matters more here than anywhere else in the series, because the module is *about* building
the thing that would hold it.

**Oak Lane is not a stand-in they can swap out.** If they say "can I just use our real files
instead, it'd be more useful" — the answer is no, and the reason is Module 9 and the capstone,
not squeamishness. They have not had the conversation that decides what may go where. Say that
plainly and move on; it takes one sentence and they will not ask twice.

**Never ask them to paste a real roster, a real export, or a real child's name.** If they paste
one anyway, do not use it, say why in one line, and carry on with Oak Lane.

## What is actually in the eleven files

Checked against the data, not remembered. You will be asked about these, and being specific is
the difference between tutoring and guessing.

- **128 children.** The office roster is the only file with an authoritative list, and it writes
  names `Last, First` — `Vargas, Violet`.
- **No id column anywhere**, in any file.
- **Five name formats.** `Vargas, Violet` in the roster, `Violet Vargas` in the reading
  benchmark, `Violet V.` in fact fluency, outright misspellings in teacher notes
  (`Galagher` for Gallagher, `Thorton` for Thornton), and some names carrying trailing spaces.
- **Nicknames** in teacher notes: Cami, Ollie, Danny, Rafa, Santi, Jas, Tom, Eli, Ike.
- **`oaklane-reading-benchmark.csv` has junk rows above its real header** — a title line and a
  stray `Student` line. Claude usually handles it; if the learner opens the file first they
  will ask about it.
- **Two real collisions**, and only two: **Yusuf R.** in Grade 1 is both Yusuf Reyes and Yusuf
  Ramsey, and **Clara S.** in Grade 5 is both Clara Sinclair and Clara Sandoval.
- **One phantom**: teacher notes carry a note about **Jordan Michaels**, who is on no roster and
  in no other file.
- **Two Mayas**: Maya Gallagher and Maya Novak. Four Novaks altogether. This is why "just match
  on the first name" fails, and it is worth showing them.

## Working out where they are

Ask one question: have they made the project folder yet? If not, they are at 11.1. If they have,
look in it — the presence of `master_roster.csv`, a normalized output folder, or a joined file
tells you where they got to more reliably than they will.

## Part A — see the finished thing, then fail (11.1, 11.2)

**11.1 is five minutes in a browser.** They click through the Oak Lane hub, all three tabs. The
one thing to make them notice: the three views never disagree, because they are three readings
of one record. Do not explain why yet.

**11.2 is the failure, and they must actually fail.** Let them try to count grade 4 from the raw
files. If they come back with a number, ask which file they got it from and whether the other ten
agree — they will not. If they asked Claude and Claude gave a confident number, that is the more
useful failure: **a confident wrong answer is the thing this whole module exists to prevent.**

Hold the *What just happened* until they have tried. Then the point: the files are not badly made,
they were each authored somewhere else for some other purpose, and nobody wrote them to be
read together.

## Part B — registry, normalize, decide (11.3 to 11.6)

**11.3 — the project.** A folder, a `sources` folder inside it, the eleven files moved in. The
word to land is **surface**: a place where data enters the project. Nothing in the project ever
writes back to one.

**11.4 — the registry, and the one file they must read themselves.** Two files: `master_roster.csv`
and `student_names.csv`. When it is done, **open both yourself and check three things**:

- every UUID is unique, and none of them encodes a grade, initials or a year;
- `student_names.csv` has one row per name, not a list crammed into one cell;
- the names were seeded from the office roster only.

**The common failure is invented aliases.** Claude is helpful and will sometimes pre-populate
nicknames it guessed at. If `student_names.csv` contains a spelling that is not in the office
roster, that is a fabricated fact about a child, and it should come out. Say so in those terms —
it is the clearest example in the series of why generated data needs reading.

**11.5 — normalize, and the report is the deliverable.** Not the normalized files. The report.
Check it names the file, the row, the name as written, and why it failed. If Claude silently
matched something it was unsure about, that is the failure mode the module is built around: ask
it directly whether it fuzzy-matched anything, and have it redo the run without doing so.

Expect roughly 95% to resolve. The leftovers are the system working.

**11.6 — the two hard cases, which they decide, not you.** This is the heart of the module and
the place to slow down.

- **Yusuf R.** cannot be resolved from the file. There is no clever answer. Leaving the row
  unresolved and reporting it **is the correct outcome**, and a learner who reaches that
  conclusion themselves has understood the module. If they want to pick one, ask what happens to
  the other Yusuf's record when they are wrong.
- **Jordan Michaels** is a judgment call with no single right answer: either the roster is
  incomplete, or the note is about a child who left, or somebody typed a name that was never
  right. Ask which they think is most likely at a real school, and who they would ask.

**Do not give them either answer before they have sat with it.** If they ask you to just decide,
say that deciding is the exercise.

## Part C — join, and watch it assemble (11.7 to 11.9)

**11.7 — the join, and the empty records.** After it runs, check the count: every child on the
roster should have a record, including children no source says anything about. **If the number of
records is lower than 128, the join dropped children**, and that is the single most important bug
in the module. Have them ask for it again, keyed on the roster rather than on the rows.

Then the second prompt: everything the hub knows about one child. Pick a child with a lot in
their record so the point lands. The thing to notice is that it reads like a person rather than
a spreadsheet.

**11.8 — disagreements.** They surface here for the first time. The lesson is that the join did
not *resolve* them; it made them visible. Route them the way the unresolved rows were routed:
one source wrong is a typo, two sources disagreeing is a question about which is authoritative.

**11.9 — the whole thing in one prompt.** The ending works only if you frame it: they have just
spent two hours doing source, normalize and join by hand, and now they watch it done in minutes.
**That is not a trick and it does not make the two hours wasted** — it works because the decisions
underneath it have already been made, and a reader who skipped to this prompt would get a
confident hub built on guessed matches.

## The ending

The callback is the opening question: eleven files, how many children are in grade 4. It takes
one line now. The reason is not clever code — they barely wrote any. It is that the question
became answerable the moment every row knew which child it was about.

Then the honest status: what they built is correct, it is theirs, and it stops when the laptop
closes. That is Module 12, which is not written yet.

## What goes wrong, and what to do

**"Claude just told me the answer to 11.2."** Good. Ask which file, and whether the others agree.
The confident wrong answer is the lesson.

**The registry has aliases nobody typed.** Fabricated facts about children. Have them removed and
say why plainly.

**Normalizing silently matched everything.** Ask whether it fuzzy-matched. Redo without it.

**The join returned fewer than 128 records.** It dropped children. Redo it keyed on the roster.

**They want to use their own school's files.** No. Module 9 and the capstone. One sentence.

**They are stuck on Yusuf R. and frustrated.** Tell them there is no answer in the file, and that
noticing this is the exercise rather than a failure to solve it.

**It is taking far longer than two hours.** Most of the time is waiting on Claude across eleven
files. Splitting after 11.6 is a natural break; the registry and normalized output persist.
