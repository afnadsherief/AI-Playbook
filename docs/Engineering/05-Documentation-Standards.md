---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Engineering Standards
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Documentation Standards

Standards for creating clear, maintainable documentation.

## Purpose

Ensure documentation is:
- Complete and accurate
- Consistent in style
- Easy to find and navigate
- Kept up-to-date

## Scope

Applies to all documentation including:
- User guides and tutorials
- API documentation
- Code comments and docstrings
- Runbooks and procedures
- Architecture Decision Records (ADRs)

## Standards

### 1. Documentation Types

#### Conceptual Documentation

Explains *what* and *why*:
- Architecture overviews
- Design principles
- Domain knowledge
- Terminology definitions

#### Procedural Documentation

Explains *how*:
- Tutorials and how-tos
- Installation guides
- Configuration instructions
- Deployment procedures

#### Reference Documentation

Provides *details*:
- API specifications
- Command reference
- Configuration options
- Data schemas

### 2. Writing Style

#### Voice and Tone

| Guideline | Do | Don't |
|-----------|-----|-------|
| Voice | Active | Passive |
| Tone | Friendly but professional | Casual or formal |
| Sentences | Short, direct | Long, rambling |
| Jargon | Defined when used | Assumed |

#### Formatting Rules

- Use sentence case for headings
- Use bullet lists for multiple items
- Use numbered lists for sequences
- Use code blocks for examples
- Use tables for comparisons
- Use bold for emphasis, not ALL CAPS

### 3. Document Structure

Every document should include:

1. **Title**: Clear, descriptive heading
2. **Introduction**: 2-3 sentences on purpose
3. **Prerequisites**: What readers need to know/have
4. **Main content**: Structured sections
5. **Examples**: Real-world usage
6. **Related information**: Links to other docs

### 4. Code Examples

#### Guidelines

- Always include working code
- Show both input and expected output
- Include comments for non-obvious parts
- Use syntax highlighting
- Test all examples

#### Example Template

```markdown
## Example: Creating a User

Shows how to create a new user with the API.

**Request:**
```http
POST /api/v1/users
Content-Type: application/json

{
    "name": "Jane Doe",
    "email": "jane@example.com"
}
```

**Response:**
```json
{
    "id": "123",
    "name": "Jane Doe",
    "email": "jane@example.com",
    "created_at": "2024-01-15T10:30:00Z"
}
```
```

### 5. Maintenance

- Review documentation quarterly
- Link to issue trackers for known gaps
- Version documentation with code
- Assign documentation owners

## Examples

### Good: Clear API Documentation

```markdown
## Create User

Creates a new user in the system.

**Endpoint:** `POST /api/v1/users`

**Request Body:**

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| name | string | Yes | User's full name (1-100 chars) |
| email | string | Yes | Valid email address |
| role | string | No | User role (default: "member") |

**Response:** `201 Created`

```json
{
    "id": "usr_abc123",
    "name": "Jane Doe",
    "email": "jane@example.com",
    "role": "member",
    "created_at": "2024-01-15T10:30:00Z"
}
```

**Errors:**
- `400 Bad Request`: Invalid input
- `409 Conflict`: Email already exists

**Example:**
```bash
curl -X POST https://api.example.com/v1/users \
    -H "Authorization: Bearer $TOKEN" \
    -d '{"name": "Jane Doe", "email": "jane@example.com"}'
```
```

### Bad: Vague Documentation

```markdown
## Users

Manage users in the system. You can do various things
with users. See the API for more details.

Contact support if you have questions.
```

## Checklist

### For New Documentation

- [ ] Purpose clearly stated
- [ ] Target audience identified
- [ ] Prerequisites listed
- [ ] All steps included
- [ ] Examples provided and tested
- [ ] Related docs linked
- [ ] Reviewed for accuracy

### For Updates

- [ ] Old information removed
- [ ] Version noted if applicable
- [ ] Cross-references updated
- [ ] Review date added

## Anti-Patterns

### 1. Documentation Debt

Outdated or missing documentation:
- Misleads users
- Causes support burden
- Blocks self-service

**Solution**: Budget time for docs; treat as part of feature.

### 2. Auto-Generated Only

Relying solely on generated docs:
- Misses context
- Lacks examples
- No how-to content

**Solution**: Supplement with manual documentation.

### 3. Walls of Text

Dense paragraphs without structure:
- Hard to scan
- Easy to miss key points
- Overwhelming

**Solution**: Use headings, lists, tables, and code blocks.

### 4. Duplicate Documentation

Same info in multiple places:
- Inconsistent updates
- Confusion about source of truth
- Maintenance burden

**Solution**: Single source of truth; link instead of copy.

### 5. Perfect Storm Documentation

Waiting for "perfect" docs:
- Never ships
- Becomes stale
- Blocks progress

**Solution**: Ship good enough; iterate.

## Future Improvements

- Implement documentation CI/CD
- Add automated link checking
- Create documentation templates
- Develop translation workflow
- Set up search functionality
- Build documentation review automation

## Related Standards

- [04-Coding-Standards](04-Coding-Standards.md) — Code documentation patterns
- [07-Definition-of-Done](07-Definition-of-Done.md) — Documentation completion criteria
- [12-Pull-Request-Standards](12-Pull-Request-Standards.md) — PR documentation requirements
