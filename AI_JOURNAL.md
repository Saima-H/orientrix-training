#IDEA VAULT:
The "Phase 1: Learn SQL → Phase 2: Build SQL" structure I gave you is **artificial**. It's how schools teach. It's not how builders work.

**Real builders do this:**

> "I need to store ideas. Hmm, how do I store data? Oh, databases. Let me learn *just enough* SQL to create this one table. Done. Now I need to fetch it back. Oh, `SELECT`. Let me learn that. Done."

That's it. That's the whole loop. **Learn → Build → Hit wall → Learn → Build → Hit wall → Learn.**

You don't "dedicate time to learn SQL." You **hit a point where you need SQL**, and you learn the 10% of SQL that solves *your* problem. Then you move on. If you need more later, you learn more later.

---

## Why the "Dedicated Learning Time" Model Fails

| Dedicated Learning | Just-in-Time Learning |
|--------------------|-----------------------|
| Watch 4-hour SQL course | Learn `CREATE TABLE` + `INSERT` in 20 min |
| Forget 80% by the time you build | Use 100% of what you learned immediately |
| No context for *why* things exist | Every concept has a reason (your app needs it) |
| Motivation drops (no output) | Motivation spikes (app grows daily) |
| Tutorial hell | Ship hell (the good kind) |

**You already knew this.** That's why you said *"if I don't organise my learning watching videos I'm not gaining much."* Trust that instinct.

---

## The Correct Model: Build-First, Learn-When-Stuck

Here's how your 6 days actually look:

### Day 1 — "I want to build an idea vault"
- Open Cursor. Start a project.
- **Stuck:** "How do I save ideas?"
- **Learn:** What a database is, `CREATE TABLE`, `INSERT`, `SELECT`. 30 minutes, not 4 hours.
- **Build:** Create `ideas` table, insert one idea, read it back.
- **Stuck:** "How do I write this in a file?"
- **Learn:** `sql-practice.sql`, how to run it.
- **Build:** Save your queries.
- **Stuck:** "How do I not lose this work?"
- **Learn:** `git init`, `git add`, `git commit`. 15 minutes.
- **Build:** Commit.
- **Done for the day.** You learned SQL, Git, and databases — *by building*.

### Day 2 — "I want tags on my ideas"
- **Stuck:** "One idea can have many tags, one tag can belong to many ideas. How?"
- **Learn:** Many-to-many relationship, junction table.
- **Build:** `tags` table + `idea_tags` table. Write JOIN queries.
- **Stuck:** "My queries are getting complex."
- **Learn:** `INNER JOIN`, `GROUP BY`. 20 minutes.
- **Build:** Finish the 20 queries.
- **Commit.**
- **Done.** You learned intermediate SQL — *by building*.

### Day 3 — "I want this to be an actual API"
- **Stuck:** "How do I make an API in Python?"
- **Learn:** FastAPI basics — `@app.get()`, `@app.post()`. 1 hour.
- **Build:** `GET /ideas`, `POST /ideas`.
- **Stuck:** "Python syntax is weird."
- **Learn:** Just the syntax you need — functions, dicts, f-strings.
- **Build:** Finish the endpoints.
- **Commit.**
- **Done.** You learned Python + FastAPI — *by building*.

### Day 4 — "The smart tag endpoint"
- **Stuck:** "How do I generate tags?"
- **Learn:** String manipulation, or how to call an LLM API. 30 minutes.
- **Build:** `POST /ideas/{id}/generate-tags`.
- **Stuck:** "I want a UI now."
- **Learn:** React basics — components, `useState`. 1 hour.
- **Build:** A basic dashboard.
- **Commit.**
- **Done.**

### Day 5 — "Make it look good + filter"
- **Stuck:** "How do I filter by tag?"
- **Learn:** React state, conditional rendering. 30 minutes.
- **Build:** Filter component.
- **Stuck:** "CORS error!"
- **Learn:** What CORS is, `CORSMiddleware`. 20 minutes.
- **Build:** Fix it. **Log it in AI_JOURNAL.**
- **Commit.**

### Day 6 — "Prove it works"
- **Stuck:** "How do I test an API?"
- **Learn:** Postman basics. 1 hour.
- **Build:** 10+ requests.
- **Stuck:** "How do I write test cases?"
- **Learn:** Test case structure, severity vs priority. 30 minutes.
- **Build:** `test-cases.md`, `bug-reports.md`.
- **Commit. Push. Done.**

---

## The Rule: Learn Only When You Have a Specific Problem

**Bad question:** "What should I learn today?"
**Good question:** "What do I want to build today, and what's blocking me?"

The block tells you what to learn. Nothing else.

---

## What About the Deliverables? (notes, questions.md, etc.)

Those still exist. But now they're **byproducts of building**, not separate tasks:

| Deliverable | How it happens naturally |
|-------------|--------------------------|
| `notes/day1.md` | You write down what you learned when you got unstuck. 5 minutes at end of day. |
| `notes/day2.md` | Same. |
| `notes/day3.md` | Same. |
| `sql-practice.sql` | It *is* your app's schema + the queries you needed. |
| `questions.md` | Every time you got stuck and figured it out, you note it. Confusions that remain → the file. |
| `AI_JOURNAL.md` | You write it *as* you prompt AI, not after. |
| `test-cases.md` | You write these *while* testing your app. |
| `bug-reports.md` | You find bugs *while* using your app. |

**None of these require dedicated time.** They're artifacts of the build.

---

## The One Exception: When You *Should* Dedicate Time

There are exactly **two** cases where dedicated learning beats just-in-time:

1. **Fundamentals that unlock everything else.** Example: understanding HTTP methods before you touch FastAPI. 30 minutes of dedicated learning saves you 5 hours of confusion.

2. **When you're stuck for more than 30 minutes.** If you've been debugging for 30+ minutes and AI isn't helping, *stop building* and *learn the concept*. The block is a knowledge gap, not a bug.

Everything else? **Learn while building.**

---

## Your Actual Daily Loop

```
1. Pick one feature for today
2. Start building it with AI (Cursor/Windsurf)
3. Hit a wall → ask AI or search the concept → learn just enough
4. Build past the wall
5. Commit
6. Write 3-5 lines in notes/ai_journal
7. Repeat until day ends
```

That's it. That's the whole method.

