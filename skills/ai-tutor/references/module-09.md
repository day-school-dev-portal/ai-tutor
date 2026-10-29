# Module 9 — Where school data is allowed to live: the page's text

Generated from `dev-portal-site/modules/09-school-data.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 9

**Title** — Where school data is allowed to live

**For** anyone who has finished Module 8 **Time** about 45 minutes, plus one conversation you cannot have by yourself **You need** your school's acceptable use policy, and the name of the person who decides this. No terminal.

---

**Label** — Before you start

Eight modules ago you could not get a program to read a file. You can now reach your school's Drive, its spreadsheets, and anything else behind a sign-in — which means the honest description of your situation is that you have become capable of a mistake you could not previously have made.

*This line sits alone in the clay-bordered box:*

You can now get at every roster, grade and note your school keeps. Which of them should you? Write your answer down before you read on.

This is the only module with nothing to build. It is here because the ones before it have made you dangerous, and because everything after it assumes you have had the conversation this module is about. The modules that follow are deliberately done on a school that does not exist — but they are teaching you to build the thing that will one day hold your own children's records, and the decision about what may go into it is not a decision you can make afterwards.

**Label** — Not legal advice

This module will not tell you what you are allowed to do. It cannot — the answer is different at every school, and in the United States it is different in every state. What it does is name the questions precisely enough that you can take them to the people at your school who own them, and recognize a real answer when you get one.

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 11 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**PII** *(Personally Identifiable Information)* Anything that points at one identifiable person. *Note:* A name is the obvious one. It is not the only one, and that gap is most of this module.

**FERPA** *(Family Educational Rights and Privacy Act)* The US federal law governing student education records. *Note:* Whether it applies to your school is a question to ask, not assume. Section 3 is about why the answer changes less than it sounds like it does.

**Directory information** The narrow category a school may share more freely — typically name, grade, photo, participation in activities. *Note:* Your school defines it, in a notice to families. Not by instinct, and not by you.

**De-identification** Taking the identifying parts out of a record so it no longer points at a person.

**Re-identification** Putting the name back using what was left behind. *Note:* This is easier than almost anyone expects, and a small school makes it easier still.

**Data minimization** Taking only the fields you actually need for the thing you are actually doing. The discipline of not pulling the whole table because the whole table was there.

**Least privilege** Giving each person — and each program — the smallest access that still lets them do the job. *Note:* You met this in Module 8 as *scope*. Same idea, pointed at people.

**At rest / in transit** The two states data can be attacked in: sitting on a disk, and moving across a network. *Note:* "It's encrypted" is an answer to one of these. Ask which.

**Acceptable use policy** *(AUP)* Your school's written rules for what staff may do with its systems and its information. *Note:* Probably written before anyone asked this question. Find it anyway.

**Vendor** *(sometimes "processor")* Any outside company that holds your school's data on your behalf. Your SIS, your gradebook, your assessment platform, your AI tool. *Note:* You are responsible for what they do with it. That is usually in the contract, and almost nobody has read it.

**Retention** How long you keep something, decided on purpose rather than by accident. *Note:* A folder nobody deletes is a retention policy. Just not a chosen one.

## **Section 1 — Make the list ^sec1**

**Heading** — Make the list

Before deciding where student data is allowed to live, find out where it already lives. Most people have never counted, and the counting is the part that changes minds.

Pick one child. A real one, in your head — you are not writing their name down.

### **Try it yourself 9.1 ^try-9-1**

On paper, or in a plain note, list every place something about that child has been recorded in the last month. Not categories — places. The gradebook is one. The spreadsheet on your desktop is another. So is the email thread with their parent, the shared doc the grade team keeps, the folder of scanned work, the app the reading specialist uses, the text message between two teachers, and the note you typed into your phone during a meeting.

Give it five minutes and stop when you stop, whether or not you think you are finished.

**Ask Claude**

> I work at a school. I'm making a list of every place one student's information might be recorded over a month. Here's what I have so far: [your list]. What kinds of places do people in schools usually forget?

### **What just happened ^reveal-r1**

**Button hint** — Make your own list first. The exercise doesn't work in reverse.

Three things are almost always true of that list, and all three matter.

**It is longer than you expected,** and the back half of it is places nobody chose. No one decided that a child's reading level should live in a text message. It ended up there because somebody needed to say something quickly.

**Most of it is copies.** The grade exists in the gradebook and in the spreadsheet and in the email, and the three will not agree for long. That is a data-architecture problem and it is what the next two modules are about — but notice that it is also a privacy problem, because every copy is another place that has to be protected, and nobody is protecting the one on the desktop.

**You do not control most of it.** This is the finding that should change what you do next. The question is not "where will I put the data I'm about to use?" It is "what am I adding to a situation that is already like this?"

### **Side note ^aside-1**

**The list is also the argument.** When you get to Section 5 and have to persuade someone that this is worth deciding, the list you just made is more convincing than anything you could say about principles. Keep it.

## **Section 2 — What counts as personal ^sec2**

**Heading** — What counts as personal

Everybody knows a name identifies a person. The useful knowledge is that a name is not required.

Take a spreadsheet of test scores with the name column deleted. Left behind: grade, homeroom, date of birth, town, scores. In a school of five hundred, how many children are in grade 4, live in that town, and were born in March? Often one. The name is gone and the record still points at exactly one child — and anyone with the school directory can finish the job in about a minute.

This is called re-identification, and it is not an exotic attack. It is what happens when a normal person with normal access looks at a file they were given in good faith.

Small schools have it worse. Specificity is identity: *the only child in grade 6 receiving that service*, *the student who joined in February*, *the one who was out for three weeks in the fall*. Deleting a column does not touch any of that.

### **Try it yourself 9.2 ^try-9-2**

Take a real file you work with — a class roster, an assessment export, an attendance report.

**Do not upload it.** Do not paste its contents. Just list its column headings, and tell Claude roughly how big your school is.

**Ask Claude**

> I work at a school of about [N] students. A file I use has these columns: [list the headings]. If I deleted the name column and gave this file to someone who has our school directory, which combinations of the remaining columns would let them work out who individual rows are about? Be specific about which fields do the work.

### **What just happened ^reveal-r2**

**Button hint** — Guess your own answer first, then compare

The fields that identify people are rarely the ones that feel sensitive. A date of birth feels like a formality. A town feels like nothing. Together, with a grade level, they are usually a name.

Two consequences worth carrying out of this section.

**"I removed the names" is not a finding about a file.** It is a step someone took. Whether the file still identifies children is a separate question, and it has to be asked separately every time.

**The protection is usually not de-identification.** It is taking fewer fields in the first place. If what you need is grade-level reading distributions, you do not need dates of birth in the file at all. That is data minimization, and it is the cheapest privacy control that exists, because it works by not having the problem.

### **Side note ^aside-2**

**Identified is not the same as forbidden.** Plenty of real school work requires knowing exactly which child a row is about — the modules after this one build a system that does, and spend most of their time on how it tells two children apart. The point of this section is not to drive you toward anonymity. It is that you should know which one you are holding, because the two call for different care.

## **Section 3 — The law, and the thing that binds you anyway ^sec3**

**Heading** — The law, and the thing that binds you anyway

### **Side note ^aside-3**

**Read this first.** Nothing in this section is legal advice, and it was not written by a lawyer. It is a map of the questions. Take them to someone qualified at your school, and treat their answer as authoritative over this page.

One law comes up in almost every conversation about student data, so it is worth knowing it is there.

**FERPA is something to think about, not something to settle here.** It is the US federal law about student education records. Whether it applies to your school depends on details this page cannot see, so do not assume either way. Ask whoever handles legal questions for your school.

**Either way, the answer changes less than it sounds like it does.** Plenty of other things bind a school, whatever FERPA says:

- **State law.** Student-privacy laws vary by state, and some may reach your school or the vendors it uses. That is another question to ask rather than assume.
- **Your enrollment contract and your published privacy policy.** Your school has already told families what it does with their children's information. That is a promise, and families are entitled to hold you to it, whatever any statute says.
- **Your vendor agreements.** Every system holding your data has terms. So does every AI tool. What they may do with what you give them is written down, and it differs enormously between a consumer account and an institutional one.
- **What families actually believe.** The standard that decides whether an incident becomes a crisis is not the legal one. It is whether a parent, told plainly what happened, would feel that their trust had been handled carefully.
### **Side note ^aside-4**

**Not covered is not the same as not accountable.** A school that reasons from "FERPA doesn't apply to us" to "so this is fine" has answered a question nobody asked. The useful move is the opposite one: assume you will one day have to explain your decision to the family it concerns, and decide what you would want to be able to say.

### **Try it yourself 9.3 ^try-9-3**

Find your school's acceptable use policy. Actually find it — the file, not the memory of it. Then find whatever your school has published to families about student information, usually in the enrollment agreement or on the website.

Read what they say about three things: who may access student records, what may be shared outside the school, and whether AI tools are mentioned at all.

**Ask Claude**

> I work at an independent school. I'm trying to work out what our own policies already commit us to about student data. Here's our acceptable use policy: [paste it]. What does it actually say about who can access student information, and about using outside tools or services with it? Where is it silent?

### **What just happened ^reveal-r3**

**Button hint** — Go and find the documents. The section does not work from memory.

Most people find one of two things.

**The policy is silent on AI,** because it was written before the question existed. This is the common case and it is not a failure. It means the decision has not been made yet, which means someone is going to make it, which is Section 5.

**The policy already covers it** without saying "AI" — a clause about not sharing student information with outside services, or about approved systems only. Those clauses were written about something else and they apply anyway. If one of them is in your policy, you already have your answer for today, and the conversation in Section 5 is about changing it deliberately rather than quietly.

The thing you must not conclude is that silence is permission.

## **Section 4 — Four questions, answered by people ^sec4**

**Heading** — Four questions, answered by people

Everything above collapses into four questions. None of them is technical, and none of them is yours to answer alone.

**How sensitive is this?** Not all student data is alike, and treating it as though it were produces rules nobody follows. A sorting that works looks something like this — **ours, as a worked example, not a template**:

| Tier | What's in it | Rough rule |
| --- | --- | --- |
| 1 · Directory | Name, grade, homeroom, school email | Shared inside school freely; outside only as your directory notice allows |
| 2 · Academic record | Grades, assessment scores, attendance, teacher notes about learning | Staff who work with that child. Stays in school systems. |
| 3 · Sensitive | Learning plans, evaluations, counseling and medical notes, discipline records, financial aid | Named people only, by role. Does not leave approved systems, ever, without an explicit decision. |

Draw yours with the people who already handle tier 3, because they have been making these calls informally for years and their instincts are the raw material.

**Who gets access?** Least privilege, applied to humans: the smallest group that can still do the work. The question to resist is "who would find this useful," which is everyone. The question to ask is "who cannot do their job without it."

**How is it secured?** Three plain questions get you most of the way: is it behind a school account that leaves when the person does; is it encrypted in transit and at rest; and would you know if someone had taken a copy. If a system fails the first one, nothing else about it matters very much.

**And what may go to an AI tool?** The one the other three were building toward, and the only one that is new. The things that decide it: whether the account is institutional or personal, what the terms say about training and retention, whether the data leaves your tenancy at all, and which tier you are talking about. A tier 1 list of homeroom names and a tier 3 evaluation are not the same decision and should never be governed by the same sentence.

### **Side note ^aside-5**

**Do not write a policy for the whole school.** You are one person who has learned some things. What you can usefully produce is a proposal about the specific work you want to do, with the specific data it needs — which is small enough for someone to say yes to. School-wide policy is a different job, with different people in the room, and proposals like yours are what eventually prompt it.

## **Section 5 — The conversation ^sec5**

**Heading** — The conversation

The decision belongs to someone. At most schools it is a head of school, an assistant head, a division head, or whoever owns the SIS — and at a surprising number of schools, no one is certain which. Find out who. If two people might own it, that is itself worth surfacing.

A good answer has three properties, and you should keep asking until it does.

**It is written down.** A verbal yes evaporates when the person who said it changes jobs, and it cannot be handed to the next person who asks.

**It is specific about tiers and systems.** "Be careful with student data" is not a decision. "Tier 1 and tier 2 may go into tools on our institutional account; tier 3 may not go into any outside tool" is.

**It names who to ask next time.** So that the next person with your question does not have to repeat this entire module.

### **Try it yourself 9.4 ^try-9-4**

Write the proposal. One page, for the person who owns the decision.

**Ask Claude**

> Help me write a one-page proposal to [role] at my school. I want to use [AI tool, on our institutional/personal account] with [describe exactly which data, and which tier]. The work it's for is [what you're trying to do]. Here's where that data currently lives: [your list from 9.1]. Here's what our acceptable use policy says: [what you found in 9.3]. Write it for someone who is not technical and is responsible if this goes wrong. Be concrete about what data is involved, what happens to it, and what I am asking them to decide. Include what I will do if the answer is no.

Read it before you send it. The last clause matters: a proposal that has no answer for "no" reads as a request for permission rather than a decision.

### **What just happened ^reveal-r4**

**Button hint** — Write the thing and read it back before opening this

Claude can draft that memo well, and it can tell you which parts of your own policy are relevant, and it can list the risks you did not think of. Those are real and they save real hours.

What it cannot do is the part that matters.

It cannot decide which data is sensitive at your school. It cannot know what your families were told when they enrolled. It cannot hold the meeting, carry the responsibility, or be the person who explains the decision to a parent a year from now. And it will never tell you that you should not be doing this — not reliably, and not in a way you should depend on.

Which is the shape of this whole series. The technical obstacles came down fast, and once they were down, the remaining obstacles turned out to be the ones that were always the actual obstacles: who decides, who is responsible, and whether the people around you trust the result. Those do not yield to better tooling.

## **Module tasks ^checklist**

The 8 checkboxes near the end, in the order the module does them:

1. Listed every place one child's information lives in a month
1. Noticed how much of that list nobody chose
1. Worked out which columns identify a child once the names are gone
1. Found a place where taking fewer fields solves the problem outright
1. Read my school's acceptable use policy, the actual file
1. Found out what my school has already told families
1. Sorted the data I want to use into a tier
1. Identified who owns the decision, and written them a page

## **Section 6 — Before you finish ^sec6**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

You can now get at every roster, grade and note your school keeps. Which of them should you?

Answer it again. The answer you wrote at the start was probably about what you would be comfortable with. The one you would write now is about what your school has decided, what families were told, and which tier you are holding — and if you cannot answer it yet, you now know exactly whose answer you are waiting on.

Then notice what still feels unresolved. In this module, unlike the others, that feeling is usually accurate: something at your school genuinely has not been decided. Name it to the person in Section 5.

### **Side note ^aside-6**

**Next:** Module 10 — *Deciding what is true.* Where this module asked what data may live at your school, that one asks something narrower and harder: which copy of it everyone has agreed to believe. It builds nothing either. The two together are the decisions that come before any of this is worth automating — and the module after them builds the thing, a single place where staff can find out how a child is doing, assembled out of the sources you just inventoried.

That build is done on a school that does not exist — a hundred and twenty invented children and eleven messy exports — and that is deliberate. Nothing in it needs a real name, so by the time any of this points at your own school, you will have the answer this module sent you to get.

Until you do, keep building on invented names. Module 8's practice sheet is still there.

## **Footer ^footer**

Developing with AI · Module 9. Nothing in this module is legal advice; it names questions for the people at your school who own them.
