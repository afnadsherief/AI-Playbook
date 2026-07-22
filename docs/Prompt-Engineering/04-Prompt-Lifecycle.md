---
Status: Active
Version: 1.0
Owner: Engineering Team
Category: Prompt Engineering
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Prompt Lifecycle

Management of prompts from conception through retirement.

## Purpose

Define a systematic lifecycle for prompt management:

- Ensure consistent quality through defined stages
- Enable tracking and governance
- Support continuous improvement
- Facilitate compliance and auditing

## Scope

Applies to:

- All production prompts
- Critical business prompts
- Shared prompt libraries
- Prompt templates

## Core Principles

### 1. Stage Gating

Progress through defined stages with approval:

- Each stage has entry criteria
- Quality gates must pass before advancement
- Documentation required at each transition
- Stakeholder sign-off for stage completion

### 2. Continuous Improvement

Lifecycle supports iterative refinement:

- Feedback loops inform improvements
- Metrics drive optimization
- Lessons learned feed future design
- Anti-patterns documented and avoided

### 3. Traceability

Complete record of prompt evolution:

- Version history maintained
- Change rationale documented
- Author and reviewer attribution
- Audit trail for compliance

### 4. Retirement Planning

End-of-life handled systematically:

- Deprecation notice periods
- Migration path documentation
- Fallback strategies defined
- Legacy support when needed

## Engineering Standards

### Lifecycle Stages

```
┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐
│  Plan   │───►│Develop │───►│  Test   │───►│ Deploy  │
└─────────┘    └─────────┘    └─────────┘    └─────────┘
                                                     │
┌─────────┐    ┌─────────┐    ┌─────────┐            │
│ Retire  │◄───│ Monitor │◄───│ Evaluate│◄──────────┘
└─────────┘    └─────────┘    └─────────┘
```

| Stage | Duration | Primary Activity | Gate |
|-------|----------|-----------------|------|
| **Plan** | 1-3 days | Requirements and design | Approved design doc |
| **Develop** | 2-5 days | Implementation | Passing tests |
| **Test** | 3-7 days | Validation | Quality metrics met |
| **Deploy** | 1 day | Release | Deployment approval |
| **Monitor** | Ongoing | Observation | Anomaly detection |
| **Evaluate** | Periodic | Assessment | Performance review |
| **Retire** | 2-4 weeks | Deprecation | Migration complete |

### Stage Specifications

#### Plan Stage

**Activities:**
- Define requirements and acceptance criteria
- Identify dependencies and constraints
- Design prompt architecture
- Create initial documentation
- Assign ownership

**Deliverables:**
- Requirements document
- Design specification
- Initial test plan
- Risk assessment

**Exit Criteria:**
- Requirements approved
- Design reviewed
- Dependencies identified
- Owner assigned

#### Develop Stage

**Activities:**
- Implement prompt components
- Create unit tests
- Draft documentation
- Establish version control
- Set up monitoring

**Deliverables:**
- Working prompt implementation
- Unit tests
- Documentation draft
- Version-controlled code

**Exit Criteria:**
- Implementation complete
- Unit tests passing
- Documentation started
- Version tagged

#### Test Stage

**Activities:**
- Execute comprehensive test suite
- Perform quality assessment
- Conduct security review
- Run integration tests
- Validate against requirements

**Deliverables:**
- Test results
- Quality assessment
- Security review report
- Integration test results

**Exit Criteria:**
- All tests passing
- Quality metrics met
- Security review approved
- Requirements validated

#### Deploy Stage

**Activities:**
- Prepare deployment package
- Execute deployment
- Validate deployment
- Enable monitoring
- Notify stakeholders

**Deliverables:**
- Deployment record
- Validation results
- Monitoring configured
- Stakeholder notification

**Exit Criteria:**
- Deployment successful
- Validation passed
- Monitoring active
- Stakeholders notified

#### Monitor Stage

**Activities:**
- Track performance metrics
- Detect anomalies
- Collect usage data
- Identify degradation
- Trigger evaluation

**Deliverables:**
- Performance reports
- Anomaly alerts
- Usage analytics
- Health status

**Exit Criteria:**
- Anomaly detected
- Performance degraded
- Evaluation requested
- Scheduled review due

#### Evaluate Stage

**Activities:**
- Assess current performance
- Compare to baselines
- Identify improvement areas
- Recommend changes
- Plan optimization

**Deliverables:**
- Performance assessment
- Comparison report
- Improvement recommendations
- Optimization plan

**Exit Criteria:**
- Evaluation complete
- Recommendations documented
- Decision made (continue/improve/retire)
- Action plan approved

#### Retire Stage

**Activities:**
- Announce deprecation
- Migrate consumers
- Provide fallbacks
- Document retirement
- Archive artifacts

**Deliverables:**
- Deprecation notice
- Migration guide
- Fallback available
- Retirement record

**Exit Criteria:**
- All consumers migrated
- Fallback operational
- Documentation archived
- Retirement complete

## Workflow

### Lifecycle Management Process

1. **Initiate**
   - Submit request for new prompt
   - Assign to appropriate owner
   - Begin planning stage

2. **Progress**
   - Complete current stage
   - Request stage approval
   - Advance to next stage
   - Update tracking

3. **Monitor**
   - Track performance continuously
   - Detect and respond to issues
   - Collect feedback
   - Schedule evaluations

4. **Improve**
   - Identify optimization opportunities
   - Plan improvements
   - Implement changes
   - Validate improvements

5. **Retire**
   - Trigger retirement when needed
   - Execute retirement process
   - Archive appropriately
   - Update registry

## Examples

### Lifecycle Tracking Record

```yaml
prompt_id: PRMPT-ORDER-001
name: Order Information Extractor
owner: data-engineering@company.com

lifecycle:
  created: 2024-01-01
  current_stage: monitor
  
  stages:
    plan:
      started: 2024-01-01
      completed: 2024-01-03
      approved_by: tech-lead@company.com
    
    develop:
      started: 2024-01-04
      completed: 2024-01-08
      version: 1.0.0
    
    test:
      started: 2024-01-09
      completed: 2024-01-15
      test_results: 98% pass rate
      quality_score: 0.92
    
    deploy:
      started: 2024-01-16
      completed: 2024-01-16
      environment: production
    
    monitor:
      started: 2024-01-16
      last_review: 2024-01-20
      performance: stable
      issues: 0

next_review: 2024-04-16
retirement_date: null
```

## Checklist

### Plan Stage

- [ ] Requirements documented
- [ ] Design approved
- [ ] Owner assigned
- [ ] Dependencies identified
- [ ] Risk assessment completed

### Develop Stage

- [ ] Implementation complete
- [ ] Unit tests written
- [ ] Documentation started
- [ ] Version tagged
- [ ] Peer reviewed

### Test Stage

- [ ] Test suite executed
- [ ] Quality metrics met
- [ ] Security reviewed
- [ ] Integration tested
- [ ] Requirements validated

### Deploy Stage

- [ ] Deployment approved
- [ ] Successfully deployed
- [ ] Validated in environment
- [ ] Monitoring enabled
- [ ] Stakeholders notified

### Monitor Stage

- [ ] Performance tracked
- [ ] Anomalies detected
- [ ] Usage logged
- [ ] Alerts configured
- [ ] Dashboards updated

## Anti-Patterns

### 1. Skipping Stages

Bypassing required lifecycle stages:

**Problem**: Quality issues, missing documentation, untracked changes.

**Solution**: Enforce stage gates, automate checks.

### 2. No Retirement Planning

Leaving prompts in production indefinitely:

**Problem**: Accumulated technical debt, security risks.

**Solution**: Define retirement criteria, plan deprecation.

### 3. Insufficient Monitoring

Deploying without observability:

**Problem**: Unknown issues, silent failures.

**Solution**: Enable comprehensive monitoring before deploy.

### 4. Missing Documentation

Incomplete or outdated documentation:

**Problem**: Knowledge loss, onboarding friction.

**Solution**: Require documentation at each stage.

## Related Documents

- [01-Prompt-Engineering-Overview](01-Prompt-Engineering-Overview.md) — Framework introduction
- [05-Prompt-Versioning](05-Prompt-Versioning.md) — Version control
- [06-Prompt-Review](06-Prompt-Review.md) — Review process
- [07-Prompt-Evaluation](07-Prompt-Evaluation.md) — Assessment criteria

## Future Evolution

- **v1.1**: Automated lifecycle tracking
- **v1.2**: Lifecycle analytics dashboard
- **v1.3**: Predictive retirement warnings
- **v2.0**: Automated stage progression
