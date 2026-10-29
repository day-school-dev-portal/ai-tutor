# Module 3 — Lesson planning and design with AI: the page's text

Generated from `dev-portal-site/modules/03-lesson-design.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 3

**Title** — Lesson planning and design with AI

**For** anyone who has finished Module 2 **Time** about an hour and a half **You need** Claude Code, and a lesson you already teach, as a PDF or document

---

**Label** — Before you start

So far you have made things from nothing: a game, then a stack of letters. Most of what you actually teach on Monday wasn't made from nothing. It came from a curriculum, a colleague or a book, and the work went into adapting it. This module follows one published lesson through two rewrites, and has you make the same moves on a lesson of your own.

*This line sits alone in the clay-bordered box:*

Think of a lesson you teach that came from somewhere else. What do you do in the room that isn't written anywhere on the page? Think about it for a moment.

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 8 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**Resource** The published or inherited material you start from. *Note:* Not the same thing as the lesson. The lesson is what happens when a particular teacher uses it with particular students.

**Student-facing** Written for the student to read and act on, without a teacher translating.

**Gating** The student can't see the next part until they've committed to an answer for this one. *Note:* On paper it's "stop, don't turn the page." On screen it can be a section that stays locked until something is written.

**Free license** Permission to reuse an image or text under stated conditions. *Note:* Creative Commons licenses are the common ones. CC0 asks nothing. CC BY asks for credit. CC BY-SA asks for credit and that you share what you make under the same terms.

**Attribution** The credit line a license requires: who made it, under what license, and where it came from.

**Counterexample** One case that breaks a definition or a claim. One is enough.

**Pressure-test** Running a plan against the actual students who will meet it, on purpose, looking for where it breaks.

**Primary source** The original text, as opposed to a summary of it. *Note:* That includes Claude's summary.

## **Section 1 — One lesson, two rewrites ^sec1**

**Heading** — One lesson, two rewrites

The case is Lesson 1.1 of Math Medic's geometry course, *Creating Definitions.* It is a good lesson, and it was written for a teacher standing in a room.

The teacher pulls objects out of a bag (sneakers, high heels, flip-flops, socks, slippers, Barbie shoes) and students sort them: shoe, or not a shoe? They write a definition, watch the objects break it, and revise. Then the teacher leads a debrief that names what they did. A good definition *classifies* (what group is it in?) and *differentiates* (what sets it apart from the rest of the group?). Students write their own thinking in blue pen and anything from the debrief in red, so the change shows on the page. There is a lesson video to go with it.

It was rewritten twice:

- **For one student working entirely alone.** No teacher, no classmates, no video. That version was built with Claude almost from start to finish.
- **For Jonah's own class.** A lesson he would actually teach, with a different point. He wrote that plan himself, and the materials from the first rewrite carried straight into it.
You will do the same moves on a lesson of yours.

### **Try it yourself 3.1 ^try-3-1**

Make a folder inside *Projects* called **lesson-redesign**, the way you did in Module 2. Put a lesson you teach into it. A PDF is best. A Google Doc works if you download it first (*File → Download → PDF*).

Pick something you'd genuinely like to change, not something you're proud of. Then open Claude Code and choose *lesson-redesign* as the folder to work in.

### **Try it yourself 3.2 ^try-3-2**

**Ask Claude**

> Read [your lesson file]. Don't change anything yet. Tell me what this lesson is trying to teach, what the teacher does during it step by step, and which of those teacher moves aren't written anywhere a student would see.

### **What just happened ^reveal-r1**

**Button hint** — Read Claude's answer about your own lesson first

*What happened in the case study*

The last part of that question does the most work. A published lesson is mostly the student's page. The teacher's moves live in the margins, in the video, or nowhere.

For *Creating Definitions*, Claude named three things the lesson can't run without:

- **Someone who holds back the debrief** until every student has committed to an answer. If you see the right answer first, you never find out what you actually thought.
- **Classmates who argue with your definition.** The arguing is where the definition gets tested.
- **The red pen.** It turns the change in your thinking into something you can see.
Every design decision in the self-guided version came from replacing those three. That is why the question comes before the rewrite.

## **Section 2 — Rewrite it for a student alone ^sec2**

**Heading** — Rewrite it for a student alone

Now the first rewrite. Even if you never plan to hand a lesson to a student working alone, doing it shows you everything the lesson was quietly relying on you for.

### **Try it yourself 3.3 ^try-3-3**

**Ask Claude**

> Rewrite this lesson for a student doing it entirely alone: no teacher, no classmates, no videos. For each teacher move you listed, put something on the page that does that job. Keep the original activities, in the original order. Make it a single HTML page I can open in my browser.

Open the page and read it.

### **What just happened ^reveal-r2**

**Button hint** — Open your rewrite first

*What happened in the case study*

Claude replaced each of the three:

- **Gating, for the held-back debrief.** Each section stays locked until the student has written something in the one before it. It never checks whether the answer is right, only that the student went first.
- **The Challenger, for the classmates.** Six counterexamples that attack the student's *own* definition, one at a time. *The sock problem:* most first attempts say something like "a covering for your foot," and so is a sock. *The horseshoe problem:* if your definition doesn't say "human," the horseshoe walks straight in, and if you add "human," you've just thrown out the doll shoes.
- **The red pen stayed.** The page uses the same two colors for the same two jobs.
**Here is the honest part.** The first draft still said what the teacher would do at several points, and it had a whole section built around the lesson video. Math Medic's lessons come with video, and this student would never see it. Jonah's correction was two sentences:

**What Jonah typed**

> Take out any reference to the teacher doing something. This will be self-guided and also they won't have access to the videos.

Claude found and removed six references to a teacher or a classroom, and the whole video section.

The lesson in that: **Claude rewrites toward the resource's assumptions unless you tell it who the student actually is.** It has never met your student. You have.

### **Try it yourself 3.4 ^try-3-4**

Do the first activity yourself, as the student. Not a skim: sit where the student will sit and actually answer the first question.

Mark every sentence that assumes someone else is in the room, or something the student won't have. Then tell Claude, in plain words, the way Jonah did.

## **Section 3 — Go and get what the lesson points to ^sec3**

**Heading** — Go and get what the lesson points to

Published lessons point at things they don't include. *Show pictures of. Read the passage aloud. Display a map of.* For a teacher that's a ten-minute errand. For a student alone it's a dead end.

### **Try it yourself 3.5 ^try-3-5**

**Ask Claude**

> List everything this lesson mentions but doesn't include: images, texts, objects, videos. For the images, find freely licensed ones on Wikimedia Commons and save them in a folder called img. Write a file called IMAGE-CREDITS.md listing the author, license and source link for each one.

Open the folder and look at what came back.

### **What just happened ^reveal-r3**

**Button hint** — Look at your images first

*What happened in the case study*

Math Medic's plan has the teacher pull objects out of a bag. Claude went to Wikimedia Commons and came back with twelve photographs, picked to **break** definitions, not just illustrate them. Alongside the sneakers and cowboy boots there was a sock, a horseshoe, snowshoes, swim fins, an ice skate and a pair of crocheted baby booties. Each was saved with its author and license: some public domain, some CC0, most CC BY or CC BY-SA.

Then, just before the finished materials went into Google Drive, Claude noticed the printable PDFs had no credits anywhere. Eight of the twelve photos were under licenses that require them. It added a credits paragraph to the student guide before uploading.

The lesson: **"free" almost always means free with conditions.** Ask for the credits file in the same breath as the images, and it's handled before it matters.

### **Side note ^aside-1**

**Why not just search Google Images?** An image search finds pictures, not permission. Wikimedia Commons and Openverse only carry images whose licenses are stated, which is the whole reason to ask for them by name.

## **Section 4 — Look at it the way the student will ^sec4**

**Heading** — Look at it the way the student will

Now turn the pieces into the thing the student actually holds. This is the section where your judgment matters most, because it is the easiest place for a well-made thing to quietly undercut the lesson.

### **Try it yourself 3.6 ^try-3-6**

Ask for whatever form fits your lesson. For example:

**Ask Claude**

> Make a slide deck with one image per slide, in the order the lesson uses them, with the question the student is answering on each slide.

Or a printable packet, or one picture sheet. Then go through it page by page and ask one question of each:

**What does this page tell the student before they've had a chance to think?**

### **What just happened ^reveal-r4**

**Button hint** — Go through yours page by page first

*What happened in the case study*

Claude built fifteen clean slides: a cover with the rules, one object per slide with its name in large type, and a closing slide. Jonah got to slide 12 and wrote:

**What Jonah typed**

> Take the labels off the slide, like don't say "an ice skate"

*Snowshoes. A horseshoe.* The answer is inside the word. A student asked "shoe, or not a shoe?" under a heading that says HORSESHOE has been handed half the answer.

Claude made the deck quickly and made it tidy, and never noticed it had undercut the activity. That is the split in this whole module: **Claude is fast at making the thing. You're the one who knows what the thing is for.**

One more catch: **a single fix doesn't find every copy.** The same names were still on the printed picture sheet and on the worksheet's list. When you find a problem like this, ask Claude where else it shows up.

### **Try it yourself 3.7 ^try-3-7**

Ask for one change that's purely about how it looks: bigger, clearer, simpler. Then watch whether Claude checks that the change will actually work, or just does it.

### **What just happened ^reveal-r5**

**Button hint** — Make your change first

*What happened in the case study*

Jonah asked to make the pictures bigger. Making them bigger in the layout is easy. But the image files were small, and stretching them would have made them blurry. So Claude checked their size, went back to Wikimedia for the originals (most were thousands of pixels wide and had been shrunk for the first version) and fetched them again. Two, the snowshoes and the slipper, had no bigger original anywhere. They are softer than the rest, and Claude said so instead of hoping nobody would notice.

It also made a mistake on the way: for one pass, those same two pictures came out *smaller* than before. It caught that only because it looked at the finished slides. **Ask to see the result, every time.** Claude reporting that a change went fine is not the same as the change going fine.

## **Section 5 — The second version is yours ^sec5**

**Heading** — The second version is yours

The self-guided lesson stays close to Math Medic. Its point is Math Medic's point: a good definition classifies and differentiates.

When Jonah rewrote it for his own class, he started from somewhere else:

**From Jonah's plan**

> I think the point of this lesson is that to do math, or any rational inquiry, you need to know exactly what you're talking about.

Then the lesson changed shape. Definitions written with a hevruta partner, in sixty seconds. Every pair's definition put to a vote, because "just having to raise your hand to agree or disagree puts some skin in the game." The pairs build one class definition together. The twelve pictures come out selectively, depending on what that class definition gets wrong. There is a question that runs underneath the whole thing: when a picture breaks the definition, is the *definition* wrong, or are we wrong about what a shoe *is*? Then Euclid, and how few definitions he needed to build all of geometry. It ends with Wittgenstein's *family resemblances* (*Philosophical Investigations*, §66–67) and the question of whether words have precise definitions at all.

None of that is in Math Medic. It is a different lesson with a different point.

What carried over was the material. "Have all 12 ready." "Vote: Is it a shoe?" The twelve pictures and the unlabeled slides, built for one student working alone, turned out to be exactly what a room of thirty needs for a vote, once the labels were off.

### **Try it yourself 3.8 ^try-3-8**

Before you ask Claude anything, write one paragraph that starts **"The point of this lesson is…"** in your own words. Not the published objective. What you actually want your students to walk out having wrestled with.

Then:

**Ask Claude**

> Here is what I think this lesson is for: [your paragraph]. Where does the published version serve that point, and where does it serve a different one? Which activities would you keep, cut or change?

### **What just happened ^reveal-r6**

**Button hint** — Write your paragraph before opening this

*What happened in the case study*

Claude can show you where the published lesson and your paragraph disagree. It can't write the paragraph.

Math Medic's lesson ends with notes on *classify* and *differentiate.* Jonah's ends with a philosopher asking whether that kind of definition exists at all. Neither one is wrong. But only the second was available, because the person planning knew what he wanted this class to wrestle with.

### **Try it yourself 3.9 ^try-3-9**

Now use Claude to rehearse the students.

**Ask Claude**

> Write six answers that real students in [grade] would plausibly give to [the lesson's first question] in their first minute. Include the most common one, one that's too broad, one that's too narrow, and one that's clever and almost right. For each, tell me which of my [examples, images or problems] would break it.

### **What just happened ^reveal-r7**

**Button hint** — Read your six first

*What happened in the case study*

In the self-guided version there's no class to produce wrong answers, so the lesson has to bring its own. The Challenger opens with the definition most first attempts produce, "a covering for your foot," and breaks it with a sock.

In the whole-class version, the same work becomes preparation. Jonah's plan says the challenges to show "will depend on their definition." Knowing ahead of time that "for walking" throws out the ice skate and the swim fins, and that "human" throws out the doll shoes, is what lets you reach for the right picture at the moment the class needs it.

### **Side note ^aside-2**

**Describe your students in general terms only.** "Ninth graders who hate being wrong in front of each other" is plenty. No names, no grades, no records. Where student data is allowed to live is its own module later in this series. Until you've done it, keep students out of your project folders and your prompts.

## **Section 6 — Know what you're simplifying ^sec6**

**Heading** — Know what you're simplifying

Lots of lessons carry a little history: where an idea came from, who first proved it. You will almost always simplify it, and you should. A ninth-grade class doesn't need all of the original. But leaving something out on purpose is different from leaving it out because you didn't know it was there.

### **Try it yourself 3.10 ^try-3-10**

Paste the history or background part of your plan into the chat, then:

**Ask Claude**

> Here is the background for this lesson, simplified for [grade]. Check it against the original source. Quote the source wherever my version differs, and tell me what it leaves out. For each point, tell me whether it's safe to leave out at this level or whether leaving it out would mislead students. Say which of your points you're least sure about.

### **What just happened ^reveal-r8**

**Button hint** — Run the check on yours first

*What happened in the case study*

Jonah got his Euclid background from a conversation with Claude while he was planning. Then he boiled it down to seven lines for the lesson, starting with "A point is the smallest mark you can make." He did that on purpose. In his words, "I definitely oversimplified for the sake of this lesson."

That's a fair call, and checking it wasn't about undoing it. The point was to know exactly what the seven lines leave out. Here is how they compare with Book I of the *Elements*, in Heath's translation:

- **Euclid's point isn't a mark.** "A point is that which has no part." It has no size at all, so it's a definition of something nobody can actually draw.
- **The seven lines mix two kinds of starting points.** Euclid separates *definitions* (23 of them, saying what words mean) from *postulates* (5 of them, saying what you're allowed to assume). "A line can be extended" and "all right angles are equal" are postulates.
- **His definition of parallel has one more phrase.** Parallel lines are lines "in the same plane" that never meet. Without that phrase, a line along the floor and a line across the ceiling going the other way never meet, and they aren't parallel.
- **The most famous postulate isn't there.** That's the fifth, the *parallel postulate.* For two thousand years mathematicians tried to prove it from the other four. In the 1800s, Lobachevsky and Bolyai showed you could replace it and still get a geometry that holds together. Just not Euclid's.
- **"You can prove everything" is generous.** Euclid's very first proof assumes that two circles cross, and nothing in his list says they must. Hilbert rebuilt the foundations in 1899 with about twenty axioms.
Most of that is safe to leave out of a ninth-grade lesson, and the simplification stands. But **two of the things it leaves out could earn their way back in.** Euclid defines an obtuse angle without degrees, "an angle greater than a right angle," which answers a question the plan asks out loud. And the fifth postulate is the shoe lesson at full scale: change one assumption and you haven't fixed geometry, you've found a different one. In Jonah's words, "it could be that this exercise actually changes what we think a shoe IS."

The lesson: **simplify on purpose, not by accident.** And **ask Claude to check, not just to tell.** Asking for background gets you a confident paragraph. Asking it to check against the source, quote the source, and say what it's unsure of gets you something you can verify. Then verify one thing yourself. Heath's translation is from 1908 and free online.

## **Section 7 — If something went wrong ^sec7**

**Heading** — If something went wrong

| You saw | It means | Try this |
| --- | --- | --- |
| The rewrite still mentions the teacher, or a video | Claude kept the original's assumptions. | Say who the student is and what they don't have, in one sentence. |
| Claude can't read your lesson, or the text comes out garbled | It's a scan, a picture of text rather than text. | Download a fresh PDF from the original, or paste the text into the chat. |
| The rewrite is longer than the original and says less | You asked for a rewrite without saying what to keep. | Ask it to keep the original activities in order and change only who does what. |
| Images arrived with no license, or from sites you don't recognize | It searched the open web. | Ask for Wikimedia Commons or Openverse only, with a credits file. |
| The sample student answers sound like no student you've met | Claude doesn't know who's in your room. | Tell it the grade and what your students tend to write in the first minute. No names. |
| The background check agreed with everything | You asked "is this right?" | Ask it to quote the source and list the corrections it's least sure about. |
| Pictures look blurry once enlarged | The image files are small. | Ask Claude to check their pixel size and fetch the originals. |
| You fixed something, but it's still in the printout | The same text lives in more than one file. | Ask: *where else does this appear?* |

## **Module tasks ^checklist**

The 8 checkboxes near the end, in the order the module does them:

1. Put a lesson I teach into a project folder and had Claude name what the teacher does that the page doesn't
1. Had Claude rewrite it for a student working alone
1. Did the first activity myself as the student, and fixed whatever assumed someone else was in the room
1. Collected what the lesson points to, with a credits file
1. Turned it into the material the student will use, and checked every page for what it gives away
1. Wrote "the point of this lesson is…" in my own words, and compared it with the published version
1. Had Claude write plausible first answers, and matched each one to what breaks it
1. Checked my simplified background against the source, and decided on purpose what to leave out

## **Section 8 — Before you finish ^sec8**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

Think of a lesson you teach that came from somewhere else. What do you do in the room that isn't written anywhere on the page?

Answer it again now. Your list is probably longer than it was an hour ago. Claude can rebuild nearly everything on it, once you can say what it is. What it can't do is notice the item in the first place, or notice when a perfectly good slide gives the answer away.

Then notice what still feels unclear. That part is the most useful thing you could ask Claude in the next five minutes.

### **Side note ^aside-3**

**Next:** Module 4 — *Putting it on the internet.* You have made things that work on your laptop. Next, giving other people an address where they can use them.

## **Footer ^footer**

Developing with AI · Module 3. Written for macOS; the ideas are identical on Windows.
