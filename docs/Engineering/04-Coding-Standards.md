---
Status: Active
Version: 1.0
Owner: Engineering Team
Category: Engineering Standards
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Coding Standards

Language-agnostic coding standards for producing maintainable code.

## Purpose

Enable teams to:
- Write code that others can understand
- Maintain consistency across codebases
- Reduce defects through convention
- Onboard new developers quickly

## Scope

Applies to all source code including:
- Application logic
- Test code
- Scripts
- Configuration as code

## Standards

### 1. Naming Conventions

#### Variables and Functions

| Type | Convention | Example |
|------|------------|---------|
| Variables | snake_case | `user_name`, `total_count` |
| Functions | snake_case | `get_user()`, `calculate_total()` |
| Classes | PascalCase | `UserService`, `PaymentProcessor` |
| Constants | UPPER_SNAKE | `MAX_RETRIES`, `DEFAULT_TIMEOUT` |
| Private members | _prefix | `_internal_state` |
| Type aliases | PascalCase | `UserId`, `ApiResponse` |

#### Naming Guidelines

- **Be descriptive**: Names should reveal intent
- **Be consistent**: Use the same term for the same concept
- **Avoid abbreviations**: `calculate` not `calc`, `maximum` not `max`
- **Avoid Hungarian notation**: `strName` not needed in typed languages

### 2. Functions

#### Single Responsibility

Each function should do one thing well:

```python
# Good: Focused functions
def validate_email(email: str) -> bool:
    """Check if email format is valid."""
    pattern = r'^[\w\.-]+@[\w\.-]+\.\w+$'
    return bool(re.match(pattern, email))

def send_welcome_email(email: str) -> None:
    """Send welcome email after validation."""
    if not validate_email(email):
        raise ValueError("Invalid email")
    # Send email logic...
```

#### Parameter Guidelines

- Limit parameters to 4 or fewer
- Use parameter objects for related data
- Separate command from query
- Make boolean flags a signal to refactor

### 3. Error Handling

#### Exception Patterns

```python
# Good: Specific exceptions with context
def divide(a: float, b: float) -> float:
    """Divide two numbers."""
    if b == 0:
        raise ValueError(f"Cannot divide {a} by zero")
    return a / b

# Good: Catch specific exceptions
try:
    result = process_data(data)
except ValidationError as e:
    logger.warning(f"Invalid data: {e}")
    raise  # Re-raise after logging
except DatabaseError as e:
    logger.error(f"Database failure: {e}")
    raise  # Different handling
```

#### Never Do These

```python
# Bad: Bare except
try:
    do_something()
except:
    pass

# Bad: Swallowing exceptions
try:
    do_something()
except Exception:
    pass  # Silent failure

# Bad: Catching too broad
try:
    do_something()
except BaseException:
    # Catches everything including SystemExit
    pass
```

### 4. Type Safety

#### Type Annotations

All function signatures should include type hints:

```python
from typing import Optional, List, Dict

def process_users(
    user_ids: List[int],
    include_inactive: bool = False
) -> Dict[int, User]:
    """Process a list of users by ID."""
    ...
```

#### Avoid Any

Use `Unknown` or generic types instead of `Any`:

```python
# Good
def deserialize(data: Unknown) -> Optional[User]:
    ...

# Bad
def deserialize(data: Any) -> Optional[User]:
    ...
```

### 5. Code Organization

#### Import Ordering

1. Standard library
2. Third-party libraries
3. Internal packages
4. Relative imports

```python
# stdlib
import os
from typing import List, Optional

# third-party
import requests
from pydantic import BaseModel

# internal
from app.models import User
from app.utils import validate
```

#### Module Length

- Prefer small, focused modules (< 300 lines)
- Split large modules by responsibility
- Use `__init__.py` for package interfaces

## Examples

### Good: Clear Intent

```python
def calculate_monthly_payment(
    principal: Decimal,
    annual_rate: Decimal,
    months: int
) -> Decimal:
    """
    Calculate monthly mortgage payment using standard formula.

    M = P * [r(1+r)^n] / [(1+r)^n - 1]

    Where:
        M = monthly payment
        P = principal
        r = monthly interest rate
        n = number of payments
    """
    if principal <= 0:
        raise ValueError("Principal must be positive")
    if annual_rate < 0:
        raise ValueError("Interest rate cannot be negative")
    if months <= 0:
        raise ValueError("Term must be positive months")

    monthly_rate = annual_rate / 12 / 100
    if monthly_rate == 0:
        return principal / months

    numerator = monthly_rate * (1 + monthly_rate) ** months
    denominator = (1 + monthly_rate) ** months - 1

    return principal * (numerator / denominator)
```

### Bad: Obscured Intent

```python
def calc(p, r, n):
    """Calculate payment."""
    if p <= 0 or r < 0 or n <= 0:
        raise Exception("bad input")
    m = r / 12 / 100
    if m == 0:
        return p / n
    return p * (m * (1 + m) ** n) / ((1 + m) ** n - 1)
```

## Checklist

### Code Quality

- [ ] Variables have meaningful names
- [ ] Functions have single responsibility
- [ ] All public APIs are documented
- [ ] Type annotations are complete
- [ ] Error handling is explicit
- [ ] No hardcoded values

### Style

- [ ] Follows naming conventions
- [ ] Consistent indentation
- [ ] No trailing whitespace
- [ ] Files end with newline
- [ ] Imports organized correctly

### Testing

- [ ] Code is testable
- [ ] Edge cases covered
- [ ] Test names describe behavior

## Anti-Patterns

### 1. YAGNI Violations

Adding features "just in case":
```python
# Bad: Over-engineering
class UserService:
    def __init__(self):
        self.cache = {}  # Not used yet
        self.logger = Logger()  # Not used yet
        self.metrics = Metrics()  # Not used yet
```

**Solution**: Implement only what's needed now.

### 2. Boolean Trap

Overusing boolean parameters:
```python
# Bad: What does False mean?
process_data(data, False, True, False)
```

**Solution**: Use named parameters or split into separate functions.

### 3. Arrow Code

Deeply nested conditionals:
```python
# Bad
if a:
    if b:
        if c:
            do_something()
```

**Solution**: Early returns, extract conditions, use guard clauses.

### 4. Parallel Inheritance

Creating parallel class hierarchies:
```python
# Bad
DogHandler, CatHandler, BirdHandler
DogDTO, CatDTO, BirdDTO
DogValidator, CatValidator, BirdValidator
```

**Solution**: Use composition, generics, or common base classes.

## Future Improvements

- Create language-specific style guides
- Set up pre-commit hooks for style enforcement
- Develop code review guidelines for style issues
- Create automated refactoring tools
- Establish code ownership policies

## Related Standards

- [01-Engineering-Standards](01-Engineering-Standards.md) — Core engineering principles
- [05-Documentation-Standards](05-Documentation-Standards.md) — Documentation guidelines
- [06-Review-Standards](06-Review-Standards.md) — Code review practices
