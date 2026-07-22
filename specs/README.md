# Specifications Directory

Machine-readable specifications for AI systems and prompts.

## Overview

The `specs/` directory contains machine-readable specifications that complement the human-readable documentation in `docs/`. These specifications enable automation, tooling, and integration with external systems.

## Two Formats, One Source of Truth

### Human-Readable Documentation (`docs/`)

Human-readable content optimized for:

- **Learning**: Understanding concepts and principles
- **Reference**: Quick lookup of standards and guidelines
- **Collaboration**: Review and discussion among team members
- **Onboarding**: Training new team members

Examples:
- Engineering standards and best practices
- Architectural decision records (ADRs)
- Process documentation and runbooks
- Tutorial and guide content

### Machine-Readable Specifications (`specs/`)

Structured, programmatic content optimized for:

- **Automation**: Tool-driven validation and generation
- **Integration**: Connecting with external systems
- **Validation**: Automated compliance checking
- **Generation**: Code and configuration generation

Examples:
- Prompt specifications in YAML/JSON
- API schemas for prompt registries
- Validation rules and schemas
- Configuration templates

## Why Specifications Exist

### Enabling Automation

Specifications enable automated tooling:

```yaml
# Example: Automated prompt validation
specs/
  prompts/
    order-extractor.yaml    # Machine-readable spec
    sentiment-analyzer.yaml

# Tools can:
# - Validate prompts against schemas
# - Generate test cases from specifications
# - Check compliance with standards
# - Generate documentation from specs
```

### Ensuring Consistency

Specifications enforce structure:

- Consistent prompt templates
- Standardized metadata formats
- Validated schemas
- Predictable interfaces

### Supporting Integration

Specifications enable external integration:

- Prompt registries
- Model configuration systems
- AI factory pipelines
- Monitoring and observability tools

### Type Safety

Specifications provide type safety:

- Schema validation
- Completeness checking
- Type inference
- Error detection

## File Organization

```
specs/
├── README.md                    # This file
├── prompts/                     # Prompt specifications
│   ├── _schemas/               # Shared schemas
│   │   ├── prompt-schema.yaml
│   │   └── test-case-schema.yaml
│   ├── order-extractor.yaml
│   └── sentiment-analyzer.yaml
├── api/                         # API specifications
│   ├── prompt-registry.yaml
│   └── evaluation-api.yaml
└── config/                      # Configuration specs
    ├── model-config-schema.yaml
    └── evaluation-config.yaml
```

## Specification Types

### Prompt Specifications

Machine-readable definitions of prompts:

```yaml
# specs/prompts/order-extractor.yaml
apiVersion: ai-playbook/v1
kind: PromptSpec
metadata:
  id: PRMPT-ORDER-001
  name: Order Information Extractor
  version: "2.1.0"
spec:
  type: extraction
  input:
    - name: email_text
      type: string
      required: true
  output:
    schema: order-schema.yaml
  constraints:
    maxTokens: 500
    timeout: 5000
  quality:
    accuracy:
      minimum: 0.95
    latencyP95:
      maximum: 500
```

### Schema Specifications

Reusable schema definitions:

```yaml
# specs/prompts/_schemas/order-schema.yaml
$schema: https://json-schema.org/draft/2020-12/schema
type: object
properties:
  order_id:
    type: string
    pattern: "^ORD-[A-Z0-9]{5}$"
  items:
    type: array
    items:
      $ref: "#/$defs/LineItem"
  total:
    type: number
    minimum: 0
required:
  - order_id
  - items
$defs:
  LineItem:
    type: object
    properties:
      product:
        type: string
      quantity:
        type: integer
        minimum: 1
      price:
        type: number
        minimum: 0
    required:
      - product
      - quantity
      - price
```

## Future: AI-Factory Integration

The specifications directory is designed to support future AI-Factory integration:

### Planned Integrations

| Integration | Purpose | Status |
|-------------|---------|--------|
| **Prompt Registry** | Central prompt inventory | Planned |
| **Auto-Validation** | Automated spec compliance | Planned |
| **Test Generation** | Generate tests from specs | Planned |
| **Doc Generation** | Generate docs from specs | Planned |
| **Model Config** | Model configuration management | Planned |

### AI-Factory Pipeline

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   Author    │────►│  Specs/     │────►│   Validate  │
│  Prompt     │     │  Publish    │     │   Specs     │
└─────────────┘     └─────────────┘     └─────────────┘
                                              │
┌─────────────┐     ┌─────────────┐     ┌──────┴──────┐
│   Deploy    │◄────│   Generate  │◄────│   Approve   │
│  Prompt     │     │   Artifacts │     │   Specs     │
└─────────────┘     └─────────────┘     └─────────────┘
```

### Specification Lifecycle (Future)

1. **Author** → Create prompt and specification
2. **Validate** → Automated spec validation
3. **Review** → Human review of specs
4. **Approve** → Spec approved for use
5. **Generate** → Create deployment artifacts
6. **Deploy** → Deploy to target environment

## Relationship with Other Directories

### Relationship with `docs/`

| docs/ Content | specs/ Purpose |
|---------------|----------------|
| Design guides | Implementation specs |
| Best practices | Validation rules |
| Tutorials | Code examples |
| Runbooks | Automation scripts |

### Relationship with `adr/`

Architecture Decision Records document *why* decisions were made:

```markdown
<!-- adr/0012-prompt-versioning-strategy.md -->
# ADR 0012: Semantic Versioning for Prompts

## Decision
Use semantic versioning for prompt versions.

## Rationale
...

<!-- specs/prompts/_schemas/version-schema.yaml -->
version:
  type: semver
  pattern: MAJOR.MINOR.PATCH
```

### Relationship with `rfc/`

RFCs propose *changes* to specifications:

```markdown
<!-- docs/rfc/0003-multi-model-prompt-support.md -->
# RFC 0003: Multi-Model Prompt Support

## Proposal
Extend prompt spec to support multiple model targets.

## Specification
...

<!-- specs/prompts/_schemas/multi-model-schema.yaml -->
targets:
  type: array
  items:
    model: string
    config: model-config.yaml
```

## Best Practices

### Writing Specifications

1. **Be Precise**: Use exact types and constraints
2. **Be Complete**: Include all required fields
3. **Be Consistent**: Follow established patterns
4. **Be Validated**: Test against schemas
5. **Be Documented**: Link to human-readable docs

### Maintaining Specifications

1. **Keep in Sync**: Update specs when docs change
2. **Version Control**: Track specification changes
3. **Validate Early**: Catch errors before deployment
4. **Review Regularly**: Ensure accuracy over time
5. **Deprecate Gracefully**: Plan for spec evolution

### Schema Design

1. **Reuse**: Reference common schemas
2. **Compose**: Build complex from simple
3. **Document**: Add descriptions to fields
4. **Version**: Plan for schema evolution
5. **Validate**: Ensure schemas are valid

## Validation

Specifications should be validated regularly:

```bash
# Validate all specifications
make validate-specs

# Validate specific spec
validate-spec specs/prompts/order-extractor.yaml
```

## Future Evolution

- **v1.1**: Schema registry and discovery
- **v1.2**: Automated validation CI/CD
- **v1.3**: Specification versioning tools
- **v2.0**: AI-Factory pipeline integration

## Related Documentation

- [Prompt Engineering Overview](../docs/Prompt-Engineering/01-Prompt-Engineering-Overview.md)
- [Engineering Standards](../docs/Engineering/01-Engineering-Standards.md)
- [ADR Index](../adr/)
- [RFC Process](../docs/RFC/)
