# Pytest Basics

## 1. Installation

```bash
pip install pytest
```

## 2. Test Discovery Rules

Pytest automatically finds tests by default:
- Files named `test_*.py` or `*_test.py`
- Functions named `test_*`
- Classes named `Test*` (no `__init__` method)

Run tests with:
```bash
pytest                    # run all tests
pytest tests/             # run tests in a folder
pytest tests/test_math.py # run a specific file
pytest -v                 # verbose output
pytest -k "keyword"       # filter by name
```

## 3. Basic Test Structure

```python
# test_math.py

def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5

def test_add_negative():
    assert add(-1, 1) == 0
```

## 4. Assertions

Just use Python's `assert` — no special API needed:

```python
def test_strings():
    result = "hello world"
    assert "hello" in result
    assert result.startswith("hello")
    assert len(result) == 11
```

## 5. Testing Exceptions

Use `pytest.raises`:

```python
import pytest

def test_zero_division():
    with pytest.raises(ZeroDivisionError):
        1 / 0

# With message check
def test_value_error():
    with pytest.raises(ValueError, match="invalid"):
        int("not_a_number")
```

## 6. Fixtures (Setup/Teardown)

Fixtures provide reusable setup logic:

```python
import pytest

@pytest.fixture
def sample_user():
    return {"name": "Alice", "age": 30}

def test_user_name(sample_user):
    assert sample_user["name"] == "Alice"

def test_user_age(sample_user):
    assert sample_user["age"] == 30
```

### Fixture with teardown (yield):

```python
@pytest.fixture
def temp_file(tmp_path):
    f = tmp_path / "test.txt"
    f.write_text("hello")
    yield f
    # cleanup happens after yield (optional)
```

### Fixture scopes:

```python
@pytest.fixture(scope="function")  # default — per test
@pytest.fixture(scope="module")    # per module
@pytest.fixture(scope="session")   # entire test run
```

## 7. Parametrized Tests

Run the same test with multiple inputs:

```python
import pytest

@pytest.mark.parametrize("a, b, expected", [
    (1, 2, 3),
    (0, 0, 0),
    (-1, 1, 0),
    (100, -50, 50),
])
def test_add(a, b, expected):
    assert add(a, b) == expected
```

## 8. Common Assertions with `pytest.approx`

For floats:

```python
def test_float():
    assert 0.1 + 0.2 == pytest.approx(0.3)
```

## 9. Testing with `conftest.py`

Put shared fixtures in `conftest.py` — pytest auto-discovers them:

```
project/
├── conftest.py        # shared fixtures
├── test_one.py
└── tests/
    ├── conftest.py    # fixtures for tests/ folder
    └── test_two.py
```

## 10. Markers

### Built-in markers:
```python
@pytest.mark.skip(reason="not implemented yet")
@pytest.mark.skipif(sys.version_info < (3, 10), reason="needs 3.10")
@pytest.mark.xfail(reason="known bug")
@pytest.mark.parametrize(...)
```

### Custom markers (register in `pytest.ini` or `pyproject.toml`):

```python
@pytest.mark.slow
def test_slow_thing():
    ...
```

```bash
pytest -m "not slow"   # skip slow tests
```

## 11. Complete Example

```python
# calc.py
def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b
```

```python
# test_calc.py
import pytest
from calc import divide

@pytest.fixture
def numbers():
    return [10, 2]

def test_divide(numbers):
    assert divide(*numbers) == 5

def test_divide_by_zero():
    with pytest.raises(ValueError, match="Cannot divide by zero"):
        divide(1, 0)

@pytest.mark.parametrize("a, b, expected", [
    (10, 2, 5),
    (9, 3, 3),
    (-6, 2, -3),
])
def test_divide_parametrized(a, b, expected):
    assert divide(a, b) == expected
```

Run: `pytest test_calc.py -v`

## Quick Cheat Sheet

| What | How |
|------|-----|
| Assert equality | `assert x == y` |
| Assert exception | `with pytest.raises(Error):` |
| Setup/teardown | `@pytest.fixture` |
| Multiple inputs | `@pytest.mark.parametrize` |
| Skip test | `@pytest.mark.skip` |
| Shared fixtures | `conftest.py` |
| Run one test | `pytest path::test_name` |
| Show prints | `pytest -s` |
| Stop on first fail | `pytest -x` |

That covers the 90% you'll use day-to-day. Want me to go deeper on any topic (fixtures, mocking with `monkeypatch`/`unittest.mock`, async tests, or project layout)?
