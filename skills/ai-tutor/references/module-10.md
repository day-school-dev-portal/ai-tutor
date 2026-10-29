# Module 10 — Deciding what is true: the page's text

Generated from `dev-portal-site/modules/10-data-architecture.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 10

**Title** — Deciding what is true

**For** anyone who has finished Module 9 **Time** about an hour, plus some conversations **You need** somewhere to write four decisions down, and colleagues you can ask

---

**Label** — Before you start

This is the only module in the series where you will not build anything.

That is deliberate. Every module after this one assumes a set of decisions have already been made at your school — and if they have not, what you build will be a faster way to be wrong. The decisions are not technical. Not one of them requires a computer. All of them require somebody to say a thing out loud and mean it.

So hold this question while you work, and you will be asked it again at the end:

*This line sits alone in the clay-bordered box:*

Your school already holds everything it needs to answer "how is this child doing." So why can't anyone answer it?

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 8 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**Source of truth** The one place a particular fact is written. Not the most accurate copy — the one everybody has agreed to believe. *Note:* Nothing becomes a source of truth by being correct. It becomes one because somebody said so, on a date.

**Registry** The source of truth for *who exists*: which children are enrolled, which staff work here. *Note:* It is the first one you will need, because every other fact is about somebody in it.

**Stable id** A permanent label for one person that is not their name. Assigned once, never changed, never reused.

**Alias** Another name the same person is known by — a nickname, a maiden name, a misspelling that got copied around. *Note:* Recorded deliberately, never guessed at.

**Entered** *(authored)* A sheet information is created in. Often ugly and hard to read, which is fine — its readers are mostly programs.

**View** A sheet or page built *from* entered sources. Generated, never maintained. You don't update a view; you rebuild it.

**Drift** What happens to a fact that lives in ten places. One copy gets corrected. The other nine don't, and nothing announces it.

**Cut-over** The day somebody declares that from now on, *this* is the source of truth. *Note:* The single most important event in this module, and the only one with a date on it.

## **Section 1 — Three questions your school cannot answer ^sec1**

**Heading** — Three questions your school cannot answer

Not won't. *Cannot* — not reliably, not quickly, not the same way twice.

Each of the next three is an ordinary question somebody at your school asks most weeks. Work through them in order. Each one is left unsolved on purpose, and each gets its answer later in the module.

## **Section 2 — Case 1 · The day the schedule changed ^sec2**

**Heading** — Case 1 · The day the schedule changed

It is a testing morning, so the schedule is different. At 7:50 a teacher asks where she is supposed to be at 10:00. Three people answer, and two of them are wrong — not carelessly. They are reading different copies.

The grid exists. It is in a Google Sheet somebody built, in a PDF attached to Thursday's email, printed on the staff room wall, and partly in people's calendars. The grid changed on Thursday afternoon. Two of those four copies know that.

### **Try it yourself 10.1 ^try-10-1**

Think of the last special day at your school — testing, an assembly, a half day, a snow delay.

Write down, in one line, **where the authoritative schedule for that day lived**.

Then ask two colleagues the same question, without showing them your answer.

### **What just happened ^reveal-r1**

**Button hint** — Ask the two colleagues first

One of two things. Either you got three different answers, or you got the same answer and then discovered that the copies do not match.

**Nobody did anything wrong.** Every person who made a copy had a good reason: they wanted it on paper, or in their calendar, or somewhere they could find it at 7:50 in the morning. The copies are not the failure.

The failure is that **no one ever said which copy wins.** With nothing to settle it, every copy is equally entitled to be believed — so the one you happen to be holding is, as far as you can tell, the schedule.

Hold on to this one. It is the clearest case in the module, and it is the one where being wrong puts two hundred children in the wrong room.

## **Section 3 — Case 2 · Is room 12 free at 10:30? ^sec3**

**Heading** — Case 2 · Is room 12 free at 10:30?

You want to run a makeup session tomorrow. Simple question.

There is a room calendar. But some people book through the office, which keeps its own sheet — and the classes that meet in room 12 every Tuesday are not booked at all, because they live in the master schedule, which is a different system entirely.

### **Try it yourself 10.2 ^try-10-2**

Pick a real room and a real time tomorrow. Find out definitively whether it is free.

**Time yourself.** Note how many places you had to look, and whether you ended up asking a person.

### **What just happened ^reveal-r2**

**Button hint** — Go and actually find out first

This one is different from Case 1, and the difference is the point.

In Case 1 there were four copies of a fact. Here, **nobody can write the fact down at all.** "Room 12 is free at 10:30" is not something anyone could author even in principle. It is the *absence* of bookings, across three systems, at one moment in time.

The only honest way to know it is to work it out from what *is* booked. And the instant somebody keeps a tidy list of free rooms by hand, that list is wrong by Tuesday — and nothing announces that it has gone wrong. It just sits there looking helpful.

If you ended up asking a person, notice what you were really doing: running the calculation in someone's head, because no system was doing it for you.

## **Section 4 — Case 3 · Which placement list is final? ^sec4**

**Heading** — Case 3 · Which placement list is final?

It is June. The file is called `Placement 2026-27 v4 FINAL (post-committee) USE THIS.xlsx`.

There is also a v3 with one teacher's comments that never got merged, and nobody is quite certain whether the committee's last two moves made it into v4.

A row reads `M. Cohen → Davis`. There are two M. Cohens in that grade.

### **Try it yourself 10.3 ^try-10-3**

Find your school's placement file from last year. Count the versions — every copy, including the ones in email.

Then answer one question: **what made one of them final?**

### **What just happened ^reveal-r3**

**Button hint** — Count them before you open this

Two separate failures, in one file.

**Nothing inside a document can make it authoritative.** Not a filename, not a version number, not the word FINAL in capital letters. Only a person, at a specific moment, saying so. If you could not name the moment one of those versions became final, then none of them is final — they are just files with opinions in the filename.

**And "M. Cohen" was never a child.** It is a string of characters that happens to match two of them. A person reading that row can usually work out which Cohen is meant, from context, most of the time. A program cannot, and neither can a person who was not in the room.

Those two failures have two different answers, and you will meet both before the end.

## **Section 5 — One failure in three costumes ^sec5**

**Heading** — One failure in three costumes

Those three are not unrelated annoyances to be fixed one at a time. They are the same failure wearing different clothes, and the failure is this: **nobody decided.**

Not "nobody built the right system." Not "nobody bought the right software." Somebody had to say which schedule wins, somebody had to say that free-ness is calculated rather than written, somebody had to say that this file is now the placement — and in each case, nobody did, so the question stayed open and everyone resolved it privately, differently, every time it came up.

What follows are three disciplines. They are not technical practices. **Each one is a decision somebody at your school has to make**, and each one answers one of the three cases above.

Your data architecture is only ever as strong as your data discipline.

## **Section 6 — Discipline 1 · Single source of truth ^sec6**

**Heading** — Discipline 1 · Single source of truth

*Every fact is written in one, and only one, place.*

**This answers Case 1.** Four copies of the schedule, and no way to know which one wins — because nobody ever said.

A data hub is basically a list of facts about people. "Ben is in Mrs. Davis's class." "Ben's birthday is 11/15/2015." The single biggest obstacle to school data management is that these facts get duplicated.

Every year, teachers build a list of parent contacts for their own class, or a list of birthdays. The first time, they draw it from the school's information system. Over time, copies circulate.

And as lists are copied and recopied, **they drift**. Families move. Parents change their email addresses. But because that fact now lives in ten places, the correction reaches one of them. Staff begin to doubt what is in front of them, and wander around asking: *what was the spreadsheet with the accurate addresses called? Where is that again?*

The solution is to decide, as an organization, what the single source of truth is for each kind of information — and then to stick to it and keep it accurate.

Notice what kind of act that is. **It is a decision, not a discovery.** No file becomes authoritative by being correct. It becomes authoritative because somebody with the standing to say so said it, out loud, on a date.

Maintaining one is not a technical task either. It means making sure individuals do not create and distribute their own lists of organizational facts. When the source of truth is maintained and people know where it is, nobody ever again has to wonder whether what they are reading is current.

### **Try it yourself 10.4 ^try-10-4**

Find every place a parent's email address lives at your school. The information system. A class list. A room parent's sheet. Somebody's phone contacts. A mail-merge file from last October.

Write the number down. **Most people stop counting at four.**

### **Decide 10.5 ^decide-10-5**

**Write this one down**

Name, in one written line, your school's source of truth for **which children are enrolled**.

Then go and check whether it is accurate.

Most people discover that the thing they named is not the thing anybody actually uses — and that is a more useful finding than getting it right would have been.

## **Section 7 — Discipline 2 · Enter vs. view ^sec7**

**Heading** — Discipline 2 · Enter vs. view

*The sheet you author and the sheet you read are never the same sheet.*

**This answers Case 2.** Nobody could tell you whether room 12 was free, because "free" is not a fact anyone writes down.

Some sources are **entered**. Information is created in them. These are your single sources of truth, and they will often be ugly — dense, wide, hard for a human to read. That is fine. They exist to be a record of what is true, and their main readers are scripts and AI tools, not people.

Other sources are **views**. They pull from entered sources and present them however somebody wants to see them. A view is generated, never maintained. Nobody updates a view; you rebuild it, and it is correct because the thing underneath it is correct.

This distinction is what lets you stop fighting the impulse behind all those private spreadsheets. People made their own copies because the official sheet was unreadable — and they were not wrong to want something readable. The answer is not to forbid it. The answer is that **everybody can have the view they want, as long as nobody is typing into it.**

Room 12 is the pure case. "Free at 10:30" could not be authored even in principle: it is the absence of bookings across three systems at one moment. The only honest way to know it is to compute it from what is booked.

### **Try it yourself 10.6 ^try-10-6**

Name one spreadsheet you maintain by hand that is really a view of something else. Everyone has one.

How often do you update it — and **how would you know if it had gone stale?**

### **Decide 10.7 ^decide-10-7**

**Write this one down**

Take three sheets your team relies on. For each, write *entered* or *view*.

If a sheet is both — people type into it *and* read it — that is the one to fix first, and now you know why.

## **Section 8 — Discipline 3 · A stable id for every person ^sec8**

**Heading** — Discipline 3 · A stable id for every person

*Every person has an id that is not their name.*

**This answers the first half of Case 3.** "M. Cohen" was never a child. It is a string that happens to match two of them.

Your hub will hold thousands of individual facts. "Rebecca scored a 97 on her math test." But who is Rebecca? In one spreadsheet her surname is misspelled. In another she goes by Becca. And it may turn out your school has two Rebecca Millers.

A name is not an identity. It is a label that is *usually* unique, and that changes over time.

The solution is a **stable id** for every person. As far as the hub is concerned, a student does not exist unless they have one. There is nothing descriptive about it — no age, no grade, no name, no gender. That is the point. It says only *a student with this number exists*, it never changes, and it is never reused for anybody else.

You probably already have one. Most school information systems assign a permanent student id, and using theirs is usually better than minting your own: one fewer thing to keep in step.

**The registry is two files, not one.**

| File | One row per… | Holds |
| --- | --- | --- |
| master_roster.csv | child | The id, and their current official name, grade and status. This is the list of who exists. |
| student_names.csv | name a child is known by | The id, the name, and where that name came from. "Rebecca Miller", "Becca", "Rebeca Miller" and "Miller, Rebecca R." are four rows pointing at one id. |

Do not put the aliases in a single cell of the roster. A cell with five names in it looks tidy and is unusable — nothing can search it reliably, and every program that reads it has to reinvent how to split it.

### **Side note ^aside-1**

**student_names.csv is append-only.** When you find a new spelling, add a row. Never edit one, never delete one. The moment you delete "Rebeca Miller", every historical file still containing that spelling stops resolving — and years of her scores quietly disappear from her page, with nothing to tell you it happened. Old names cost nothing to keep. Removing them breaks the past.

### **Try it yourself 10.8 ^try-10-8**

Find two children at your school whose names collide, or one whose name changed mid-year.

Then find a spreadsheet that identifies children by name alone. That sheet cannot tell them apart — and neither can anything built from it.

### **Decide 10.9 ^decide-10-9**

**Write this one down**

What is your id going to be?

Check your information system first: if it already assigns a permanent student id, the answer is almost certainly *that one*.

Write down where it comes from, and **who can issue a new one**.

## **Section 9 — The cut-over ^sec9**

**Heading** — The cut-over

**This answers the second half of Case 3.** What made the placement file final?

Nothing inside a document can make it authoritative. Not a filename, not a version number, not the word FINAL in capitals. Only a person, at a specific moment, saying so.

The key moment for your school is the cut-over. That is the day you declare: *going forward, this is the source of truth for which children are enrolled.*

Do it too early, before the thing is accurate, and you have created one more unreliable list. Do it never, and you have a hub nobody trusts — which is the same as not having one.

Pick the date. Pick who announces it. Pick how people will be told. None of those is a technical question, and none of them is optional.

### **Decide 10.10 ^decide-10-10**

**Write this one down**

For the source of truth you named in 10.5: **what is the date it becomes authoritative, and who says so?**

If you cannot answer the second part, you have found the real obstacle — and it is not a spreadsheet.

## **Section 10 — What AI cannot decide for you ^sec10**

**Heading** — What AI cannot decide for you

Building a registry sounds daunting. Generating ids, making sure none collide, copying every record into a spreadsheet by hand — miserable work.

**That part AI does well.** Put your current messy files in a folder, point Claude at it, explain that you want a registry with a stable id for every child, and a while later you will have it. Module 11 does exactly that, start to finish, on a school that does not exist.

But notice what it cannot do. It cannot decide which source is the source of truth. It cannot tell you whether that source is accurate. It cannot pick the cut-over date, and it cannot make your colleagues use the thing once it exists.

Every one of the decisions you just made — 10.5, 10.7, 10.9, 10.10 — had to be made by a person with the standing to make it. That is why this module came before the one where you build anything.

**The tools are the easy half.**

**Ask Claude — to turn your four decisions into one page**

> I am setting up data discipline at my school. Here are four decisions I have made: [paste your answers to 10.5, 10.7, 10.9 and 10.10]. Turn these into a one-page summary I could hand to my head of school, written so somebody who has never thought about this can see what is being asked of them and why.

## **Section 11 — If you got stuck ^sec11**

**Heading** — If you got stuck

| You said | It means | Try this |
| --- | --- | --- |
| "Our information system is wrong." | Very common, and not a reason to pick something else. | A source of truth does not have to be accurate today. It has to be the thing you fix *into*. Name it, then make its accuracy somebody's job. |
| "Nobody will agree on one source." | The disagreement is usually about who owns the fact, not about which file is better. | Ask who is accountable when it is wrong. That person's system is almost always the right answer. |
| "I'm not the one who decides." | True for most people doing this module, and it is the actual finding. | Do 10.5 and 10.10 as a proposal rather than a decision, and take it to whoever does decide. The one-page prompt above is written for exactly that conversation. |
| "We have two systems and both are used." | You have two sources of truth, which means you have none. | Pick one per *fact*, not per system. Enrollment can live in one and grades in the other — what cannot happen is enrollment living in both. |
| "My id would just be the name anyway, we're small." | It works until the year it doesn't, and then it fails silently. | Two children shared a name at a 120-child school last year. Use the id your information system already assigns; it costs you nothing today. |
| "This feels like a lot of meetings." | It is four decisions, and you can make three of them yourself. | Only the cut-over genuinely needs authority. Do the other three now and bring them along as evidence. |

## **Module tasks ^checklist**

The 10 checkboxes near the end, in the order the module does them:

1. Asked two colleagues where the last special schedule lived, and compared the answers
1. Timed myself finding out whether one room was free
1. Counted the versions of last year's placement file
1. Counted the places a parent's email address lives
1. **10.5** — Named our source of truth for who is enrolled, and checked it
1. Named a sheet I maintain by hand that is really a view
1. **10.7** — Sorted three sheets into *entered* or *view*
1. Found two children whose names collide, or one whose name changed
1. **10.9** — Decided what our stable id is, and who can issue one
1. **10.10** — Set a cut-over date, and named who announces it

## **Section 12 — Before you finish ^sec12**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

Your school already holds everything it needs to answer "how is this child doing." So why can't anyone answer it?

Answer it again now. The data was never missing. It was scattered across sources that disagreed about who the children were, in copies nobody had ranked, mixed in with sheets that were being read and typed into at the same time. Every one of those is a decision nobody made.

You have now made four of them. Written down, they fit on one page — and that page is worth more to your school than any software you could buy, because the software assumes it.

Then notice what still feels unresolved. If it is "I don't have the authority to do this," you have found the most useful thing in the module, and the next conversation is with a person rather than a computer.

### **Side note ^aside-2**

**Next:** Module 11 — *Building the hub.* Eleven messy exports from a school that does not exist, turned into one record per child and three views onto it. Every decision you just made, carried out.

In the meantime: the one-page summary. Take it to whoever owns the roster at your school and ask them one question — *is this the source of truth?* Their answer tells you how much of this work is technical and how much of it is not.

## **Footer ^footer**

Developing with AI · Module 10. Nothing in this module needs a computer, and that is the point.
