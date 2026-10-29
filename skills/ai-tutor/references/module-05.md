# Module 5 — The Terminal: the page's text

Generated from `dev-portal-site/modules/05-terminal.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 5

**Title** — The Terminal

**For** anyone who has finished Module 2 and wants to write code in earnest **Time** about an hour **You need** a Mac, and Claude open beside you

---

**Label** — Before you start

You open your computer and look at your desktop. You click the word doc you've been working on and it opens.

*This line sits alone in the clay-bordered box:*

What is actually happening inside your computer? Think about it for a moment.

### **Side note ^aside-1**

**This is where Sequence 2 begins.** If what you want is Claude working on documents in your folders, Sequence 1 gave you everything you need, and you can stop there. Writing real programs is different: it means installing things and running them yourself, and all of that happens in the terminal. So this sequence starts by looking under the hood — at what Claude is actually doing when it works on your files, and at what that terminal window in Module 2 really was.

**What this module is for.** You are not going to become a person who lives in the terminal. Almost everything you do from here will be pasting a line Claude wrote for you and pressing return.

The point is that you will not be *surprised* when that happens. When Claude says *run this*, you will know where you are standing, what it is about to touch, and roughly what the line will do — enough to say yes, or to ask why not. That is a different thing from learning commands, and it is the part that keeps paying off.

So do the exercises, and do not try to memorize any of it.

## **Section 1 — Start by making something ^sec1**

**Heading** — Start by making something

Before any explanation. You are not expected to understand a word of this yet — that is the point of doing it first.

### **Try it yourself 5.1 ^try-5-1**

Open the terminal. On a Mac, press **⌘ Space**, type *terminal*, and press return. A window opens with some text and a blinking cursor.

That line ends in a symbol — on a current Mac, a `%`. That symbol is the **prompt**: the computer saying it is ready and waiting for you. **You never type it.**

**The command blocks on this page start with a `$` instead, and you will not see that on your screen.** The `$` is the standard way of writing "this line is a command you type" — almost every tutorial you ever read will use it, which is why it is here. Older Macs and most other computers really do show `$`; yours shows `%`. Neither is ever typed, and the **Copy** button leaves it out. If the page says `$` and your terminal says `%`, nothing is wrong.

Now press **Copy**, paste all six lines into that window, and press return.

```
$ cd ~/Desktop;
$ mkdir -p hello-terminal/one hello-terminal/two hello-terminal/three;
$ echo "You did not click anything to make this." > hello-terminal/one/open-me.txt;
$ echo "Three folders and three files, from one paste." > hello-terminal/two/open-me.txt;
$ echo "You will know what every word of this does by the end." > hello-terminal/three/open-me.txt;
$ open hello-terminal
```

**A Finder window opens by itself.** Go into each of the three folders and open the file inside.

### **What just happened ^reveal-r0**

**Button hint** — Open all three files first

Four folders and three files, in about a second, and you never clicked *New Folder* once. Doing that by hand is six right-clicks, six bits of typing, and three trips to a text editor.

**Do not worry about the words yet.** By the end of this module you will know what every one of them means — `cd`, `mkdir`, the `~`, the `>`, and why `open` made a Finder window appear on its own. We will come back to this exact line at the end and take it apart.

The thing worth noticing now is smaller, and stranger. Those folders are *real*. They are sitting on your desktop right now. You can drag them, rename them, throw them away. Nothing about them is different from a folder you made by right-clicking.

That is this whole module in one sentence: **the terminal is not a different computer. It is a different way of talking to the same one.**

**Label** — Core vocabulary

Open the core vocabulary and take a look. These are the key concepts and ideas you will learn in this module. They start from the basics and get you ready to develop with AI. **You don't need to learn this now.** You will learn as you go.

**Button** — Show the 12 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**UI** *(user interface)* Everything you click on your computer: icons, windows, folders. The UI is the picture that lets you interact with your computer.

**Terminal** A window where you type instructions and your computer types back. It can do anything the UI can do: open applications, read and write files. There are many instructions that can only be typed in the terminal. That's one of the reasons developers use it.

**Command** One instruction you type into the terminal. You press return to run it.

**File** One item of content — a document, a photo, a song.

**Directory** A container holding files and other directories. *Note:* Your UI calls this a **folder**.

**Root Directory** The directory that all the other directories on your computer are inside.

**Home directory** The directory named after you. It holds your own directories: your Desktop, Documents and Downloads. Written in shorthand as `~`

**Working directory** Wherever the terminal is standing right now. Commands run from here unless you tell them otherwise.

**Path** A file or directory's "address." It is a special format for saying where on your computer a file or folder "lives." This example shows that your desktop is actually just a folder inside the folder "users." *Note:* `/Users/yourname/Desktop/` — here the terminal is looking at your desktop folder inside two other folders.

**Extension** A file will always have an extension. It is the part of a filename after the final period — `.pdf`, `.docx`, `.txt`. It tells your computer which program should open the file. For example, `.docx` tells your computer to open the file with Microsoft Word.

**Program** A list of instructions telling your computer what to do with a file. Microsoft Word is a program. So is every command in this module.

**Prompt** This word means two things, and you will meet both. In the terminal it is the symbol at the start of the line where your typing goes — on a current Mac it is the `%`. With an AI it is what you write to ask for something. *Note:* You never type it. This module writes commands starting with `$`, the usual convention everywhere online — your own screen will show `%`.

## **Section 2 — Two ways of looking at the same thing ^sec2**

**Heading** — Two ways of looking at the same thing

Your computer isn't actually the colorful desktop that you see. At the most basic level a computer is a set of electrical impulses that encode a long series of ones and zeroes. Anything you do on your computer — clicking an icon, surfing the web — is a picture generated to make your computer easier to use.

### **Figure ^figure-1**

**Caption** — Your computer's native language.

**Description read aloud by screen readers** — Rows of ones and zeroes: the binary code a computer actually works in.

That picture is called a **UI** — a user interface. It makes it much easier to use your computer.

The terminal is a different interface, and a more direct one. It can do everything the UI can do, and a lot it cannot. In the terminal, you type instructions to your computer and it types back.

To write real programs with AI, you need to be comfortable in the terminal. You do *not* need to memorize commands — your AI will write those. But you do need a picture of how it all fits together, so you can tell what your AI is doing and whether it is what you wanted.

### **Try it yourself 5.2 ^try-5-2**

Back in your terminal window. This time type it yourself rather than pasting, then press return:

```
$ pwd
```

You will see a line that starts with `/Users/` and ends with your name.

### **What just happened ^reveal-r1**

**Button hint** — Open this after you have run it, not before

`pwd` stands for "print working directory." A **directory** is just another name for a folder. `pwd` is a way of asking your computer "Where am I?"

The **working directory** is the folder where you are currently working. If you double-click on a folder, you move into a new folder.

When you typed `pwd`, your computer typed something like this:

```
/Users/yourname
```

That string is called a **path** — a file or folder's address, written as the list of folders you would open to reach it. Yours will show your own account name where this one says "yourname," and it means that your computer is standing in that folder, inside the folder "Users."

The terminal is always standing in one particular folder. When it opens, it stands in your **home directory** — the one with your name on it, holding your Desktop, Documents and Downloads.

### **Try it yourself 5.3 ^try-5-3**

Next, try this:

```
$ ls
```

Your terminal will print the contents of your working directory. `ls` is a way of asking your computer "What is in here?"

If you want, you can find that folder through your UI and check to see that the list matches.

Your UI shows **documents in folders**. Your terminal shows **files in directories**. Those are two names for one thing. Nothing was converted or translated. You are looking at the same objects through two windows.

### **Side note ^aside-2**

Sometimes there are files that show in the terminal but not in the UI. These are hidden files most users never need to see, but they are there.

### **Figure ^figure-2**

**Caption** — Both windows end up showing the same three files. Neither is more real than the other. But only one of them can be handed to a program.

**Description read aloud by screen readers** — Two windows side by side showing the same thing. On the left, Finder with the Documents folder open and three files inside it. On the right, a terminal that has run cd Documents and then ls, listing those same three files.

## **Section 3 — Everything is inside something else ^sec3**

**Heading** — Everything is inside something else

Every file sits inside a directory. That directory sits inside another, and so on, until you reach the one that contains everything: the **root directory**. It is written as a single slash, `/`.

A **path** is the directions from the root to one particular thing. That is all a path is: a list of doors to open, in order.

To move from directory to directory in the terminal, you will use the `cd` command. It stands for "change directory."

*Click each part*

### **Try it yourself 5.4 ^try-5-4**

Walk a path in the terminal, from your home directory down to one file on your Desktop.

**One command at a time.** Run it, read what comes back, then come back for the next one. There are only three commands in the whole walk, and they are asking three different questions.

**Step 1. Where I want to go.** Start from home, so we are both in the same place:

```
$ cd ~
```

Nothing prints. That is normal — `cd` moves you, it does not report. The `~` is shorthand for your home directory.

**Step 2. Where am I?**

```
$ pwd
```

It prints something like `/Users/your-name`. That is your answer to *where am I standing right now*, and it is the only command here that answers it.

**Step 3. What is here?**

```
$ ls
```

A list: *Desktop*, *Documents*, *Downloads* and the rest. These are the things inside where you are standing. **Find *Desktop* in that list** — you are about to walk into it.

**Step 4. Where I want to go.** One step down, into a directory you just saw:

```
$ cd Desktop
```

Silence again. You have moved, and nothing told you so. That is exactly why the next command exists.

**Step 5. Where am I?** Ask again:

```
$ pwd
```

One step longer than last time: `/Users/your-name/Desktop`. Same question, different answer, because you moved.

**Step 6. What is here?**

```
$ ls
```

**Now look at your actual desktop, behind your windows.** The same things, in a different handwriting.

### **Side note ^aside-3**

**That is the whole walk, and it is only three questions.**

`pwd` — where am I? `cd` — where I want to go. `ls` — what is here?

Everything else in this module is those three, repeated. When you get lost later — and you will — the way out is `pwd`, then `ls`, then decide.

One last thing. Pick any filename from that final list and add it to the end of what `pwd` printed, with a slash between:

`/Users/your-name/Desktop/your-file.txt`

That is the full path to one file. You just walked it, one folder at a time.

### **What just happened ^reveal-r3**

**Button hint** — Check your desktop against the list first

`cd` means "change directory." You moved the terminal from your home directory into your Desktop without clicking anything, and `pwd` proved it: the path it printed is longer than before.

Your desktop is not a special place. It is an ordinary directory that your Mac happens to draw behind your windows.

To go back up one level, use `cd ..` — two dots means "the directory containing this one."

You assembled that path by hand, out of two things on your screen. You will not always want to.

Your UI knows the path of everything it is showing you. It simply does not put it in front of you, because most people never need it. Once you know where to look, it will hand you any path you ask for.

### **Try it yourself 5.5 ^try-5-5**

**First, make Finder show you where you are.** Open a Finder window, and in the menu bar choose **View → Show Path Bar**. If you did Module 1, it is already on.

A thin strip appears along the bottom. Click into a few folders and watch it change — it is the same path, drawn as icons instead of typed as words. Leave it turned on. It is the single most useful thing you can do to a Finder window.

**Now have your computer write a path out for you.** Find any file — the one on your Desktop from a moment ago will do:

- Right-click it. A menu appears, with *Copy* partway down.
- Keep the menu open and **hold down the ⌥ Option key**. Watch *Copy* change into **Copy “name” as Pathname**.
- Still holding Option, click it.
Now paste it somewhere you can read it — a new TextEdit document, or straight into Claude:

```
/Users/your-name/Desktop/notes.txt
```

Compare it against the path you built by hand in 5.4. They should be identical.

The keyboard shortcut, once you trust it, is **⌘ ⌥ C** with the file selected.

### **Try it yourself 5.6 ^try-5-6**

The trick works the other way too. In Finder, press **⌘ ⇧ G**. A box appears asking for a path.

Type a slash and start typing a folder name — it will complete as you go. Try:

```
/Users
```

Press return, and Finder takes you there. Try it with a path you copied a moment ago, and with `~/Desktop`.

### **What just happened ^reveal-r6**

**Button hint** — Copy a real path and paste it before opening this

Finder handed you the exact string the terminal prints. Not something like it — the same text, character for character.

That is the clearest proof yet of the thing this whole module is about. Two windows, one filing cabinet. The path was always there; the UI was just being polite about not showing it.

**Why this matters more than it looks.** From here on you will constantly need to tell a program — or Claude — exactly which file you mean. "The spreadsheet on my desktop" is ambiguous. `/Users/your-name/Desktop/roster.csv` is not. Option-copy is how you produce that sentence without typing it or getting it wrong.

And **⌘ ⇧ G** is the reverse: paste a path somebody sent you, and land exactly there. Between the two, you can move a location from any window to any other window without ever describing it in words.

## **Section 4 — Programs, and how your computer knows which one to use ^sec4**

**Heading** — Programs, and how your computer knows which one to use

Your computer is full of **programs**. A program is a list of instructions telling the computer what to do with a file.

Every filename ends with a period and a few letters. That part is the **extension**. It is how your computer knows which program to hand the file to. Your UI often hides it to look tidy. The computer always needs it.

*Click a file to see its extension*

### **Try it yourself 5.7 ^try-5-7**

Pick any file on your desktop. What is its extension?

If Finder is hiding it, the terminal will not. `ls` always shows the full name. That is the terminal telling you the truth about your computer.

### **Try it yourself 5.8 ^try-5-8**

Read a file without opening it. Find a `.txt` file — or make one in TextEdit first — and run this, replacing the name with yours:

```
$ cat notes.txt
```

### **What just happened ^reveal-r4**

**Button hint** — Run it first

The contents appeared right there in the terminal. No window opened, no application launched.

Except one did. `cat` *is* a program — a very small one whose whole job is to print a file's contents. When you type `cat notes.txt` you are running a program and handing it a file. That is exactly what happens when you double-click a document. The double-click just picks the program for you.

Try it on a `.pdf` and you get a screenful of nonsense. That is correct. A PDF is not made of readable text, so it needs a program that knows how to draw it.

## **Section 5 — Making things ^sec5**

**Heading** — Making things

Since 5.1 you have only looked. These two commands change your computer again — but this time you will know exactly what they are doing.

### **Try it yourself 5.9 ^try-5-9**

Make a new, empty folder on your desktop:

```
$ cd ~/Desktop;
$ mkdir my-first-folder;
$ ls
```

**Now look at your actual desktop.** It is there.

### **Try it yourself 5.10 ^try-5-10**

Move into it and create an empty text file:

```
$ cd my-first-folder;
$ touch hello.txt;
$ ls
```

Open the folder on your desktop and double-click the file. It opens in a text editor, empty, exactly as though you had made it by hand.

### **What just happened ^reveal-r5**

**Button hint** — Make sure you have seen the folder appear

You made a folder and a file by typing. Both are as real as anything you have made by right-clicking.

Two things worth keeping. The `~` in `cd ~/Desktop` is shorthand for your home directory, so that path works from anywhere. And `mkdir` and `touch` printed nothing when they worked — **silence in the terminal usually means success.** This is unnerving for about a week.

## **Section 6 — The line you started with ^sec6**

**Heading** — The line you started with

Go back to the very first thing you did, before any of this was explained:

```
$ cd ~/Desktop;
$ mkdir -p hello-terminal/one hello-terminal/two hello-terminal/three;
$ echo "You did not click anything to make this." > hello-terminal/one/open-me.txt;
$ open hello-terminal
```

You now know almost all of it:

- `cd ~/Desktop` — change directory to your Desktop. The `~` is your home directory, so this works from anywhere.
- `mkdir` — make directories. The `-p` tells it to create any folders it needs along the way, which is how one command made *hello-terminal* and three folders inside it at once.
- `open` — a program, like `cat`. Its whole job is to hand something to your Mac and let the Mac decide what to do with it. Hand it a folder and you get a Finder window.
Three pieces were never explained, so here they are. `echo` prints whatever you give it. And `>` means **put it in this file instead of printing it to the screen** — creating the file if it does not exist. That one character is how a command's output becomes something you can keep.

The `;` at the end of each line just means *and then*. It lets you put several commands in a row and have them run in order, which is why the whole thing worked from one paste.

Six lines, and nothing left in them you have not met. Forty minutes ago it was noise.

### **Side note ^aside-4**

**Tidying up.** You can drag both folders — *hello-terminal* and *my-first-folder* — to the trash like anything else. There is a terminal command for deleting things, and this module is not teaching it yet. It does not ask "are you sure?", and there is no trash to fish things out of.

## **Section 7 — Working with your AI ^sec7**

**Heading** — Working with your AI

This is what the first page promised, and it is the whole point of the last hour. Here is the shape of nearly everything you will do from here. You describe what you want. Your AI tells you the command. You paste it in and press return.

You were never going to remember these commands, and you do not need to. What you need is to look at a line somebody handed you and have a rough idea what it will do — which folder it is standing in, whether it only looks or actually changes something. That is the difference between running it and hoping, and it is the thing you now have.

**Ask Claude**

> I'm new to the terminal. I want to make a folder called "school-data" inside my Documents folder, and then move into it. What should I type? Explain each part.

Run what it gives you, then check the result in Finder. That last step is the habit worth building: **every time your AI changes something, go and look at it.**

**Ask Claude — when a command confuses you**

> Explain this command to me piece by piece, as if I have never used a terminal. Tell me if any part of it changes or deletes anything: [paste the command]

### **Side note ^aside-5**

**Worth knowing.** A command that only reads — `pwd`, `ls`, `cat` — cannot hurt anything. A command that writes or deletes can. Ask your AI which kind you are looking at. It is a fair question and it will answer.

## **Section 8 — If something went wrong ^sec8**

**Heading** — If something went wrong

| You saw | It means | Try this |
| --- | --- | --- |
| No such file or directory | You are not standing where you think you are, or the name is spelled differently. | Run `pwd` to see where you are, then `ls` to see the real names. |
| command not found | A typo, most likely. | Check the spelling. Terminal commands are almost all lowercase. |
| Nothing at all happened | It probably worked. | Run `ls` to confirm the thing you made is there. |
| File exists | You already made that folder, most likely by running the same line twice. | Nothing is wrong and nothing was overwritten. The folder you wanted is there — `ls` will show it. Carry on. |
| Permission denied | You are somewhere your account is not allowed to change — often outside your home directory. | Run `cd ~` to go home and start again. Don't reach for `sudo`. Ask your AI what is going on. |
| A screen of nonsense | You ran `cat` on a file that is not text. | Press **q**, or **Control C**. Nothing is broken. |
| The prompt symbol hasn't come back | Something is still running, or waiting for you. | Press **Control C** to stop it and get your prompt back. |

## **Module tasks ^checklist**

The 9 checkboxes near the end, in the order the module does them:

1. Made three folders and three files with one paste, and read what was inside them
1. Listed the files, and confirmed the same folder in the UI
1. Walked a path from my home directory to a file on my Desktop, changing directory as I went
1. Turned on Finder's path bar, and copied a file's path with Option
1. Jumped straight to a folder by typing its path
1. Worked out the extension of a particular file
1. Read that file using the terminal
1. Created an empty folder on my desktop from the terminal
1. Created an empty .txt file inside it

## **Section 9 — Before you finish ^sec9**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

You open your computer and look at your desktop. You click the word doc you've been working on and it opens. What is actually happening inside your computer?

Answer it again now, and notice what changed. Then notice what still feels unclear. That part is the most useful thing you could ask Claude in the next five minutes, and it is probably the start of the next module.

### **Side note ^aside-6**

**Next:** Module 6 — *Coding with AI.* Borrowing a library somebody else wrote, so you can make things that would be impossible by hand.

## **Footer ^footer**

Developing with AI · Module 5. Written for macOS; the ideas are identical on Windows but several commands differ.
