---
name: python-patterns
description: Apply modern Python idioms, type hints, testing patterns, and tooling best practices. Use when writing Python, reviewing Python code, or setting up Python project tooling.
triggers:
  - python patterns
  - python best practices
  - pythonic code
---

# Python Patterns

Apply modern Python (3.10+) idioms and tooling patterns. Write code that is readable, typed, and testable.

## Type Hints

Use type hints on all function signatures and class attributes:

```python
def fetch_user(user_id: int) -> User | None:
    ...

def process_items(items: list[str], *, limit: int = 100) -> dict[str, int]:
    ...
```

Rules:
- Use `X | None` instead of `Optional[X]` (Python 3.10+)
- Use built-in generics: `list[str]`, `dict[str, int]`, `tuple[int, ...]`
- Use `TypeAlias` for complex types: `UserMap: TypeAlias = dict[str, list[User]]`
- Use `Protocol` for structural subtyping instead of ABC when possible
- Avoid `Any` — use `object` or a type variable instead

## Dataclasses and Data Modeling

Prefer dataclasses for structured data:

```python
from dataclasses import dataclass, field
from datetime import datetime

@dataclass(frozen=True)
class Event:
    name: str
    timestamp: datetime
    tags: list[str] = field(default_factory=list)
```

- Use `frozen=True` for immutable data
- Use `field(default_factory=...)` for mutable defaults
- Use `__post_init__` for validation
- Use Pydantic for external data validation (API inputs, config files)

## Common Patterns

### Context Managers
Use for resource management:
```python
from contextlib import contextmanager

@contextmanager
def timed_operation(name: str):
    start = time.monotonic()
    yield
    elapsed = time.monotonic() - start
    logger.info(f"{name} took {elapsed:.2f}s")
```

### Generators
Use for lazy iteration over large datasets:
```python
def read_large_file(path: Path) -> Iterator[str]:
    with open(path) as f:
        for line in f:
            yield line.strip()
```

### Structural Pattern Matching (3.10+)
```python
match command:
    case {"action": "create", "name": str(name)}:
        create_item(name)
    case {"action": "delete", "id": int(item_id)}:
        delete_item(item_id)
    case _:
        raise ValueError(f"Unknown command: {command}")
```

## Testing with pytest

### Structure
- Mirror source structure: `src/models/user.py` → `tests/models/test_user.py`
- Use descriptive names: `test_create_user_raises_when_email_is_empty`
- Group related tests in classes: `class TestUserCreation:`

### Fixtures
```python
@pytest.fixture
def sample_user() -> User:
    return User(name="Ada Lovelace", email="ada@example.com")

def test_user_display_name(sample_user: User) -> None:
    assert sample_user.display_name == "Ada Lovelace"
```

### Parametrize
```python
@pytest.mark.parametrize("input_val,expected", [
    ("hello", "HELLO"),
    ("", ""),
    ("Hello World", "HELLO WORLD"),
])
def test_uppercase(input_val: str, expected: str) -> None:
    assert to_uppercase(input_val) == expected
```

## Tooling

### Required
- **Formatter:** ruff format (or black)
- **Linter:** ruff check (replaces flake8, isort, and many others)
- **Type checker:** mypy with strict mode or pyright

### Project Config
Use `pyproject.toml` as the single config file:
```toml
[tool.ruff]
line-length = 88
target-version = "py312"

[tool.mypy]
strict = true
warn_return_any = true
```

### Virtual Environments
- Always use a virtual environment (`python -m venv .venv` or `uv venv`)
- Pin dependencies in `requirements.txt` or use `uv lock`
- Never install packages globally for project work

## Do NOT
- Use bare `except:` — always catch specific exceptions
- Use mutable default arguments (`def f(x=[])`)
- Ignore type checker errors — fix them or document why with a `type: ignore[reason]`
- Use `import *` — explicit imports only
- Mix tabs and spaces — use 4 spaces (enforced by formatter)
