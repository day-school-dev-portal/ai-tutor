# Module 6 — Coding with AI: the page's text

Generated from `dev-portal-site/modules/06-coding-with-ai.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 6

**Title** — Coding with AI

**For** anyone who has finished Module 5 **Time** about 90 minutes, half of it waiting **You need** your terminal, Claude Code, and your Mac password

---

**Label** — Before you start

In Module 2 you asked Claude for a program, and the request contained a quiet restriction: *use only Python's standard library — nothing I have to install.*

That was deliberate, and it was a ceiling. Everything you have built so far was made out of parts your Mac happened to come with. That is a small box, and the interesting work is outside it.

*This line sits alone in the clay-bordered box:*

Think of something in your job you have never even considered automating — not because it is tedious, but because it seemed impossible. Hold on to it.

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 9 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**Library** *(also: package)* Code somebody else wrote, that your code uses. You do not read it and you do not maintain it. You call it. *Note:* A library is not a program you run. It is a program *your* program runs.

**Standard library** The libraries Python already comes with, free and installed. Reading files, dates, random numbers, CSVs. *Note:* This is what Module 2 restricted you to.

**Dependency** A library a project cannot run without. Somebody else's work that yours now leans on.

**Homebrew** *(the command is `brew`)* A program whose job is installing other programs. An app store for things that have no icon. *Note:* Installs **programs**. Not Python libraries — that is pip's job, below.

**Python** The language most of these scripts are written in, and also the name of the program that runs them. *Note:* Your Mac has an old one buried in it. You are about to install a real one.

**pip** The program that installs Python libraries into a Python. *Note:* Homebrew installs Python. pip installs things *into* Python. Two installers, two different jobs, and mixing them up is the single most common confusion here.

**Virtual environment** *(a venv)* A private Python belonging to one project folder, holding only that project's libraries. *Note:* Same idea as a project folder, one level down: this project's things stay in this project.

**reportlab** A library that draws PDFs directly — text, lines, page breaks, real margins. Twenty-five years old and written by people who care about font metrics so that you never have to.

## **Section 1 — Look at this first ^sec1**

**Heading** — Look at this first

Before any explanation, look at what is at the end of this module.

### **Try it yourself 6.1 ^try-6-1**

Download **worksheets-sample.pdf** and open it.

Look at page 1. Then page 2. Then page 17, or any page you like.

Then go to page 43.

### **What just happened ^reveal-r1**

**Button hint** — Open the PDF and compare two pages first

*What you are looking at*

Forty-two arithmetic worksheets. Each one has a child's name on it, and **each one has different numbers** — Ayelet's first problem is 81 + 14, Noam's is 88 + 68. No two children in that class can copy from each other, because no two of them have the same paper.

Page 43 is the answer key. Every child, every answer, in the order you will collect them.

Now the part worth sitting with. **Nobody could make this by hand.** Not slowly, not on a bad afternoon, not with a free period and determination. Forty-two different worksheets is achievable if you are willing to lose a weekend; forty-two different worksheets *with a correct answer key* is not, because you would have to do all 840 sums yourself and you would get some wrong.

That is the difference between this module and Module 2. The letters were *tedious* by hand. This is *impossible* by hand.

It takes about two seconds.

## **Section 2 — Watch it fail ^sec2**

**Heading** — Watch it fail

You are going to run the program that made that PDF, and it is going to refuse.

That is the point. The error it gives you is the reason this module exists, and it is worth meeting before anybody explains it.

### **Try it yourself 6.2 ^try-6-2**

In Finder, make a new folder inside *Projects* and call it **worksheets**.

Download both of these into it:

**make_worksheets.py** — the program **students.csv** — forty-two invented third graders

Then open your terminal, stand in that folder, and run it:

```
$ cd ~/Projects/worksheets;
$ python3 make_worksheets.py
```

### **Side note ^aside-1**

**If a box appears asking to install "command line developer tools."** That is your Mac noticing you have asked for Python for the first time. Click **Install**, wait a few minutes, then run the command again.

You get several lines ending in this:

```
ModuleNotFoundError: No module named 'reportlab'
```

### **What just happened ^reveal-r2**

**Button hint** — Get the error first

**Nothing is broken.** The program is fine, your Mac is fine, and you did not make a mistake. Read the error as a sentence: *no module named reportlab.* The program asked for a thing called reportlab and your Python does not have one.

Near the top of *make_worksheets.py* is the line that asked:

```
from reportlab.pdfgen import canvas
```

That is a program saying *I am going to need somebody else's work to do this.* It is called a **dependency**, and almost every useful program has a list of them.

This is the most common error in this entire series, and now you know what it means every time you see it: **something this code needs is not installed yet.** Not a bug. A shopping list.

## **Section 3 — Three programs, three different jobs ^sec3**

**Heading** — Three programs, three different jobs

Getting reportlab onto your computer takes three things, and people get lost here because all three are called "installing." They are not the same job.

| This | Installs | Into |
| --- | --- | --- |
| **Homebrew** | Programs | Your Mac |
| **Python** | — it *is* a program — | — |
| **pip** | Libraries | One particular Python |

Read it downward. Homebrew installs Python. Python runs your script. pip puts libraries inside Python so your script can reach them.

If you remember one sentence from this module: **Homebrew installs programs, pip installs libraries, and they are not interchangeable.** Typing `brew install reportlab` will not work, and typing `pip install python` is nonsense. Everyone tries at least one of them.

## **Section 4 — Homebrew ^sec4**

**Heading** — Homebrew

**Homebrew is an app store for programs that have no icon.** You type the name of what you want and it fetches it and puts it where it belongs. Every developer on a Mac has it. Once it is there you will use it for years without thinking about it.

### **Try it yourself 6.3 ^try-6-3**

Paste this whole line and press return:

```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

It explains what it is about to do and waits for you to press return. It asks for your Mac password — the one you log in with. **Nothing appears as you type it.** That is normal and it is not frozen.

It takes several minutes.

### **Try it yourself 6.4 ^try-6-4**

When it finishes it prints a short section headed **Next steps** with two or three commands in it. **Run them.** On most Macs they look like this:

```
$ echo >> ~/.zprofile;
$ echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile;
$ eval "$(/opt/homebrew/bin/brew shellenv)"
```

Use the ones your own installer printed if they differ. Then check:

```
$ brew --version
```

A version number means it worked.

### **What just happened ^reveal-r3**

**Button hint** — Get a version number back first

*Why it made you do that last part*

In Module 5 you saw that every command is a program: `cat`, `open`, `mkdir`. When you type a word, your terminal goes looking for a program by that name, but only in a short list of folders. That list is called your **PATH**. Homebrew installed itself somewhere that is not on that list yet, so without those commands you would type `brew` and be told *command not found* — with the program sitting right there on the disk.

Those lines add Homebrew's folder to PATH, and write it into *.zprofile* so it happens in every future terminal window rather than just this one.

**If you skipped them,** nothing is damaged. Run them now.

## **Section 5 — A Python of your own ^sec5**

**Heading** — A Python of your own

Your Mac already has a Python — that is what ran your script in Module 2, and what just gave you the error. So why install another?

Because that one belongs to Apple. macOS uses it for its own purposes, it is usually several years old, and things you install into it can be wiped out by a system update. It is there to run your Mac, not to run your projects.

### **Try it yourself 6.5 ^try-6-5**

Notice how ordinary installing is from here on:

```
$ brew install python
```

Then check what you have:

```
$ python3 --version
```

A 3.13 or 3.14 means you are on the new one. If it still says 3.9, close the terminal window, open a new one, and check again.

That is the whole shape of installing software from now on. `brew install` and a name. No download page, no dragging anything into Applications, no clicking Next four times.

## **Section 6 — The project's own Python ^sec6**

**Heading** — The project's own Python

Now install the library. The obvious command is the one that will not work, and it is worth doing anyway, because what it says next is genuinely useful.

### **Try it yourself 6.6 ^try-6-6**

Standing in *~/Projects/worksheets*:

```
$ pip3 install reportlab
```

It refuses:

```
error: externally-managed-environment
```

and then tells you, in its own words, exactly what to do instead.

Read what it printed. Underneath the error it says: *if you wish to install a Python library that isn't in Homebrew, use a virtual environment* — and gives you the commands.

This is a refusal with a reason. Homebrew's Python belongs to Homebrew, and letting every project shove libraries into it is how you end up with one project breaking another. So it asks you to make one that belongs to *this folder*.

### **Try it yourself 6.7 ^try-6-7**

Make this project its own private Python, and switch to it:

```
$ python3 -m venv .venv;
$ source .venv/bin/activate
```

**Look at your prompt.** It now begins with `(.venv)`. That is the terminal telling you which Python you are talking to — the same way it has always told you which folder you are standing in.

Now install the library. Inside a venv you can drop the 3:

```
$ pip install reportlab
```

### **Try it yourself 6.8 ^try-6-8**

Run the same command that failed twenty minutes ago:

```
$ python make_worksheets.py
```

Then open the folder in Finder and look at what appeared.

### **What just happened ^reveal-r4**

**Button hint** — Open worksheets.pdf before you read this

Forty-two worksheets and an answer key, in about two seconds, on your own computer.

**You did not write the hard part.** Nothing you did today knows how to draw a letter shape on a page, or how wide a 7 is in Helvetica, or what a PDF file looks like on the inside. Somebody spent twenty-five years on that and gave it away.

Open *make_worksheets.py* and look at how short it is. Roughly a hundred lines, and most of them are about *your* problem — twenty sums, two columns, a name at the top. The unglamorous, difficult, universal part came from the library.

**That is what this whole sequence is about.** Not learning to write everything. Learning to write the small part that is yours, on top of the enormous part that is everybody's.

### **Side note ^aside-2**

**Tomorrow, when you come back.** A venv is switched off when you close the terminal. Standing in the folder again, run `source .venv/bin/activate` before anything else — look for `(.venv)` in your prompt. If you forget, you get `ModuleNotFoundError` again, which by now you can read. Typing `deactivate` switches it off on purpose.

## **Section 7 — Now make it yours ^sec7**

**Heading** — Now make it yours

The program is in your folder and it is not precious. Change it.

### **Try it yourself 6.9 ^try-6-9**

Open *make_worksheets.py* and find these lines near the top:

```
PROBLEMS = 20
LOW, HIGH = 12, 99
```

Make it 12 problems between 100 and 999. Save, and run it again.

Everything downstream — the layout, the answer key, all forty-two children — follows.

### **Try it yourself 6.10 ^try-6-10**

Now ask for something the file does not do. Open Claude Code in this folder and try:

**Ask Claude**

> Change make_worksheets.py so the problems are multiplication instead of addition, and put the date in the top right corner of every worksheet. Keep the answer key working.

Then run it and check the key against a sheet. Do one sum yourself.

### **What just happened ^reveal-r5**

**Button hint** — Run it twice first

*Why the answer key can be trusted*

Run the script twice and Ayelet gets the same worksheet both times. That is not luck. Inside is a line that seeds the random numbers with the student's name:

```
rng = random.Random(name)
```

Which means "random" here is *random-looking but fixed*: the same name always produces the same twenty problems. If it were truly random, re-running the script would give you fresh worksheets and an answer key for the previous batch — and you would not find out until a child did.

It is a small decision by whoever wrote the program, and it is the difference between a clever tool and one you can actually put in front of a class. Worth noticing when Claude writes things for you.

### **Side note ^aside-3**

**Use your own class list — carefully.** *students.csv* has two columns and forty-two invented children, and your real class list would work exactly the same way. **Not yet.** Where school data is allowed to live is its own module and it comes later in this series. Until you have done it, keep real students out of your project folders — invent names, or use a staff list.

## **Section 8 — Where this goes ^sec8**

**Heading** — Where this goes

What you just ran is a small version of something real. The math fluency materials at Schechter are a folder of generators like this one: rules in, finished PDFs out, a set for every child, keys for every teacher, regenerated whenever the rules change.

None of that required learning to draw a PDF. It required knowing that somebody else already had.

**The question worth carrying out of this module is no longer "can I build that?"** It is "has somebody already built the hard part of that?" — and for almost anything you can think of, the answer is yes, it is free, and it installs in one line.

Ask Claude. *Is there a Python library that already does this?* is one of the most useful questions you can put to it, and it is the question people who have been doing this for years ask first.

## **Section 9 — If something went wrong ^sec9**

**Heading** — If something went wrong

| You saw | It means | Try this |
| --- | --- | --- |
| command not found: brew | Homebrew installed, but your terminal does not know where it is. | Run the **Next steps** commands from 6.4, then open a new terminal window. |
| externally-managed-environment | You are trying to install into Homebrew's Python instead of the project's. | That is expected — it is 6.6. Make the venv in 6.7 and install inside it. |
| ModuleNotFoundError | Almost always: the venv is not switched on. | Look for `(.venv)` at the start of your prompt. If it is missing, run `source .venv/bin/activate`. |
| No such file or directory | The terminal is standing somewhere else. | `cd ~/Projects/worksheets`, then `ls` to check both files are there. |
| The two files are in Downloads, not the folder | They were opened rather than moved. | Drag them in Finder into *worksheets*. Then `ls` should show both. |
| `python3 --version` still says 3.9 | This terminal window started before Homebrew was on PATH. | Close it and open a new one. If it persists, run the 6.4 commands again. |
| The PDF opens but every page is identical | The seeding was changed or removed. | Check the line `rng = random.Random(name)` is still there. Ask Claude to restore it. |
| Claude changed it and now nothing runs | Something in the edit is broken. | Paste the whole error back to Claude. If it is beyond saving, download *make_worksheets.py* again. |

## **Module tasks ^checklist**

The 8 checkboxes near the end, in the order the module does them:

1. Looked at the sample PDF and found two pages with different numbers
1. Ran the program and got ModuleNotFoundError on purpose
1. Installed Homebrew and ran its Next steps commands
1. Installed Python with brew install python
1. Saw externally-managed-environment and read what it suggested
1. Made a venv, saw (.venv) in my prompt, installed reportlab
1. Generated forty-two worksheets and an answer key
1. Changed the program myself, and then had Claude change it further

## **Section 10 — Before you finish ^sec10**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

Think of something in your job you have never even considered automating — not because it is tedious, but because it seemed impossible.

Go and ask Claude whether a library already exists for the hard part of it. Not whether it can be built — whether somebody has already built the difficult middle of it and given it away.

Then notice what still feels unclear. That part is the most useful thing you could ask Claude in the next five minutes.

### **Side note ^aside-4**

**Next:** Module 7 — *Using somebody else's project.* You have just used somebody else's library. Next is somebody else's whole project: how to get a copy of it, run it, and change it without asking anyone's permission.

## **Footer ^footer**

Developing with AI · Module 6. Written for macOS; the ideas are identical on Windows but several commands differ.
