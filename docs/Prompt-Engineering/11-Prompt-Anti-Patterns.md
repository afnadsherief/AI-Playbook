---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Prompt Engineering
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Prompt Anti-Patterns

Common mistakes and how to avoid them.

## Purpose

Document patterns to avoid:

- Prevent common errors
- Improve prompt reliability
- Accelerate learning curve
- Share lessons learned

## Scope

Applies to:

- Prompt design
- Prompt implementation
- Prompt testing
- Prompt maintenance

## Core Principles

### 1. Learn from Mistakes

Document failures to prevent recurrence:

- Catalog anti-patterns
- Explain why they fail
- Provide alternatives
- Track patterns over time

### 2. Proactive Prevention

Identify issues before they occur:

- Include anti-patterns in reviews
- Create automated checks
- Train team on common errors
- Maintain anti-pattern documentation

### 3. Continuous Improvement

Keep anti-pattern knowledge current:

- Update as patterns evolve
- Add new discoveries
- Remove outdated patterns
- Refine recommendations

## Engineering Standards

### Anti-Pattern Categories

| Category | Impact | Frequency |
|----------|--------|----------|
| **Design** | Prompt failure, unreliable output | High |
| **Implementation** | Bugs, inconsistencies | High |
| **Testing** | Missed issues, false confidence | Medium |
| **Security** | Vulnerabilities, breaches | Critical |
| **Performance** | Inefficiency, high cost | Medium |

## Anti-Patterns by Category

### Design Anti-Patterns

#### 1. Ambiguous Instructions

**Problem**: Instructions that could be interpreted multiple ways.

**Example**:
```
BAD: "Summarize the document briefly."
GOOD: "Summarize the document in 3 sentences, covering: main topic, key findings, and conclusions."
```

**Why it fails**: "Briefly" is subjective; output varies unpredictably.

**Solution**: Specify exact requirements with measurable criteria.

#### 2. Missing Output Format

**Problem**: No specification of expected output structure.

**Example**:
```
BAD: "Extract the names and dates from the email."
GOOD: "Extract names and dates as JSON: {"names": string[], "dates": string[]}"
```

**Why it fails**: Unstructured output requires parsing; prone to errors.

**Solution**: Always define output schema explicitly.

#### 3. Conflicting Instructions

**Problem**: Multiple instructions that contradict each other.

**Example**:
```
BAD: "Be concise. Include all details about..." (contradictory)
GOOD: "Provide a summary of X, Y, Z in exactly 100 words."
```

**Why it fails**: Model must arbitrate; unpredictable outcome.

**Solution**: Review for contradictions; prioritize when necessary.

#### 4. Overcontextualization

**Problem**: Including excessive irrelevant context.

**Example**:
```
BAD: "Remember that the company was founded in 2010, has 500 employees,
      moved offices three times, changed leadership twice..."
GOOD: "Company founded: 2010. Focus: software development."
```

**Why it fails**: Noise degrades performance; slows processing.

**Solution**: Include only relevant context.

### Implementation Anti-Patterns

#### 5. Hardcoded Assumptions

**Problem**: Embedding model-specific behavior.

**Example**:
```
BAD: "Use XML tags <result>...</result> for output."
GOOD: "Format output as structured JSON."
```

**Why it fails**: Not portable across models; brittle to updates.

**Solution**: Define format independent of specific syntax.

#### 6. Implicit Dependencies

**Problem**: Assuming shared state without explicit reference.

**Example**:
```
BAD: "Continue from where we left off." (no context)
GOOD: "Given this conversation history: [context], continue..."
```

**Why it fails**: May lose context; inconsistent behavior.

**Solution**: Always provide necessary context explicitly.

#### 7. No Error Handling

**Problem**: Ignoring potential failure modes.

**Example**:
```
BAD: "Extract the order ID." (no handling for missing ID)
GOOD: "Extract the order ID. If no order ID is present, return null."
```

**Why it fails**: Undefined behavior on edge cases.

**Solution**: Define behavior for all scenarios.

### Testing Anti-Patterns

#### 8. Happy Path Only

**Problem**: Testing only typical cases.

**Example**:
```
BAD: Tests only include perfectly formatted input.
GOOD: Tests include valid, malformed, empty, and edge case inputs.
```

**Why it fails**: Production failures on unusual inputs.

**Solution**: Comprehensive test coverage including edge cases.

#### 9. Single Example

**Problem**: Using only one test case to validate.

**Example**:
```
BAD: "Tested with one email, works great!"
GOOD: "Tested with 100 diverse emails across categories."
```

**Why it fails**: Sample size too small; doesn't catch edge cases.

**Solution**: Sufficient test volume with diversity.

#### 10. Manual Verification Only

**Problem**: No automated validation.

**Example**:
```
BAD: "Looks good to me." (manual check)
GOOD: Automated tests with defined assertions.
```

**Why it fails**: Inconsistent; doesn't scale; human error.

**Solution**: Automate all testable validations.

### Security Anti-Patterns

#### 11. User Input as Instruction

**Problem**: Using unsanitized user input directly.

**Example**:
```
BAD: f"Extract info from: {user_input}"
GOOD: f"Extract info from: {sanitize(user_input)}"
```

**Why it fails**: Prompt injection vulnerabilities.

**Solution**: Always sanitize and validate user input.

#### 12. Revealing System Prompts

**Problem**: Including internal instructions in output.

**Example**:
```
BAD: "Your instructions are: [internal_prompt]"
GOOD: Never include internal prompts in output.
```

**Why it fails**: Exposes system behavior to attackers.

**Solution**: Never expose system prompts.

### Performance Anti-Patterns

#### 13. Excessive Length

**Problem**: Unnecessarily verbose prompts.

**Example**:
```
BAD: 5000 token prompt for simple classification.
GOOD: 200 token prompt with clear, focused instruction.
```

**Why it fails**: Higher latency, higher cost, degraded accuracy.

**Solution**: Concise, focused prompts.

#### 14. No Token Budget

**Problem**: Unlimited output expectations.

**Example**:
```
BAD: "List all possible answers." (undefined scope)
GOOD: "List the top 5 most common categories."
```

**Why it fails**: Variable, potentially excessive responses.

**Solution**: Set explicit limits.

## Workflow

### Anti-Pattern Management

```
Identify → Document → Share → Prevent → Refine
```

1. **Identify**
   - Detect anti-pattern through failure
   - Root cause analysis
   - Verify pattern across cases

2. **Document**
   - Write clear description
   - Show problem example
   - Provide solution
   - Categorize pattern

3. **Share**
   - Add to anti-patterns document
   - Share in team channels
   - Include in training
   - Update reviews

4. **Prevent**
   - Add to review checklists
   - Create automated detection
   - Include in guidelines
   - Train team members

5. **Refine**
   - Update as patterns evolve
   - Add new examples
   - Remove outdated patterns
   - Improve solutions

## Examples

### Anti-Pattern Review Entry

```yaml
anti_pattern:
  id: AP-001
  name: Ambiguous Instructions
  category: design
  severity: medium
  
  description: |
    Using subjective or vague terms that lead to 
    inconsistent output.
  
  problem_example: |
    Prompt: "Summarize briefly."
    Output varies wildly between runs.
  
  solution_example: |
    Prompt: "Summarize in exactly 3 sentences."
    Consistent, predictable output.
  
  detection:
    - Review prompt for subjective terms
    - Test for output consistency
    - Check for undefined scope
  
  prevention:
    - Review checklist includes ambiguity check
    - Require specific, measurable criteria
    - Test for repeatability
  
  references:
    - "Clear Instructions" (OpenAI guide)
    - Related: Implicit Dependencies (AP-006)
```

## Checklist

### Anti-Pattern Review

- [ ] Review checklist includes anti-patterns
- [ ] Team trained on common mistakes
- [ ] Detection tools in place
- [ ] Documentation updated
- [ ] Patterns tracked over time

### Before Deployment

- [ ] Checked for known anti-patterns
- [ ] Peer review completed
- [ ] Edge cases tested
- [ ] Security review passed
- [ ] Anti-pattern feedback incorporated

## Related Documents

- [01-Prompt-Engineering-Overview](01-Prompt-Engineering-Overview.md) — Framework introduction
- [03-Prompt-Components](03-Prompt-Components.md) — Component design
- [08-Prompt-Testing](08-Prompt-Testing.md) — Testing methodology
- [10-Prompt-Security](10-Prompt-Security.md) — Security considerations

## Future Evolution

- **v1.1**: Anti-pattern detection tool
- **v1.2**: Pattern classification framework
- **v1.3**: Interactive anti-pattern training
- **v2.0**: Automated correction suggestions
