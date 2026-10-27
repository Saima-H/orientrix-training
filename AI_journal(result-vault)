Lets start with visualizing how can we make this app ,we will try diifferent iterations of architecture and ultimately compare idea vault and result vault N=and how can i make that
```
flowchart TD
    subgraph Frontend ["Next.js Frontend (TypeScript)"]
        T_Dash["👩‍🏫 Teacher Dashboard<br/>(Upload scripts, edit marks)"]
        S_Dash["🧑‍🎓 Student Portal<br/>(View published results)"]
    end

    subgraph Backend ["FastAPI Backend"]
        Auth["JWT Verification<br/>(Strict Signature Check)"]
        Engine["Marking Engine<br/>(Pure Python Math)"]
        Matcher["Fuzzy Name Matcher<br/>(Suggest Student)"]
        API["API Endpoints<br/>(/marks, /scripts, /students)"]
    end

    subgraph Database ["Supabase PostgreSQL"]
        Users[("Users Table<br/>(Auth managed)")]
        Relational[("Relational Tables<br/>(Students, Papers, Questions, Marks)")]
        Audit[("Audit Log Table<br/>(Immutable Triggers)")]
        RLS{"Row Level Security<br/>(DB-level filter)"}
    end

    T_Dash -->|Login + JWT| Auth
    S_Dash -->|Login + JWT| Auth

    Auth -->|Teacher Role| API
    Auth -->|Student Role| API

    API --> Engine
    API --> Matcher
    
    API --> RLS
    RLS --> Relational
    Relational -.->|On Update| Audit
```
