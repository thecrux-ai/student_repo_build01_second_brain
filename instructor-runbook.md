# Instructor Runbook: Build 1 — "Your Second Brain"

**Duration:** 60 minutes
**When:** Day 1, after Build 0 (approx 11:00 AM)
**Format:** Instructor demo (10 min) + build-along (50 min)
**Energy state:** Moderate-high. They've just survived Build 0 and have confidence. Channel that into awe.

---

## The Session's Logic (Read This First)

This session has a **clean split** between demo data and personal data:

- **Parts 1-2 use Arjun's data** (the messy-workspace). This is a showcase — "look what Claude can do with files." The before/after CLAUDE.md moment also uses Arjun's data, but the point is that different people in the room will see it through different lenses based on their own CLAUDE.md.
- **Parts 3-4 pivot to THEIR world.** Students build an empty second brain for their own role, seed it with something real from their own work, and set up a daily workflow. No more Arjun.

**Why this split matters:** If students build their second brain from Arjun's files, then ask "what should I focus on this week?" — the answer is about Arjun's week, not theirs. That kills the emotional payoff. The pivot in Part 3 is deliberate: "Arjun showed you what's possible. Now build it for yourself."

---

## Pre-Session Checklist

- [ ] Student repo cloned and working on instructor machine
- [ ] Tested all 3 demo prompts against the messy-workspace files (outputs change slightly each time — know what to expect)
- [ ] Messy-workspace has all 20+ files intact (no leftover organized folders from a previous run)
- [ ] If demoing from a fresh clone, verify: `ls messy-workspace/` shows all files
- [ ] TAs briefed on their roles:
  - Parts 1-2: Walk the room, help anyone stuck on prompts or directory navigation
  - Part 2 (CLAUDE.md interview): Actively coach — help people give specific answers, not vague ones
  - Parts 3-4: Help with the pivot to personal data — some people will be unsure what to put in

**IMPORTANT:** The instructor demo in Part 1 will reorganize the messy-workspace. If you need to demo again, reset with:
```bash
git checkout -- messy-workspace/
```
Students' repos are their own — they don't need to reset.

---

## Session Arc

| Time | Part | What Happens | Instructor Role | Data Used |
|------|------|-------------|-----------------|-----------|
| 0:00-0:10 | **The Wow** | Instructor demos Claude reading + organizing Arjun's 20 files | PERFORM. This is theater. | Arjun's |
| 0:10-0:20 | **Their Turn + Before/After** | Students explore Arjun's files, then build CLAUDE.md | COACH. Help with specifics. | Arjun's (demo) + Their own (CLAUDE.md) |
| 0:20-0:35 | **CLAUDE.md Deep Dive** | Complete the interview, do the before/after, iterate | NARRATE. Call out the moment. | Arjun's files, viewed through their CLAUDE.md |
| 0:35-0:50 | **Build YOUR Second Brain** | Create personal folder structure, seed with real data | GUIDE. Help them pivot to their own world. | **Their own** |
| 0:50-1:00 | **Monday Setup** | Daily workflow, real-work question | LAND IT. Make it real. | **Their own** |

---

## Part 1: "The Wow" — Instructor Demo (10 min)

**Goal:** Show what Claude can do with file system access. This should feel like magic.

**Setup:** Open Claude Code in the student repo directory with the messy-workspace intact.

```bash
cd student_repo_build01_second_brain
claude
```

**Introduce the case study (30 sec):**

> "There's a guy called Arjun Mehta. VP of Product at a SaaS startup in Koramangala, Bangalore. Series B, 100 employees, board breathing down his neck. His biggest client Acme Corp — 45 lakhs a year — is threatening to leave. He's got a board meeting in March. And his files are a complete mess. Sound familiar to anyone?"

### Demo 1: "What's in this mess?" (2 min)

Type this prompt (project it on screen):

```
Look at the messy-workspace folder. Tell me what's in there —
group things by theme, flag what looks important, and tell me
what this person's work life looks like based on their files.
```

**PAUSE while Claude works.** Let the spinner run. Let the class watch.

**Talk over the output as it appears:**

> "See the spinner? Claude is reading every file in that folder right now. Not listing them — READING them."
>
> "It found the Acme Corp renewal risk across three separate files — the client call, the email feedback, and the to-do list. It connected the dots."
>
> "Notice it figured out Arjun is a VP of Product without being told. It read 20 files and built a profile."

**KEY LEARNING POINT:** Claude Code has file system access. It reads and comprehends file contents. This is fundamentally different from ChatGPT or Claude.ai where you manually upload one file at a time.

### Demo 2: "Organize this chaos" (3 min)

```
Now organize this messy-workspace into a clean folder structure.
Group related files into folders that make sense. Rename files
that have bad names. Create a README that serves as a table of
contents for everything.
```

**PAUSE. Watch Claude create folders, move files, rename things.**

**Talk over it:**

> "Claude just created a folder structure from scratch."
>
> "It renamed 'URGENT - client feedback acme.txt' to something sensible."
>
> "It generated a README that maps everything — like a personal wiki."

**KEY LEARNING POINT — The permission model.** When Claude asks permission:

> "See that? Claude is ASKING you before it changes anything. You approve each action. You're always in control. Claude proposes, you approve."

**Terminal tip:** "You can press `y` to approve, or type `yes` to approve all similar actions."

### Demo 3: "Find me something specific" (2 min)

```
What did the client from Acme Corp say about the timeline?
And what's the budget situation looking like for Q1?
```

> "I didn't tell Claude which file to look in. It searched everything and found the answer."
>
> "It pulled the Acme timeline from the client call transcript AND the email feedback — two different files, one answer."
>
> "This is what having a second brain feels like. You dump stuff in, you ask questions, it knows."

### Transition (30 sec)

> "That was Arjun's mess. Now you're going to explore it yourselves — and then teach Claude who YOU are. That's where things get really interesting."

---

## Part 2: Their Turn + Build CLAUDE.md (15 min combined)

**This part combines the hands-on exploration with the CLAUDE.md build.** The before/after moment is the emotional peak.

### Their turn with Arjun's files (5 min)

**Instructor says:**

> "Open Claude Code in the student_repo_build01_second_brain directory. Your prompts are in the student handbook. Explore Arjun's messy-workspace — let Claude read it, organize it, search it."

**Prompt 1 on screen:**
```
Look at everything in the messy-workspace folder. Read the files and tell me:
what kind of professional left this mess? What are they working on?
What seems urgent?
```

Give them 3 minutes. Then:

**Prompt 2 on screen:**
```
Organize messy-workspace into a clean structure. Create folders, move files
where they belong, rename anything with a bad name. Create a table-of-contents
README when you're done.
```

**Quick check:** "Raise your hand if Claude organized your files." (Should be everyone.)

### The "Before" Snapshot (1 min)

> "Before we move on — everyone ask Claude this exact question."

**On screen:**
```
Write me a one-paragraph executive summary of what's happening
in Arjun's messy-workspace files. What should he focus on?
```

> "Notice the output. It's accurate. But it's generic — everyone in the room got roughly the same answer. Hold onto that."

### Build CLAUDE.md (8 min)

> "Now we're going to teach Claude who YOU are. After this, the same question gets a completely different answer."
>
> "CLAUDE.md is a special file. Claude reads it automatically every time you start a session. It's your second brain's memory. Build it well, and you never explain yourself to Claude twice."

**On screen:**
```
I want to create my personal CLAUDE.md file. This will be saved at the root
of this project and will tell you who I am so every future conversation
is personalized.

Interview me to build this. Ask me about:
1. My role, industry, and what my company does
2. What I'm working on right now (top 2-3 priorities)
3. How I like information presented (bullets vs prose, formal vs casual, etc.)
4. What I want to use Claude for most

Ask 2-3 questions at a time. After I answer, ask the next batch.
When you have enough, create the CLAUDE.md file.
```

> "You have 8 minutes. Answer with specifics from YOUR real work. Not 'I'm in tech.' Say 'I'm a regional sales manager for an automotive company covering South India.' The more specific you are, the better this works."

**KEY LEARNING POINT — say this while they work:**

> "Notice Claude is asking questions BEFORE building. This is the pattern — have a conversation, guide it, iterate. Claude works best when you treat it like a smart new hire who needs context."

**TAs: Walk the room.** If someone is stuck:
- "What did you do at work last Monday?"
- "What took too long this week?"
- "What do you wish someone else could handle for you?"
- "What kind of documents do you write most often?"

**If Claude is asking too many questions:** Tell them to say: "That's enough, create the CLAUDE.md now."

### The "After" Moment — THE KEY MOMENT OF THE SESSION

**Once most people have their CLAUDE.md (around the 8-min mark):**

> "OK. Now ask Claude to look at Arjun's files AGAIN — but through YOUR eyes."

**On screen:**
```
Now write me that executive summary of Arjun's messy-workspace files again.
But this time, frame it for ME — based on what you know about me from CLAUDE.md.
What would I care about most in Arjun's situation? What would I notice that
a generic summary would miss?
```

**Wait for reactions. Then narrate:**

> "Same 20 files. Same question. Completely different answers around the room."
>
> "Sunita in sales noticed the Acme renewal risk and the unsent ROI email — because that's a deal she'd be saving."
>
> "Deepa in finance spotted the over-budget cloud infra and the expiring vendor contract — because those are numbers that keep her up at night."
>
> "Rajesh the founder zeroed in on the board meeting prep and the competitive threat — because that's his world."
>
> "The AI didn't get smarter between the first answer and the second. YOU gave it your brain."

**KEY LEARNING POINT:**

> "This is Rule #1 of working with AI: **Context is everything.** Not better prompts. Not tricks. Context. You experienced it just now — same files, radically different output, because Claude knows who you are."

**Why this works even though it's Arjun's data:** The point isn't that Claude analyzed YOUR files differently. The point is that the same information looks different to different people — and CLAUDE.md teaches Claude to see through YOUR lens. When they use this on their own files later, the effect is even stronger.

### Iterate (2 min)

**On screen:**
```
Read my CLAUDE.md and suggest 3 things I should add to make you
more useful to me. What's missing that would help you help me better?
```

> "This is the build-test-iterate loop. Build something, test it, ask Claude to critique it, make it better. You'll use this loop all weekend."

---

## Part 3: Build YOUR Second Brain (15 min)

### The Pivot — Make This Explicit

> "Everything so far used Arjun's files — that was the demo. Now we leave Arjun behind. From here on, you're building for YOUR life."
>
> "Your CLAUDE.md tells Claude who you are. Now let's build the actual second brain — a folder structure on YOUR machine for YOUR work. You'll start filling it with real data today and keep using it on Monday."

### Create the structure (7 min)

**On screen:**
```
I want to set up a "my-second-brain" folder structure in this project.
Based on what you know about me from CLAUDE.md, create a directory
structure that would be useful for MY work. Include:

- A place for project notes and documents
- A place for meeting notes and decisions
- A place for templates I reuse
- A place for reference material and research
- A daily log / journal area

Create the folders, add a README in each one explaining what goes there,
and create 2-3 starter templates that would be useful for my specific role.

Also update CLAUDE.md to include a section about this second brain —
where things live, what goes where, so you always know how to find things.
```

**While they work — callouts:**

> "Notice Claude used your CLAUDE.md to decide the folder structure. Sunita got a pipeline tracker and client meeting notes folder. Karthik got a deal flow and portfolio monitoring folder. Deepa got a budgets folder and a compliance tracker."
>
> "See how it updated CLAUDE.md? That file is growing. Every time you add context, Claude gets smarter."
>
> "Look at the templates — they're tailored to YOUR role. Not generic. Yours."

**KEY LEARNING POINT — Compounding:** CLAUDE.md started as a bio. Now it has your role, your priorities, AND a map of your second brain. Each addition makes everything else better. This is what "compounding AI" means — and it's the theme of the whole bootcamp.

### Seed it with something real (5 min)

> "Your second brain is ready but empty. Let's put something real in it right now. You've got three options."

**On screen — give them the choice:**

**Option A — Paste real notes:** If you have meeting notes, a to-do list, or an email thread handy (phone, email, whatever), paste it in:
```
I'm going to paste some notes from a real meeting I had recently.
Save them in the right place in my second brain, and extract any
action items or follow-ups into the appropriate tracker.

[paste your real notes here]
```

**Option B — Dictate from memory:** Just brain-dump what's on your plate:
```
Here's a rough dump of what's on my plate right now:

[type out 3-5 things you're working on or worrying about — messy is fine]

Organize this into my second brain. Put things where they belong.
Create any files needed.
```

**Option C — Generate realistic samples:**
```
Create a realistic sample set of 3-4 files for my second brain based on
what you know about my role from CLAUDE.md. Make them feel like things
I'd actually have. Put them in the right folders.
```

> "Any option works. The point is: your second brain should have something in it before we leave this session."

**TAs:** Help anyone who's frozen on what to put in. "What's the last meeting you were in? What was it about? Just paste or type that."

### Test it (3 min)

**On screen:**
```
Based on everything in my second brain, what are the most important things
I should focus on this week? Where in my second brain can I find the
relevant files?
```

> "Claude just searched YOUR second brain, with YOUR files, through YOUR CLAUDE.md lens, and gave you a personalized priority list. That's not a chatbot. That's a chief of staff."

### If students see subagents

If Claude spawns subagents, **call it out:**

> "See those additional spinners? Claude delegated parts of the task to sub-agents on its own. You didn't ask — it decided. We'll go deeper on this in Build 2."

---

## Part 4: Make It Stick — The Monday Setup (10 min)

### Daily workflow (3 min)

**On screen:**
```
Add a section to my CLAUDE.md called "Daily Workflow" that describes how I
should use my second brain each day. Include:
- What to do when I start my day (morning review)
- How to capture notes during the day (just dump files in the right folder)
- What to do at end of week (weekly review)
```

### Real Monday morning question (5 min)

> "Last thing. Think about what you'd actually face on Monday morning. Ask Claude."

**Put role-specific examples on screen** (from the student handbook). Let them pick one or write their own.

> "This is the moment it becomes real. Some of you are looking at your screen right now thinking 'this is actually useful.' That's the point."

### How CLAUDE.md actually works — quick explainer (2 min)

**This is an important teaching moment.** Students need to understand that what they built isn't trapped in this bootcamp repo.

> "Quick thing before we wrap. You might be wondering — does Claude read my CLAUDE.md every time? Do I have to tell it? The answer is: **it loads automatically, every session.** You never ask. It just happens."

**On screen — draw or show this:**

```
~/.claude/CLAUDE.md          --> Loads EVERY session, everywhere
                                 (who you are, preferences)

~/my-second-brain/CLAUDE.md  --> Loads when you're in that folder
                                 (folder map, workflows)
```

> "There are two levels. Your global CLAUDE.md at `~/.claude/CLAUDE.md` — that's your identity. It loads no matter where you are on your machine. Then each project folder can have its own CLAUDE.md with project-specific context."
>
> "So the move after this bootcamp: take your personal stuff — role, preferences, communication style — and put it in `~/.claude/CLAUDE.md`. Set up your second brain as a real folder on your machine — `~/my-second-brain/` — with its own CLAUDE.md for the folder map and daily workflow."
>
> "The student handbook has a 'Take It Home' section with the exact steps. Do it tonight or tomorrow. It takes 5 minutes."

**KEY LEARNING POINT:** Claude Code reads CLAUDE.md automatically. No command, no setup, no remembering. That's why this system sticks — zero friction to use it every day.

**Do NOT spend more than 2 minutes on this.** Plant the seed, point them to the handbook section, move on. They'll set it up at home.

### Landing the session (1 min)

> "Look at what you have. A CLAUDE.md that knows who you are. A second brain ready for your work. Templates for your role. A daily workflow. And now you know how to make it permanent on your machine."
>
> "Arjun's mess was the demo. YOUR second brain is the takeaway. On Monday morning: `cd ~/my-second-brain`, type `claude`, and say 'What should I focus on today?' It'll know."
>
> "And here's the thing — this CLAUDE.md carries into every session today. Build 3 will add your writing voice. Build 4 will connect it to your tools. By the end of the day, this second brain will be fully operational."

**Transition to break / Build 2:**

> "Take a 5-minute break. When we come back, you're going to assemble a panel of AI experts to evaluate a real business idea. Same CLAUDE.md. New superpower."

---

## Common Issues & TA Quick Reference

| Issue | Response |
|-------|----------|
| "Claude won't read my files" | `pwd` to check directory. They're probably one level up. `cd student_repo_build01_second_brain` fixes it. |
| "My CLAUDE.md is too generic" | "Give Claude more specific answers. Not 'I'm in tech' — say 'I'm a PM at a Series B SaaS company building onboarding automation.'" |
| "Claude is asking too many questions" | "Say: 'That's enough, create the CLAUDE.md now.' You can always add more later." |
| "The before/after looks the same" | Their CLAUDE.md is too vague. Help them add role-specific details. Then re-run the after prompt. |
| "I don't know what to put in my second brain" | "What did you do at work last week? What files did you touch? What meeting were you in? Start there." |
| "The folder structure doesn't fit my work" | "Tell Claude to change it. 'Rename X to Y. Add a folder for Z.' It's YOUR brain." |
| "I don't want to use real work data" | "Totally fine. Use Option C — have Claude generate realistic samples for your role." |
| Student finishes early | "Add more context to CLAUDE.md. Or pair up with someone nearby and compare your setups." |
| "I can't find the `.claude` folder on my machine" | Dot-folders are hidden by default. **Mac Finder:** `Cmd + Shift + .` to toggle. **Windows Explorer:** View > Show > Hidden items. **Terminal:** `ls -a` always works. |
| Student didn't do Build 0 / just arrived | Have them clone the repo and jump in at Part 2. Sessions are independent. |

---

## Key Lines to Deliver (Practice These)

These are the lines that land hardest. Know them cold.

**During the demo:**
> "Claude didn't just list Arjun's files. It READ every single one and understood what's inside."

**Introducing the case study:**
> "Arjun's got a 45-lakh client threatening to leave, a board meeting in 6 weeks, and his files look like a hurricane hit them. Sound like anyone you know?"

**During the before/after:**
> "Same files. Same question. Completely different answer. The AI didn't get smarter — you gave it your brain."

**On the pivot to personal data:**
> "Arjun was the demo. Now we leave him behind. From here, everything you build is for YOUR life."

**On CLAUDE.md:**
> "CLAUDE.md is the highest-leverage thing you'll build this weekend. Ten minutes now saves you hours every week."

**On the iterate loop:**
> "You don't write the perfect CLAUDE.md on the first try. You build it, test it, and make it better. That loop is everything."

**On the second brain:**
> "On Monday morning, dump your meeting notes into this folder, start Claude, and ask what you should focus on. It'll know."

**On making it permanent:**
> "Your global CLAUDE.md at `~/.claude/` loads every single session automatically. Set it up once, and Claude knows you forever."

**On compounding (sets up the rest of the day):**
> "This CLAUDE.md is going to follow you all day. By Build 5, Claude will know who you are, write in your voice, and ship products for you. It all starts here."

---

## What Students Should Have After This Session

- [ ] Experience watching Claude read and organize Arjun's 20+ files
- [ ] A personal **CLAUDE.md** with: role, priorities, preferences, second brain map, daily workflow
- [ ] The before/after experience — same data, different lens — burned into their memory
- [ ] A **my-second-brain** folder structure with READMEs and role-specific templates
- [ ] At least one real piece of their own content seeded into the second brain
- [ ] A real-work question answered by Claude using their second brain
- [ ] Understanding of the build-test-iterate loop

---

## Features Taught Through Doing (Not Lectured)

| Feature | Where It Appears | What to Say If Asked |
|---------|-----------------|---------------------|
| File reading | Demo + Part 2 | "Claude Code can read any file on your machine. It doesn't just see names — it reads contents." |
| File write / create | Parts 2, 3 | "Claude creates files and folders directly. No copy-paste needed." |
| File move / rename | Parts 1, 2 | "Claude can reorganize your entire file system. You approve each action." |
| CLAUDE.md | Part 2 | "It's a markdown file Claude reads at session start. Put it in the project root. It loads automatically." |
| Permission model | Parts 1, 2 | "Claude always asks before changing files. Press y to approve. You're in control." |
| Iterative building | Part 2 (iterate) | "Build, test, ask Claude to critique, improve. This is the loop for everything." |
| Context = quality | Part 2 (before/after) | "Context is the #1 lever. Not fancy prompts. Context." |
| Search across files | Parts 1, 3 | "You don't need to remember which file. Just ask. Claude searches everything." |
| Subagents (if they appear) | Part 3 | "Claude can delegate to sub-agents on its own. You didn't ask — it decided. More on this in Build 2." |

---

## Timing Adjustment Guide

**Running behind (common — the CLAUDE.md interview takes longer than expected):**
- Compress Part 2's hands-on exploration to 3 min (just the explore prompt, skip organize — they saw you do it)
- Cut the "seed with real data" step — they can use Option C (generated samples) which is faster
- Cut Part 4 Monday test to 3 min — just the daily workflow prompt
- Do NOT cut the before/after moment. That's the session.

**Running ahead:**
- Let them seed more real data into the second brain
- Have them pair up and compare CLAUDE.md files — "What did they include that you didn't?"
- Have them ask Claude: "Read my second brain and tell me 3 insights I might be missing."
- Preview Build 2: "In the next session, you'll assemble a team of AI experts. Same CLAUDE.md, totally different use."

---

## FAQ — Questions Students Will Ask (and How to Answer Them)

### About CLAUDE.md

**"Can Claude see my CLAUDE.md? Can I ask it to read it?"**
Yes — and it already has. Claude Code reads CLAUDE.md automatically at the start of every session. You don't need to tell it to. But you can also ask "Read my CLAUDE.md and tell me what you know about me" to verify.

**"What if I have multiple projects? Do I need a different CLAUDE.md for each?"**
Yes, and that's the point. Your global CLAUDE.md at `~/.claude/CLAUDE.md` has your identity — who you are, how you work. Each project folder gets its own CLAUDE.md with project-specific context. Claude loads both: your identity + the project context.

**"What if my CLAUDE.md gets really long? Is there a limit?"**
Keep it under a page or two. Claude reads the whole thing at the start of every session, and a bloated CLAUDE.md wastes context. Be specific, not lengthy. Five sharp lines beat fifty vague ones. If it's growing too long, move details into separate files in your second brain and just reference them in CLAUDE.md ("For client details, see clients/").

**"Can my team share a CLAUDE.md?"**
Yes. A project-level CLAUDE.md checked into a shared repo becomes the team's shared context — coding conventions, project structure, key decisions. It's one of the most powerful uses of CLAUDE.md in professional settings.

**"Does CLAUDE.md work with regular Claude (claude.ai) or just Claude Code?"**
CLAUDE.md is a Claude Code feature. In claude.ai, you'd use Projects or the system prompt to achieve something similar. But the file-based approach in Claude Code is much more natural — it just sits in your folder and works.

### About files and privacy

**"Can Claude read ANY file on my computer?"**
Claude Code can read files in the directory you're working in and its subdirectories. It asks permission before reading, creating, or modifying files. You approve every action. It cannot silently access files outside your current directory without you explicitly pointing it there.

**"Is Claude sending my files to the cloud? Is this safe for work data?"**
Claude Code sends your prompts and the file contents it reads to Anthropic's API for processing. The data is not used to train models. If your company has strict data policies, check with your IT team. For personal use and most professional use, the privacy model is solid — but don't paste passwords, API keys, or highly classified documents.

**"What if I accidentally let Claude delete something important?"**
If you're inside a git repo (which this student repo is), you can always recover with `git checkout -- filename` to restore any file to its last committed state. Outside of git, Claude always asks before deleting — read the permission prompt carefully before approving.

### About the second brain

**"Can I use this with files that aren't text? Like PDFs, images, spreadsheets?"**
Claude Code can read PDFs, images (screenshots, photos of whiteboards), CSV files, and most text-based formats. It can't directly open Excel (.xlsx) or PowerPoint (.pptx) files — but you can export them as CSV or PDF first, or just paste the content.

**"I already use Notion / Obsidian / Google Docs for notes. Why would I switch?"**
You don't have to switch. The second brain works alongside your existing tools. The key difference: Claude Code can read and search local files instantly without an integration. You can export from Notion/Obsidian into your second brain's inbox folder, or just keep using those tools and use the second brain for things you want Claude to have direct access to. Use whatever captures fastest — the inbox sorts it out.

**"How is this different from just using ChatGPT with file uploads?"**
Three big differences. First, Claude Code reads your entire folder structure — not one file at a time. It can search across 20 files and connect dots. Second, CLAUDE.md gives persistent context — Claude knows who you are every session without re-explaining. Third, Claude Code can create, move, and organize files directly on your machine — it's not just answering questions, it's doing work.

### About the terminal

**"I accidentally closed the terminal. Is my work lost?"**
No. Everything Claude created — your CLAUDE.md, your second brain folders, your files — is saved on your machine. Just open the terminal again, navigate to the same folder (`cd student_repo_build01_second_brain`), and type `claude`. Your CLAUDE.md loads automatically. You're right back where you were.

**"Claude seems stuck or is taking forever. What do I do?"**
If Claude has been spinning for more than 2 minutes, press `Ctrl+C` to stop it, then try again with a simpler prompt. If you're asking it to read many files at once, that's normal — give it a minute. If it's stuck in a loop (repeating itself), type `/clear` to reset the conversation and start fresh.

**"I typed something wrong and now the terminal looks broken."**
If you see something weird (strange characters, no prompt): press `Ctrl+C` first. If that doesn't help, type `reset` and press Enter. If you're accidentally in a text editor (vim), type `:q!` and press Enter to escape. Nothing is broken — the terminal just looks confusing sometimes.

### About what comes next

**"Can I use this second brain for my team, not just for myself?"**
Absolutely. A shared second brain in a team repo — with a CLAUDE.md that describes team context, project status, and conventions — is extremely powerful. Every team member gets personalized output from the same shared knowledge base. That's an advanced use case we'll touch on later.

**"How do I keep this going after the bootcamp?"**
The student handbook has a "Take It Home" section with exact steps: set up your global CLAUDE.md at `~/.claude/CLAUDE.md`, move your second brain to `~/my-second-brain/`, and start using it Monday. The daily habit is simple — dump things into inbox, run a sorting prompt once a day, ask Claude what to focus on. Five minutes a day is enough to keep it alive.
