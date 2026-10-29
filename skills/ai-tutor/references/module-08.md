# Module 8 — APIs, tokens and signing in: the page's text

Generated from `dev-portal-site/modules/08-apis.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 8

**Title** — APIs, tokens and signing in

**For** anyone who has finished Module 7 **Time** about 90 minutes, nearly all of it once and never again **You need** Claude Code, your terminal, and your school Google account

---

**Label** — Before you start

Claude Code can open any file on your computer. You have watched it do that for three modules.

Now ask it about a spreadsheet in your Google Drive. It cannot. Not the roster, not the sign-up sheet, not the one you have open in a browser tab right now — even though every one of those is yours, and you are looking at it.

*This line sits alone in the clay-bordered box:*

Your Drive is yours. Claude runs on your computer, working for you. So what is actually standing between them — and what would it take to let it through? Think about it for a moment.

This module is the answer, and it is the one that changes what you can build. Everything up to now happened inside your own laptop. After this, your programs can reach the systems your school actually runs on.

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 13 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**API** *(Application Programming Interface)* A way for one program to ask another program for something. Not a web page for a human to read — a service window built for software. *Note:* Google has one. So does your student information system, your library catalogue, and almost everything else.

**Endpoint** One specific request an API accepts, written as a web address. `/drive/v3/files` is "list the files."

**JSON** *(say "jay-son")* The format programs use to write things down for each other: labels and values, in nested brackets. *Note:* Square brackets are a list. Curly brackets are one thing with labelled parts. That is the whole format.

**Token** A pass a program carries to prove it is allowed to ask. Issued to you after you sign in. *Note:* A token is not your password, and this difference is the whole point of the module.

**Scope** How much a token is allowed to do. "Read my Drive" is a different scope from "change my Drive," and you can hold one without the other.

**OAuth** *(say "oh-auth")* The agreed procedure for handing out tokens without anybody handing over a password. It is what happens when you click *Sign in with Google* anywhere.

**Consent screen** The page that says "*this app wants access to your Google Drive*." Google shows it, not the app. You are the one who approves.

**Google Cloud project** A container on Google's side that holds a registered app: which APIs it may use, and what its permission screen says. *Note:* You are about to make one. It is free, and it will have exactly one user.

**OAuth client** The small file that says *which app* is asking. It identifies; it does not unlock.

**Enable an API** *(per project)* Switching one API on for one project. Off by default. A token that claims to allow something still fails if the API was never switched on.

**Internal / External** Whether only people in your school's Google organization can use your app, or anyone. *Note:* Internal is the one you want, and the module explains what goes wrong otherwise.

**Revoke** Cancelling a token from your Google account page. Instant, and it kills every copy of it everywhere.

**Connector** A ready-made link between Claude and a system like Drive or Gmail, switched on in Claude's own settings. *Note:* A connector signs *Claude* in while you are talking to it. A token signs *your program* in, which is what anything that runs without you needs.

## **Section 1 — The thing Claude cannot do ^sec1**

**Heading** — The thing Claude cannot do

Start by watching it fail. That is more useful than being told.

First, make yourself something to practise on. **Do not use a real class list for this module.** Invent one.

### **Try it yourself 8.1 ^try-8-1**

In your browser, make a new Google Sheet in your own Drive. Call it *API practice*. Put a few made-up names and grades in it — six rows is plenty, and none of them should be a real student.

Copy the address from your browser's address bar. Then open Claude Code in any project folder and ask it:

**Ask Claude**

> Read the names out of this Google Sheet for me: [paste the address]

It will not be able to. Read what it says carefully — especially if it tries something first and then reports back.

### **Side note ^aside-1**

**If it reads the sheet perfectly well,** you already have Claude's Google Drive connector switched on — a shortcut that did not exist when this module was written. Turn it off for now, so you can see the gap the module is about. The last section before the troubleshooting comes back to it and explains when it is the right tool.

### **What just happened ^reveal-r1**

**Button hint** — Ask it first, and read its answer

Claude did not refuse. It *could not*, and the reason is worth being precise about.

**That spreadsheet is not a file on your computer.** It never was. There is nothing in any folder to open — the sheet lives on Google's computers, and what you see in your browser tab is a picture of it, drawn fresh each time by a program that signed in as you.

Claude has no browser and is not signed in to anything. If it tried to fetch the address you gave it, what came back was Google's sign-in page — the same thing you would see in a private window.

So the gap is not a permission Claude is missing on your laptop. It is that Drive is a different computer, in a different building, and the only way in is over the internet through a door Google controls.

There is such a door. It has been there the whole time.

## **Section 2 — What an API is ^sec2**

**Heading** — What an API is

Think about the school office. You do not walk into the records room and pull a folder. You go to the window and ask for a specific thing, and somebody who works there decides whether to hand it to you, and fetches it.

The window is deliberate. It means the records can be reached without the room being open.

**An API is that window, built for programs instead of people.** Google has one for Drive. Your student information system has one. So does your library catalogue, your payment processor, and the weather. It is not a special arrangement you have to negotiate — it is a normal part of how software is built, and it is sitting there right now.

You can walk up to it yourself, and you should do it twice.

### **Try it yourself 8.2 ^try-8-2**

**First window.** Open this address in your browser:

```
https://poetrydb.org/title/Ozymandias
```

Shelley arrives, all fourteen lines, in about a second. No account, no sign-in, no setup, nothing installed. Try *https://poetrydb.org/author/Emily Dickinson/title* too, and get seventeen hundred poem titles back.

**Second window.** Now open this one — a real request to Google's Drive API, asking it to list files:

```
https://www.googleapis.com/drive/v3/files
```

You will get something that looks like this. Read the message.

```
{
  "error": {
    "code": 403,
    "message": "Method doesn't allow unregistered callers
      (callers without established identity). Please use
      API Key or other form of API consumer identity to
      call this API.",
    "status": "PERMISSION_DENIED"
  }
}
```

You just made two API requests by hand. One handed you a poem; one turned you away. **Notice what the refusal did not say.** It did not say the page doesn't exist, and it did not say your password was wrong.

### **What just happened ^reveal-rJ**

**Button hint** — Open both addresses first

*What came back — and what JSON is*

Neither of those was a web page. There is no styling, no navigation, no header, nothing arranged for a human eye. Both replies came back as **JSON**, which is how programs write things down for each other, and you are going to see it constantly from here on.

It has only two shapes, and once you can spot them you can read any of it.

**Square brackets are a list.** Things in order, comma separated.

```
["I met a traveller from an antique land",
 "Who said: Two vast and trunkless legs of stone"]
```

**Curly brackets are one thing with labelled parts.** A label, a colon, a value.

```
{
  "title": "Ozymandias",
  "author": "Percy Bysshe Shelley",
  "linecount": 14,
  "lines": [ ... ]
}
```

That is the whole format. The only other rule is that they nest: the value of `lines` is itself a list, and a list can hold more labelled things. The Google error you got is the same two shapes — a labelled thing called `error`, holding a `code`, a `message` and a `status`.

**Why not just use a spreadsheet?** Think about what a CSV could do with that poem. A CSV is a grid: rows and columns, everything flat. A poem has one title and fourteen lines, so you would either repeat the title fourteen times or keep two files and hope they stay together. JSON holds the shape of the thing — one poem, containing its lines — which is why programs pass it around instead of grids.

You are not expected to write it. You need to recognize it, and to find the piece you want inside it. When something arrives looking like a wall of brackets, **paste it into Claude and ask what is in it.** That is a completely ordinary thing to do, and it is faster than squinting.

One more thing worth knowing now: the credentials you make later in this module are JSON files too. When you open one and see labels and brackets, that is all you are looking at.

### **What just happened ^reveal-r2**

**Button hint** — Go and read the actual error first

*Why one worked and one didn't*

Two requests, the same shape, one line each. The difference is not that Google is harder than PoetryDB, or that one is a better-built system. **The difference is whose data was being asked for.**

Shelley belongs to everybody. There is nothing to protect, so there is nothing to check, so there is no setup — and that is what an API looks like when the answer is public. A great many are: library catalogues, museum collections, census figures, the weather, transit times, every text on Sefaria. All of it, one line, no account.

Your Drive is the opposite. The refusal is the interesting part. *"Method doesn't allow unregistered callers — callers without established identity."*

It does not know **who is asking**. And it means something more specific than you might assume: not *which person*, but *which program*. You went to the window with no name badge and no request slip, and the window has nothing personal against you. It just does not deal with anonymous strangers.

**So there are two separate questions,** and the rest of this module answers them one at a time:

- **Which program is asking?** — answered by registering an app, which produces a file called an *OAuth client*.
- **On whose behalf, and for what?** — answered by you signing in once, which produces a *token*.
Those two questions are why setup has two halves that feel unrelated. They are not. Each one answers one of these.

## **Section 3 — A token is not a password ^sec3**

**Heading** — A token is not a password

The obvious way to let a program into your Drive would be to give it your Google password. That is also the worst possible way, and it is worth being clear about why, because the reasoning shows up everywhere in this work.

A password is a master key. It opens everything you have — mail, files, calendar, the account itself. It does not expire. It cannot be handed out narrowly. And once somebody has a copy, the only way to take it back is to change it, which breaks it for you and for everything else you had given it to.

**A token is a key cut for one room.** You get one after proving who you are, it opens a defined set of things and nothing else, and you can cancel it from your phone in ten seconds without changing your password or disturbing anything else.

It has four properties worth memorizing, because you will judge every future integration by them:

- **It is narrow.** A token's *scope* says what it may do. Read your Drive, or change it. Draft mail, or send it. These are separate and you can hold one without the other.
- **It is revocable.** One click, from a page in your Google account, and it is dead everywhere at once.
- **It does not reveal your password.** Whoever holds the token cannot work backwards to your account.
- **It is yours.** It reaches exactly what you reach. Not what your principal reaches, and not what the whole school reaches.
That last one is the one people get wrong. Giving Claude a token does not give it the school's Drive. It gives it your view of the Drive — the same files you would see if you signed in on a borrowed laptop.

### **Figure ^figure-1**

**Caption** — Two files, two questions, one request. The token is created once, by you, on a page belonging to Google — and it can be destroyed from that same account whenever you like.

**Description read aloud by screen readers** — Diagram: a box for your computer containing Claude Code and two credential files, one identifying which app is asking and one identifying whose account and how much access. An arrow labelled one request carrying both goes to a box for Google, which contains the Drive API and your Drive. A reply arrow returns only what was asked for.

### **Side note ^aside-2**

**You have done this before.** Every time you clicked *Sign in with Google* on some other website, this exact procedure ran. The difference now is that you are on the other side of it, building the thing that asks.

## **Section 4 — Why you would want this ^sec4**

**Heading** — Why you would want this

It is a fair question, given that you can already open Drive yourself.

The answer is that **almost everything a school actually needs done is a loop.** Not one document — a hundred and forty of them. Not one lookup, but the same lookup for every child in a grade. That is the work software is for, and it is the work that stays undone because doing it by hand is unbearable and nobody has time to build the tool.

Once Claude can reach your Drive, that work becomes describable:

- Read a sheet of assessment scores and write a summary tab that flags who has moved backwards since the fall.
- Take a folder of narrative comments and check every one against the same rubric.
- Pull three sheets that different offices maintain, and produce a list of the rows that disagree.
- Turn a roster into a hundred and forty personalized documents, correctly named, in the right folders.
You could do any of these by exporting to CSV and pasting into a chat window. People do. But the export is a snapshot that is stale the moment you take it, the paste has a size limit, and the result comes back as text you then have to put somewhere by hand. Nothing you build that way runs a second time.

With a token, the whole loop is one instruction, and it works again next term.

### **Side note ^aside-3**

**Being able to is not the same as being allowed to.** A token gets you a technical door. Whether a particular list of children may go through it is a different question, with a different answer at every school, and it is not one Claude can decide for you. **Module 9 — *Where school data is allowed to live* — is the one that covers it, and it comes next.** That is why every exercise here uses a sheet of invented names. Keep it that way until you have had that conversation with the people at your school who own it.

## **Section 5 — Question one: which program is asking? ^sec5**

**Heading** — Question one: which program is asking?

Time to register an app.

That sentence sounds much bigger than what you are about to do. Your app has one user — you. It never leaves your laptop, it will never be listed anywhere, and nobody will ever review it. What you are really doing is telling Google "requests are going to start arriving from a thing called *this*, and here is the permission screen I want shown when they do."

You are not going to work out how to do that from a manual. **You are going to hand the job to Claude** — which is the same move as Module 7, and the actual point of all of this.

The split is clean, and worth knowing before you start:

### **Figure ^figure-2**

**Caption** — Google offers no way for a program to configure a Cloud project on your behalf — no command, no API. That is deliberate, and it is why the left column stays with you. Everything on the right, Claude does.

**Description read aloud by screen readers** — Diagram: a box labelled anything in a browser is yours, listing the five console errands, beside a box labelled anything on your laptop is Claude's, listing the environment, the downloaded file, the token, the config and the final check.

### **Try it yourself 8.3 ^try-8-3**

Clone the helper, the way you cloned *group-maker*:

```
$ git clone https://github.com/day-school-dev-portal/google-workspace-helper.git ~/Projects/google-workspace-helper
```

Open that folder in Claude Code. Then say exactly this:

**Ask Claude**

> Set this up for me.

Four words. **Claude already knows the whole procedure** — it is written down inside the folder you just copied — so it will start checking things, and then send you to the first screen.

**Sign in to Google with your school account** when it does. Which account you use matters more than anything else in this module, for reasons that become clear at 8.5.

### **Try it yourself 8.4 ^try-8-4**

Claude will hand you a link to make a new Cloud project, then ask you for its **project id**. Give it. That id is how it builds the rest of your links, so from here on every screen you are sent to is already pointing at the right project.

Then it will give you three more links, one per API: **Drive**, **Sheets** and **Docs**. Each lands on a page with one *Enable* button.

They are all off by default, and that is the thing worth noticing. **An API that is switched off cannot be called even by a token that says it is allowed.** It is a real second lock, not a formality — which is why turning on only what you need is worth doing.

### **Try it yourself 8.5 ^try-8-5**

The next link Claude gives you is the **consent screen** — and this one you are writing, not filling in. It is the page you will be shown in a few minutes when you authorize, and the page you would be shown again in two years if you had forgotten all of this.

Two of the answers matter:

- **App name** You will see this on the permission screen. Make it something you would recognize in six months — `Claude workspace helper` rather than `test`.
- **Audience** **Internal.** Only people in your school's Google organization can use your app. This is the one that matters — see below.
The rest is your email twice. Claude will tell you to skip **Data Access** entirely, and it is right to: scopes only have to be listed there for apps used by people outside your organization.

### **Side note ^aside-4**

**If Internal is greyed out.** That means the account you signed in with is not part of a Google Workspace organization — almost always because it is a personal `@gmail.com` address. Go back and sign in with your school account.

If your school account genuinely has no organization, you can choose **External**, but know what it costs: an External app left in *Testing* gets a sign-in that **Google expires after seven days**. It will work beautifully, and then break next week for no visible reason. If you go this way, also open **Audience → Test users** and add your own email address, or Google will refuse you outright.

### **Try it yourself 8.6 ^try-8-6**

Last screen in the browser. Claude sends you to **Clients**, where you create the thing that actually identifies your app, and download it.

- **Application type** **Desktop app.** Not Web application — the code you are about to run opens a browser on your own machine, which is what "desktop" means here. Pick wrong and nothing works; Claude checks this and will tell you.
Create it, then use the **download icon** on your new client's row and choose **Download JSON**.

It lands in your Downloads folder with an unhelpful name like `client_secret_8471….json`. **Leave it where it is** — don't rename it and don't move it. Claude looks in your Downloads folder, finds it, and puts it where it belongs under the name the code expects.

### **What just happened ^reveal-r3**

**Button hint** — Get the file downloaded first

You answered question one. That download is your app's ID card, and from now on Google's answer to "which program is asking?" is "the one holding this."

Go and open it in a text editor before Claude tidies it away — it is worth ten seconds. It is about ten lines: a `client_id`, a `project_id`, a `client_secret`, and some fixed addresses. That is the entire thing you spent four screens making.

**`client_secret` is a badly chosen name.** It is not a password and it unlocks nothing. Anyone holding this file can put your app's name on a permission screen; they still cannot reach one byte of your Drive, because that requires a human to sign in and click Allow. Treat it as private housekeeping, not as a credential — do not commit it, do not paste it into a chat, and do not lose sleep over it either.

Notice that **you have granted nothing yet.** You have registered an asker. Nobody has said yes.

## **Section 6 — Question two: on whose behalf? ^sec6**

**Heading** — Question two: on whose behalf?

The browser part is over. Everything left happens on your own computer, which means everything left is Claude's job.

It will find your download, put it where the code expects it, build the Python environment the helper needs, and check its own work as it goes. You do not have to follow along — but it is worth watching once, because this is the part people assume is hard.

### **Try it yourself 8.7 ^try-8-7**

While Claude works, run this yourself in a terminal, from inside the helper folder:

```
$ cd ~/Projects/google-workspace-helper;
$ python3 scripts/check_setup.py
```

You get a list of what is done, what is missing, and a line beginning **NEXT**.

This is the same command Claude has been running after every step. **It is worth knowing about for its own sake:** if you walk away now and come back next week, this tells you exactly where you stopped, and "carry on with the setup" is enough to restart it.

### **Side note ^aside-5**

**If you would rather drive yourself,** every command is written out under *Doing it by hand* in the project's `SETUP.md`. Nothing here is hidden from you — handing it to Claude is a choice, not a requirement.

### **Try it yourself 8.8 ^try-8-8**

Now the moment the whole module has been building to. Claude runs this — it is the last step of the setup, and worth reading so you know what opened your browser:

```
$ .venv/bin/python scripts/authorize.py drive write
```

A browser window opens on Google's own sign-in page. Sign in with the same school account.

**Then stop, and actually read the permission screen.** Do not click Allow yet. It names your app — the name you chose in 8.5 — and it lists exactly what is being asked for. Read the list. This is the one screen in the entire process where a human decides something, and almost everybody clicks past it without looking.

Now click **Allow**.

### **What just happened ^reveal-r4**

**Button hint** — Read the consent screen before you open this

You answered question two, and the way you answered it is the entire idea behind OAuth.

Look at what did *not* happen. You did not type your password into the helper. You did not type it into Claude, or into your terminal, or into anything written by anybody at your school. **You typed it into Google's own page** — the same page you use every morning, at an address you can check — and Google, not the app, asked you the question.

That separation is the whole design. The program that wants access never sees your credentials. It is standing outside while you and Google talk, and it gets handed a narrow pass at the end.

What came back was written to a file. It is not your password and it cannot be turned into your password. It says, in effect: *the holder of this may read and change the Drive of this one person, until that person says otherwise.*

If you saw a screen warning you that **Google hasn't verified this app**, that was your own app, and clicking *Advanced → Go to (unsafe)* was the right call. On an Internal app it does not appear at all. It is worth noticing how that warning feels, though, because you will meet it again on somebody else's app, where it deserves more suspicion than it just got.

## **Section 7 — Two files that look alike and are not ^sec7**

**Heading** — Two files that look alike and are not

Look in the *credentials* folder now.

### **Try it yourself 8.9 ^try-8-9**

**Ask Claude**

> There are two JSON files in credentials/. Explain the difference between them as if I were handing my laptop to a colleague: which one would matter, and what exactly could they do with it?

Then open `.gitignore` in that project and find the rule that keeps both of them out of git.

### **What just happened ^reveal-r5**

**Button hint** — Read the .gitignore rule first

They sit in the same folder and end in the same three letters, and one of them is nothing while the other is everything.

**The token file is the one that matters.** Copy it to another computer and that computer is you, as far as Google is concerned, until somebody revokes it. It does not expire on its own. It is not tied to your laptop. That is why tokens are never emailed, never put in a shared folder, and never committed — and why the setup told you to clone this project rather than copy a colleague's folder.

Look at how the `.gitignore` is written. It does not list the files to exclude. It excludes *everything* in the folder and then names the two harmless ones to let back in. That is deliberate: the next API you add will drop a new credential file with a name nobody predicted, and a deny-by-default rule catches it without anyone having to remember.

**That is a habit worth taking with you.** When the cost of forgetting is high, arrange things so forgetting is not possible.

## **Section 8 — Using it ^sec8**

**Heading** — Using it

There was one more thing to do, and Claude has already done it: without it, only *this one folder* would know the helper exists.

What makes it available *everywhere* is a note in your `~/.claude/CLAUDE.md` — the memory file you met in Module 1, except that this one is global, and Claude reads it at the start of every session in every project. Setting that up was the last thing on Claude's side of the list.

It is worth going to look at, because it is not only a description.

### **Try it yourself 8.10 ^try-8-10**

**Ask Claude**

> Show me exactly what you added to my ~/.claude/CLAUDE.md, and explain the rules in it.

**Read it properly.** Some of it describes what the helper can do. The rest is rules — only touch files I name, show me destructive changes first, drafts never send. Those are instructions to Claude about how to behave with your Drive, they are written in plain English in a file you own, and **you can change them.**

Now **start a new Claude Code session**, in any folder you like, and ask the question that failed at the start of this module:

**Ask Claude**

> Read the names out of this Google Sheet for me: [paste the address of your practice sheet]

### **Try it yourself 8.11 ^try-8-11**

Reading is half of it. Now have it write something back — still in your practice sheet, still with invented names:

**Ask Claude**

> In that same sheet, add a new tab called Summary listing how many students are in each grade. Tell me what you are going to write before you write it.

Then go and look at the sheet in your browser. It changed while you were watching.

### **What just happened ^reveal-r6**

**Button hint** — Watch the sheet change first

The request that was impossible ninety minutes ago is now ordinary, and nothing about your computer changed. What changed is that a door which was always there now opens for you.

Notice that **the new session knew.** You did not point it at the helper, or explain any of this. It read your global `CLAUDE.md`, found the note, and used it — which is what that file is for, and why it is worth keeping tidy.

Notice also that you never wrote any code. You described what you wanted in a sentence, and Claude wrote the call. The library exists so that there is something correct for it to call.

**And it wrote to a real Google document.** That is the moment to feel the weight of, because the same sentence that added a harmless tab could have cleared one. The token you minted says *write*, which means the safety is no longer technical — it is that you asked to see the change first, and that the rules in your `CLAUDE.md` tell Claude to offer. That is a real safeguard and it is also only a convention. Keep the habit of asking to see what will change before it changes.

## **Section 9 — Taking it back ^sec9**

**Heading** — Taking it back

You gave something access. You should know, today and not in an emergency, how to take it away.

### **Try it yourself 8.12 ^try-8-12**

Open this page, signed in as yourself:

```
myaccount.google.com/permissions
```

Find your app in the list — the name you chose in 8.5, sitting among everything else you have ever signed in to. Click it and read what it says it can do.

**Do not remove it** unless you want to run 8.8 again. Just look.

### **What just happened ^reveal-r7**

**Button hint** — Go and find it in the list first

Your app is in the same list as every other thing you have ever let into your Google account, described in the same words, removable by the same button.

That list is worth a scroll. Most people find things they signed in to years ago and forgot, still holding access.

**Removing an app here kills the token instantly and everywhere** — every copy, on every machine, whoever holds it. You do not have to find the file. You do not have to change your password. That single property is what makes it reasonable to hand out tokens at all, and it is the thing to check for before you trust any integration: *can I take this back without breaking everything else?*

If a system ever wants your actual password instead, the honest reading is that its author skipped this, and you are the one carrying the risk.

## **Section 10 — The shorter way, and what it costs ^sec10**

**Heading** — The shorter way, and what it costs

Everything you just built still stands. But there is now a much shorter path to that same practice sheet, and it would be dishonest to end the module without showing it to you.

**Claude has connectors** — ready-made links to Drive, Gmail, Calendar and a growing list of other systems, switched on in Claude's own settings. You click through the same Google permission screen you read in 8.8, and that is the whole setup. No Cloud project, no client file, no helper to clone. About a minute, most of it waiting for a browser tab.

When this module was first written the Drive connector could only read, which made it a curiosity. It can write now, which makes it a real alternative — so the honest question is no longer *how* but *which*.

### **Try it yourself 8.13 ^try-8-13**

Open Claude's settings, find the connectors list, and switch on Google Drive. Sign in when it asks, and **read the permission screen on the way past** — it is the same screen, asking for the same things, shown by the same Google.

Then ask for your practice sheet again, exactly as you did in 8.1.

### **What just happened ^reveal-r8**

**Button hint** — Turn it on and try the question first

*So why did you do all that*

Because the two things sign in *different parties*, and the difference decides what you can build.

**A connector signs Claude in.** It works while you are in a conversation, because the conversation is what carries it. That is exactly right when what you want is for Claude to go and do something to a Drive file in front of you — and for that, it is better than what you built: faster to set up, nothing to maintain, nothing to keep on your laptop.

**Your token signs your program in.** Which matters the moment you want something to run when you are not there — the letters generated at six in the morning, the sheet checked every night, the tool a colleague runs on their own machine against their own account. There is no conversation in any of those, so there is nothing for a connector to hang on. That is the whole of Sequence 2 pointed at one problem: making things that work without you.

There is a second difference worth noticing. The connector's reach is whatever the connector asks for. **Your token's reach you chose** — that was the scope conversation, and it is why a program that only needs to read can be given a key that cannot write.

What is identical is the part that matters most: go back to `myaccount.google.com/permissions` and the connector is in the same list as your app, described the same way, removable by the same button. One procedure, one place, one habit.

### **Side note ^aside-6**

**So: use the connector when you want Claude to do a thing now, and your own credentials when you are building something that has to keep working after you close the laptop.** Most people end up with both switched on, and that is the right answer rather than a compromise.

## **Section 11 — What this unlocks ^sec11**

**Heading** — What this unlocks

You can now build things that reach outside your own laptop.

And what you learned is not really about Google. Every serious system your school runs — the student information system, the library, the billing platform, the learning management system — has an API, and nearly all of them work exactly the way this one does. Register the app, sign in once, hold a narrow token, ask for what you need. The screens have different names. The shape does not change.

So the useful skill is not that you can now read a Google Sheet. It is that the next time somebody says "there's an API for that," you know what they mean, roughly what it will cost you, and what questions to ask.

**Ask Claude — when you want to reach a new system**

> I want a program to read data out of [system]. Does it have an API? What kind of sign-in does it use, what would I have to register, what would I be able to reach, and who at my school would have to approve it?

### **Side note ^aside-7**

**The last question in that prompt is not a formality.** Your Google token reached your own Drive, which was always yours. A token for the student information system may reach every family in the building, and that is not a decision to make quietly because it was technically easy. Whoever owns that data at your school should know before you ask for a key to it.

## **Section 12 — If something went wrong ^sec12**

**Heading** — If something went wrong

| You saw | It means | Try this |
| --- | --- | --- |
| Missing credentials/oauth_client.json | The downloaded file isn't in place, or isn't named exactly that. | Check for a doubled extension — `oauth_client.json.json` is the usual culprit. Ask Claude to check the folder. |
| No token at …_token_….json | 8.8 hasn't run, or ran in a different folder. | `cd ~/Projects/google-workspace-helper` first, then run it again. |
| access_denied | The account you signed in with isn't allowed to use this app. | On Internal, sign in with your school account. On External, add yourself under **Audience → Test users**. |
| Token has been expired or revoked | Usually the seven-day External-in-Testing expiry. | Run 8.8 again. If it keeps happening weekly, that is why — go back to 8.5 and get onto Internal. |
| has not been used in project … or it is disabled | That API was never switched on. | Back to 8.4. The error names which one. Check the project selector is showing the right project. |
| insufficient authentication scopes | Your token doesn't cover what was asked for. | Re-run `authorize.py` with the right pair, e.g. `drive write` rather than `drive readonly`. |
| Internal is greyed out | You're signed in with a personal account. | Sign out, sign in with your school address, and make the project again from 8.4. |
| Google hasn't verified this app | Expected on an External app. It means yours. | **Advanced → Go to (unsafe)**. If you never chose External, check which project you're in. |
| Claude still says it can't reach Drive | The session started before the note was added. | Start a new Claude Code session. The global `CLAUDE.md` is read once, at the start. |
| command not found: python3 | Python isn't installed, or is too old. | `brew install python@3.12`, then open a new terminal window. You need 3.10 or newer. |

### **Side note ^aside-8**

**Before any of that, run the checker.** From the helper folder, `python3 scripts/check_setup.py` diagnoses most of this on its own and tells you what to do next. Add `--live` once you have a token and it will make a real call and name the account it signed in as.

**Then paste the whole error into Claude.** It has the setup instructions in front of it and these messages are precise. This is the situation Claude is best at, and reading the error is faster than guessing at it.

## **Module tasks ^checklist**

The 10 checkboxes near the end, in the order the module does them:

1. Made a practice sheet of invented names, and watched Claude fail to read it
1. Talked to an API by hand, and read the refusal
1. Cloned the helper and asked Claude to set it up
1. Created a Cloud project and switched on the three APIs
1. Set the consent screen to **Internal**
1. Made a Desktop client and downloaded its file
1. Ran `check_setup.py` myself and saw where I'd got to
1. Read the permission screen before clicking Allow
1. Read a sheet, and wrote a tab back into it
1. Found my own app in my Google permissions, and know how to revoke it

## **Section 13 — Before you finish ^sec13**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

Your Drive is yours. Claude runs on your computer, working for you. So what is actually standing between them — and what would it take to let it through?

Answer it again now. What stood between them was that Drive is somebody else's computer, and it does not deal with anonymous strangers — it wants to know which program is asking and on whose behalf. What let it through was a registration and a single click on a page belonging to Google.

Then notice what still feels unclear. That part is the most useful thing you could ask Claude in the next five minutes.

### **Side note ^aside-9**

**Next:** Module 9 — *Where school data is allowed to live.* You are now holding a working key to a real system, which is exactly why every exercise here used invented names. That module is where it gets decided what may go through the door for real.

In the meantime: whatever you have been putting off because it was too repetitive to face. You now have the piece that was missing. Start with the smallest version of it, on made-up data, and see how far you get.

## **Footer ^footer**

Developing with AI · Module 8. Written for macOS; the ideas are identical on Windows but several commands differ.
