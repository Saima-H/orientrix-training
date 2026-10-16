# Idea Vault: Complete Topic Roadmap (No Videos Needed)

Here's the full step-by-step topic list. Each topic has: **what to learn**, **why it matters for Idea Vault**, and **what you build with it**. No video links — just the concepts, in the order you need them.

---

## PHASE 0: Setup & Mental Model (Day 1 Morning)

### 0.1 — How the Web Works
- Client vs Server
- Request/Response cycle
- HTTP methods: `GET`, `POST`, `PUT`, `DELETE`
- HTTP status codes: `200`, `201`, `400`, `404`, `500`
- Headers, body, JSON
- What an API actually is

**Build:** Sketch on paper: "User clicks Add Idea → browser sends POST → FastAPI saves to DB → returns JSON → React re-renders." That's your entire app in one diagram.

### 0.2 — Git & GitHub
- `git init`, `git add`, `git commit`, `git status`, `git log`
- Branching: `git branch`, `git checkout`, `git merge`
- Remote: `git remote add`, `git push`, `git pull`
- `.gitignore` (critical — never commit `node_modules` or `.env`)
- Commit message conventions (imperative mood: "Add tag endpoint" not "added stuff")

**Build:** `mkdir idea-vault && cd idea-vault && git init`. Write `README.md`, commit. Write `notes/day1.md`, commit. **This is Deliverable #1 done on Day 1.**

---

## PHASE 1: Database Design (Day 1 Afternoon – Day 2)

### 1.1 — Relational Database Concepts
- Tables, rows, columns
- Primary key vs foreign key
- One-to-many vs many-to-many relationships
- Why we normalize (avoid duplicate data)

### 1.2 — SQL Basics
- `CREATE TABLE` with data types (`INTEGER`, `TEXT`, `TIMESTAMP`, `BOOLEAN`)
- `INSERT INTO`
- `SELECT` with `WHERE`, `ORDER BY`, `LIMIT`
- `UPDATE`, `DELETE`
- `PRIMARY KEY`, `FOREIGN KEY`, `NOT NULL`, `UNIQUE`

### 1.3 — SQL Intermediate
- `GROUP BY` + aggregate functions (`COUNT`, `AVG`, `MAX`)
- `JOIN` types: `INNER JOIN`, `LEFT JOIN`
- Many-to-many via a **junction table** (`idea_tags`)
- Subqueries (basic)

### 1.4 — Schema Design for Idea Vault
Design these tables:
- `users` (id, username, email, created_at)
- `ideas` (id, user_id, content, url, created_at)
- `tags` (id, name)
- `idea_tags` (idea_id, tag_id) ← junction table

**Build:** Write `sql-practice.sql` with 20 queries. **This is Deliverable #2 done.** Include at least 3 JOINs:
1. Get all ideas with their tags
2. Get all ideas by a specific user
3. Count how many ideas each tag has

**Also write:** `questions.md` with 5 things that confused you. **Deliverable #3 done.**

**Commit Day 2.** That's 2 of your 3 required commits.

---

## PHASE 2: Python Fundamentals (Day 3)

### 2.1 — Python Basics
- Variables, data types (`str`, `int`, `float`, `bool`, `list`, `dict`)
- `if/elif/else`, `for`, `while`
- Functions: `def`, parameters, return values
- String methods: `.split()`, `.join()`, `.strip()`, f-strings

### 2.2 — Python Intermediate
- Lists & dicts (comprehensions: `[x*2 for x in nums]`)
- Classes: `__init__`, `self`, methods
- Modules: `import`, `from x import y`
- Virtual environments: `python -m venv venv`, `pip install`
- `requirements.txt`

### 2.3 — Python for APIs
- `requests` library: `requests.get()`, `requests.post()`
- JSON handling: `json.loads()`, `json.dumps()`
- Error handling: `try/except/finally`
- Environment variables: `os.getenv()`, `.env` files
- Type hints: `def get_idea(id: int) -> dict:`

**Build:** 3 tiny scripts in `scripts/` folder:
1. `fetch_api.py` — hits `https://jsonplaceholder.typicode.com/posts/1` and prints the title
2. `tag_generator.py` — takes a string, returns 2-3 fake tags (mock NLP)
3. `read_json.py` — reads a JSON file of ideas and prints them

**Commit Day 3.** **All 3 required commits done.**

---

## PHASE 3: FastAPI Backend (Day 4)

### 3.1 — FastAPI Basics
- What is ASGI vs WSGI (one sentence: async-capable)
- `uvicorn` as the server
- `@app.get()`, `@app.post()`, `@app.put()`, `@app.delete()`
- Path params: `/ideas/{id}`
- Query params: `/ideas?tag=python`
- Request body with Pydantic models
- Response models
- Auto-generated docs at `/docs`

### 3.2 — Pydantic
- `BaseModel` classes
- Field validation
- Nested models
- `Field(...)` for required/optional

### 3.3 — Database Integration
- SQLite for simplicity (`sqlite3` or SQLAlchemy)
- ORM basics with SQLAlchemy (or use raw SQL if you prefer)
- Session management
- Migrations (optional — just use `create_all()` for now)

### 3.4 — CORS
- What CORS is (browser security feature)
- Why your Next.js app on `:3000` can't talk to FastAPI on `:8000` without it
- `CORSMiddleware` setup
- **This WILL break. Log it in AI_JOURNAL.**

### 3.5 — The Smart Endpoint
- Two options:
  - **Mock NLP:** keyword extraction with `re` or a simple word list
  - **Real LLM:** call OpenAI/Anthropic API with `requests`
- Endpoint: `POST /ideas/{id}/generate-tags` → returns 2-3 tags

**Build:** FastAPI app with these endpoints:
- `GET /ideas` — list all
- `POST /ideas` — create new
- `GET /ideas/{id}` — get one
- `DELETE /ideas/{id}` — delete
- `POST /ideas/{id}/generate-tags` — the smart one

**Test each one** in the `/docs` UI before moving on.

**Log in `AI_JOURNAL.md`:** Every prompt you gave Cursor/Windsurf, what worked, what failed, what you had to fix.

**Commit after each working endpoint.** That's 5+ commits on Day 4 alone.

---

## PHASE 4: Next.js Frontend (Day 5)

### 4.1 — React Fundamentals
- Components (function components)
- JSX syntax
- Props
- `useState` hook
- `useEffect` hook
- Event handling (`onClick`, `onChange`, `onSubmit`)
- Conditional rendering
- Lists and `key` prop

### 4.2 — Next.js Specifics
- App Router vs Pages Router (use App Router)
- File-based routing (`app/page.tsx`, `app/ideas/page.tsx`)
- `"use client"` directive
- Server components vs client components (just know the difference)
- `fetch` in client components

### 4.3 — Talking to Your API
- `fetch()` with `POST`, headers, JSON body
- `async/await`
- Loading states
- Error states
- CORS errors (you'll see them here)

### 4.4 — UI Basics
- Tailwind CSS (fastest way to make it not look ugly)
- Basic layout: header, main, cards
- Forms with controlled inputs
- Tag chips / badges

**Build:** Next.js app with:
- `app/page.tsx` — dashboard listing all ideas
- `app/components/IdeaCard.tsx` — one idea with its tags
- `app/components/AddIdeaForm.tsx` — form to POST a new idea
- `app/components/TagFilter.tsx` — filter ideas by tag

**Commit after each component works.**

**Log in `AI_JOURNAL.md`:** The CORS blunder, the "why is my state not updating" bug, the "AI used `useEffect` wrong" moment.

---

## PHASE 5: Testing (Day 6)

### 5.1 — Manual Testing Fundamentals
- SDLC (Software Development Life Cycle)
- STLC (Software Testing Life Cycle)
- Test case vs test scenario
- Bug life cycle: New → Assigned → Open → Fixed → Retest → Closed
- Severity vs Priority (with examples)

### 5.2 — Writing Test Cases
- Structure: ID, Title, Steps, Expected Result, Actual Result, Priority
- Positive vs negative tests
- Boundary values (empty input, max length, special chars)

### 5.3 — API Testing with Postman
- Creating a collection
- `GET`, `POST`, `PUT`, `DELETE` requests
- Headers (`Content-Type: application/json`)
- Body (raw JSON)
- Tests tab: `pm.response.to.have.status(200)`
- Checking response fields: `pm.expect(jsonData.title).to.eql("...")`
- Environment variables (base URL)
- Exporting collection as JSON

### 5.4 — Bug Reports
- Title (specific: "POST /ideas returns 500 when content is empty")
- Steps to reproduce (numbered, exact)
- Expected vs Actual
- Severity (Critical/High/Medium/Low)
- Priority (P0/P1/P2/P3)
- Screenshot

**Build:**
- `test-cases.md` — 30 test cases for Idea Vault (login not needed if no auth; focus on create/read/delete/filter/tag generation)
- `bug-reports.md` — 5 real bugs from your own app (you'll find them)
- Postman collection exported as JSON with 10+ requests

**Commit everything.** **All deliverables done.**

---

## PHASE 6: Documentation & Polish (Day 6 Evening)

### 6.1 — AI_JOURNAL.md (Your Most Important File)
Structure:
```
## Tool Used
Cursor / Windsurf / Claude Code

## Prompt Log
### Prompt 1: "Create FastAPI endpoint for POST /ideas"
- Result: Worked, but forgot Pydantic model
- Fix: Added IdeaCreate(BaseModel)

### Prompt 2: "Connect Next.js to FastAPI"
- Result: CORS error
- Fix: Added CORSMiddleware with allow_origins=["http://localhost:3000"]

## AI Hallucinations
- AI used `useEffect` for form submission (wrong — should be `onSubmit`)
- AI imported `requests` in FastAPI (wrong — should use `httpx` for async)

## Lessons Learned
- Always specify the exact framework version
- AI doesn't know your file structure — tell it
```

### 6.2 — README.md
- What the app does
- Setup instructions (backend + frontend)
- API endpoints list
- Screenshots

### 6.3 — Final Commit
- `git add . && git commit -m "Complete Idea Vault with tests and docs"`
- `git push`

---

## Final Deliverables Checklist

| Deliverable | Where | Done? |
|-------------|-------|-------|
| 3 days of notes, committed on 3 days | `notes/day1.md`, `day2.md`, `day3.md` | ☐ |
| `sql-practice.sql` with 20 queries | `sql-practice.sql` | ☐ |
| `questions.md` with 5 confusions | `questions.md` | ☐ |
| Working FastAPI backend | `backend/` | ☐ |
| Working Next.js frontend | `frontend/` | ☐ |
| `AI_JOURNAL.md` | root | ☐ |
| Iterative commits (10+) | `git log` | ☐ |
| `test-cases.md` (30 cases) | `qa/test-cases.md` | ☐ |
| `bug-reports.md` (5 bugs) | `qa/bug-reports.md` | ☐ |
| Postman collection JSON | `qa/idea-vault.postman_collection.json` | ☐ |

---

## Time Estimate Per Phase

| Phase | Topic | Time |
|-------|-------|------|
| 0 | Setup + Git | 2 hrs |
| 1 | SQL + schema | 4 hrs |
| 2 | Python | 4 hrs |
| 3 | FastAPI | 6 hrs |
| 4 | Next.js | 6 hrs |
| 5 | Testing | 4 hrs |
| 6 | Docs | 2 hrs |
| **Total** | | **~28 hrs** |

Spread over 6 days = **~5 hrs/day**. Very doable.

---

## The One Thing to Remember

**You don't need to master any topic before moving to the next.** You need to know *just enough* to build the next piece. The app is the curriculum. The topics above are just the vocabulary.

Want me to go deep on any specific phase — like writing the actual FastAPI code structure, or the SQL schema with all 20 queries?
