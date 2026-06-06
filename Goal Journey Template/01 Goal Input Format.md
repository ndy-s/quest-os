# Goal Input Format

> Fill this out before running the Master Prompt. The more specific you are, the better Claude's output.

---

## The Format

```
GOAL: [One sentence describing what you want to achieve]

DEADLINE: [Target date or timeframe, be realistic]

CURRENT STATE: [Where you are now: role, skills, situation, resources]

MOTIVATION: [Why this matters to you, honest not polished]

CORE SKILL or ACTIVITY: [The main thing you'll need to practice repeatedly, if any]
  Example: coding problems, writing, language speaking, sales calls, workouts

TRACKING UNIT: [What you'll track per session: problems solved, pages read, reps done, etc.]

REVIEW SYSTEM: [Do you want spaced repetition? Or just linear progress?]
  Options: "spaced repetition" / "linear" / "not applicable"

PHASES: [How many phases do you want? 2–4 is ideal. Or write "auto" to let Claude decide]

TARGET LIST: [List 5–10 specific targets: companies, clients, schools, publishers, etc.]

VISIBILITY: [How do you want to show progress publicly? LinkedIn / blog / GitHub / none]

BUDGET:
  - Time per week: [hours]
  - Money available: [amount or "none"]

EXTRA CONTEXT: [Anything else Claude should know: constraints, past attempts, preferences]
```

---

## Example: Job Search

```
GOAL: Land a mid-level SWE role in Singapore's fintech sector

DEADLINE: October 2026 (5 months from now)

CURRENT STATE: Backend engineer at a financial company in Jakarta. 3 years experience.
Strong in Java/Spring. Weak in DSA and system design.

MOTIVATION: Better salary, career growth, and a new environment. Jakarta's ceiling is low.

CORE SKILL: DSA problem solving (LeetCode-style)

TRACKING UNIT: Problems solved per day

REVIEW SYSTEM: Spaced repetition (+2, +7, +30 days)

PHASES: 3 (Foundation > Ramp Up > Full Push)

TARGET LIST: Grab, Sea, Wise, Stripe, Shopee, DBS Tech, Nium, Aspire, Fazz, GoTo

VISIBILITY: LinkedIn (2 posts/week), technical blog (monthly)

BUDGET:
  - Time per week: 15 hours
  - Money available: SGD 500 for courses/tools

EXTRA CONTEXT: Already have 4 strong STAR stories. Fintech domain is a differentiator.
```

---

## Example: Learning a Language

```
GOAL: Reach conversational fluency in Japanese (JLPT N3 level)

DEADLINE: 12 months from now

CURRENT STATE: Complete beginner. Learned hiragana/katakana once but forgot.

MOTIVATION: Want to work in Japan eventually. Also love anime.

CORE SKILL: Vocabulary recall and listening comprehension

TRACKING UNIT: Vocabulary cards reviewed + listening minutes per day

REVIEW SYSTEM: Spaced repetition (Anki-based: +1, +3, +7, +30 days)

PHASES: 3 (Kana & basics > Grammar & vocabulary > Immersion & speaking)

TARGET LIST: N5 exam, N4 exam, N3 exam, 3 conversation partners, 1 Japan trip

VISIBILITY: none

BUDGET:
  - Time per week: 7 hours
  - Money available: $50/month for apps and classes

EXTRA CONTEXT: I learn best by doing, not by reading textbooks. Gamified systems work well for me.
```

---

## Example: Freelance Business

```
GOAL: Earn $2,000/month from freelance web development within 6 months

DEADLINE: 6 months from today

CURRENT STATE: Full-time dev with 2 years experience. Never done freelance before.
Good at React and Node.js.

MOTIVATION: Supplement income. Build toward full-time independence.

CORE SKILL: Sales (writing proposals, closing clients)

TRACKING UNIT: Proposals sent per week

REVIEW SYSTEM: linear

PHASES: 2 (Setup & First Clients > Scale)

TARGET LIST: Upwork, Toptal, local SMEs, startup communities, LinkedIn outreach

VISIBILITY: LinkedIn (weekly posts), GitHub portfolio

BUDGET:
  - Time per week: 10 hours
  - Money available: $100 for tools/subscriptions

EXTRA CONTEXT: I'm shy about cold outreach. The system should push me to do it anyway.
```

---

## Tips for Writing a Good Input

- Be honest about your current state. Don't inflate it.
- "Motivation" matters more than you think. Claude uses it to set the right tone throughout the files.
- If you're not sure about phases, write `auto` and Claude will decide based on your timeline.
- The more specific your Target List, the more useful the files will be.
- If there's no core skill to track (e.g. a research goal), write "not applicable" for Core Skill and Tracking Unit.
