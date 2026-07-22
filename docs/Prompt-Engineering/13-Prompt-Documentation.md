---
Status: Active
Version: 1.0
Owner: Engineering Team
Category: Prompt Engineering
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Prompt Documentation

Standards and practices for documenting prompts.

## Purpose

Establish documentation practices:

- Capture design decisions
- Enable knowledge transfer
- Support maintenance
- Facilitate collaboration

## Scope

Applies to:

- Individual prompts
- Prompt libraries
- Templates
- System documentation

## Core Principles

### 1. Document Intent

Capture why, not just what:

- Design rationale
- Decision context
- Assumption documentation
- Constraint explanation

### 2. Keep Current

Documentation must be accurate:

- Update on change
- Version alongside code
- Review periodically
- Remove outdated content

### 3. Enable Reuse

Documentation supports sharing:

- Clear usage patterns
- Dependency information
- Integration examples
- Configuration guidance

### 4. Structured Approach

Consistent documentation structure:

- Standard templates
- Required sections
- Clear formatting
- Searchable content

## Engineering Standards

### Documentation Types

| Type | Audience | Purpose |
|------|----------|---------| 
| **Design Doc** | Developers | Explain design and rationale |
| **API Doc** | Integrators | Guide usage and integration |
| **Runbook** | Operators | Support operations and debugging |
| **Changelog** | All | Track changes over time |

### Documentation Structure

#### Prompt Design Document

```yaml
design_document:
  header:
    prompt_id: string
    name: string
    version: string
    author: string
    created: date
    updated: date
    status: draft|active|deprecated|retired
  
  overview:
    purpose: "What this prompt does"
    scope: "Boundaries and limitations"
    classification: "Risk level"
  
  design:
    requirements: []
    architecture: string
    components: []
    dependencies: []
    constraints: []
  
  behavior:
    inputs: []
    outputs: []
    edge_cases: []
    error_handling: []
  
  quality:
    metrics: []
    targets: []
    test_coverage: percentage
  
  lifecycle:
    created: date
    changes: []
    deprecation_date: date|null
  
  review:
    last_review: date
    reviewers: []
    approvals: []
  
  references:
    - related_prompts: []
    - related_docs: []
    - external_links: []
```

#### API Documentation

```yaml
api_documentation:
  endpoint:
    path: string
    method: POST
    description: string
  
  request:
    parameters: []
    body_schema: string
    headers: []
    authentication: string
  
  response:
    success_schema: string
    error_schemas: []
    status_codes: []
  
  examples:
    - request_example: {}
      response_example: {}
  
  usage:
    best_practices: []
    limitations: []
    rate_limits: string
  
  errors:
    - code: string
      message: string
      resolution: string
```

### Documentation Checklist

```yaml
completeness:
  - [ ] Purpose clearly stated
  - [ ] Input/output documented
  - [ ] Examples provided
  - [ ] Edge cases documented
  - [ ] Error handling explained
  - [ ] Dependencies listed
  - [ ] Version tracked
  - [ ] Author recorded

quality:
  - [ ] No broken links
  - [ ] Consistent formatting
  - [ ] Clear structure
  - [ ] Accurate information
  - [ ] Current version

maintenance:
  - [ ] Last updated date
  - [ ] Change history
  - [ ] Review schedule
  - [ ] Owner assigned
```

## Workflow

### Documentation Process

```
Create → Review → Publish → Maintain → Archive
```

### Documentation Lifecycle

1. **Create**
   - Use templates
   - Fill required sections
   - Include examples
   - Document decisions

2. **Review**
   - Technical accuracy check
   - Completeness review
   - Clarity assessment
   - Approval

3. **Publish**
   - Add to documentation system
   - Index appropriately
   - Notify stakeholders
   - Link from code

4. **Maintain**
   - Update on changes
   - Review periodically
   - Fix issues found
   - Improve based on feedback

5. **Archive**
   - Mark as historical
   - Keep for reference
   - Update links
   - Remove from active

## Examples

### Complete Documentation Example

```yaml
prompt_documentation:
  id: PRMPT-ORDER-001
  name: Order Information Extractor
  version: v2.1.0
  status: active
  
  # Header
  header:
    author: engineering@company.com
    owner: data-engineering-team
    created: 2024-01-01
    updated: 2024-01-15
    reviewed: 2024-01-15
    classification: high
  
  # Overview
  overview:
    purpose: |
      Extract structured order information from customer 
      support emails containing order-related content.
    scope: |
      - Extracts order IDs matching pattern ORD-XXXXX
      - Extracts line items with product, quantity, price
      - Calculates order totals
      - Does NOT process payment information
    classification: high
    
  # Design
  design:
    requirements:
      - R-001: Extract order ID with 95% accuracy
      - R-002: Handle partial information gracefully
      - R-003: Return structured JSON output
      - R-004: Process within 500ms p95 latency
    
    architecture: |
      Single-purpose prompt with modular components.
      Uses template-based composition for flexibility.
      
    components:
      - OrderIDExtractor: Extracts order ID
      - LineItemParser: Parses product, quantity, price
      - TotalCalculator: Computes order total
      - OutputFormatter: Produces JSON output
    
    dependencies:
      - None (standalone)
      
    constraints:
      - Input: Plain text email content
      - Output: Valid JSON only
      - Latency: < 500ms p95
  
  # Behavior
  behavior:
    inputs:
      - name: email_text
        type: string
        required: true
        description: Raw email content
        
    outputs:
      - name: order_id
        type: string|null
        format: "ORD-XXXXX"
        
      - name: items
        type: array
        items:
          - product: string
            quantity: integer
            price: number
            
      - name: total
        type: number|null
        
    edge_cases:
      - Empty input: Return nulls
      - Missing order ID: Return null, continue processing
      - Invalid price: Set price to null
      - Multiple orders: Return first only
      
    error_handling:
      - Malformed input: Return error object with message
      - Timeout: Return partial results with flag
      - Validation failure: Return errors array
  
  # Quality
  quality:
    metrics:
      - accuracy: 0.967
      - precision: 0.998
      - latency_p95: 342ms
      
    targets:
      - accuracy: ">= 0.95"
      - precision: ">= 0.99"
      - latency_p95: "<= 500ms"
      
    test_coverage: 0.92
  
  # Version History
  versions:
    v1.0.0:
      date: 2024-01-01
      changes: "Initial release"
      
    v2.0.0:
      date: 2024-02-01
      changes: |
        - Added multi-item support
        - Breaking change to output structure
        
    v2.1.0:
      date: 2024-01-15
      changes: |
        - Added confidence scores
        - Improved partial order handling
  
  # Usage
  usage:
    integration: |
      POST /api/v1/extract/order
      Content-Type: application/json
      
      {
        "email_text": "..."
      }
      
    examples:
      - input: "Order ORD-12345: 2x Widget at $10"
        output: |
          {
            "order_id": "ORD-12345",
            "items": [{"product": "Widget", "quantity": 2, "price": 10}],
            "total": 20
          }
```

## Checklist

### Documentation Creation

- [ ] Template applied
- [ ] Required sections complete
- [ ] Examples provided
- [ ] Dependencies listed
- [ ] Version recorded
- [ ] Author assigned

### Documentation Review

- [ ] Technical accuracy verified
- [ ] Completeness checked
- [ ] Clarity assessed
- [ ] Links validated
- [ ] Approved by owner

### Documentation Maintenance

- [ ] Updated on changes
- [ ] Reviewed quarterly
- [ ] Outdated content removed
- [ ] Links maintained

## Anti-Patterns

### 1. No Documentation

Releasing without docs:

**Problem**: Unusable, unsupportable.

**Solution**: Require documentation before release.

### 2. Outdated Documentation

Not updating on changes:

**Problem**: Misleading, causes errors.

**Solution**: Version docs with code.

### 3. Incomplete Examples

Generic, useless examples:

**Problem**: Doesn't help users.

**Solution**: Include real, diverse examples.

### 4. Inconsistent Structure

Different formats across docs:

**Problem**: Hard to find information.

**Solution**: Use standard templates.

## Related Documents

- [01-Prompt-Engineering-Overview](01-Prompt-Engineering-Overview.md) — Framework introduction
- [04-Prompt-Lifecycle](04-Prompt-Lifecycle.md) — Lifecycle stages
- [05-Prompt-Versioning](05-Prompt-Versioning.md) — Version control
- [06-Prompt-Review](06-Prompt-Review.md) — Review process

## Future Evolution

- **v1.1**: Auto-generated documentation from code
- **v1.2**: Interactive documentation
- **v1.3**: Documentation validation tools
- **v2.0**: AI-assisted documentation
