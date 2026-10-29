# ai-tutor

Claude as a tutor for the **Developing with AI** modules from the
[Day School Development Portal](https://dev-portal-byauh7qecq-ue.a.run.app/modules.html).
The same modules as the website, done in conversation instead: Claude gives you one step,
waits while you do it, explains what you actually ran into, and, in Claude Code, looks at
your folder to check your work.

All ten written modules, from how your computer is organized into folders (Module 1) to
deciding which copy of your school's data is true (Module 10). It never needs, and will not
use, real student data.

## Install

In the Claude app (claude.ai or the desktop app): **Customize → Plugins → Add → Add
marketplace**, enter `day-school-dev-portal/ai-tutor`, then turn on **ai-tutor**. On a school
Team or Enterprise plan, an administrator may have switched off adding your own plugins; if
the Add option isn't there, ask them.

In Claude Code (the terminal, or the Code tab of the Claude desktop app):

```
/plugin marketplace add day-school-dev-portal/ai-tutor
/plugin install ai-tutor@day-school-dev-portal
```

Then start a new session and say **start Module 1**, or name any module.

If you would rather not install anything, every module page on the website has a
*Rather do this with Claude?* strip with a prompt you can paste into any Claude chat. The
plugin is the fuller version: it knows each module's exercises, what to check, and what
goes wrong.

## How it is built

```
.claude-plugin/          plugin.json, marketplace.json
skills/ai-tutor/
  SKILL.md               how to tutor: the rules every module shares
  references/
    module-NN.md         the module page's own words, generated
    module-NN-tutor.md   how to teach that module, written by hand
```

**Don't edit `references/module-NN.md` here.** It is generated from the module pages in the
portal repo by `tools/make-tutor.py`, so the website and the tutor cannot teach two
different versions of a module. Change the page, regenerate, commit here. The portal's
deploy refuses to publish a page this repo hasn't caught up with.

The hand-written `module-NN-tutor.md` files are edited here, and only here.

## License

MIT. Take it, change it, use it at your school.
