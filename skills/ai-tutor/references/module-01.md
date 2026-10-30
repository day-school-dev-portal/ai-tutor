# Module 1 — Getting set up with Claude Code: the page's text

Generated from `dev-portal-site/modules/01-claude-code.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 1

**Title** — Getting set up with Claude Code

**For** anyone. This is where the series starts **Time** about an hour and a quarter **You need** a Mac, and about 2 GB of free space

---

**Label** — Before you start

You have used Claude in a browser. It can read what you paste into it, and it can write things back. It cannot open the files and folders on your computer.

So when you ask it to make something substantial — a web page, a document, a small app — there is nowhere for it to save it. It hands you an **artifact** instead: a panel beside the conversation showing the finished thing. An artifact lives inside that conversation. It is not a file, and it is not on your computer until you download it.

Claude Code can open your files. It can read them, change them, and make new ones, so by default what it makes is files — in a folder you chose, where any other program can open them. That is most of the difference between the two, and it is why the rest of this module is about folders.

*This line sits alone in the clay-bordered box:*

If Claude can reach into your computer, what do you think decides which of your files it is allowed to touch? Think about it for a moment.

**Label** — Core vocabulary

Open this and take a look. These are the words this module will give you. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 13 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**Claude Code** Claude, running on your computer, able to read and write real files. Same Claude, but with hands.

**Artifact** Something Claude made that lives inside the conversation, rather than in a folder on your computer. Claude in a browser makes these, because it has nowhere else to put things. *Note:* It is not a file until you download it. Module 4 comes back to this.

**Folder** *(or directory)* A container that holds files and other folders. Everything on your computer is inside one. *Note:* Programmers call a folder a **directory**. Same thing — Claude will use both words.

**Home folder** The folder named after you. Your Desktop, Documents and Downloads are all folders inside it. *Note:* Written in shorthand as `~`, so `~/Projects` means the *Projects* folder inside your home folder.

**Path** A file or folder's address: the folders you would open to reach it, in order, with a slash between each. *Note:* `/Users/your-name/Documents/Budget.docx`

**Working directory** The one folder Claude Code is working inside. You choose it when you start. *Note:* It is the single most important idea in this module.

**Project** A folder holding everything for one piece of work: the files, the notes, the history. Not a special kind of folder — just an ordinary one you have decided to treat as a unit. *Note:* Keep them all together in one `~/Projects` folder, one folder per project.

**Session** One continuous conversation with Claude Code. Close the window and the conversation ends. The files it made stay.

**Context** Everything Claude can see right now: your messages, and the files it has read from your working directory. It cannot see anything else.

**Permission** Claude asks before it changes or deletes something. You approve or decline. Reading is usually free; writing usually asks.

**`CLAUDE.md`** A plain text file in your project that Claude reads at the start of every session. What you write here, Claude knows next time. *Note:* This is what people mean by "giving Claude a memory." The memory is a file.

**`README.md`** A plain text file describing what a project is and how it works, written for a person. Claude reads it too, which is most of why it is worth writing.

**Markdown** *(the .md ending)* A way of writing formatted text in a plain file. A `#` makes a heading, `**stars**` make bold. A plain text format that both people and AIs read easily — which is why AIs write `.md` files when they document a project or write something down to remember.

## **Section 1 — Claude, with hands ^sec1**

**Heading** — Claude, with hands

Everything you do with files by hand — open a folder, see what is in it, read a file, make a new one — Claude Code (or another AI) can do. You describe what you want in plain language. It does the work.

That is the whole idea. You are not learning to write code. You are learning to use a tool that is very good at writing code — an experienced software engineer that does exactly what you ask. Which means what you ask matters.

### **Try it yourself 1.1 ^try-1-1**

Install the app.

- Go to claude.ai/download and download Claude for Mac.
- Open the file you downloaded and drag Claude into your Applications folder.
- Open Claude and sign in with your school account.
- In the app, find the **Code** tab in the top left corner. It looks like this: `</>`
You will be asked to allow a few things the first time. That is expected — the app is asking permission to work on your computer, which is exactly what you want it to be careful about.

### **Side note ^aside-1**

**If the screen doesn't match.** This app changes often, and a button may have moved since this was written. The shape stays the same: download, install, sign in, find Code. If something looks different, that is the app being updated, not you doing it wrong.

## **Section 2 — Everything on your computer is in a folder ^sec2**

**Heading** — Everything on your computer is in a folder

Claude Code works inside folders, so it is worth being sure what a folder is before you hand it one.

A **file** is one thing: a document, a photo, a spreadsheet. A **folder** is a container. It holds files, and it can hold other folders, which can hold more folders. That is the whole idea, and your entire computer is built out of it.

### **Try it yourself 1.2 ^try-1-2**

Find the folder with your name on it.

- Click once on your desktop, so Finder is the app in front. Then choose **Go → Home** from the menu bar at the top of the screen, or press **⌘ ⇧ H**.
- A window opens with your name at the top. Inside it you will find *Desktop*, *Documents* and *Downloads*, among others.
- Now choose **View → Show Path Bar**. A thin strip appears along the bottom of the window.
- Open *Documents*, then any folder inside it. Watch the strip at the bottom change as you go.
### **What just happened ^reveal-r0**

**Button hint** — Watch the path bar change first

You found your **home folder**: the one with your name on it, which holds nearly everything that is yours.

Notice what was inside it. Your Desktop is not a special place. It is an ordinary folder, sitting in your home folder next to *Documents* and *Downloads*. Your Mac just happens to draw what is in it behind your windows. Open the *Desktop* folder and you will find everything that is on your desktop.

The strip at the bottom is the **path bar**. It shows where you are as a chain of folders, each one inside the one before it. Your home folder is inside a folder called *Users*, which is inside your Mac's disk — the folder at the very top, holding everything else.

Leave the path bar turned on. It is the single most useful thing you can do to a Finder window, because it always answers the question *where am I?*

### **Figure ^figure-1**

**Caption** — Folders inside folders. Every file on your computer is somewhere in this nest, and in exactly one place.

**Description read aloud by screen readers** — Diagram: folders drawn as boxes inside boxes. The outermost box is Macintosh HD. Inside it is Users. Inside that is your-name, your home folder, highlighted. Inside your home folder are three folders side by side: Desktop holding notes.txt, Documents holding Budget.docx and Handbook.pdf, and Downloads holding roster.csv.

That chain of folders, written out with a slash between each one, is called a **path**. It is a file's address. The handbook in the drawing lives here:

`/Users/your-name/Documents/Handbook.pdf`

Read it left to right: start at the top, open *Users*, open your home folder, open *Documents*, and there is the file. Each slash is one folder you step inside.

Your home folder comes up so often that it has a shorthand: `~`. So `~/Documents` means the Documents folder inside your home folder, whoever you are.

You will rarely type a path. But Claude will show you paths constantly, because a path is the only way to say exactly which file you mean. “The spreadsheet on my desktop” could be three different files. A path is one.

### **Try it yourself 1.3 ^try-1-3**

Have your Mac write a path out for you. Find any file — something on your desktop will do.

- Right-click it. A menu appears, with *Copy* partway down.
- Keep the menu open and **hold down the ⌥ Option key**. Watch *Copy* change into **Copy “name” as Pathname**.
- Still holding Option, click it.
Paste it somewhere you can read it — a new TextEdit document will do. Then compare it with the path bar at the bottom of the Finder window. Same folders, same order: one written as words, one drawn as icons.

The keyboard shortcut, once you trust it, is **⌘ ⌥ C** with the file selected.

## **Section 3 — Claude works inside one folder ^sec3**

**Heading** — Claude works inside one folder

Before Claude Code will do anything, it asks you a question: *which folder?*

That folder is the **working directory**, and it is the most important thing in this module. Claude works on the files inside it. To reach anything outside it — your Downloads, your Documents, the rest of your Mac — it has to ask you first, and you can say no.

So the first real skill is deciding what folder you want Claude to work in.

### **Try it yourself 1.4 ^try-1-4**

Before the first project, make the place the projects will live: one folder in your home folder called **Projects**. Every time you start something new, you will make a folder inside it to hold the files Claude creates.

Go back to your home folder (**⌘ ⇧ H**), right-click an empty part of the window, and choose *New Folder*. Name it **Projects**.

You will see it alongside Desktop, Documents and Downloads — an ordinary folder, sitting where you will always be able to find it. Its path is `~/Projects`.

You only ever do this once.

**Tip.** When you need the path of any folder, use the Option-copy trick from 1.3: right-click it, hold **⌥**, and choose *Copy “name” as Pathname*.

### **Side note ^aside-2**

**Why not the desktop?** Because in a year there will be nine of these, and a desktop is where things go to get lost. One predictable home means you never have to hunt for a project, and neither does anyone you hand your computer to.

### **Try it yourself 1.5 ^try-1-5**

Now make the folder for this particular project inside it, called **tic-tac-toe**. Same move: open *Projects*, right-click, *New Folder*.

One folder, empty, with a name that says what it holds. This is where you will build your first project with Claude.

Now open Claude, make sure you are in **Code**, and click **+ New**. A window appears with a box at the bottom where you type. What you write in that box is called a **prompt**.

When you start a new session, Claude asks which folder to work in. Point it at *tic-tac-toe*, inside *Projects*.

If it does not ask — because it has remembered somewhere from last time — the folder it is using is shown just above the box where you type. Click it and change it.

**Open the project folder itself — not *Projects*.** You want Claude standing in *one* project, not looking at all of them.

### **Figure ^figure-2**

**Caption** — The working directory is not a setting. It is a fence, and you hold the gate. Everything inside it is Claude's world for this session; to go past it, Claude has to ask you.

**Description read aloud by screen readers** — Diagram: a box labelled tic-tac-toe contains three files and is fully lit. Outside the box, other folders on the computer are drawn faded, with a line noting that Claude has to ask before reaching them.

### **Try it yourself 1.6 ^try-1-6**

Ask Claude where it is standing. Type this into Claude Code:

**Ask Claude**

> What folder are you working in right now, and what files can you see in it?

It will tell you the path — the same kind of path you copied in 1.3 — and that the folder is empty.

### **What just happened ^reveal-r1**

**Button hint** — Ask it first

Claude answered with a path, because a path is genuinely where it is. Put it next to your path bar and you will see the same chain of folders: your home folder, then *Projects*, then *tic-tac-toe*.

This matters more than it sounds. When people say Claude "did something weird to my files," it is almost always because it was standing somewhere they did not expect. If you know which folder Claude is in, you know exactly what it can reach without asking you.

**One folder, one job.** Make a new folder inside *Projects* for each new piece of work. A folder holding one project is easy to reason about. A folder holding everything you have ever made is not.

**And this is how every session starts, forever.** Claude Code may offer the folder you had open last time, but it never goes looking for the one you mean. Every time you sit down, the first thing you do is point it at the project you intend to work on. Open the wrong folder and Claude is standing somewhere else, unable to see any of your work — not broken, just somewhere else.

## **Section 4 — Make something ^sec4**

**Heading** — Make something

An empty folder is the right place to start, because you will be able to see exactly what appears in it.

### **Try it yourself 1.7 ^try-1-7**

Ask for a game.

**Ask Claude**

> Make me a tic tac toe game. Two players taking turns on the same computer. When you are done, tell me how to open it.

Claude will ask permission to create a file. Say yes. Watch what it does — it is writing, then reading back what it wrote, and it will tell you when it is done.

### **Try it yourself 1.8 ^try-1-8**

Go and find the file Claude made. You will have to leave Claude to do this, which is the point.

Open your *Projects* folder, then *tic-tac-toe*. There is a new file in there that was not there ten minutes ago.

It will be an `.html` file — the kind of file websites are made of. Whether an HTML file is on the internet or sitting in a folder on your computer, your browser can open it either way.

**Double-click it and play a round.** You just built a computer game.

### **What just happened ^reveal-r2**

**Button hint** — Play a round first

Claude made a file. That is the entire thing it did.

There is no game stored inside Claude, and nothing was saved to a website. There is a file in your project folder, made of text, which your browser knows how to draw as a game. You could email it to someone. You could open it in ten years.

That is the difference from an artifact, and it is bigger than it looks. **A file is yours.** It sits on your disk, it is backed up with everything else you own, any program can open it, and it needs no account anywhere. An artifact is convenient, and it is a feature of somebody's product.

Everything Claude Code does ends up as a change to a file in your working directory. Every single time. That is all Claude does.

This is also why **going to look** is the habit worth building. Claude will tell you what it did. The folder will show you what it did.

## **Section 5 — Change it ^sec5**

**Heading** — Change it

Now the part that is really amazing. You do not have to know how to write HTML, or any other computer language, in order to change it.

### **Try it yourself 1.9 ^try-1-9**

You are going to change your game. Think of something you want to be different about it. You do not have to use technical language — just describe, as concretely as you can, what you want.

Use this prompt, or change it however you like:

**Ask Claude**

> Change the colors. I want a warm palette — a cream background, deep terracotta for X, and a muted blue for O. Keep the board lines thin and light.

Reload the game in your browser and look.

### **Try it yourself 1.10 ^try-1-10**

Now ask for something vaguer, and see how far plain language gets you. Pick one, or write your own:

- Make it feel like a board game from the 1970s.
- Make it look like it was drawn by hand in pencil on graph paper.
- Make it feel calm and expensive. Lots of space, one accent color.
**Ask Claude**

> Redesign the look of the game so that it feels like it was drawn by hand in pencil on graph paper. Change only the appearance, not how the game works.

If you don't like it, say so and ask for something else. That is a normal part of the work, not a failure — it often takes some back and forth to get it looking the way you want.

### **What just happened ^reveal-r3**

**Button hint** — Make at least two changes first

You described an outcome. Claude edited the file. You looked at the result and decided whether it was right.

Notice what you did *not* do: you never opened the file, and you never learned what any line of it means. Your job was to know what you wanted and to judge what came back. That is most of this work.

Notice also that the second request was vague on purpose. "Drawn in pencil on graph paper" is not an instruction a computer could follow. It is a description a person can interpret — and interpreting it is exactly what Claude is for. Being specific about *feeling* is often more useful than being specific about *technique*.

And the file in your project folder is different now. Same file, new contents. Nothing else on your computer changed.

## **Section 6 — Telling Claude something worth remembering ^sec6**

**Heading** — Telling Claude something worth remembering

Close Claude Code and open it again, and the conversation is gone. It will not remember that you like warm colors, or that this is a two-player game, or anything else you said.

Unless you write it down. And the place you write it down is a file called `CLAUDE.md`.

### **Try it yourself 1.11 ^try-1-11**

Ask Claude to remember something about how you want this project to look:

**Ask Claude**

> Please create a CLAUDE.md file in this folder and write down that this project should always use a warm, paper-like color palette, and that the game must stay in one single HTML file.

Then go and open `CLAUDE.md` yourself, in your project folder. You should recognize what is in it. It is your own instruction, written into a file.

### **What just happened ^reveal-r4**

**Button hint** — Read the file before opening this

You gave Claude a memory, and the memory turned out to be a text file sitting in your folder.

Think of `CLAUDE.md` as Claude's memory for this project. It is read at the start of every session here, so anything in it is something Claude knows before you say a word — tomorrow, next month, or on a colleague's computer if you send them the folder.

The `.md` is an extension, the same as `.docx` or `.csv`. It stands for Markdown: a plain text format with a few marks in it — `#` for a heading, `**stars**` for bold — that both people and AIs read easily. That is why AIs reach for `.md` files when they want to document something or write something down to remember.

Because it is a plain file, **you can open it and edit it yourself**. You do not have to ask Claude to change its own memory. Open it in TextEdit and add a line, and Claude will read your line next time.

This is the whole trick to working well with Claude Code over time. A thing you have to explain twice is a thing that belongs in `CLAUDE.md`.

**It also explains why pointing Claude at the right folder matters so much.** This memory lives in *this* project. Open *tic-tac-toe* and Claude reads it. Open a different project and Claude reads that one's memory instead, and knows nothing about warm colors. The memory is not attached to Claude. It is attached to the folder.

### **Side note ^aside-3**

**Worth knowing.** Keep it short and keep it true. `CLAUDE.md` works best as a handful of durable facts and preferences — how you want things to look, what must not change, what this project is for. It is not a diary, and a stale instruction in it is worse than no instruction at all.

## **Section 7 — Leaving a note for whoever comes next ^sec7**

**Heading** — Leaving a note for whoever comes next

There is one more file worth having, and it is the one every project in the world already has: a **README**.

A README says what this thing is, who it is for, and how to use it. It is written for a person. But it is also the first thing Claude reads when it wants to understand a project it has not seen before — which, after a few weeks away, includes this one.

### **Try it yourself 1.12 ^try-1-12**

Ask for one:

**Ask Claude**

> Write a README.md for this project. Say what the game is, how to open and play it, and how someone would change the way it looks. Write it for a person who has never seen this folder before.

Read it, and then open the *tic-tac-toe* folder in Finder and look one last time.

### **What just happened ^reveal-r5**

**Button hint** — Read your README first

Three files, and between them they hold everything: the thing itself, the instructions for changing it, and the explanation of what it is.

The README is doing double duty, and that is the part worth carrying forward. A person opening this folder can find their footing. So can Claude — when you come back in March having forgotten all of this, Claude reads the README and picks the project up faster than you will.

This is why the advice "write a README" is not bureaucracy. On a school system that a colleague will inherit, or that you will return to after a year, it is the difference between a folder someone can use and a folder someone has to reverse-engineer.

## **Section 8 — What you actually learned ^sec8**

**Heading** — What you actually learned

You installed an application, which is the least interesting thing that happened.

The rest is this. Claude Code stands in one folder. It can reach everything inside it, and nothing outside it without your yes. Everything it does turns into a change to a file you can open, read, email, or throw away. And two of those files — `CLAUDE.md` and `README.md` — are how the folder explains itself to whoever opens it next, including Claude.

None of that is about tic tac toe. It is exactly how you will work on a class roster, a report card template, or a schedule.

**Ask Claude — before you start anything real**

> I want to start a new project about [describe it]. What should I call the folder, where should I put it, and what should go in the CLAUDE.md before we start?

### **Side note ^aside-4**

**Before you point this at school data.** Do not put student information into a project folder yet. Where school data is allowed to live, and how to keep it out of places it should not go, is its own module — and it comes before the first real system you build, not after.

## **Section 9 — Now go and make something strange ^sec9**

**Heading** — Now go and make something strange

The game does not matter. What matters is that the distance between *I wonder what that would look like* and a working thing on your screen is now about ten minutes.

That is worth spending before you learn any more machinery. The next module is practical — making something you would otherwise have made by hand. This one ends by letting you loose.

The most useful thing you can do this week is pick something you have tried to explain to students and failed to explain well, and ask Claude to build you a way to show it instead.

*Two things educators here built exactly this way*

An interactive, time-scaled phylogeny. Time runs downward, and students move through deep time watching where the branches actually split — instead of looking at a diagram in a textbook.

Natural selection running in front of you. Change the pressure on a population and watch which traits survive — the thing that is genuinely hard to convey by describing it.

Neither is complicated. Both started as a sentence describing what a student should be able to see.

**Ask Claude — when you want ideas**

> I teach [subject] to [grade]. There is a concept my students consistently struggle with: [describe it]. Suggest three small interactive things I could build to help them see it, each one a single HTML file I can open by double-clicking. For each, tell me what a student would actually do with it.

### **Side note ^aside-5**

**Pick the small one.** Whatever Claude suggests, build the least ambitious of the three first. A finished small thing teaches you more than an unfinished big one, and you can always make it bigger afterwards.

## **Section 10 — If something went wrong ^sec10**

**Heading** — If something went wrong

| You saw | It means | Try this |
| --- | --- | --- |
| The name “Projects” is already taken | You already have a *Projects* folder — you have been through this once before. | Nothing is wrong. That is exactly the folder you wanted. Press Cancel, delete the new *untitled folder*, and use the one you have. |
| There is no path bar | It is turned off in this Finder window. | Click on the window, then choose **View → Show Path Bar**. If the menu says *Hide Path Bar*, it is already on; look at the very bottom edge of the window. |
| Claude says it can't find the folder or the file | It is standing somewhere else. | Ask it: *what folder are you working in?* If it is the wrong one, open the right folder and start again. |
| A permission box you weren't expecting | Claude is about to change or delete something. | Read what it says before approving. If you don't understand it, ask Claude what the command does before you say yes. |
| The game opened as a page of code | It opened in a text editor, not a browser. | Right-click the file, choose *Open With*, and pick a browser. |
| Your change didn't appear | The browser is showing the old version. | Reload the page. Hold **⇧** while you reload if it is stubborn. |
| Claude changed more than you wanted | The request was broader than you meant it. | Say so plainly: *undo that and change only the colors.* It has the file and can put it back. |
| Claude made something other than an HTML file | The request was open enough to be read another way. | Say: *redo this as a single HTML file I can open by double-clicking.* |

## **Module tasks ^checklist**

The 11 checkboxes near the end, in the order the module does them:

1. Installed Claude Code and signed in
1. Found my home folder, and turned on Finder's path bar
1. Copied a file's path with Option, and matched it to the path bar
1. Made a Projects folder in my home directory
1. Made an empty project folder inside it, and opened that folder in Claude Code
1. Asked Claude what folder it was standing in
1. Had Claude build the game, and played it
1. Looked in the folder myself and found the file it made
1. Changed the colors, then changed the whole look
1. Saved a memory in CLAUDE.md, and read the file back
1. Had Claude write a README, and read it

## **Section 11 — Before you finish ^sec11**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

If Claude can reach into your computer, what do you think decides which of your files it is allowed to touch?

Answer it again now. The answer is one folder, chosen by you, every time.

Then notice what still feels unclear. That part is the most useful thing you could ask Claude in the next five minutes, and it is probably the start of the next module.

### **Side note ^aside-6**

**Next:** Module 2 — *Making something you actually need.* You have built a game. Next you build something you would otherwise have made by hand.

## **Footer ^footer**

Developing with AI · Module 1. Written for macOS; the ideas are identical on Windows but the menus and shortcuts differ.
