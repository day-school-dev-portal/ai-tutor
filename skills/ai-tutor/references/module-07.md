# Module 7 — Using somebody else's project: the page's text

Generated from `dev-portal-site/modules/07-github.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 7

**Title** — Using somebody else's project

**For** anyone who has finished Sequence 1 **Time** about an hour **You need** Claude Code, and your terminal

---

**Label** — Before you start

Everything you have built so far, you built from nothing. That is a slow way to work, and it is not how anybody actually does this.

Almost every useful program starts as somebody else's program.

*This line sits alone in the clay-bordered box:*

A teacher at another school has already built the thing you need. How would you get a copy — and what do you think you would actually be getting? Think about it for a moment.

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 12 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**GitHub** Google Drive, but for computer programs. A place where developers put their projects so that other people can find them, download them, and use them. *Note:* Most of it is readable by anyone, without an account.

**Homebrew** A program whose job is installing other programs. Think of it as an app store for the terminal: you type the name of the thing you want, and it fetches and installs it.

**git** *(lowercase, not GitHub)* The program that copies projects down from GitHub and keeps track of every change made to them. *Note:* **git** is the tool on your computer. **GitHub** is the website. Different things, confusingly similar names.

**Repository** *(a repo)* One project on GitHub: its files, and the whole record of every change ever made to them. *Note:* A repo is a folder. You already know what to do with a folder.

**Clone** Copying a project onto your computer, once, because you do not have it yet. That is all the word means. *Note:* It lands in whatever folder you are standing in, so where you are standing when you type it matters.

**Pull** Updating a copy you already have, with whatever changed in the original since you took it. *Note:* Not the same thing as a **pull request**, further down, despite the name. Pull brings somebody's changes to you. A pull request offers yours to them.

**Public / private** A public repo can be read and copied by anyone in the world. A private one can only be seen by people who were given access. *Note:* Public does not mean editable. Anyone can read it; only the owner can change it.

**Open source** Software published so that anyone can read it, use it, and change it.

**License** A file saying what you are allowed to do with somebody's work. Without one, you technically may not use it at all, even if you can see it.

**Commit** One saved change, with a note explaining it. A repo's history is a list of these.

**Fork** Your own copy of somebody's repo, kept on GitHub under your name, which you *are* allowed to change.

**Pull request** An offer. "Here is a change I made to your project — would you like it?" The owner says yes or no.

## **Section 1 — A place where the work is kept ^sec1**

**Heading** — A place where the work is kept

**GitHub is basically Google Drive for computer programs.** It is a place where developers put their projects so that other people can find them, download them, and use them. There are hundreds of millions of them, and most can be read by anybody, without signing in.

That is stranger than it sounds. Imagine if every school's curriculum, every scheduling spreadsheet, every hard-won solution to a problem you also have, were simply readable — and you could take a copy and change it for your own building.

For software, that's how things work.

### **Try it yourself 7.1 ^try-7-1**

Go and look at a project. Open this in your browser:

```
github.com/day-school-dev-portal/group-maker
```

You did not sign in, and you can read every file. Click *index.html* and look at it — you are not expected to understand it.

Your goal in this module will be to download this project onto your computer and use Claude Code to improve it.

### **What just happened ^reveal-r1**

**Button hint** — Open a couple of the files first

You read somebody else's work without asking, and that's how it's supposed to work.

A folder on GitHub is called a **repository** — a repo. When it is public, anyone can read it and anyone can copy it. Only the owner can change it. Those are three separate things, and people new to this often assume that being able to read something means being able to break it. You cannot.

But to work on someone else's project, you will need to download the folder onto your computer — otherwise known as **cloning** the repo.

## **Section 2 — Two programs you need first ^sec2**

**Heading** — Two programs you need first

To get a project off GitHub and into your Projects folder you need one small program, and to install that one comfortably you want another. Neither costs anything and neither needs an account.

**Homebrew** is a program whose only job is installing other programs. Think of it as an app store for the terminal: you type the name of what you want, and it fetches it and puts it in the right place. Every developer on a Mac has it, and once it is there you will use it for years without thinking about it.

**If you did Module 6, you already have it.** Type `brew --version`; a version number means skip straight to 7.3. The full instructions are here anyway, because people arrive at these modules out of order and it is a bad thing to be missing.

**git** is a program that copies projects down from GitHub and keeps track of changes. It is an essential tool for developers.

### **Side note ^aside-1**

**git and GitHub are two different things.** `git`, lowercase, is a program on your computer. GitHub is a website. GitHub is named after git because it stores things git made, which is a genuinely confusing piece of naming that everybody just gets used to.

### **Try it yourself 7.2 ^try-7-2**

Install Homebrew. Paste this whole line into your terminal and press return:

```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

It will explain what it is about to do and wait for you to press return. It will ask for your Mac password — the one you use to log in to your computer. Nothing appears as you type it; that is normal. Type your computer's password and hit return.

It takes several minutes. When it finishes it prints a short section headed **Next steps** with two or three commands in it. **Copy and run those commands.** They tell your terminal where Homebrew lives. On most Macs they look like this:

```
$ echo >> ~/.zprofile;
$ echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile;
$ eval "$(/opt/homebrew/bin/brew shellenv)"
```

Use the ones your own installer printed if they differ. Then check it worked:

```
$ brew --version
```

If it prints Homebrew with a version number, it worked.

### **Try it yourself 7.3 ^try-7-3**

Now use Homebrew to install git. This is what it looks like to install anything from now on:

```
$ brew install git
```

Then check:

```
$ git --version
```

A version number means you are ready.

### **What just happened ^reveal-rA**

**Button hint** — Get a version number back first

You installed two programs by typing, and you will never install them again. Homebrew and git both stay on this computer.

Notice how small the second one was. `brew install git` — that is the whole shape of installing software from the terminal, and it is the same for the next hundred things. No download page, no dragging into Applications, no clicking Next.

Your Mac probably already had a version of git, tucked inside Apple's developer tools. Homebrew's is newer and easier to keep up to date, which is why we did it this way. If `brew install git` told you it was already installed, nothing is wrong.

**The password.** Homebrew asked for it because it needs to create folders your account does not normally write to. That is a reasonable thing to be asked once, by something you understood and chose to install, from an address you can read.

## **Section 3 — Cloning a repo ^sec3**

**Heading** — Cloning a repo

**Cloning just means copying a project onto your computer.** The command is `git clone`, and it brings down every file plus the whole record of changes made to it.

One thing decides where it lands: **the folder you are standing in when you type it.** Clone from the wrong place and the project ends up somewhere you will not find it again. So make sure your terminal is in your Projects folder before you clone the repo.

### **Try it yourself 7.4 ^try-7-4**

Move into your Projects folder — the one you made in Module 1 — and check you are actually there before doing anything else.

You can get there by using your terminal to navigate to *Projects* with the `cd` command.

**Tip.** You can also turn on a setting that opens a terminal window at any folder. Open **System Settings → Keyboard → Keyboard Shortcuts → Services**, find *Files and Folders*, and tick **New Terminal at Folder**. It is off on every Mac until you turn it on, and it is worth doing once — after that you can right-click any folder and choose *New Terminal at Folder* to open a terminal already standing in it.

Now take the copy. In that terminal window, run:

```
$ git clone https://github.com/day-school-dev-portal/group-maker.git
```

A new folder called *group-maker* appears alongside your other projects. Go in and look, by clicking or through the terminal:

```
$ cd group-maker;
$ pwd;
$ ls
```

Open Finder and look at *Projects* as well. The folder is really there, next to *tic-tac-toe*.

### **Side note ^aside-2**

**If you would rather be explicit.** You can say exactly where a project should land, and then it does not matter where you are standing:

```
$ git clone https://github.com/day-school-dev-portal/group-maker.git ~/Projects/group-maker
```

The path on the end is where to put it. Same result, no guessing.

### **Figure ^figure-1**

**Caption** — Cloning copies in one direction. From this moment the two are separate: you can do anything you like to your copy, and nobody else will ever see it unless you deliberately send it back.

**Description read aloud by screen readers** — Diagram: a box labelled GitHub, holding the group-maker repository, with a one-way arrow labelled git clone pointing to a second box labelled your computer, holding a folder inside Projects. A note says changes you make do not travel back.

### **What just happened ^reveal-r2**

**Button hint** — Look inside the folder first

You now have a complete copy of somebody else's project, sitting in your Projects folder like anything else you have made.

Not a download of the current version — the *whole repository*, including every change anyone has ever made to it and why. That history is in a hidden folder called `.git`, which you will meet properly in a later module.

The important part is what this copy is **not**. It is not connected to anything. It is not shared. Nothing you do to it will reach the original, or anybody else's copy, or the internet. You can delete every file in it and no one will notice.

It is as if you photocopied an entire book and brought it home. You can mark up that photocopy as much as you like.

That freedom is the whole point. You can experiment on a stranger's software with no possibility of damaging their work.

## **Section 4 — Ask before you struggle ^sec4**

**Heading** — Ask before you struggle

You now have a folder full of a project somebody else built. Open *index.html* and it is nine hundred lines of code you did not write. This is the normal situation, and it is where most people give up.

**You do not need to understand these files yourself.** That sentence is the point of this entire module, so it is worth saying plainly: from here on, **Claude is your interface to other people's code** — the way Finder is your interface to files you never look inside.

You do not read a PDF by opening it in a text editor. You do not inspect a photo byte by byte. You hand it to something that knows how to read it, and you work at the level you actually care about. Somebody else's project is the same: you hand it to Claude, and you stay at the level of *what should this do differently?*

So do not go hunting through the files. **Point Claude at the folder and ask.** When you inherit a project, the first thing you do is hand it over and get your bearings.

### **Try it yourself 7.5 ^try-7-5**

Open a new Claude Code session and select the *group-maker* folder as your working directory — the folder itself, inside *Projects*. Then ask this:

**Ask Claude — the first thing to ask about any project you did not write**

> I just cloned this and didn't write any of it. What is it, how do I run it, and what should I know before I change anything?

**Now do what it told you** — open the folder and double-click *index.html*. Paste in a real class list, or use the sample. Make some groups. Print them if you like. Feel free to ask Claude any other questions about this project as well.

Then try this: **put in thirteen names and ask for groups of four.** Look carefully at the last group.

### **What just happened ^reveal-r3**

**Button hint** — Ask, run it, and try the thirteen names first

You asked instead of guessing, and thirty seconds later you knew what the project was, that you needed nothing installed, and exactly how to start it.

**That prompt is the reusable thing here.** It is not about this project. Use it on anything you did not write — a repo a colleague sends you, something you find on GitHub, a folder you made yourself and forgot about. The four questions are always the same: what is it, what do I need, how do I run it, what should I be careful of.

The middle one matters most. Almost every "I couldn't get it working" is a missing prerequisite, and it is the question a beginner does not know to ask. Here the answer was *nothing* — you double-clicked a file you downloaded four minutes ago and it worked. That is not luck. Somebody decided to keep the whole thing in one file with nothing else required, precisely so a teacher could do what you just did. Plenty of projects are not like that. Whether a project is easy to start is a choice its author made.

And you found the flaw. Thirteen students in groups of four gives you 4, 4, 4, and then one child sitting alone. The README warned you, the app greys out that card — and it still does the wrong thing.

You are now looking at a real problem in real software, and you have the source code on your computer.

## **Section 5 — Every project has house rules ^sec5**

**Heading** — Every project has house rules

Claude told you how to run it. It also knew something less obvious: what this project will and will not allow you to do to it.

### **Try it yourself 7.6 ^try-7-6**

Still in *group-maker*, ask:

**Ask Claude**

> What rules does this project have about how it must be built, and where are those rules written down? Quote the file to me.

Then go and open that file yourself, in your project folder, and read it.

### **What just happened ^reveal-r4**

**Button hint** — Read the file yourself before opening this

The rules were in `CLAUDE.md`, and Claude had already read them before you asked.

Look at what they say: one file only, no frameworks, nothing leaves the browser because class lists are student information, it must print. Those are the author's decisions, and Claude will follow them while working here. Not because you asked it to. Because they were written down in the folder.

`README.md` and `CLAUDE.md` are the two files you wrote in Module 1, and this is the payoff. You wrote them for a hypothetical stranger. Now *you* are the stranger, opening somebody else's folder — and the folder explains itself, to you and to Claude at the same time.

This is the strongest argument for writing those files in your own projects, and it is hard to feel until you have been on this side of it. Somebody you have never met is about to save you an hour, because they spent ten minutes writing down what they knew.

## **Section 6 — Making it better ^sec6**

**Heading** — Making it better

Now fix the thing that is wrong with it.

### **Try it yourself 7.7 ^try-7-7**

**Ask Claude**

> The README describes a known problem: when the class does not divide evenly, all the leftover students end up in the last group and one student can be left on their own. Fix it so the group sizes differ by at most one. Follow the rules in CLAUDE.md.

Then **go and check**. Reload the page in your browser and try thirteen names in groups of four again. You should get 4, 3, 3, 3. Nobody alone.

Try a few awkward numbers — seven, nine, twenty-two. Try one name. Try none.

### **Try it yourself 7.8 ^try-7-8**

The README is now wrong: it still describes a problem that no longer exists. Fix that too:

**Ask Claude**

> Update the README now that the leftover-student problem is fixed. Move it out of "Known problem" and describe the behaviour as it is now.

### **What just happened ^reveal-r5**

**Button hint** — Check thirteen names before you open this

You improved somebody else's software. Forty minutes ago you had never seen it.

Notice the sequence, because it is the whole method: you read what the project said about itself, you ran it, you reproduced the problem with your own eyes, you described the fix in plain language, and then you checked the result yourself instead of believing the report.

Nothing about that required you to read the code.

And the second exercise matters as much as the first. You changed how something behaves, so the writing that described it became a lie. Documentation that no longer matches is worse than none, because the next person — or the next Claude — will believe it. Updating it is part of finishing, not a chore afterwards.

## **Section 7 — Whose copy is it now? ^sec7**

**Heading** — Whose copy is it now?

Your version is better than the published one. The published one has not changed.

Nothing you did travelled anywhere. The copy on your computer is yours, permanently and privately, and you can keep using it exactly as it is.

If you wanted to offer the fix back, that is a **pull request** — you make your own copy of the repo on GitHub, called a **fork**, put your change there, and offer it to the owner, who says yes or no. That is a later module. It is worth knowing the door exists.

**The reverse is true as well, and it catches people out: the original can change, and your copy will not notice.**

`git clone` copied the project once, on the day you ran it. It took a photograph; it did not open a window. If somebody improves *group-maker* next month, nothing about your folder changes. It does not check. It will not tell you.

Catching up is a second command, and the difference between the two is worth holding on to:

| Command | What you are saying | How often |
| --- | --- | --- |
| git clone | I do not have this project. Get me a copy. | Once, ever, per project. It creates the folder. |
| git pull | I already have it. Bring me whatever changed since. | Whenever you want to catch up. Run it inside the folder. |

Almost everyone new to this tries to clone a second time to get updates. It is the one thing clone will not do — git stops and says *destination path already exists*, which is the error in the table at the end of this module, and now you know why it happens.

### **Try it yourself 7.9 ^try-7-9**

Ask your copy whether the original has moved on. From inside *group-maker*:

```
$ cd ~/Projects/group-maker;
$ git pull
```

You will almost certainly get back `Already up to date.` Nothing has changed in the original since you cloned it, so nothing came down. **That is the answer to your question, not a failure to do anything.**

### **Side note ^aside-3**

**Notice what you did not have to tell it.** Not which project, not what address to fetch from. **The folder remembers where it came from.** That came down with the copy and has been sitting in the hidden `.git` folder ever since — which is the real difference between a folder you cloned and a folder you made yourself. They look identical in Finder. Only one of them can answer *has the original changed?*

### **Side note ^aside-4**

**If it ever says something other than that.** You changed *index.html* in 7.7. Had the original changed that same file, `git pull` would have stopped and told you, rather than quietly picking one version over the other. That is git being careful with your work, and it is also an annoying afternoon. Paste the whole message into Claude when it happens; it looks far more alarming than it usually is.

### **Try it yourself 7.10 ^try-7-10**

One last thing, and it is the one people skip. Find out what you are actually allowed to do with this:

**Ask Claude**

> There is a LICENSE file in this project. In plain English, what does it let me do? Could I use this at my school, change it, and give it to a colleague?

### **What just happened ^reveal-r6**

**Button hint** — Ask about the license first

This project is MIT licensed, which is about as permissive as it gets: use it, change it, share it, even sell it, as long as the copyright notice stays attached.

The reason to check is that **the absence of a license means the opposite.** Code with no LICENSE file is all-rights-reserved by default — you can read it, but strictly speaking you may not use it, even though it is sitting there in public. Most people ignore this. For something your school is going to depend on, ignoring it is a bad habit.

Two minutes and one question is the whole cost of knowing.

## **Section 8 — What this unlocks ^sec8**

**Heading** — What this unlocks

You can now take any public project in the world, put it on your computer, get it running, understand it well enough to judge it, and change it to suit your school.

That is a genuinely different position from where you were this morning. Most problems you have are problems somebody has already solved, and their answer is readable, copyable, and usually free.

The skill that made it work was not `git clone`. It was reading the README, running the thing, and checking the result with your own eyes.

**Ask Claude — when you find something you might use**

> I am looking at this project on GitHub: [paste the link]. Before I clone it, tell me what it does, what I would need installed to run it, whether it is still maintained, and what its license allows.

### **Side note ^aside-5**

**A word of care.** Cloning a repository copies somebody else's files onto your computer, and running one runs somebody else's instructions. For a single HTML file you can see, that is nothing. For a project that wants to install things or asks for a password, stop and ask Claude what it does before you run it — the same question you would ask about any command you did not write.

## **Section 9 — If something went wrong ^sec9**

**Heading** — If something went wrong

| You saw | It means | Try this |
| --- | --- | --- |
| command not found: brew | Homebrew installed, but your terminal doesn't know where it is yet. | Run the *Next steps* commands the installer printed. If that window is gone, close the terminal, open a new one, and try again. |
| git: command not found | Git isn't installed yet. | Run `brew install git`. If Homebrew isn't there either, do 7.2 first. |
| The clone landed in the wrong place | You were standing somewhere else when you typed it. | Drag the folder into *Projects* in Finder, or delete it and clone again after `cd ~/Projects`. |
| destination path already exists | You already cloned it. | You're done — `cd group-maker` and carry on. To start clean, delete the folder in Finder first. |
| Repository not found | A typo in the address, most likely. | Copy the link again from the button above. Watch for a missing `.git` at the end. |
| The game opened as a page of code | It opened in a text editor, not a browser. | Right-click *index.html*, choose *Open With*, and pick a browser. |
| Claude can't see the project | It's standing in a different folder. | Ask it what folder it's in. Open *group-maker* itself, not *Projects*. |
| Your fix didn't seem to work | The browser is showing the old version. | Reload the page. Hold **⇧** while reloading if it's stubborn. |

## **Module tasks ^checklist**

The 10 checkboxes near the end, in the order the module does them:

1. Read a stranger's project on GitHub without signing in
1. Installed Homebrew, and got a version number back
1. Installed git with `brew install git`
1. Cloned the project into my Projects folder, on purpose
1. Ran it, and reproduced the known problem myself
1. Opened it in Claude Code and had it explain the project
1. Fixed the problem, and checked the fix with my own eyes
1. Updated the README so it tells the truth again
1. Ran `git pull`, and know why cloning twice is not how you get updates
1. Found out what the license lets me do

## **Section 10 — Before you finish ^sec10**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

A teacher at another school has already built the thing you need. How would you get a copy — and what do you think you would actually be getting?

Answer it again now. You would get all of it — every file, every change ever made, and the right to do whatever you like with your copy.

Then notice what still feels unclear. That part is the most useful thing you could ask Claude in the next five minutes.

### **Side note ^aside-6**

**Next:** Module 8 — *APIs, tokens and signing in.* You can now take somebody else's code. Next is somebody else's *data* — starting with a poem that arrives in three seconds and needs nothing at all, and ending with your own Google account, which does.

## **Footer ^footer**

Developing with AI · Module 7. Written for macOS; the ideas are identical on Windows but several commands differ.
