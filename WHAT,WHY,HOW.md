Here is the complete tech stack we have used across both of your repositories, broken down exactly how you asked.

### 🧱 The Full Tech Stack (Start to End)

| Name | What is it? | Why did we use it? | How did we use it? |
| :--- | :--- | :--- | :--- |
| **Git** | Version control system. | To track changes and save our progress safely. | Used terminal commands (`git add`, `git commit`, `git push`) to save code locally. |
| **GitHub** | Cloud hosting for Git. | To store our code online and make it visible to reviewers/recruiters. | Created remote repositories and pushed our local commits to the cloud. |
| **SQLite** | A lightweight, local database. | To test our database schema quickly without needing a server. | Used `sqliteonline.com` and later `vault.db` to test SQL queries and save local data. |
| **PostgreSQL** | A powerful, production-grade database. | To store data securely in the cloud so it works anywhere. | Hosted on Supabase; connected to FastAPI using the `psycopg` driver. |
| **Python** | Programming language. | To write the backend logic, handle API requests, and process data. | Wrote `main.py`, `database.py`, and `test_main.py`. |
| **FastAPI** | A modern Python web framework. | To build the REST API that connects the frontend to the database. | Created endpoints (`GET /ideas`, `POST /ideas`) and ran it with `uvicorn`. |
| **SQLAlchemy** | Python ORM (Object Relational Mapper). | To talk to the database using Python objects instead of raw SQL. | Created `Idea` models and used `db.query()` to fetch and save data. |
| **Pydantic** | Data validation library for Python. | To ensure the frontend sends the right data types (e.g., no blank ideas). | Created `IdeaCreate` models to validate incoming JSON. |
| **Uvicorn** | ASGI web server for Python. | To actually run the FastAPI application on port 8000. | Ran `uvicorn main:app --reload` in the terminal. |
| **CORS Middleware** | Security feature in FastAPI. | To allow the Next.js frontend (port 3000) to talk to FastAPI (port 8000). | Added `CORSMiddleware` to `main.py` and allowed `localhost:3000`. |
| **Mock NLP** | Fake Natural Language Processing. | To auto-generate tags based on keywords without needing an AI API. | Wrote Python `if/else` logic to scan text and append tags like `#health`. |
| **Supabase** | Backend-as-a-Service (BaaS). | To provide a cloud PostgreSQL database and a built-in authentication system. | Connected FastAPI to the Supabase database URI and used Supabase Auth for login. |
| **Row Level Security (RLS)** | A Supabase/Postgres security feature. | To ensure users can only read/write their own data at the database level. | Wrote an SQL policy: `auth.jwt() ->> 'email' = user_id`. |
| **JWT (JSON Web Token)** | A secure "VIP Pass" string. | To prove the user is logged in without sending their password every time. | FastAPI reads the token from the `Authorization` header and extracts the email. |
| **Next.js** | React framework. | To build the frontend UI, handle routing, and make the app fast. | Created the `app/page.tsx` (Login) and `app/dashboard/page.tsx` (Dashboard). |
| **React** | UI library. | To build interactive components like the form and the ideas list. | Used `useState` for form inputs and `useEffect` to fetch data on load. |
| **TypeScript** | JavaScript with types. | To catch bugs before running the code and make the code self-documenting. | Defined `interface Idea` and typed all React states (e.g., `useState<Idea[]>`). |
| **Tailwind CSS** | Utility-first CSS framework. | To make the UI look modern and beautiful without writing custom CSS. | Added classes like `bg-gray-900`, `text-blue-400`, and `rounded-lg` to HTML tags. |
| **Node.js** | JavaScript runtime. | To run the Next.js development server and install frontend packages. | Ran `npm run dev` to start the frontend and installed Supabase client. |
| **NPM** | Node Package Manager. | To install libraries (like React, Supabase, Playwright) into the project. | Ran `npm install @supabase/supabase-js` and `npm run dev`. |
| **Pytest** | Python testing framework. | To write automated tests that prove the backend is secure. | Created `test_main.py` and ran 5 tests to prove User A can't see User B's data. |
| **Playwright** | Browser automation tool. | To write automated E2E tests that click through the UI like a real user. | Created `saucedemo.spec.ts` and ran `npx playwright test --headed`. |
