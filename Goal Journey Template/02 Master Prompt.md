# Master Prompt

> Copy everything inside the code block below. Paste it into a new Claude conversation. Fill in your goal where it says `[PASTE YOUR GOAL INPUT HERE]`.

---

````
You are helping me build a complete goal journey system inside my Obsidian vault.

I'll give you my goal in a structured format. Your job is to generate a full set of Obsidian files, one by one, that I can paste or save into a new folder called `[JOURNEY FOLDER NAME] Journey/`.

---

## My Goal Input

[PASTE YOUR GOAL INPUT HERE]

---

## What to Generate

Generate the following files, in order. For each file, output the full markdown content. Label each one clearly so I know which file it is.

### File 1 — `00 MOC.md`
Map of Content. Include:
- A one-line description of the goal and target date
- A table listing all 9+ files with a one-line description of each
- A "DSA System" section (or equivalent tracking system section) with paths to the tracker and context files
- A "Current Phase" checklist showing all phases
- Instructions on how to start a daily quest (just say: open Claude, say "daily quest")

### File 2 — `01 Context & Why.md`
Why this goal is worth pursuing. Include:
- Current opportunity or market context (be specific, research-informed)
- What AI or automation is doing to this space (if relevant)
- The person's specific strengths that fit this goal (inferred from their input)
- A clear verdict: is this worth doing?

### File 3 — `02 Strategy.md`
The full preparation or execution strategy. Include:
- All major areas that need work (e.g. for a job search: DSA, system design, behavioral, English)
- Priority level for each area (High / Medium / Low)
- Best resources for each
- A suggested weekly schedule that fits their time budget

### File 4 — `03 Skill Strategy.md`
The system for the core repeatable skill. If no core skill, skip this and note it.
Include:
- Step-by-step process for one session (how to approach a new problem/chapter/rep)
- Daily time split between new work and review
- Review schedule (if spaced repetition) or progress logic (if linear)
- Phase-by-phase focus
- Resources

### File 5 — `04 Timeline & Phases.md`
Full phase breakdown. For each phase include:
- Duration and motto
- Specific tasks (not vague: mention actual topics, targets, actions)
- A readiness gate (checklist of what must be true before moving to the next phase)
- End with an Offer / Outcome section describing what success looks like

### File 6 — `05 Tracker.md`
A tracker for the core unit they're tracking. Include:
- A table with appropriate columns for their goal type
- A stats block (Total / Completed / Pending Review or equivalent)
- Clear column schema documentation below the table
- Seed the table with 5–10 example rows using realistic starting data so it's not empty

For a skill-based goal using spaced repetition, use this column schema:
`Item | Difficulty | Status | Solved/Started | Review 1 Date | R1 Done | Review 2 Date | R2 Done | Review 3 Date | R3 Done`

For a linear goal, use:
`Item | Category | Status | Started | Completed | Notes`

### File 7 — `06 Visibility & Branding.md`
How to show progress publicly. Include:
- Platform strategy (based on their input)
- Content ideas and posting cadence
- Personal brand narrative (2–3 sentences they could use on LinkedIn)
- Milestones to announce publicly

### File 8 — `07 Target List.md`
Specific targets with context. Include:
- A tiered table (Tier 1 / 2 / 3 or equivalent) of their targets
- A one-line note on each: what makes it a good fit, what to watch out for
- A pitch narrative: 2–3 sentences they can use to introduce themselves to any target

### File 9 — `08 Budget & Resources.md`
Time and money plan. Include:
- Weekly time breakdown by activity
- One-time vs recurring costs
- Free alternatives where possible
- A "minimum viable" version if budget is tight

### File 10 — `09 Key Decisions.md`
Settled decisions. Include:
- 3–5 decisions that are relevant to this goal and commonly second-guessed
- For each: the question, the decision, and a one-line rationale
- A note at the top: "These are settled. Don't revisit them weekly."

### File 11 — `[Skill or Activity]/Daily Quest Context.md`
The context file that Claude reads every time to generate daily quests. This is the most important file.

Include ALL of the following sections:

**Vault Paths:** table showing where the tracker and daily quest notes live

**Quest Types:** table of quest tags and what they mean. Must include at minimum:
- `review` — spaced repetition review of something already done
- `new` — new item to tackle today
- `system` / `deep` — strategic or deep work (e.g. reading, design, research)
- `behavioral` / `reflection` — soft skills, storytelling, or reflection

**Review Schedule:** the spaced repetition or progress logic (if applicable)

**How to Pick Quests:** specific rules for how to select:
- How many review items (and how to pick the most overdue)
- How to pick the next new item (in order, random, by priority?)
- What the system/deep quest should be today
- What the reflection/behavioral quest should be (e.g. rotate through a list)

**Daily Quest Note Format:** full markdown template for a quest note, including:
- Frontmatter with date, phase, type, tracker_updated
- Quest checklist with appropriate emoji and tags
- Session Notes section (what went well / what was hard / mistakes)
- Review Log table (if applicable)
- Claude Evaluation section

**Submit Quest Instructions:** step-by-step logic for when the user says "submit quest":
1. Idempotency check (if tracker_updated: true, stop)
2. Update the tracker (what to change for each checked quest type)
3. Claude Evaluation (scoring rubric, tone, what to write)
4. Mark tracker_updated: true

**Tracker Column Schema:** exact column names and meanings (so Claude knows what to update)

**Phase Logic:** date ranges for each phase

---

## Output Rules

- Write full, production-ready markdown. No placeholders like "[insert content here]"
- Be specific: use real topic names, real resource names, real timelines
- Tone: direct, honest, like a good coach. Not motivational-poster style.
- Do not use bullet points where prose works better
- Each file should be self-contained. Someone reading just that file should understand it.
- After all files are generated, tell me: "All files ready. Create a folder called `[name] Journey/` and save each file inside it. Then say 'daily quest' to start."

---

## Folder Name

Name the journey folder after the main goal. Examples:
- `FAANG SWE Journey`
- `Japanese Fluency Journey`
- `Freelance Dev Journey`
- `GMAT Prep Journey`

Use the format: `[Short Goal Name] Journey/`
````

---

## After You Get the Files

1. In Obsidian, create a new folder: `[Your Journey Name] Journey/`
2. Inside it, create a subfolder for the skill tracker (e.g. `DSA/` or `Vocab/` or `Writing/`)
3. Save each generated file to the right path
4. Open Claude and say **"daily quest"** — it will read your context file and generate today's quests automatically

---

## Customizing the Prompt

Before you paste, you may want to adjust:

- **Number of review quests per day:** default is 2, change it in the "How to Pick Quests" section after generation
- **Quest types:** if your goal has no behavioral component, remove that quest type from the context file
- **Tracker schema:** if your tracking unit is unusual (e.g. "client calls"), edit the tracker columns after generation
- **Phase count:** if you wrote "auto", Claude will decide; you can always edit the phases file afterward

---

## Re-running the Prompt

If you want to build a second journey (e.g. you finished your job search and now want a fitness goal), just fill in a new goal input and run the same prompt again. Each journey lives in its own folder and is completely independent.
