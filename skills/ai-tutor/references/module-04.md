# Module 4 — Putting it on the internet: the page's text

Generated from `dev-portal-site/modules/04-publishing.html` by `tools/make-tutor.py`. **Do not
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

**Module number** — 4

**Title** — Putting it on the internet

**For** anyone who has finished Module 3 **Time** about forty-five minutes **You need** a browser, and something you made in Module 1, 2 or 3

---

**Label** — Before you start

You have made several things that work. Every one of them exists in exactly one place: a folder on your laptop.

That has been fine, because you were the only person who needed to open them. This module is about the moment that stops being true — when a colleague should be able to try the thing, or a family should be able to use it, or you want to put a link in an email rather than an attachment nobody can open.

*This line sits alone in the clay-bordered box:*

You can email somebody a file. So what is a web address actually *for*? Think about it for a moment.

**Label** — Core vocabulary

Open this and take a look. **You don't need to learn them now.** You will meet each one by doing something.

**Button** — Show the 11 terms

### **The terms ^vocab-terms**

The clay-colored lines are the notes that appear underneath a definition. Not every term has one.

**Browser** A program that opens a file and draws it on screen. Double-click a page on your laptop and it opens a file on your computer; type a web address and it opens one on somebody else's. *Note:* Same program, same kind of file. The only difference is whose computer it is on — which is the whole of this module.

**Render** What a browser does with an HTML file: reads the text in it and draws the page you see. *Note:* The file really is just text. You can open it in TextEdit and read it yourself.

**Artifact** Something Claude made that lives inside Claude, in the conversation, rather than in a folder on your computer. *Note:* It is not a file until you download it — and a host can only publish files.

**Static site** A website made only of files: pages, styles, pictures. Nothing is calculated when somebody visits; the files are simply handed over. *Note:* Almost everything Claude builds for you is already this shape.

**Web server** A computer that is always on, waiting to hand files to anyone who asks for them. *Note:* The whole difference between a file store and a website is what happens when a stranger asks.

**Host** A company that runs that computer for you. You give them files; they give you an address.

**Deploy** Putting a new version of your files on the host. *Note:* Not "saving." Publishing. The live site changes the moment it finishes.

**`index.html`** The file a web address opens by default. A folder without one has nothing to show. *Note:* The single most common reason a first publish looks broken.

**Public** Readable by anyone who has the address, with no sign-in, forever, including by machines that keep copies.

**URL** *(web address)* The name people type. Yours will be invented for you and you can change it once.

**HTTPS** The padlock. It means the connection is private; it does **not** mean the page is.

## **Section 1 — First, do you have a file? ^sec1**

**Heading** — First, do you have a file?

This module publishes *files*, so before anything else, find out whether you have one. The answer depends on where you have been working, and a lot of people are surprised by it.

**If you have been working in Claude Code, you do.** Everything it made is sitting in a folder you named. You can open that folder in Finder right now and see it.

**If you have been working in the Claude app or on claude.ai, you may not.** When Claude builds you a page there, it usually appears as an **artifact** — a panel beside the conversation showing the finished thing, which you can click around in. That artifact lives inside Claude, in that conversation. It is not in any folder on your computer, and there is nothing yet for you to drag anywhere.

The distinction is worth more than this module. **A file is yours.** It sits on your disk, it is backed up with everything else you own, any program can open it, any host will take it, and it will still be there in ten years with no account anywhere. An artifact is convenient, and it is a feature of somebody's product.

If yours is an artifact, get it out before going on. In the Claude app there is a download control on the artifact itself. In Claude Code, ask:

**Ask Claude — to turn what you made into real files**

> Write what you just made into its own folder in my Projects folder, as real files I can open in Finder. Tell me the folder's full path when you are done.

### **Side note ^aside-1**

**Claude can also publish an artifact for you**, and for showing somebody something once, that is a perfectly good answer. What it does not give you is an address of your own, a name you chose, the ability to hand the same thing to a different host next year, or anything that outlives the product. Those are what the rest of this module is about, and they are worth forty minutes exactly once.

## **Section 2 — A browser is a program that opens files ^sec2**

**Heading** — A browser is a program that opens files

Start with what you already have on your laptop, because what you are about to do is a much smaller change than it sounds.

### **Try it yourself 4.1 ^try-4-1**

Find the page Claude built you — the game from Module 1 is ideal. It is a file whose name ends in `.html`.

Open it in **TextEdit** first. Right-click it, choose *Open With*, then TextEdit. Read a few lines of what is in there.

Now close that without saving, and **double-click the same file**. It opens in your browser.

### **What just happened ^reveal-r1**

**Button hint** — Look at it in TextEdit first

One file, two programs, two completely different-looking results — and **the file did not change between them.**

**An HTML file is just text.** Not a special format, not something compiled or locked. You could read the whole thing aloud. TextEdit showed you that text as text, because showing text is what TextEdit does. The browser read the same characters and **drew a page** from them, because that is what a browser does. Drawing it is called **rendering**, and it is the browser's job — not the file's, and not anybody else's.

Now the quieter thing, which is the one that matters. **Your browser just opened a file on your computer.** No internet was involved. Nothing was downloaded. A browser is a program that opens a file and renders it, and it had one sitting right there.

## **Section 3 — The only difference is whose computer ^sec3**

**Heading** — The only difference is whose computer

Here is the part that is smaller than people expect.

When you type a web address, your browser does exactly what it just did — opens a file and renders it. **The file is simply on somebody else's computer.**

That is the whole of it. Not a different kind of document, not a different sort of program, nothing that needed converting. The same act, aimed somewhere else.

So publishing is not a transformation of your work. It is **putting your file on a computer that is always on, and that will hand it to anyone who asks.** A computer doing that job is a **web server**, and a site that is nothing but files sitting there waiting to be handed over is called **static**.

Which is what you already have. A page, a stylesheet, maybe some pictures, in a folder. You have been making static sites for three modules without needing the word.

But that raises a fair question, and it deserves a real answer rather than being skipped past: **you can already give people the file. Why not just do that?**

### **Try it yourself 4.2 ^try-4-2**

Email the file to yourself. Then open it on your phone.

Now go back to your laptop and ask Claude to change something you would notice — a heading, a color.

Then open the emailed copy on your phone again.

### **What just happened ^reveal-r2**

**Button hint** — Make the change before opening this

Two things, and the first one is the honest half that this kind of module usually skips.

**Sending somebody the file genuinely works.** On a laptop they download it, double-click it, and their browser renders it exactly as yours does. For one colleague, today, that is a completely reasonable thing to do, and nobody should be made to feel it is wrong. On a phone it is already awkward — mail apps will not usually render an attached page, so it may have offered you nothing useful at all.

**And the copy you sent is now wrong.** It still shows the old heading. It will show the old heading forever, because it is not your page — it is a photograph of your page, taken at the moment you pressed send, sitting on somebody else's machine where you cannot reach it.

That is what is wrong with giving people files, and it has nothing to do with whether it technically works. A copy is a snapshot. You have to decide in advance who gets one. You have to send a new one every time anything changes, to everybody, and hope they open the right one. And anyone you did not think of gets nothing at all.

**What you actually want is for the thing to be available to anyone.** One copy, in one place, always current, that you can point a person at without knowing in advance who they are. That is a web address, and it is a different idea from a file you send — not a better way of sending.

### **Side note ^aside-2**

There is another kind of site, where a program runs on the far end every time somebody visits — anything with accounts, a database, a shopping cart. Those are harder, cost money, and need looking after. You do not need one, and a surprising number of people who think they do are wrong.

## **Section 4 — Getting the folder right ^sec4**

**Heading** — Getting the folder right

One rule, and nearly every first failure is this rule.

**The folder you publish must contain a file called `index.html` at its top level.** That is the file a bare web address opens. A folder without one publishes perfectly successfully and then shows a 404 or a list of filenames — which reads as "it's broken" when in fact everything worked and there was simply nothing to show first.

### **Try it yourself 4.3 ^try-4-3**

Ask Claude to put the thing you are publishing into a folder of its own, correctly named:

**Ask Claude**

> Put [the game you built in Module 1] into its own folder inside my Projects folder, called [name]. Make sure the main page is called index.html, and that any stylesheets or images it needs are in that folder too. Then show me the folder and tell me its full path.

Open that folder in Finder and look at it. One `index.html`, plus whatever else it needs. Double-click `index.html` and check the thing still works from its new home.

### **What just happened ^reveal-r3**

**Button hint** — Double-click index.html in its new folder first

If it still works, every link inside it is **relative** — each file refers to the others by name, not by where they live on your machine. That is why the folder can be picked up and put somewhere else entirely and still work.

If something broke — a picture missing, the styling gone — it is almost certainly a file left behind. Ask Claude what the page is asking for and where it expects to find it.

This is worth understanding properly, because it is why publishing is a *move* rather than a rebuild. The folder is self-contained. It does not care which computer it is on.

## **Section 5 — Publishing it ^sec5**

**Heading** — Publishing it

You are going to use **Netlify**, which is a company that runs a web server so you do not have to. There are several others like it; this one is the least work to start.

**Make the account first.** You can publish without one — drag a folder at netlify.com/drop and you get a live address in about four seconds, which is genuinely impressive. But a site published that way is not attached to you, and taking it down again is awkward. For the first thing you ever put on the open internet, being able to delete it is worth thirty seconds of signing up.

### **Try it yourself 4.4 ^try-4-4**

- Go to **netlify.com** and make a free account.
- Find **Sites**, and the area that invites you to deploy a project manually by dragging a folder. (Netlify moves this around; it is always within one screen of the Sites list, and "drop" is usually in the wording.)
- Drag your whole folder onto it. Netlify will also take a single file, but yours needs its stylesheet and pictures alongside it, so send the folder.
- Wait. It will take a few seconds and then show you a web address, something like `fluffy-marmot-a81b3c.netlify.app`.
- Open it. Then open it **on your phone**, off wifi.
### **What just happened ^reveal-r4**

**Button hint** — Open it on your phone first

That address works from anywhere in the world, for anyone, with no sign-in, on a connection you did not configure, over HTTPS you did not set up. It cost nothing, took one drag, and no part of it involved a terminal.

Look at what you did *not* have to do. You did not buy a server, or rent one, or install anything, or learn what a DNS record is, or put a credit card down. For a static site this is now genuinely free for the amount of traffic a school will ever send it.

The phone test matters because it proves the thing you actually wanted. It is not on your computer. Your computer could be off.

## **Section 6 — And now it is public ^sec6**

**Heading** — And now it is public

Stop and take this one seriously, because it is the part of the module with consequences.

**That page is public.** Not "unlisted." Not "only people with the link." Public. The address is hard to guess, which is not the same as private — search engines find pages nobody linked to, archive services keep copies, and anyone you send it to can forward it, screenshot it, or paste it anywhere.

And there is no undo. **You can take a page down, but you cannot take back a copy somebody already has.** Deleting the site stops future visitors. It does not reach into a search index, a cache, an archive, or a colleague's screenshot.

So, one rule, and it is not a soft one:

Nothing with a real child on it. Ever. Not a name, not a photograph, not a grade, not a comment, not an initial next to a score. Not even for five minutes while you check it looks right.

"I'll take it down straight after" is the plan that fails, because the five minutes is exactly when an automated crawler is most likely to be the visitor.

This is not the whole of the question — **where school data may and may not go is Module 9**, and it is a bigger conversation than one rule. But Module 9 is five modules away and you can publish something this afternoon, so the rule comes now.

### **Side note ^aside-3**

Invented data is completely fine, and you have a model for it already: everything in this series uses made-up children. If you want to show a colleague a tool that works with real information, show them the tool with fake information in it.

## **Section 7 — Taking it down ^sec7**

**Heading** — Taking it down

Know how to do this today rather than in an emergency. It is the same reason Module 8 makes you find the revoke button before you need it.

### **Try it yourself 4.5 ^try-4-5**

In Netlify, open your site, find its settings, and delete it. It will ask you to type the site's name to confirm, which is a good habit on anybody's part.

Then open the address again in a private window.

### **What just happened ^reveal-r5**

**Button hint** — Check the address after deleting first

Gone, in seconds, and you did not have to ask anyone.

That is the property to check for in any tool that publishes on your behalf: *can I take this back, by myself, immediately?* If the answer is no, or "email support," that is worth knowing before you publish rather than after.

But notice precisely what you have and have not undone. **Future visitors get nothing. Everything already fetched is still out there.** Deletion is a tap you turn off, not a copy you recall — which is the practical reason the rule in the last section is absolute rather than careful.

Now publish it again. It takes four seconds, and you will want it for the next part.

## **Section 8 — Giving it a name ^sec8**

**Heading** — Giving it a name

`fluffy-marmot-a81b3c` is fine for a test and useless for anything you intend to send to a person.

### **Try it yourself 4.6 ^try-4-6**

In your site's settings, change the site name to something you would be willing to put in an email — `oakridge-grade4-fractions`, or whatever yours is. Save it, and open the new address.

### **What just happened ^reveal-r6**

**Button hint** — Open the new address first

The old address stops working and the new one starts, instantly, which tells you something about what an address is: not a place where your files live, but a **label pointing at them**. The files never moved.

That is also why you should change it once and then stop. Every link you have sent out points at whatever the name was when you sent it.

### **Side note ^aside-4**

You can put your own domain on it instead — `fractions.myschool.org` — but that means buying a domain and editing DNS records, which is a different afternoon and the first thing in this module that costs money. The free address is a real address; plenty of things live on one permanently.

## **Section 9 — Changing it ^sec9**

**Heading** — Changing it

You will want to fix something. Here is the whole workflow.

### **Try it yourself 4.7 ^try-4-7**

Ask Claude for a visible change:

**Ask Claude**

> In that folder, change [the heading / the colors / whatever you want]. Keep everything in the same folder with the same filenames.

Then drag the folder onto your site's deploys area again, and reload the live address.

### **What just happened ^reveal-r7**

**Button hint** — Reload the live address first

That is a **deploy**: you replaced the files, and the live site became the new version the moment it finished. Everybody who opens the address from now on sees the change.

Two things follow from that, and they are the reason the next sequence exists.

**You just overwrote the live site by dragging a folder.** There was no check, no preview, no "are you sure." Whatever was in the folder is now what the world sees, including a mistake.

**And there is no history.** Netlify keeps a list of your past deploys and you can roll back to one, which is a real safety net — but *your folder* has no history at all. If you ask Claude for a change and preferred the old version, the old version is gone from your laptop. That is the problem Module 7 solves, and it is why a lot of people who publish regularly end up connecting a repository instead of dragging folders: publishing becomes automatic, and every version is kept.

For now, dragging is fine. Know that it is the simple version of something that gets better.

## **Section 10 — What you can and cannot publish this way ^sec10**

**Heading** — What you can and cannot publish this way

**You can publish anything that is just files.** Pages, stylesheets, pictures, fonts, a slideshow, a calculator, a quiz, a game, an interactive diagram, a schedule people can filter — all of it. Anything Claude builds you that opens by double-clicking `index.html` will work on a host, unchanged.

**You cannot publish anything that needs a secret.** If a page has to sign in to something — to read a Google Sheet, to call a paid service — then whatever it uses to sign in is sitting in a file that anybody can read. There is no such thing as a hidden file on a static site. Publishing a page with a key in it is publishing the key.

That sounds like a limitation and is mostly a clarification: it tells you which half of your ideas are a four-second drag and which half are a different kind of project. **Module 8 is where the second half starts.**

**Ask Claude — when you are not sure which kind you have**

> I want to publish [the thing] as a static site. Does it need anything that a plain folder of files can't do — a server, a database, an API key, a password? If it does, tell me exactly which part, and whether there's a simpler version that wouldn't.

## **Section 11 — If something went wrong ^sec11**

**Heading** — If something went wrong

| You saw | It means | Try this |
| --- | --- | --- |
| A list of filenames instead of your page | No `index.html` at the top level of the folder. | Rename your main page to exactly `index.html` — lower case — and publish again. |
| "Page not found" straight after publishing | Usually the same thing, or you dragged a folder containing your folder. | Open the folder you dragged. `index.html` should be right there, not one level down. |
| The page loads but looks unstyled | The stylesheet did not come with it. | Ask Claude which files the page needs and whether they are all in the folder. |
| Pictures are broken online, fine on your laptop | A path that only exists on your machine, or a capital letter. | Hosts care about capitalization and your Mac does not. `Photo.JPG` and `photo.jpg` are different online. |
| Your change is not showing | Your browser is showing you its saved copy. | Hard reload, or open the address in a private window. |
| The link works for you and not a colleague | You sent the Netlify admin link, not the site address. | The site address is the short one ending `.netlify.app`, with no `app.netlify.com` in it. |
| You cannot find where to drag the folder | Netlify has moved it. | It is within one screen of your Sites list; "deploy manually" or "drop" is usually in the wording. |

## **Module tasks ^checklist**

The 10 checkboxes near the end, in the order the module does them:

1. Worked out whether what I made was a file or an artifact, and got files
1. Opened an HTML file in TextEdit and in a browser, and saw one file twice
1. Emailed myself the file, changed the original, and watched the copy go stale
1. Got the folder right, with `index.html` at its top level
1. Published it, and opened the address on my phone
1. Read the rule about whose name may appear on a public page
1. Deleted the site, and confirmed the address stopped working
1. Published it again and gave it a name I would put in an email
1. Made a change and deployed it over the top
1. Can say which of my ideas need more than a folder of files

## **Section 12 — Before you finish ^sec12**

**Heading** — Before you finish

*This line sits alone in the clay-bordered box:*

You can email somebody a file. So what is a web address actually *for*?

Answer it again now. A file you send is a copy: it arrives on somebody's machine, it is theirs, it is already out of date, and whether it opens at all depends on what they have. An address is not a copy. It is a pointer to the one living version, it works on a phone, it needs nothing installed, and when you change what it points at, everyone who follows it sees the new thing.

That is the difference between giving somebody your work and giving somebody *access* to your work.

Then notice the cost that came with it. The thing you now have is public, permanent in the only sense that matters, and one drag away from being overwritten. None of those was true of a folder on your laptop.

### **Side note ^aside-5**

**Next:** Module 5 — *The Terminal.* You have now made things and put them where other people can use them, which is the whole of Sequence 1. Sequence 2 is about what you can build once you stop being limited to what your Mac came with, and it starts by looking under the hood.

### **Side note ^aside-6**

In the meantime: publish something small that a colleague has been asking you for. The thing that makes this worth the forty-five minutes is not the first publish — it is the second one, when somebody says "could it also…" and the answer is a change and a drag.

## **Footer ^footer**

Developing with AI · Module 4. Written for macOS; the ideas are identical on Windows.
