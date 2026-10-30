# Module 11 — Building the hub: the page's text

Generated from `dev-portal-site/modules/11-building-the-hub.html` by `tools/make-tutor.py`. **Do not
edit this file;** edit the page and regenerate, or the tutor and the website will
teach different versions of the module.

This is every word learners see on the website, in order. How to read it:

- **Try it yourself N.N** blocks are what the learner does.
- **What just happened** blocks are the explanation. Hold each one back until
  the learner has done the exercise before it.
- Blockquotes under **Ask Claude** are prompts the learner types to Claude.
- **Side note** blocks are asides. **Figure** blocks describe a drawing in
  words; describe it if it helps, since the learner cannot see it here.
- The **Module tasks** list is what "done" means for the module.
- Fenced blocks are terminal commands. This module has none.

---

## **Cover ^cover**

**Series line** — Developing with AI · A series of modules

**Module number** — 11

**Title** — Building the hub

**For** anyone who has finished Module 10 **Time** about two hours, in two sittings if you like **You need** Claude Code, a terminal, and the Oak Lane files. No school data of your own, and that is deliberate.

---

**Label** — Before you start

Module 10 left you holding four decisions and nothing built. This is where they get spent.

You are going to take eleven exports from a school that does not exist and turn them into one place where a teacher can find out how a child is doing. Every stage you were told about, you will do: source, normalize, join, view.

*This line sits alone in the clay-bordered box:*

Eleven files, one question: **how many children are in grade 4?** Write down how long you think that should take.

Nothing in this module touches a real child. Oak Lane has a hundred and twenty invented students, their scores generated from a fixed seed, and no record from any real school was read to make them. That is not a limitation of the exercise — it is the point. By the time you point any of this at your own school you will have done it once, in a place where being wrong costs nothing.

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 8 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**Surface** A place where data *enters* your project — a MAP export, a report card PDF, the qualitative notes spreadsheet. *Note:* Humans write to surfaces. They write nowhere else in the hub, and that one rule prevents most of what goes wrong.

**Registry** The two files that say who exists: `master_roster.csv`, one row per child, and `student_names.csv`, one row per name a child is known by. *Note:* You met these as a decision in Module 10. Here you build them.

**Resolve** To work out which child a row is about, and attach that child's UUID to it. *Note:* By exact name, by a recorded alias, or not at all.

**Normalize** Making every surface say the same thing the same way, and attaching a UUID to every row. *Note:* The step where the hub is won or lost.

**Unresolved row** A row that matched nobody, or matched more than one child. *Note:* Set aside and reported, never guessed at. These are not failures of the system. They are its output.

**Join** Gathering every row that shares a UUID into one record per child. *Note:* No human ever writes to a join.

**Record** Everything the hub knows about one child, in one place. *Note:* Not a spreadsheet row — one roster entry holding lists of test sittings, attendance days and notes.

**View** A reading of the joined records, generated and never maintained. *Note:* School, My Class and Student are three views of one record, which is why they cannot disagree.

## **Section 1 — Look at this first ^sec1**

**Heading** — Look at this first

Before any of it, go and look at what you are building toward.

### **Try it yourself 11.1 ^try-11-1**

Open the Oak Lane student hub and spend five minutes clicking. Use all three tabs. Pick a child on the School tab and follow them through to their own page.

Then notice one thing deliberately: **the three views never disagree.** A child who looks fine at the school level looks the same on their own page, because all three are readings of one record rather than three things somebody maintains.

That hub was built from eleven files. They are below, and they are a mess.

## **Section 2 — Watch it fail ^sec2**

**Heading** — Watch it fail

### **Try it yourself 11.2 ^try-11-2**

Download the Oak Lane source files — eleven exports from a school that does not exist — and unzip them into a folder. Don't open them in a spreadsheet yet. Just look at the list of filenames, then answer one question on paper:

**How many children are in grade 4?**

Now open the files and actually try it.

**Ask Claude**

> Here is a folder of exports from different school systems. Without changing anything, tell me: how many distinct children appear across all of these files, and how confident are you?

### **What just happened ^reveal-r1**

**Button hint** — Try to answer it yourself first. Five minutes is enough to feel it.

You could not answer it, and neither could Claude — not honestly.

Count the ways those eleven files disagree. **Five formats for a name**: the office roster says "Vargas, Violet", the reading benchmark says "Violet Vargas", fact fluency says "Violet V.", teacher notes misspell a surname outright ("Galagher" for Gallagher), and somewhere a name carries a trailing space you cannot see. **Five formats for a grade**: 4, Grade 4, 04, Fourth, G4. **Four formats for a date.** And the thing that matters most — **no id column anywhere.** Eleven files about the same 128 children, and not one of them says which child a row is about in a way a program can trust.

This is not because Oak Lane is badly run. It is because each of those files was authored by a different system for a different purpose, and none of them was written with the other ten in mind. Your school's files look exactly like this.

## **Section 3 — Four stages, and why the order is fixed ^sec3**

**Heading** — Four stages, and why the order is fixed

So far you have met two of them. **Entering** is how data gets into the system and **viewing** is how it comes out — the beginning and the end. There are two more, and they sit between.

- **Source** Eleven surfaces, each authored somewhere else. You do not control their shape and you should not try to.
- **Normalize** Every row resolved to a child, every date and grade made to say the same thing the same way.
- **Join** Everything that shares a UUID gathered into one record per child.
- **View** School, My Class, Student — generated from the records, never maintained by hand.
The order is not a style. Each stage is only cheap because the one before it happened: the join has nothing to get wrong because normalizing already spent the judgment, and the views cannot disagree because they are three readings of the same join.

## **Section 4 — Make the project ^sec4**

**Heading** — Make the project

With the three disciplines in mind, you're ready to start building. You are building it on your own laptop for now — Module 12 is about moving it somewhere it can run without you.

First, create a new project — an empty folder — in your projects folder. You can call it whatever you want. Ours is named `data-hub`. This is where you will put all the files related to this project.

### **Try it yourself 11.3 ^try-11-3**

Make the folder, then make a folder inside it called `sources`, and move the eleven Oak Lane files into it.

**Ask Claude**

> I'm building a student data hub in this folder. The files in sources/ are exports from different school systems. Don't change them — they are surfaces, the places data enters the project, and nothing in this project should ever write back to them. Just tell me what you see: what each file appears to be, and what it uses to identify a student.

### **Side note ^aside-1**

**Which sources go in is Module 10's question, not this one's.** Sorting them — external or internal, quantitative or qualitative — is how you decide what belongs in a hub at all, and that decision comes before the building. Each file you put in `sources` is a **surface**: a place where data enters your project.

## **Section 5 — Build the registry ^sec5**

**Heading** — Build the registry

You need a student registry with UUIDs. This source of truth determines which students exist, and makes sure you can connect student data to the correct record across sources and projects.

Oak Lane has an office roster, which is the closest thing it has to an authoritative list. That is where the registry comes from.

### **Try it yourself 11.4 ^try-11-4**

**Ask Claude**

> Build me a registry from sources/oaklane-office-roster.csv, as two files in the project root. master_roster.csv: one row per child, with a generated UUID, their official name, grade and status. student_names.csv: one row per name a child is known by, with the UUID, the name, and which file that spelling came from. Seed student_names.csv with the names exactly as the office roster spells them. Do not invent aliases.

Open both files and read them. **This is the only moment in the module where you should read a file Claude made, line by line.** Everything downstream trusts it.

### **What just happened ^reveal-r2**

**Button hint** — Open the two files first

You now have the thing Module 10 asked you to decide about, built. Notice three properties it has.

**The UUID says nothing.** No grade, no initials, no birth year. That is deliberate — anything descriptive in an id eventually becomes wrong, and then you have a lie that looks like a fact.

**There are two files, not one.** The aliases are rows, not a list crammed into a cell. A cell with five names in it looks tidy and is unusable: nothing can search it reliably, and every program that reads it has to re-invent how to split it.

**`student_names.csv` is append-only.** When you discover a new spelling, you add a row. You do not edit a row and you do not delete one — because the moment you delete "Galagher, Maya", every historical file still containing that misspelling stops resolving, and three years of her reading scores silently vanish from her page. Old names cost nothing to keep. Removing them breaks the past.

## **Section 6 — Normalize ^sec6**

**Heading** — Normalize

Before any of this can be joined, something has to decide that the "Gallagher, Maya" in one file and the "Galagher, Maya" in another are the same child. That step is called **normalizing**, and it is where the whole hub is won or lost.

**Normalizing is the step where every surface is made to say the same thing the same way, and — above all — where every row is attached to the UUID of the child it is about.**

Not the child's name. The UUID. Names drift: children go by a nickname from October, a surname gets misspelled once and copied forever, two children in the same grade genuinely share a name. A UUID is assigned once, never reused, and never changes. After normalizing, every spelling of Maya Gallagher points at one id. Every one of her rows carries the same string of characters, and the question "how many children are in grade 4" has one answer.

### **Try it yourself 11.5 ^try-11-5**

**Ask Claude**

> Normalize every file in sources/ against the registry. Attach the right UUID to each row. Make dates and grade labels consistent. Write the results somewhere new — never back into sources/. Then give me a report: how many rows resolved, how many did not, and for every row that did not, the file, the row, the name as written, and why it failed.

Read the report before you read anything else.

*A row that does not resolve to exactly one child is set aside and reported. It is never guessed at.*

Normalizing the Oak Lane files will leave you with two piles of trouble, and they are different kinds:

**A name that matches more than one child.** `fact-fluency.csv` identifies every child as "First L." — and in Grade 1 two children are "Yusuf R.", Yusuf Reyes and Yusuf Ramsey. A fuzzy match would pick one, probably the first, and be wrong about half the time, invisibly, forever. The honest system refuses, names the file and the row, and asks a human which Yusuf this is. Whoever typed it knows. Nobody else does.

**A name that matches nobody.** `teacher-notes.csv` carries a thoughtful note about Jordan Michaels, who appears in no other file and is not on the roster. Either the roster is wrong, or the note is about a child who left, or somebody typed a name that was never right. All three are worth knowing and none of them is fixable by a program.

Notice these two failures route to **different people**. An unreadable name goes back to the person who wrote it. A child the roster has never heard of goes to whoever owns the roster — and that is a conversation about the surface, the source of truth, not about a spreadsheet. Build the report so it says which, because a list of 40 problems with no owner gets ignored, and a list of 6 problems addressed to the person who can fix them gets fixed.

Expect to resolve 95% of rows automatically, spend an afternoon on the rest, and never have to do it again at that scale. **The leftovers are not a sign the system failed. They are the system working** — those rows were always wrong, and the only change is that you can now see them.

### **Try it yourself 11.6 ^try-11-6**

Resolve the two hard cases yourself, the way a school would.

For the ambiguous "Yusuf R.", you cannot know which child is meant — so decide what the honest thing to do is, and tell Claude to do that. For the note about a child who is not on the roster, decide which is more likely to be wrong: the roster, or the note.

**You are allowed to leave a row unresolved.** That is a real answer, and the report is where it lives.

### **Side note ^aside-2**

**Why this comes before joining.** Once every row carries the right UUID, putting the sources together is no longer an act of judgment. It is just gathering rows that share an id — all the ambiguity has already been spent, in one place, in the open, by people who could resolve it. Skip normalizing and you have not avoided that work. You have smeared it across every question anyone ever asks the hub, to be re-decided, differently, each time.

## **Section 7 — Join ^sec7**

**Heading** — Join

Once all the data has been normalized, you can produce a join. This is the step that collects all the data points across the different surfaces. It creates one record per student, and lets you ask questions about a child across the records.

### **Try it yourself 11.7 ^try-11-7**

**Ask Claude**

> Join the normalized sources into one record per child, keyed on the UUID. Every child in master_roster.csv gets a record, even if no source has anything about them. Then tell me how many records you made, and how many of them are empty.

Then ask it about one child.

**Ask Claude**

> Tell me everything the hub knows about [pick a child from the roster]. Reading, math, attendance, what their teachers wrote. Don't summarize it into a verdict — lay it out and tell me where the sources agree and where they don't.

### **What just happened ^reveal-r3**

**Button hint** — Ask about a real child from the roster first

Three things to notice, and the third is the one that matters.

**The join was boring.** It had nothing to decide, because the deciding already happened. That is the whole argument for doing it in this order.

**The record is not a spreadsheet row.** Maya Gallagher has one roster entry, twelve MAP sittings across four years, a hundred and eighty attendance days and six teacher notes. Those do not flatten into a row without either throwing most of it away or inventing ninety columns nobody can query. A record is one child **holding lists**.

**Every child on the roster got a record, including the empty ones.** Join the obvious way — for every row, find the matching child — and a child nobody has written anything about simply does not appear. The one who moved in last month, the one who missed the testing window, the one whose teacher hasn't entered notes yet: gone, from a system whose entire purpose is noticing children. So the roster is the spine, and an empty record is useful information. It says *we have no evidence about this child*, which is very different from the child not existing.

### **Try it yourself 11.8 ^try-11-8**

**Ask Claude**

> Across the joined records, find every place two sources disagree about the same fact — a child in one grade here and another grade there, a name spelled differently, a date that doesn't line up. List them with the files they came from.

### **What just happened ^reveal-r4**

**Button hint** — Run it and read the list before opening this

Because the join pulls everything into one place, it also exposes where surfaces disagree. A child listed in 4th grade in one place and 5th in another. Joining pulls that together.

**The join did not resolve those disagreements. It revealed them.** Before the join, the contradiction existed and was unobservable — spread across two files nobody reads side by side. The join is the first moment anything could notice.

So treat "sources disagree" as a category of finding rather than a bug, and route it the way you routed the unresolved rows. One source wrong is a typo, and the person who typed it fixes it. Two sources disagreeing is a question about which one is the source of truth, and that needs somebody with the standing to answer it. You made that decision in Module 10; this is where you find out whether it holds.

### **Side note ^aside-3**

**A view will always pull from a join.** A valid join is normalized and free of contradiction, so what you are looking at reflects the most up-to-date state of the whole project. **No human ever writes to a join.** Humans only write to source surfaces.

And the rule that follows from it, which is the one that bites years later: **a join never reads from a view.** The chain runs one way, source → normalize → join → view. The moment a join reads a view you have bent that line into a circle, and today's record depends on yesterday's rendering. It is tempting because it works — somebody already has a nicely shaped sheet with exactly the columns you need. It keeps working, too, right up until that view goes stale or its definition changes. Then the error is baked into the record itself and copied into everything downstream, with no file left to point at and say *this is what was true*.

## **Section 8 — View ^sec8**

**Heading** — View

In a module about using AI to build a student data hub, you might be surprised there has been so little AI so far. But AI can organize and build for you; it cannot replace your decision making and discipline. Until now you have been organizing. Now you are ready to view.

Think about how you want to interact with the data you have collected. Look back at the Oak Lane hub from 11.1 for inspiration, then point Claude at your project and describe what you want.

### **Try it yourself 11.9 ^try-11-9**

Ask for the whole thing in one go — and watch it do in a few minutes what took you the last two hours. That is not a trick: it can only do it because the decisions underneath it have already been made.

**Ask Claude**

> I have folders of exports, one per system the school already uses — a testing vendor's MAP files, DIBELS, AVANT Hebrew, the Blackbaud gradebook and attendance, and teachers' own written notes. Each folder is messy in its own way and names the same children slightly differently. Build me one internal website for staff. First, resolve every row to a child by a single stable student id. Match on exact name or a recorded alias; a row that matches nobody is set aside and reported, never guessed at. Then join the resolved sources into one record per child, and generate all the views from that record — never maintain a view by hand. Three views, one record read at three distances. School: how is the whole school doing? Pick an assessment, see the distribution by grade, and a watch list of the students that view would raise. Clicking a band gives you the children in it. My Class: pick a section, one line per child, sorted so the ones who need a look come first. Organized by area — reading, math, Hebrew, classroom, attendance — not by which system the number came from. Every name links through to the student. Student: one child, every source, one page. The three must never be able to disagree. Make it look like the New York Times op-ed page, not a dashboard. White background, a serif for headlines (Playfair Display or similar), a clean sans for body text, real paragraph-sized type rather than dense UI text. No cards, no boxes, no shadows, no rounded corners — hairline rules and whitespace do the dividing. Numbers set large in the serif. Color only where it carries meaning, one accent and one alarm, never for decoration. It should read like something written, and print cleanly.

When the build finishes you will have a working data hub that pulls together everything you chose to include, in one place.

## **Section 9 — What this does not yet do ^sec9**

**Heading** — What this does not yet do

Your hub works. It also stops the moment you close your laptop, which makes it a very good demonstration and not yet a thing a colleague can depend on.

Two things are missing, and they are the next sequence.

**It does not run without you.** Nothing updates when a new export arrives. Somebody has to open a terminal, which means it is your job forever.

**It will fail quietly.** This is the one worth carrying. When a pipeline like this breaks, it rarely announces itself — a pointer still aimed at last year's file, an export whose settings changed, a job that reports success while reading nothing. The hub keeps rendering, the numbers look reasonable, and somebody acts on them.

## **Module tasks ^checklist**

The 9 checkboxes near the end, in the order the module does them:

1. Clicked through the finished Oak Lane hub, all three views
1. Tried to count grade 4 from the raw files, and failed
1. Made the project folder and put the eleven surfaces in sources/
1. Built the registry — two files, and read them both
1. Normalized every surface against it, and read the unresolved report
1. Decided what to do about the two rows that could not resolve
1. Joined the records, and confirmed every child on the roster got one
1. Found a place where two sources disagree
1. Built the three views and clicked through my own hub

## **Section 10 — Before you finish ^sec10**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

Eleven files, one question: how many children are in grade 4?

Answer it again. It takes one line now, and the reason it takes one line is not that you wrote clever code — you barely wrote any. It is that the question became answerable the moment every row knew which child it was about.

Then notice which part of this you would not want to repeat by hand next September. That is the part Module 12 is about.

### **Side note ^aside-4**

**Next:** Module 12 — *Moving it off your laptop.* The same hub, on Google Cloud, updating itself while you are asleep. Buckets to hold the surfaces, scheduled jobs to keep them current, and what changes once it no longer depends on your computer being on.

Until then, the honest status of what you built: it is correct, it is yours, and it is one closed laptop away from being nothing.

## **Footer ^footer**

Developing with AI · Module 11. Every child in this module is invented; the mess is not.
