# Module 2 — Making something you actually need: the page's text

Generated from `dev-portal-site/modules/02-letters.html` by `tools/make-tutor.py`. **Do not
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
- Fenced blocks are terminal commands. A line beginning `$` is one the learner
  types; a line without one is what the computer prints back.

---

## **Cover ^cover**

**Series line** — Developing with AI · A series of modules

**Module number** — 2

**Title** — Making something you actually need

**For** anyone who has finished Module 1 **Time** about an hour **You need** Claude Code, and nothing installed

---

**Label** — Before you start

So far you have made a game. Useful for learning, useless on a Tuesday. This module makes something you would otherwise have made by hand.

*This line sits alone in the clay-bordered box:*

Think of something you make one of, and then make thirty more of by hand. What actually changes between the first one and the thirtieth? Think about it for a moment.

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 8 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**Template** The one version of a thing, with gaps where the details go. You write it once.

**CSV** *(comma-separated values)* A spreadsheet saved as plain text: one line per row, commas between the columns. *Note:* Excel and Google Sheets both save this format. It is the plainest way to hand a list to a program.

**Row** *(or record)* One line of that list. One family, one student, one item — whatever the list is a list of.

**In place** Changing the file you already have, rather than making a new copy alongside it. *Note:* Same name, same folder, different contents. There is no "Save As" step and no undo button.

**Generate** Making many finished things out of one template and one list, automatically.

**Script** A saved list of instructions you can run again whenever you want. *Note:* The difference between asking somebody to do a job and being handed the machine that does it.

**Standard library** The tools a programming language already has, with nothing to install. Everything in this module runs on what your Mac came with.

**Print to PDF** Your Mac can turn any page it can print into a PDF. In the print window, the *PDF* button in the bottom corner. No extra software.

## **Section 1 — Start with one ^sec1**

**Heading** — Start with one

Every school sends a welcome letter at the start of the year. Somebody writes it, and then somebody puts a name at the top of it thirty times.

We are going to write it once and let the computer do the thirty.

### **Try it yourself 2.1 ^try-2-1**

Make a folder for this project inside *Projects*, called **welcome-letters**. Do it in Finder, the way you make any folder: open *Projects*, right-click, *New Folder*, type the name.

Now open Claude Code and start a new session. **When it asks which folder to work in, choose *welcome-letters* — the folder itself, not *Projects*.**

If it does not ask, it has remembered somewhere from last time. The folder it is using is shown just above the box where you type; click it and change it. Getting this right now saves a confusing ten minutes later, when Claude cannot find a file that is plainly sitting there.

### **Try it yourself 2.2 ^try-2-2**

Ask for the letter:

**Ask Claude**

> Make a welcome letter for the start of the school year as a single HTML file called letter.html that I can open by double-clicking. It should fill one printed page. Address it to a family. Leave the school name as [School Name] and the date as [Date] for now. Keep it warm and short.

Now go and find *letter.html* in the folder and **double-click it**. It opens in your browser, looking like a letter.

### **What just happened ^reveal-r1**

**Button hint** — Open the letter in your browser first

Same move as the game in Module 1 — you described something and Claude wrote a file. The only difference is that this one is a document rather than a toy.

**It is an HTML file, and that is deliberate.** You asked for a letter and got a web page, which sounds like the wrong answer until you notice that your browser prints beautifully. HTML is the easiest thing on your computer to make, to change, and to print — and at the end of this you will hit ⌘P and get a PDF.

The `[School Name]` and `[Date]` in square brackets are placeholders. You will fill them in a moment, and that habit — leaving an obvious gap rather than a plausible guess — is worth keeping. A wrong date looks right. A bracket does not.

## **Section 2 — It changes your file, not a copy of it ^sec2**

**Heading** — It changes your file, not a copy of it

The letter is probably fine and almost certainly not yours. Make it yours.

### **Try it yourself 2.3 ^try-2-3**

Fill in the real details, and change how it looks. Use this, or say whatever you actually want:

**Ask Claude**

> Put my school's name in: [your school]. Set the date to the first day of school. Then change the look so it feels like it came from us rather than from a template — warmer, a bit more spacious, and give it a heading I would not be embarrassed to send home.

Reload the page in your browser and look. Ask for more changes until it is close to something you would actually send. This is the same back-and-forth as restyling the game, and it is meant to take a few rounds.

**Now look at the folder.** How many files are in it?

### **What just happened ^reveal-r2**

**Button hint** — Count the files in the folder before opening this

One file. Still called `letter.html`. There is no *letter-v2*, no *letter-final*, no *letter-FINAL-actually*.

Claude edited the file **in place** — it opened the one you had, changed it, and saved it back under the same name. That is what it will do to every file you point it at from now on.

Which is worth a moment's unease. **There is no undo button.** You can ask Claude to put something back and it usually can, because it remembers what it changed — but only within the conversation you are having. Close the session and that memory is gone, and the file is whatever it last was.

The real answer to that problem is a way of keeping every version of every file forever, so that any bad afternoon is a five-second recovery. That is Module 7. Until then, if a file matters and you are about to let Claude loose on it, **duplicate it first** — the same instinct that makes you save a copy before a big edit in Word.

## **Section 3 — Now do it twenty-five times ^sec3**

**Heading** — Now do it twenty-five times

Here is the list. Twenty-five families, all invented.

### **Try it yourself 2.4 ^try-2-4**

Download **families.csv**, then move it into your *welcome-letters* folder alongside the letter. Drag it in Finder like any other file.

Then double-click it. It opens in Excel or Numbers and looks like an ordinary spreadsheet — three columns, twenty-five rows.

Now open it a second way. In Claude Code, ask:

**Ask Claude**

> What is in families.csv? Show me the first three lines exactly as they are stored, not as a table.

### **What just happened ^reveal-r3**

**Button hint** — Look at it both ways first

The same file, twice. Excel drew it as a grid. Underneath it is three words and two commas per line.

That is all a **CSV** is, and it is why programs like it: there is nothing to decode.

**Any spreadsheet you already have can become one.** In Google Sheets it is *File → Download → Comma-separated values*; in Excel or Numbers, *File → Save As* or *Export*, and pick CSV. The moment you do, a list that lived in a browser tab becomes something a program on your computer can read.

That is worth knowing before you go looking for something cleverer. People assume the answer is to connect Claude to Google somehow. Downloading the sheet takes four seconds, needs no setup at all, and is what you would do anyway.

**You now have two separate things in that folder.** A letter that says nothing about who it is for, and a list that says nothing about what to send. Keep noticing that. It is the whole trick of this module, and most of the reason the rest of this series exists.

### **Try it yourself 2.5 ^try-2-5**

Put them together:

**Ask Claude**

> Using letter.html as the template and families.csv as the list, make one file called letters.html containing a copy of the letter for every family, each one addressed to that family by name and mentioning their child. Put a page break between them so each prints on its own page. Do not change letter.html.

Double-click *letters.html*. Scroll.

Then press **⌘P**. The preview shows twenty-five pages. In the bottom corner of that window there is a **PDF** button — choose *Save as PDF*.

### **What just happened ^reveal-r4**

**Button hint** — Get to the print preview first — that is the moment

Twenty-five letters, correctly addressed, ready to print, in about the time it takes to read this sentence.

Notice what you did *not* do. You did not write twenty-five letters. You did not copy and paste a name twenty-five times and miss one. You wrote **one** letter and pointed at a list.

And notice the PDF. Nothing on your computer was installed to make it. Your Mac has always been able to turn anything printable into a PDF; most people have simply never needed the button.

**The instruction said "do not change letter.html" on purpose.** The template stays clean and reusable. The output is a separate file you can throw away and remake. Mixing those two up — editing the finished thing instead of the thing that makes it — is the most common way this kind of work goes wrong.

### **Try it yourself 2.6 ^try-2-6**

Change one word in the template. Ask Claude to alter a sentence in *letter.html* — anything, as long as you would notice it.

Then ask for *letters.html* again, exactly as before.

All twenty-five changed.

## **Section 4 — Ask for the machine, not the output ^sec4**

**Heading** — Ask for the machine, not the output

Something is unsatisfying about what you just did, and it is worth naming.

Next September you will want these letters again. You will open Claude, explain the whole thing a second time, and hope you describe it the same way. The work you did today does not survive.

So ask for something else.

### **Try it yourself 2.7 ^try-2-7**

**Ask Claude**

> Instead of making letters.html yourself, write me a program that makes it. Call it make_letters.py. It should read letter.html as the template and families.csv as the list, and write letters.html. Use only Python's standard library — nothing I have to install. Then tell me how to run it.

Now run it yourself. That means typing one line into the **terminal**, a window where you give your computer instructions by typing instead of clicking. You only need it to do two things: stand in your project folder, and run the program.

- Open the Terminal app. Press **⌘ Space**, type *terminal*, and press return. A window opens with a blinking cursor.
- Type `cd` and a space, but do not press return yet. Drag the *welcome-letters* folder from Finder into the terminal window, and its path appears after the `cd`. Now press return. `cd` means *go into this folder*, and the terminal is now standing in your project.
- Press **Copy** below, paste into the terminal, and press return. (The `$` just marks a line you type. Copy leaves it out.)
```
$ python3 make_letters.py
```

Double-click *letters.html* to check it worked. Then open *make_letters.py* and read it. You are not expected to follow every line — look for the two filenames you recognize.

### **Side note ^aside-1**

**If a box appears asking to install "command line developer tools."** That is your Mac noticing you have asked for Python for the first time. Click **Install** and wait a few minutes. It is Apple's own software, you only do it once, and nothing about it is your fault.

**Curious what the terminal actually is?** That is Module 5, the first module of Sequence 2. You do not need it to finish here.

### **Try it yourself 2.8 ^try-2-8**

Open *families.csv* in Excel or Numbers, add a family at the bottom, and save it — keeping the CSV format when it asks.

Then run the program again, in the same terminal window. (If you closed it, repeat the `cd` and the drag from 2.7 first.)

```
$ python3 make_letters.py
```

Twenty-six letters. You did not open Claude to do that.

### **What just happened ^reveal-r5**

**Button hint** — Run it the second time before opening this

You stopped asking for the letters and asked for the thing that makes the letters. That is the difference this module exists for.

Here is the honest version: **Claude wrote code both times.** In 2.5 it wrote something, ran it, produced your file, and threw the code away. In 2.7 it wrote the same sort of thing and *left it in your folder*. The difference is not code versus no code. The difference is whether you kept it.

Look at what that buys you. Next September you change the list and type one line. In 2.5, next September you start the conversation again from nothing.

**This is the shape of every useful thing in this series.** A template, a list, and a small program that puts them together. Class lists and name tags. A roster and a set of conference slips. A schedule and forty personal timetables. Once you can see that shape you start seeing it everywhere in your job, and most of what you see is something you are currently doing by hand.

## **Section 5 — Where this goes ^sec5**

**Heading** — Where this goes

Two years of doing what you just did produces something like the math fluency materials at Schechter: a folder of small generators that turn one set of rules into forty-two finished worksheets, each one a real PDF, ready to hand out.

That version does need things installed — a library that draws PDFs directly, so the script produces the finished file without anybody pressing ⌘P. That is the next thing you will want, and it is the reason a later module deals with installing properly.

You do not need it yet. What you built today runs on a Mac with nothing added to it, and will still run in five years for exactly that reason.

### **Side note ^aside-2**

**Use your own list — carefully.** Everything here works just as well with a real list, and you should try it with one. It almost certainly lives in a Google Sheet already: *File → Download → Comma-separated values*, and drop it in the folder like the one you used here.

**Not a class list, and not families, yet.** Use a staff list, a committee, a book club, the people running a trip. Where school data is allowed to live is its own module and it comes later in this series; until you have done it, keep students and families out of your project folders.

## **Section 6 — If something went wrong ^sec6**

**Heading** — If something went wrong

| You saw | It means | Try this |
| --- | --- | --- |
| The letter opened as a page of code | It opened in a text editor, not a browser. | Right-click *letter.html*, choose *Open With*, and pick a browser. |
| Claude can't find families.csv | The file is not in the folder Claude is standing in. | Check it is in *welcome-letters*, not still in Downloads. Ask Claude what files it can see. |
| Every letter has the same name on it | The template was copied, but the name was never swapped in. | Say so plainly: *each page should use that row's family name, not the same one every time.* |
| All twenty-five ran together on one page | The page break did not survive. | Ask: *put a proper page break between letters so each prints on its own sheet.* Check with ⌘P, not by scrolling. |
| command not found: python3 | Your Mac has not been asked for Python before. | Run `python3 --version` and accept the install box that appears. Then try again. |
| No such file or directory | The terminal is standing somewhere else. | Type `cd` and a space, drag the *welcome-letters* folder into the window, press return, and run it again. |
| The script ran but nothing changed | The browser is showing the old version. | Reload the page. Hold **⇧** while reloading if it is stubborn. |
| Claude edited the template by mistake | The instruction was not specific enough. | Ask it to put *letter.html* back, and say *do not change the template* next time. |

## **Module tasks ^checklist**

The 8 checkboxes near the end, in the order the module does them:

1. Made a project folder and had Claude write the letter
1. Opened it in a browser and saw a letter, not code
1. Restyled it until I would send it, and noticed the folder still held one file
1. Moved the list into the folder and looked at it both ways
1. Generated twenty-five letters and saw them in the print preview
1. Saved them as a PDF
1. Asked for the script instead of the output, and ran it myself
1. Added a family to the list and re-ran it without opening Claude

## **Section 7 — Before you finish ^sec7**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

Think of something you make one of, and then make thirty more of by hand. What actually changes between the first one and the thirtieth?

Answer it again now. Almost nothing changes — a name, a grade, a date. Everything else you were retyping was already written.

Then notice what still feels unclear. That part is the most useful thing you could ask Claude in the next five minutes.

### **Side note ^aside-3**

**Next:** Module 3 — *Lesson planning and design with AI.* You can make a thing. Next, making the thing you would actually use on Monday.

## **Footer ^footer**

Developing with AI · Module 2. Written for macOS; the ideas are identical on Windows but several commands differ.
