# Sql &DB
DBMS PERFORMS CRUD ON DB


<img width="419" height="182" alt="image" src="https://github.com/user-attachments/assets/0dd7f3ce-76da-48c9-a591-2d1290c836d5" />

<img width="290" height="145" alt="image" src="https://github.com/user-attachments/assets/99efbe74-7acf-4ea8-9f66-d0125bde88ca" />


┌─────────────────────────────────────────────────────────────────────────────┐
│                    PYTHON MASTER FLOWCHART                                   │
│                    Noob ─────────────────────────────────► Pro                │
└─────────────────────────────────────────────────────────────────────────────┘

                            ┌──────────────┐
                            │   START      │
                            └──────┬───────┘
                                   │
   ┌───────────────────────────────┼───────────────────────────────┐
   │                               │                               │
   ▼                               ▼                               ▼
┌──────────┐              ┌────────────────┐              ┌──────────────┐
│  DATA    │              │  CONTROL FLOW  │              │  STRUCTURE   │
└────┬─────┘              └───────┬────────┘              └──────┬───────┘
     │                            │                              │
     ├─ Strings                   ├─ if/elif/else                ├─ Functions
     ├─ Ints/Floats               ├─ and/or/not                  │   • def / return
     ├─ Lists                     ├─ Falsy values                │   • args/kwargs
     ├─ Tuples                    │                              │   • defaults
     ├─ Sets                      ├─ for loops                   │
     └─ Dicts                     │   • break / continue         ├─ Scope (LEGB)
                                  │   • range()                  │   • local
                                  ├─ while loops                 │   • enclosing
                                  │   • infinite + break         │   • global
                                  │                              │   • built-in
                                  │                              │
                                  │                              ├─ Modules
                                  │                              │   • import
                                  │                              │   • from..import
                                  │                              │   • as alias
                                  │                              │   • sys.path
                                  │                              │
                                  │                              └─ Stdlib
                                  │                                  • random
                                  │                                  • math
                                  │                                  • datetime
                                  │                                  • os
                                  │                                  • csv
                                  ▼                                  │
                       ┌──────────────────────┐                      │
                       │  DEBUGGING SKILLS    │                      │
                       │  try/except/finally  │◄─────────────────────┘
                       │  raise               │
                       │  as e                │
                       └──────────┬───────────┘
                                  │
        ┌─────────────────────────┼─────────────────────────┐
        │                         │                         │
        ▼                         ▼                         ▼
  ┌──────────┐            ┌──────────────┐          ┌──────────────┐
  │ FILE I/O │            │  WEB / HTTP  │          │  DATA FORMATS│
  └────┬─────┘            └──────┬───────┘          └──────┬───────┘
       │                         │                         │
       ├─ open()                 ├─ requests.get()         ├─ CSV
       ├─ with (context mgr)     ├─ params / headers       │   • csv.reader
       ├─ 'r'/'w'/'a'/'rb'/'wb'  ├─ POST data/json         │   • DictReader
       ├─ read/readline/         ├─ r.text / r.json()      │   • DictWriter
       │   readlines             ├─ status_code / ok       │
       ├─ tell / seek            ├─ timeout / auth         ├─ JSON
       ├─ write                  ├─ Session                │   • json.loads
       └─ copy (chunks)          └─ stream / download      │   • json.dumps
                                                           │
                                                           └─ HTML output
                                                               (f-strings)

                                  │
                                  ▼
                       ┌────────────────────────┐
                       │   OS & FILESYSTEM      │
                       │   • os.getcwd/chdir    │
                       │   • listdir/mkdir      │
                       │   • rename/remove      │
                       │   • walk               │
                       │   • environ            │
                       │   • path.join/exists   │
                       └───────────┬────────────┘
                                   │
                                   ▼
                       ┌────────────────────────┐
                       │   AUTOMATION SCRIPTS   │
                       │   • batch rename       │
                       │   • CSV → HTML         │
                       │   • download images    │
                       │   • parse files        │
                       └───────────┬────────────┘
                                   │
                                   ▼
                       ┌────────────────────────┐
                       │   QUALITY & SAFETY     │
                       │   • Unit tests         │
                       │   • Mocking            │
                       │   • try/except         │
                       │   • assert*            │
                       └───────────┬────────────┘
                                   │
                                   ▼
                       ┌────────────────────────┐
                       │   ENVIRONMENTS         │
                       │   • venv (built-in)    │
                       │   • pipenv (combined)  │
                       │   • requirements.txt   │
                       │   • Pipfile / .lock    │
                       │   • .env secrets       │
                       └───────────┬────────────┘
                                   │
                                   ▼
                       ┌────────────────────────┐
                       │   COMMON MISTAKES      │
                       │   • tabs vs spaces     │
                       │   • shadowing names    │
                       │   • mutable defaults   │
                       │   • iterator exhausted │
                       │   • wildcard imports   │
                       └───────────┬────────────┘
                                   │
                                   ▼
                            ┌──────────┐
                            │   PRO    │
                            └──────────┘


┌─────────────────────────────────────────────────────────────────────────────┐
│  DEBUGGING DECISION TREE                                                    │
└─────────────────────────────────────────────────────────────────────────────┘

    Error message?
         │
         ├─► IndentationError ────► Check tabs vs spaces; use editor setting
         │
         ├─► SyntaxError ─────────► Check line before; missing colon/paren
         │
         ├─► NameError ───────────► Variable out of scope / typo / check LEGB
         │
         ├─► TypeError ───────────► Wrong type / variable shadowing function
         │
         ├─► ValueError ──────────► Right type wrong value (int('abc'))
         │
         ├─► KeyError ────────────► Dict key missing → use .get()
         │
         ├─► IndexError ──────────► List index OOR → check len()
         │
         ├─► AttributeError ──────► Method doesn't exist → dir(obj)
         │
         ├─► ImportError ─────────► sys.path / venv / shadowing file
         │
         ├─► FileNotFoundError ───► Check path / cwd / typo
         │
         └─► ZeroDivisionError ───► Guard with if y != 0



