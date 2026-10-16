# IDEA VAULT:

## The Correct Model: Build-First, Learn-When-Stuck

Here's how your 6 days actually look:

### 1 — "I want to build an idea vault"
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

### 2 — "I want tags on my ideas"
- **Stuck:** "One idea can have many tags, one tag can belong to many ideas. How?"
- **Learn:** Many-to-many relationship, junction table.
- **Build:** `tags` table + `idea_tags` table. Write JOIN queries.
- **Stuck:** "My queries are getting complex."
- **Learn:** `INNER JOIN`, `GROUP BY`. 20 minutes.
- **Build:** Finish the 20 queries.
- **Commit.**
- **Done.** You learned intermediate SQL — *by building*.

###  3 — "I want this to be an actual API"
- **Stuck:** "How do I make an API in Python?"
- **Learn:** FastAPI basics — `@app.get()`, `@app.post()`. 1 hour.
- **Build:** `GET /ideas`, `POST /ideas`.
- **Stuck:** "Python syntax is weird."
- **Learn:** Just the syntax you need — functions, dicts, f-strings.
- **Build:** Finish the endpoints.
- **Commit.**
- **Done.** You learned Python + FastAPI — *by building*.

###  4 — "The smart tag endpoint"
- **Stuck:** "How do I generate tags?"
- **Learn:** String manipulation, or how to call an LLM API. 30 minutes.
- **Build:** `POST /ideas/{id}/generate-tags`.
- **Stuck:** "I want a UI now."
- **Learn:** React basics — components, `useState`. 1 hour.
- **Build:** A basic dashboard.
- **Commit.**
- **Done.**

###  5 — "Make it look good + filter"
- **Stuck:** "How do I filter by tag?"
- **Learn:** React state, conditional rendering. 30 minutes.
- **Build:** Filter component.
- **Stuck:** "CORS error!"
- **Learn:** What CORS is, `CORSMiddleware`. 20 minutes.
- **Build:** Fix it. **Log it in AI_JOURNAL.**
- **Commit.**

###  6 — "Prove it works"
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

# Idea Vault — Flowchart for GitHub

Here are **two versions**. Pick whichever you like. Both are ready to paste into a `README.md` on GitHub (GitHub renders Mermaid diagrams automatically).

---

## Version 1: System Architecture (Recommended)

Shows how the pieces fit together.

```mermaid
flowchart LR
    User([👤 User]) -->|Opens browser| FE[Next.js Frontend<br/>localhost:3000]
    FE -->|HTTP Request<br/>GET / POST / DELETE| BE[FastAPI Backend<br/>localhost:8000]
    BE -->|SQL Query| DB[(SQLite Database<br/>ideas · tags · idea_tags)]
    BE -->|If tags requested| AI{Smart Tag<br/>Generator}
    AI -->|Mock NLP<br/>or| LLM[LLM API<br/>OpenAI / Claude]
    DB -->|Return data| BE
    BE -->|JSON Response| FE
    FE -->|Rendered UI| User
```

---

## Version 2: User Flow (What the user does)

Shows the app from the user's point of view.

```mermaid
flowchart TD
    Start([User opens Idea Vault]) --> ViewAll[See all saved ideas]
    ViewAll --> Choice{What do you want to do?}

    Choice -->|Add idea| AddForm[Fill form:<br/>text or URL]
    AddForm --> GenTags[Click ✨ Generate Tags]
    GenTags --> ShowTags[Show 2-3 suggested tags]
    ShowTags --> Save[Click Save]
    Save --> PostAPI[POST /ideas<br/>to FastAPI]
    PostAPI --> StoreDB[(Save to DB)]
    StoreDB --> ViewAll

    Choice -->|Filter| PickTag[Pick a tag]
    PickTag --> FilterAPI[GET /ideas?tag=xyz]
    FilterAPI --> ShowFiltered[Show filtered list]
    ShowFiltered --> ViewAll

    Choice -->|Delete| PickIdea[Pick an idea]
    PickIdea --> DelAPI[DELETE /ideas/:id]
    DelAPI --> ViewAll
```

---

## Version 3: Simple Linear Flow (Cleanest for README)

If you want something minimal and beginner-friendly.

```mermaid
flowchart LR
    A[👤 User] --> B[Next.js<br/>Frontend]
    B --> C[FastAPI<br/>Backend]
    C --> D[(SQLite<br/>Database)]
    C --> E[🤖 Smart Tag<br/>Generator]
    E --> C
    D --> C
    C --> B
    B --> A
```

---

## How to Use on GitHub

1. Create a file called `README.md` in your `idea-vault/` repo
2. Paste any of the code blocks above (including the ` ```mermaid ` and closing ` ``` `)
3. Commit and push
4. GitHub renders it as a diagram automatically

**Example README snippet:**

````markdown
# 💡 Idea Vault

A personal app to save ideas/links and auto-tag them.

## Architecture

```mermaid
flowchart LR
    User([👤 User]) --> FE[Next.js Frontend]
    FE --> BE[FastAPI Backend]
    BE --> DB[(SQLite Database)]
    BE --> AI[Smart Tag Generator]
    AI --> BE
    DB --> BE
    BE --> FE
```

## How it works
1. User adds an idea
2. Backend saves it + generates tags
3. Frontend displays tagged ideas
````

---

## Which One Should You Use?

| Use Case | Pick |
|----------|------|
| Portfolio / showing off architecture | **Version 1** |
| Explaining how the app works to a user | **Version 2** |
| Clean, minimal README | **Version 3** |
| Best of both worlds | **Version 1 + Version 2** (architecture + user flow) |

**My recommendation:** Use **Version 1** as the main architecture diagram. Add **Version 2** below it as "How the user interacts with it." That's a professional-looking README.

---

Want me to also draw the **database schema** as a Mermaid diagram (showing the `ideas`, `tags`, and `idea_tags` tables with their relationships)? That's the third diagram most good READMEs have.

---
