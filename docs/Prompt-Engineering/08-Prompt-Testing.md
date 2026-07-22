---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Prompt Engineering
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Prompt Testing

Methodology for validating prompt behavior and quality.

## Purpose

Establish testing practices for prompt development:

- Validate expected behavior
- Detect regressions
- Ensure quality consistency
- Support confidence in deployment

## Scope

Applies to:

- Individual prompts
- Prompt compositions
- Template instantiations
- System integrations

## Core Principles

### 1. Test-Driven Development

Define tests before implementation:

- Specify expected behavior as tests
- Validate against requirements
- Iterate until tests pass
- Maintain test coverage

### 2. Comprehensive Coverage

Test across relevant scenarios:

- Happy path cases
- Edge cases and boundaries
- Error conditions
- Regression cases

### 3. Reproducible Results

Tests must be deterministic:

- Fixed seeds for randomness
- Controlled inputs
- Clear assertions
- Isolated execution

### 4. Continuous Validation

Test throughout lifecycle:

- Unit tests during development
- Integration tests before deploy
- Regression tests on changes
- Monitoring tests in production

## Engineering Standards

### Test Categories

| Category | Purpose | Timing | Coverage |
|----------|---------|--------|----------|
| **Unit** | Component validation | Development | High |
| **Integration** | Component interaction | Pre-deploy | Medium |
| **Regression** | Change impact | Every change | High |
| **Performance** | Latency validation | Pre-deploy | Medium |
| **Security** | Vulnerability detection | Pre-deploy | Critical |

### Test Case Design

#### Input Categories

```yaml
test_inputs:
  normal:
    description: "Typical valid inputs"
    count: "10-20 cases"
    selection: "Representative samples"
    
  boundary:
    description: "Edge of acceptable range"
    count: "5-10 cases"
    selection: "Min, max, just inside, just outside"
    
  invalid:
    description: "Invalid or malformed inputs"
    count: "5-10 cases"
    selection: "Common error patterns"
    
  adversarial:
    description: "Potentially malicious inputs"
    count: "Variable"
    selection: "Known attack patterns"
```

#### Expected Outputs

```yaml
expected_outputs:
  exact:
    description: "Output must match exactly"
    validation: "String equality or structure match"
    
  schema_valid:
    description: "Output must match schema"
    validation: "Schema validation"
    
  semantic:
    description: "Output meaning must be correct"
    validation: "Human evaluation or semantic check"
    
  range:
    description: "Output within acceptable range"
    validation: "Numeric comparison with tolerance"
```

### Test Execution

```yaml
execution:
  environment:
    controlled: true
    isolation: "Per test case"
    cleanup: "After each test"
  
  parameters:
    max_retries: 3
    timeout_seconds: 30
    parallel: false
  
  reporting:
    pass_fail: true
    timing: true
    output_capture: true
    error_details: true
```

## Workflow

### Testing Workflow

```
Write Tests → Execute → Verify → Report → Iterate
```

### Test Development Process

1. **Analyze Requirements**
   - Understand expected behavior
   - Identify edge cases
   - Define acceptance criteria
   - Document assumptions

2. **Design Test Cases**
   - Cover happy path
   - Cover edge cases
   - Cover error cases
   - Define assertions

3. **Implement Tests**
   - Write test code
   - Set up fixtures
   - Configure execution
   - Add assertions

4. **Execute and Verify**
   - Run tests
   - Verify results
   - Debug failures
   - Iterate

5. **Report and Maintain**
   - Document results
   - Update test suite
   - Track coverage
   - Refine tests

### Test Maintenance

- Review tests quarterly
- Update for new requirements
- Remove obsolete tests
- Refactor for clarity

## Examples

### Test Suite Structure

```yaml
test_suite:
  name: OrderExtractorTests
  prompt_id: PRMPT-ORDER-001
  version: v2.1.0
  
  test_cases:
    - id: TC-001
      name: Valid Complete Order
      category: unit
      priority: high
      
      input:
        text: "Order ORD-12345: 2x Widget at $10 each. Total: $20."
      
      expected:
        order_id: "ORD-12345"
        items:
          - product: "Widget"
            quantity: 2
            price: 10
        total: 20
      
      validation:
        type: exact
        schema: order_schema.yaml
      
      status: pass
      
    - id: TC-002
      name: Partial Order Information
      category: boundary
      priority: medium
      
      input:
        text: "Order ORD-12345: Widget"
      
      expected:
        order_id: "ORD-12345"
        items:
          - product: "Widget"
        total: null
      
      validation:
        type: partial
        required_fields: [order_id]
      
      status: pass
      
    - id: TC-003
      name: Malformed Input
      category: invalid
      priority: high
      
      input:
        text: "!!!INVALID ORDER FORMAT!!!"
      
      expected:
        error: true
        message: "Unable to parse order information"
      
      validation:
        type: error_handling
      
      status: pass
```

### Test Report

```yaml
test_report:
  suite: OrderExtractorTests
  execution_date: 2024-01-15
  duration_ms: 4523
  
  summary:
    total: 25
    passed: 23
    failed: 1
    skipped: 1
    
  by_category:
    unit:
      total: 15
      passed: 15
    integration:
      total: 5
      passed: 4
      failed: 1
    regression:
      total: 5
      passed: 4
    performance:
      total: 0
      skipped: 1
  
  failures:
    - test_id: TC-010
      category: integration
      error: "Timeout exceeded"
      details: "Response time 3200ms > 3000ms threshold"
      recommendation: "Optimize or increase timeout"
  
  coverage:
    requirements: 0.95
    edge_cases: 0.88
    error_cases: 0.92
  
  recommendation: "Proceed with fix for TC-010"
```

## Checklist

### Test Design

- [ ] Happy path covered
- [ ] Edge cases identified
- [ ] Error cases defined
- [ ] Security cases included
- [ ] Assertions specific

### Test Execution

- [ ] All tests run
- [ ] Results documented
- [ ] Failures analyzed
- [ ] Fixes verified
- [ ] Report generated

### Test Maintenance

- [ ] Tests reviewed quarterly
- [ ] Obsolete tests removed
- [ ] Coverage tracked
- [ ] False positives addressed

## Anti-Patterns

### 1. Weak Assertions

Tests that don't actually validate:

**Problem**: False passes, bugs in production.

**Solution**: Specific, meaningful assertions.

### 2. Brittle Tests

Tests that fail on unrelated changes:

**Problem**: Slow development, test distrust.

**Solution**: Test behavior, not implementation.

### 3. No Edge Cases

Only testing obvious cases:

**Problem**: Production failures on boundary conditions.

**Solution**: Systematic edge case coverage.

### 4. Manual Testing Only

No automated test coverage:

**Problem**: Inconsistent, unscalable, error-prone.

**Solution**: Automate all testable scenarios.

## Related Documents

- [01-Prompt-Engineering-Overview](01-Prompt-Engineering-Overview.md) — Framework introduction
- [06-Prompt-Review](06-Prompt-Review.md) — Review process
- [07-Prompt-Evaluation](07-Prompt-Evaluation.md) — Quality assessment
- [09-Prompt-Benchmarking](09-Prompt-Benchmarking.md) — Performance testing

## Future Evolution

- **v1.1**: Property-based testing framework
- **v1.2**: Mutation testing for prompts
- **v1.3**: Visual test design tools
- **v2.0**: AI-generated test cases
