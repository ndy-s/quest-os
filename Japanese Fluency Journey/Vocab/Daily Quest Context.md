# Daily Quest Context — Japanese Fluency

> This file is read by Claude every time you say "daily quest". Do not delete sections — Claude needs all of them.

---

## Vault Paths

| File | Path |
|---|---|
| Vocab Tracker | `Japanese Fluency Journey/05 Tracker.md` |
| Daily Quest Notes | `Japanese Fluency Journey/Vocab/Quests/YYYY-MM-DD.md` |
| Context File (this file) | `Japanese Fluency Journey/Vocab/Daily Quest Context.md` |
| Strategy | `Japanese Fluency Journey/02 Strategy.md` |
| Timeline | `Japanese Fluency Journey/04 Timeline & Phases.md` |

---

## Quest Types

| Tag | Type | What it means |
|---|---|---|
| `review` | Review | Spaced repetition review of a vocab word or grammar point already in the tracker |
| `new` | New item | Learn a new vocab word or grammar point and add it to the tracker |
| `listening` | Listening | Watch a Comprehensible Japanese video or listen to a podcast episode |
| `grammar` | Grammar deep work | Study a new grammar point in Genki or Bunpro, write 2 example sentences |
| `speaking` | Speaking | iTalki lesson, HelloTalk exchange, or Claude conversation practice |
| `reading` | Reading | Satori Reader session or reading any Japanese text |
| `reflection` | Reflection | Review your progress, update phase status, note what's hard |

---

## Review Schedule

| Review | Interval from start date |
|---|---|
| Review 1 | +1 day |
| Review 2 | +3 days |
| Review 3 | +7 days |
| Review 4 (mastery check) | +30 days |

An item is "overdue" if today's date is past its next review date and the review is not marked ✅.

---

## How to Pick Quests

**Review quests (pick 2–3):**
Look at the tracker. Find items where the next review date is today or earlier and the review column is not ✅. Prioritize the most overdue items first. If more than 5 items are overdue, pick all 5 and skip new items for today.

**New item quest (pick 1):**
Add the next item sequentially from the current Anki deck or Genki chapter. In Phase 1, prioritize kana and N5 vocab. In Phase 2, N4 vocab and grammar. In Phase 3, N3 grammar. If more than 30 Anki reviews are due today, skip new items.

**Listening quest (pick 1):**
In Phase 1: Comprehensible Japanese absolute beginner playlist, next unwatched video.
In Phase 2: Comprehensible Japanese beginner/intermediate playlist.
In Phase 3: anime or J-drama with Japanese subtitles, 20 min minimum.

**Grammar quest (3x per week — Tue, Fri, Sat):**
Current chapter in Genki or current N-level in Bunpro. Write 2 original example sentences after studying the point.

**Reflection quest (once per week, Sunday):**
Review the week: how many items added, how many reviews completed, what felt hard, whether the phase readiness gates are getting closer.

---

## Daily Quest Note Format

```
---
date: YYYY-MM-DD
phase: 1 / 2 / 3
quest_types: [review, new, listening, grammar]
tracker_updated: false
---

# Daily Quest — YYYY-MM-DD

## Quests

- [ ] 🔁 `review` — Recall: ありがとう (arigatou)
- [ ] 🔁 `review` — Recall: は particle usage
- [ ] ✨ `new` — Learn: [next item from deck]
- [ ] 👂 `listening` — Comprehensible Japanese: [episode title or URL]
- [ ] 📖 `grammar` — Study: [grammar point] + write 2 example sentences

## Session Notes

**What went well:**

**What was hard:**

**Mistakes made:**

**Example sentences written today:**
1.
2.

## Review Log

| Item | Recalled? | Notes |
|---|---|---|
| | | |

## Claude Evaluation

[Claude fills this in when you submit]
```

---

## Submit Quest Instructions

When the user says "submit quest", follow these steps exactly:

**Step 1 — Idempotency check:**
Read the frontmatter of today's quest note. If `tracker_updated: true`, stop and say: "This quest was already submitted. Tracker is up to date." Do not make any changes.

**Step 2 — Update the tracker (`05 Tracker.md`):**
For each checked `review` quest: find the item in the tracker. Mark the corresponding review column ✅. Set the next review date if applicable. If all 3 reviews are done, change Status to "Mastered".
For each checked `new` quest: add the new item as a new row in the tracker. Set Started to today. Set Review 1 Date to tomorrow. Set Status to "New".
Update the Stats block at the top: recount Total, Mastered, In Progress, New, and Overdue.

**Step 3 — Claude Evaluation:**
Write a short evaluation (3–5 sentences) in the Claude Evaluation section of the quest note. Include:
- Score: X/5 based on quests completed (5/5 = all done, 3/5 = majority done, etc.)
- One specific observation about what was hard or what to watch for next session
- One encouraging but honest sentence — not cheerleader-style
- If example sentences were written, comment on one (grammar accuracy or natural usage)

**Step 4 — Mark tracker_updated:**
Update the quest note frontmatter: `tracker_updated: true`

---

## Tracker Column Schema

| Column | How to update |
|---|---|
| Item | Full item text including reading and meaning |
| Type | Vocab or Grammar |
| Difficulty | Set by user on first encounter; don't change after |
| Status | New → In Progress (after R1) → Mastered (after R3) |
| Started | Date of first study; never change |
| Review 1 Date | Started + 1 day |
| R1 Done | ✅ when review quest completed |
| Review 2 Date | Started + 3 days |
| R2 Done | ✅ when review quest completed |
| Review 3 Date | Started + 7 days |
| R3 Done | ✅ when review quest completed; set Status to Mastered |

---

## Phase Logic

| Phase | Date Range | Focus |
|---|---|---|
| Phase 1: Kana & Foundations | June 2026 – August 2026 | Kana, N5 vocab, Genki I |
| Phase 2: Grammar & Vocabulary | September 2026 – January 2027 | N4 grammar, Core 2000/6000, listening |
| Phase 3: Immersion & Speaking | February 2027 – June 2027 | N3 grammar, reading, speaking, exam prep |
