# Sql &DB
DBMS PERFORMS CRUD ON DB


<img width="419" height="182" alt="image" src="https://github.com/user-attachments/assets/0dd7f3ce-76da-48c9-a591-2d1290c836d5" />

<img width="290" height="145" alt="image" src="https://github.com/user-attachments/assets/99efbe74-7acf-4ea8-9f66-d0125bde88ca" />

# Python 

## finallllllll

| Topic | Info / Explanation / Syntax |
|-------|------------------------------|
| **1. STRINGS** | |
| Create | `'text'`, `"text"`, `'''multi\nline'''` |
| Length | `len(msg)` |
| Index | `msg[0]` first, `msg[-1]` last, `msg[11]` → IndexError |
| Slice | `msg[0:5]` start incl, stop excl. `msg[:5]`, `msg[6:]` |
| `.lower()` / `.upper()` | Return new string |
| `.count(x)` | Count occurrences |
| `.find(x)` | Index or -1 |
| `.replace(a,b)` | Returns NEW string (not in-place) |
| Concat | `'Hi, ' + name` |
| Format | `'{} {}'.format(a, b)` or `f'{a} {b}'` (3.6+) |
| `dir()` / `help()` | Inspect methods |
| **2. NUMBERS** | |
| Types | `int` (whole), `float` (decimal). `type(x)` to check. |
| Operators | `+ - * / // ** %` |
| `/` vs `//` | True division vs floor division |
| Increment | `n += 1`, `n *= 10` |
| Built-ins | `abs()`, `round(x, n)` |
| Comparisons | `== != > < >= <=` |
| Casting | `int('100')`, `float('3.14')`, `str(5)` |
| **3. LISTS / TUPLES / SETS** | |
| List | `[1, 2, 3]` — mutable, ordered |
| Tuple | `(1, 2, 3)` — immutable, ordered |
| Set | `{1, 2, 3}` — mutable, unordered, unique |
| Empty | `[]`, `()`, `set()` (NOT `{}` = dict) |
| Index | `li[0]`, `li[-1]` |
| Slice | `li[0:2]`, `li[:2]`, `li[2:]` |
| List methods | `.append()`, `.insert(i, x)`, `.extend()`, `.remove(x)`, `.pop()`, `.reverse()`, `.sort()` |
| `sorted()` | Returns NEW list; `.sort()` in-place |
| `min/max/sum` | On numeric list |
| `.index(x)` | Find index or ValueError |
| `x in list` | Membership test |
| `enumerate()` | index + value in loop |
| `' - '.join(li)` / `s.split(' - ')` | List ↔ string |
| Set ops | `.intersection()`, `.difference()`, `.union()` |
| **4. DICTIONARIES** | |
| Create | `{'k1': v1, 'k2': v2}` |
| Access | `d['key']` → KeyError if missing |
| `.get(k, default)` | Safe access |
| Add/Update | `d['new'] = x` |
| `.update({...})` | Multiple updates |
| Delete | `del d['key']` or `d.pop('key')` |
| Iterate | `.keys()`, `.values()`, `.items()` |
| Loop | `for k, v in d.items(): ...` |
| **5. CONDITIONALS** | |
| Syntax | `if cond: ... elif cond: ... else: ...` |
| Operators | `== != > < >= <= is in not in` |
| Boolean ops | `and or not` |
| `is` vs `==` | Identity vs equality |
| Falsy | `False, None, 0, '', [], (), {}, set()` |
| Truthy | Everything else |
| **6. LOOPS** | |
| For | `for x in seq: ...` |
| While | `while cond: ...` |
| Break | Exit loop |
| Continue | Skip to next iteration |
| Nested | loop inside loop |
| `range(a, b, step)` | Generate numbers |
| Infinite | `while True:` + break |
| Interrupt | Ctrl+C |
| **7. FUNCTIONS** | |
| Define | `def fn(params): ...` |
| Return | `return value` (None if omitted) |
| Call | `fn(args)` |
| Defaults | `def fn(x, y=10): ...` |
| `*args` | Positional tuple |
| `**kwargs` | Keyword dict |
| Unpack | `fn(*list, **dict)` |
| Docstring | `"""Description"""` |
| **8. SCOPE (LEGB)** | |
| Order | Local → Enclosing → Global → Built-in |
| `global x` | Modify global inside function |
| `nonlocal x` | Modify enclosing variable |
| Builtins | `print, min, max, list, int, range` |
| **9. MODULES** | |
| Import | `import m` / `from m import x` / `from m import x as y` |
| Alias | `import numpy as np` |
| Avoid | `from m import *` |
| `sys.path` | Search directories list |
| Stdlib | `random, math, datetime, calendar, os, csv, sys, unittest` |
| **10. OS MODULE** | |
| Get cwd | `os.getcwd()` |
| Change dir | `os.chdir(path)` |
| List | `os.listdir(path)` |
| Create | `os.mkdir()` / `os.makedirs()` |
| Remove | `os.rmdir()` / `os.removedirs()` |
| Rename | `os.rename(old, new)` |
| Walk | `os.walk(path)` → (dirpath, dirnames, filenames) |
| Env vars | `os.environ.get('HOME')` |
| Paths | `os.path.join/basename/dirname/split/exists/isdir/isfile/splitext` |
| **11. FILES** | |
| Open | `f = open('f.txt', 'r')` |
| Context | `with open('f.txt') as f: ...` (auto-close) |
| Modes | `'r'` read, `'w'` write (truncate), `'a'` append, `'rb'`/`'wb'` binary |
| Read | `.read()`, `.read(n)`, `.readlines()`, `.readline()`, iterate `for line in f` |
| Position | `.tell()`, `.seek(0)` |
| Write | `.write('text')` |
| Copy | Loop lines or chunks (4096) |
| **12. CSV** | |
| Reader | `csv.reader(f)` → list per row |
| Writer | `csv.writer(f, delimiter='\t')` |
| DictReader | `csv.DictReader(f)` → dict per row |
| DictWriter | `csv.DictWriter(f, fieldnames=[...])` |
| `writeheader()` | Write header row |
| Skip header | `next(reader)` |
| **13. DATETIME** | |
| Types | `date`, `time`, `datetime`, `timedelta` |
| Naive vs Aware | No tz info vs has tz info |
| Today | `date.today()`, `datetime.now()`, `datetime.utcnow()` |
| Timedelta | `timedelta(days=7)` — add/subtract |
| Date math | `date + td` → date; `date - date` → timedelta |
| Timezones | `pytz.UTC`, `pytz.timezone('US/Mountain')` |
| Convert | `.astimezone(tz)`, `.localize(dt)` |
| Format | `.strftime('%B %d, %Y')`, `.isoformat()` |
| Parse | `datetime.strptime(s, fmt)` |
| **14. SORTING** | |
| `sorted()` | Returns new list; any iterable |
| `.sort()` | In-place; list only |
| Reverse | `reverse=True` |
| Key | `key=abs`, `key=lambda e: e.name`, `key=attrgetter('age')` |
| **15. ERROR HANDLING** | |
| Try | `try: ... except E: ... else: ... finally: ...` |
| Specific | `except FileNotFoundError as e:` |
| Order | Specific first, general last |
| Raise | `raise ValueError('msg')` |
| Finally | Always runs (cleanup) |
| **16. UNIT TESTING** | |
| Import | `import unittest` |
| Test file | `test_<module>.py` |
| Class | `class TestX(unittest.TestCase):` |
| Method | `def test_y(self):` (must start with `test_`) |
| Asserts | `assertEqual`, `assertRaises`, `assertTrue`, `assertFalse` |
| setUp/tearDown | Before/after each test |
| setUpClass/tearDownClass | Once before/after all tests |
| Mocking | `from unittest.mock import patch` |
| Run | `python -m unittest test_x` or `unittest.main()` |
| **17. PIPENV** | |
| Install | `pip install pipenv` |
| Add pkg | `pipenv install requests` |
| Dev pkg | `pipenv install pytest --dev` |
| Shell | `pipenv shell` / `exit` |
| Run | `pipenv run python` |
| Pipfile | Env description (TOML) |
| Pipfile.lock | Deterministic versions + hashes |
| Lock | `pipenv lock` |
| Prod install | `pipenv install --ignore-pipfile` |
| Check | `pipenv check` |
| Graph | `pipenv graph` |
| Remove env | `pipenv --rm` |
| **18. VENV** | |
| Create | `python -m venv <name>` |
| Activate (Win) | `<name>\Scripts\activate.bat` |
| Deactivate | `deactivate` |
| Delete | `rmdir /S /Q <name>` |
| Freeze | `pip freeze > requirements.txt` |
| Install from file | `pip install -r requirements.txt` |
| System pkgs | `python -m venv venv --system-site-packages` |
| Only local | `pip list --local` |
| **19. COMMON MISTAKES** | |
| Tabs vs spaces | → IndentationError |
| Module shadows import | Don't name file `math.py`/`flask.py` |
| Variable shadows function | `radians = radians(90)` breaks later |
| Mutable default args | Use `None` + init inside |
| Iterators exhausted | Cast to `list()` once |
| Wildcard imports | Use explicit imports / aliases |
| **20. REQUESTS (ESSENTIALS)** | |
| Install | `pip install requests` |
| GET | `r = requests.get(url)` |
| Params | `requests.get(url, params={'q': 'x'})` |
| Status | `r.status_code`, `r.ok` |
| Text | `r.text` (string) |
| JSON | `r.json()` (dict) |
| Headers | `r.headers` |
| Custom headers | `requests.get(url, headers={'User-Agent': '...'})` |
| POST form | `requests.post(url, data={'k': 'v'})` |
| POST JSON | `requests.post(url, json={'k': 'v'})` |
| Auth | `requests.get(url, auth=('user', 'pass'))` |
| Timeout | `requests.get(url, timeout=5)` |
| Download image | `r = requests.get(url, stream=True)` + iterate `r.iter_content(1024)` |
| Image to file | `with open('img.jpg', 'wb') as f: f.write(r.content)` |
| Session | `s = requests.Session()` — persists cookies/headers |
| Raise for status | `r.raise_for_status()` |

---

## 🌊 Flowchart — Complete Python Roadmap

```mermaid
flowchart TD
    START([START]) --> DATA[Data Types]
    START --> CONTROL[Control Flow]
    START --> STRUCT[Structure]

    DATA --> D1[Strings]
    DATA --> D2[Ints / Floats]
    DATA --> D3[Lists]
    DATA --> D4[Tuples]
    DATA --> D5[Sets]
    DATA --> D6[Dicts]

    CONTROL --> C1[if / elif / else]
    CONTROL --> C2[and / or / not]
    CONTROL --> C3[Falsy values]
    CONTROL --> C4[for loops<br/>break / continue / range]
    CONTROL --> C5[while loops<br/>infinite + break]

    STRUCT --> S1[Functions<br/>def / return / args / kwargs]
    STRUCT --> S2[Scope LEGB<br/>local / enclosing / global / built-in]
    STRUCT --> S3[Modules<br/>import / from / as / sys.path]
    STRUCT --> S4[Stdlib<br/>random / math / datetime / os / csv]

    C4 --> DEBUG[Debugging Skills<br/>try / except / finally / raise]
    C5 --> DEBUG

    S1 --> DEBUG
    S2 --> DEBUG
    S3 --> DEBUG
    S4 --> DEBUG

    DEBUG --> FILES[File I/O<br/>open / with / read / write / seek]
    DEBUG --> WEB[Web / HTTP<br/>requests.get / POST / JSON / Session]
    DEBUG --> FORMATS[Data Formats<br/>CSV / JSON / HTML output]

    FILES --> OS[OS & Filesystem<br/>getcwd / chdir / listdir / walk / environ / path]
    WEB --> OS
    FORMATS --> OS

    OS --> AUTO[Automation Scripts<br/>batch rename / CSV → HTML / download / parse]

    AUTO --> QUALITY[Quality & Safety<br/>Unit tests / Mocking / try-except / asserts]

    QUALITY --> ENV[Environments<br/>venv / pipenv / requirements.txt / .env]

    ENV --> MISTAKES[Common Mistakes<br/>tabs-spaces / shadowing / mutable defaults / iterators / wildcards]

    MISTAKES --> PRO([PRO])
```

### 🧭 Debugging Decision Tree

```mermaid
flowchart TD
    ERR[Error message?] --> IND[IndentationError]
    ERR --> SYN[SyntaxError]
    ERR --> NAME[NameError]
    ERR --> TYPE[TypeError]
    ERR --> VAL[ValueError]
    ERR --> KEY[KeyError]
    ERR --> IDX[IndexError]
    ERR --> ATTR[AttributeError]
    ERR --> IMP[ImportError]
    ERR --> FILE[FileNotFoundError]
    ERR --> ZERO[ZeroDivisionError]

    IND --> IND_FIX[Check tabs vs spaces<br/>enable editor conversion]
    SYN --> SYN_FIX[Check line before<br/>missing colon / paren]
    NAME --> NAME_FIX[Variable out of scope / typo<br/>check LEGB]
    TYPE --> TYPE_FIX[Wrong type or variable<br/>shadowing function]
    VAL --> VAL_FIX[Right type, wrong value<br/>e.g. int 'abc']
    KEY --> KEY_FIX[Dict key missing<br/>use .get]
    IDX --> IDX_FIX[List index OOR<br/>check len]
    ATTR --> ATTR_FIX[Method doesn't exist<br/>use dir obj]
    IMP --> IMP_FIX[sys.path / venv<br/>or file-name shadowing]
    FILE --> FILE_FIX[Check path / cwd / typo]
    ZERO --> ZERO_FIX[Guard with if y != 0]
```

> **Note:** If your GitHub README does not render Mermaid, replace the fenced code blocks above with the plain ASCII flowchart below.

### ASCII Flowchart (fallback)

```text
                            [ START ]
                                |
        +-----------------------+-----------------------+
        |                       |                       |
        v                       v                       v
   [ DATA ]             [ CONTROL FLOW ]         [ STRUCTURE ]
        |                       |                       |
   Strings                 if/elif/else             Functions
   Ints/Floats             and/or/not               Scope LEGB
   Lists                   Falsy values             Modules
   Tuples                  for loops                Stdlib
   Sets                    while loops
   Dicts
        |                       |                       |
        +-----------------------+-----------------------+
                                |
                                v
                     [ DEBUGGING SKILLS ]
                     try/except/finally/raise
                                |
        +-----------------------+-----------------------+
        |                       |                       |
        v                       v                       v
   [ FILE I/O ]           [ WEB/HTTP ]           [ DATA FORMATS ]
   open / with            requests.get            CSV / JSON
   read / write           POST / JSON             HTML output
   seek / tell            Session
        |                       |                       |
        +-----------------------+-----------------------+
                                |
                                v
                     [ OS & FILESYSTEM ]
                     getcwd / chdir / listdir
                     walk / environ / path
                                |
                                v
                     [ AUTOMATION SCRIPTS ]
                     batch rename / CSV->HTML
                     download / parse
                                |
                                v
                     [ QUALITY & SAFETY ]
                     Unit tests / Mocking
                                |
                                v
                     [ ENVIRONMENTS ]
                     venv / pipenv
                     requirements.txt / .env
                                |
                                v
                     [ COMMON MISTAKES ]
                     tabs-spaces / shadowing
                     mutable defaults / iterators
                                |
                                v
                              [ PRO ]
```

---

## 💻 All Code Snippets — In Order

### 📦 1. Strings

```python
message = 'Hello World'
print(message)
print(len(message))              # 11
print(message[0])                # H
print(message[10])               # d
print(message[0:5])              # Hello
print(message[:5])               # Hello
print(message[6:])               # World
print(message.lower())
print(message.upper())
print(message.count('l'))        # 3
print(message.find('world'))     # 6
print(message.find('universe'))  # -1

new_message = message.replace('world', 'universe')
print(new_message)

greeting = 'Hello'
name = 'Michael'
message = greeting + ', ' + name + '. Welcome!'
print(message)
message = '{}, {}. Welcome!'.format(greeting, name)
print(message)
message = f'{greeting}, {name}. Welcome!'
print(message)
message = f'{greeting}, {name.upper()}. Welcome!'
print(message)

print(dir(message))
print(help(str))
print(help(str.lower))

message = 'Bobby\'s World'
message = "Bobby's World"
message = '''Bobby's World was a good
cartoon in the 1990s'''
```

### 🔢 2. Integers & Floats

```python
num = 3
print(type(num))         # int
num = 3.14
print(type(num))         # float

print(3 + 2)    # 5
print(3 - 2)    # 1
print(3 * 2)    # 6
print(3 / 2)    # 1.5
print(3 // 2)   # 1
print(3 ** 2)   # 9
print(3 % 2)    # 1

print(3 * 2 + 1)     # 7
print(3 * (2 + 1))   # 9

num = 1
num = num + 1
num += 1
num *= 10

print(abs(-3))          # 3
print(round(3.75))      # 4
print(round(3.75, 1))   # 3.8

num_1 = 3
num_2 = 2
print(num_1 == num_2, num_1 != num_2)
print(num_1 > num_2, num_1 < num_2)
print(num_1 >= num_2, num_1 <= num_2)

num_1 = '100'
num_2 = '200'
print(num_1 + num_2)               # 100200
print(int(num_1) + int(num_2))     # 300
```

### 📋 3. Lists / Tuples / Sets

```python
courses = ['History', 'Math', 'Physics', 'CompSci']
print(courses)
print(len(courses))              # 4
print(courses[0], courses[-1])
print(courses[0:2])
print(courses[:2])
print(courses[2:])

courses.append('Art')
courses.insert(0, 'Art')
courses_2 = ['Art', 'Education']
courses.insert(0, courses_2)
courses = ['History', 'Math', 'Physics', 'CompSci']
courses.extend(courses_2)
courses.remove('Math')
popped = courses.pop()
courses.reverse()
courses.sort()
nums = [1, 5, 2, 4, 3]
nums.sort(reverse=True)
sorted_courses = sorted(courses)

print(min(nums), max(nums), sum(nums))
print(courses.index('CompSci'))
print('Art' in courses)

for item in courses:
    print(item)

for index, course in enumerate(courses, start=1):
    print(index, course)

course_str = ', '.join(courses)
new_list = course_str.split(', ')

tuple_1 = ('History', 'Math', 'Physics', 'CompSci')
# tuple_1[0] = 'Art'  # TypeError

cs_courses = {'History', 'Math', 'Physics', 'CompSci', 'Math'}
art_courses = {'History', 'Math', 'Art', 'Design'}
print(cs_courses.intersection(art_courses))
print(cs_courses.difference(art_courses))
print(cs_courses.union(art_courses))

empty_list = []
empty_tuple = ()
empty_set = set()      # NOT {}
```

### 🗂 4. Dictionaries

```python
student = {'name': 'John', 'age': 25, 'courses': ['Math', 'CompSci']}
print(student['name'])
print(student.get('phone'))            # None
print(student.get('phone', 'Not Found'))

student['phone'] = '555-5555'
student.update({'name': 'Jane', 'age': 26})

del student['age']
age = student.pop('age')

print(len(student))
print(student.keys())
print(student.values())
print(student.items())

for key in student:
    print(key)

for key, value in student.items():
    print(key, value)
```

### 🔀 5. Conditionals & Booleans

```python
if True:
    print('Conditional was True')

language = 'Python'
if language == 'Python':
    print('Language is Python')
elif language == 'Java':
    print('Language is Java')
else:
    print('No match')

user = 'admin'
logged_in = True
if user == 'admin' and logged_in:
    print('Admin Page')
else:
    print('Bad Creds')

if user == 'admin' or logged_in:
    print('Admin Page')

if not logged_in:
    print('Please Log In')

a = [1, 2, 3]
b = [1, 2, 3]
print(a == b)      # True
print(a is b)      # False
print(id(a) == id(b))

for condition in [False, None, 0, '', [], {}, ()]:
    if condition:
        print('Truthy')
    else:
        print('Falsy')
```

### 🔁 6. Loops

```python
nums = [1, 2, 3, 4, 5]

for num in nums:
    print(num)

for num in nums:
    if num == 3:
        print('Found!')
        break

for num in nums:
    if num == 3:
        print('Found!')
        continue
    print(num)

for num in nums:
    for letter in 'abc':
        print(num, letter)

for i in range(10):
    print(i)

for i in range(1, 11):
    print(i)

x = 0
while x < 10:
    print(x)
    x += 1

x = 0
while True:
    if x == 5:
        break
    print(x)
    x += 1
```

### ⚙️ 7. Functions

```python
def hello_func():
    pass

def hello_func():
    return 'Hello Function.'

print(hello_func().upper())

def hello_func(greeting, name='You'):
    return '{}, {}'.format(greeting, name)

print(hello_func('Hi'))
print(hello_func('Hi', name='Corey'))

def student_info(*args, **kwargs):
    print(args)
    print(kwargs)

student_info('Math', 'Art', name='John', age=22)
courses = ['Math', 'Art']
info = {'name': 'John', 'age': 22}
student_info(*courses, **info)

month_days = [0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]

def is_leap(year):
    """Return True for leap years."""
    return year % 4 == 0 and (year % 100 != 0 or year % 400 == 0)

def days_in_month(year, month):
    """Return number of days in month."""
    if not 1 <= month <= 12:
        return 'Invalid Month'
    if month == 2 and is_leap(year):
        return 29
    return month_days[month]
```

### 🔍 8. Scope (LEGB)

```python
x = 'Global X'

def test():
    y = 'Local Y'
    print(y)

test()

def test():
    x = 'Local X'
    print(x)

test()
print(x)

def test():
    global x
    x = 'Local X'

test()
print(x)

import builtins
print(dir(builtins))
m = min([5, 1, 4, 2, 3])

def outer():
    x = 'Outer X'
    def inner():
        x = 'Inner X'
        print(x)
    inner()
    print(x)

def outer():
    x = 'Outer X'
    def inner():
        nonlocal x
        x = 'Inner X'
        print(x)
    inner()
    print(x)
```

### 📚 9. Modules

```python
# my_module.py
print('Imported my_module...')
test = 'Test String'

def find_index(to_search, target):
    for i, value in enumerate(to_search):
        if value == target:
            return i
    return -1
```

```python
# intro.py
import my_module
from my_module import find_index, test
from my_module import find_index as fi
import my_module as mm

import sys
print(sys.path)

import random
print(random.choice(['a', 'b', 'c']))

import math
print(math.radians(90))
print(math.sin(math.radians(90)))

import datetime, calendar
print(datetime.date.today())
print(calendar.isleap(2020))

import os
print(os.getcwd())
print(os.__file__)
```

### 🖥 10. OS Module

```python
import os

print(dir(os))
print(os.getcwd())
os.chdir('/Users/corey/Desktop')
print(os.listdir())
os.mkdir('OS-Demo-2')
os.makedirs('OS-Demo-2/Sub-Dir-1')
os.rmdir('OS-Demo-2')
os.removedirs('OS-Demo-2/Sub-Dir-1')
os.rename('test.txt', 'demo.txt')

print(os.stat('demo.txt'))
print(os.stat('demo.txt').st_size)

from datetime import datetime
mod_time = os.stat('demo.txt').st_mtime
print(datetime.fromtimestamp(mod_time))

for dirpath, dirnames, filenames in os.walk('/Users/corey/Desktop'):
    print(dirpath, dirnames, filenames)

print(os.environ.get('HOME'))
print(os.path.join(os.environ.get('HOME'), 'test.txt'))
print(os.path.basename('/tmp/test.txt'))
print(os.path.dirname('/tmp/test.txt'))
print(os.path.split('/tmp/test.txt'))
print(os.path.exists('/tmp/test.txt'))
print(os.path.isdir('/tmp'))
print(os.path.isfile('/tmp/test.txt'))
print(os.path.splitext('/tmp/test.txt'))
```

### 📄 11. File Objects

```python
# Manual open/close
f = open('test.txt', 'r')
print(f.name)
print(f.mode)
f.close()

# Context manager
with open('test.txt', 'r') as f:
    pass
print(f.closed)     # True

with open('test.txt', 'r') as f:
    print(f.read())

with open('test.txt', 'r') as f:
    print(f.readlines())

with open('test.txt', 'r') as f:
    print(f.readline(), end='')
    print(f.readline(), end='')

with open('test.txt', 'r') as f:
    for line in f:
        print(line, end='')

with open('test.txt', 'r') as f:
    print(f.read(100))

with open('test.txt', 'r') as f:
    size_to_read = 100
    f_contents = f.read(size_to_read)
    while len(f_contents) > 0:
        print(f_contents, end='*')
        f_contents = f.read(size_to_read)

with open('test.txt', 'r') as f:
    print(f.tell())
    f.seek(0)

with open('test2.txt', 'w') as f:
    f.write('Test')

with open('test.txt', 'r') as rf:
    with open('test_copy.txt', 'w') as wf:
        for line in rf:
            wf.write(line)

with open('bronx.jpg', 'rb') as rf:
    with open('bronx_copy.jpg', 'wb') as wf:
        for line in rf:
            wf.write(line)

with open('bronx.jpg', 'rb') as rf:
    with open('bronx_copy.jpg', 'wb') as wf:
        chunk_size = 4096
        rf_chunk = rf.read(chunk_size)
        while len(rf_chunk) > 0:
            wf.write(rf_chunk)
            rf_chunk = rf.read(chunk_size)
```

### 📊 12. CSV Files

```python
import csv

with open('names.csv', 'r') as csv_file:
    csv_reader = csv.reader(csv_file)
    for line in csv_reader:
        print(line)
    next(csv_reader)   # skip header

with open('names.csv', 'r') as csv_file:
    csv_reader = csv.reader(csv_file)
    with open('new_names.csv', 'w') as new_file:
        csv_writer = csv.writer(new_file, delimiter='\t')
        for line in csv_reader:
            csv_writer.writerow(line)

with open('names.csv', 'r') as csv_file:
    csv_reader = csv.DictReader(csv_file)
    for line in csv_reader:
        print(line['email'])

with open('names.csv', 'r') as csv_file:
    csv_reader = csv.DictReader(csv_file)
    with open('new_names.csv', 'w') as new_file:
        fieldnames = ['first_name', 'last_name', 'email']
        csv_writer = csv.DictWriter(new_file, fieldnames=fieldnames, delimiter='\t')
        csv_writer.writeheader()
        for line in csv_reader:
            del line['email']
            csv_writer.writerow(line)
```

### 📅 13. Datetime

```python
import datetime
import pytz

d = datetime.date(2016, 7, 24)
today = datetime.date.today()
print(today.year, today.day, today.weekday(), today.isoweekday())

tdelta = datetime.timedelta(days=7)
print(today + tdelta)
print(today - tdelta)

bday = datetime.date(2016, 9, 24)
till_bday = bday - today
print(till_bday.days, till_bday.total_seconds())

t = datetime.time(9, 30, 45, 100000)
dt = datetime.datetime(2016, 7, 26, 12, 30, 45, 100000)
print(dt.date(), dt.time())

dt_utc = datetime.datetime.now(tz=pytz.UTC)
print(dt_utc)
dt_mountain = dt_utc.astimezone(pytz.timezone('US/Mountain'))
print(dt_mountain)

for tz in pytz.all_timezones:
    print(tz)

dt = datetime.datetime.now()
mountain_tz = pytz.timezone('US/Mountain')
dt = mountain_tz.localize(dt)
print(dt)

print(dt_mountain.isoformat())
print(dt_mountain.strftime('%B %d, %Y'))

dt_str = 'July 26, 2016'
dt = datetime.datetime.strptime(dt_str, '%B %d, %Y')
print(dt)
```

### 🔤 14. Sorting

```python
li = [9, 1, 8, 2, 7, 3, 6, 4, 5]
s_li = sorted(li)
li.sort()
s_li = sorted(li, reverse=True)
li.sort(reverse=True)

tup = (9, 1, 8, 2, 7, 3, 6, 4, 5)
s_tup = sorted(tup)

di = {'name': 'Corey', 'job': 'programming', 'age': None, 'os': 'Mac'}
s_di = sorted(di)

li = [-6, -5, -4, 1, 2, 3]
s_li = sorted(li, key=abs)

class Employee:
    def __init__(self, name, age, salary):
        self.name = name
        self.age = age
        self.salary = salary

    def __repr__(self):
        return f'({self.name},{self.age},${self.salary})'

e1 = Employee('Carl', 37, 70000)
e2 = Employee('Sarah', 29, 80000)
e3 = Employee('John', 43, 90000)
employees = [e1, e2, e3]

def e_sort(emp):
    return emp.name

s_employees = sorted(employees, key=e_sort)
s_employees = sorted(employees, key=lambda e: e.name)

from operator import attrgetter
s_employees = sorted(employees, key=attrgetter('age'))
s_employees = sorted(employees, key=attrgetter('salary'), reverse=True)
```

### 🚨 15. Error Handling

```python
try:
    f = open('testfile.txt')
except Exception:
    print('Sorry. This file does not exist.')

try:
    f = open('test_file.txt')
    var = bad_var
except FileNotFoundError as e:
    print(e)
except Exception as e:
    print(e)
else:
    print(f.read())
    f.close()
finally:
    print('Executing Finally...')

try:
    f = open('currupt_file.txt')
    if f.name == 'currupt_file.txt':
        raise Exception('This is a corrupt file!')
except FileNotFoundError as e:
    print(e)
except Exception as e:
    print(e)
else:
    print(f.read())
    f.close()
finally:
    print('Executing Finally...')
```

### 🧪 16. Unit Testing

```python
# calc.py
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y ==
