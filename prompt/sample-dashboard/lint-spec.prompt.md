---
name: compile
agent: agent
description: Lint specification for quality and completeness
---

# Lint Specification

## Task
Review `dashboard.prompt.md` specification for quality, clarity, completeness, and technical feasibility.

## Clarity Review

### Requirements Clarity
- [ ] All requirements unambiguous?
- [ ] Technical terms defined?
- [ ] Examples provided for complex features?
- [ ] No contradicting statements?
- [ ] Acceptance criteria are testable?
- [ ] "Should", "must", "may" used correctly?

#### Issues to Check
```
UNCLEAR: "Dashboard should be fast"
CLEAR: "Dashboard should load in < 2 seconds with < 1MB initial bundle"

UNCLEAR: "Support multiple charts"
CLEAR: "Support Line Chart, Bar Chart, and Pie Chart with configuration options"

UNCLEAR: "Good performance"
CLEAR: "Initial page load: < 2s | Widget update: < 500ms | Export: < 2s"
```

### Technical Definition
- [ ] All APIs documented?
- [ ] Data structures clearly defined with types?
- [ ] UI components described with states?
- [ ] Edge cases explained?
- [ ] Error scenarios covered?

### Examples Quality
- [ ] Code examples are correct?
- [ ] Mock data examples realistic?
- [ ] UI examples match implementation?
- [ ] User flow examples complete?

## Consistency Review

### Terminology
- [ ] Same terms used throughout?
- [ ] Abbreviations defined once and used consistently?
- [ ] No synonyms for same concept?
  - Example: "export" vs "download" vs "save"
- [ ] Naming conventions consistent?

### Formatting
- [ ] Consistent heading levels?
- [ ] Consistent code block formatting?
- [ ] Table structures aligned?
- [ ] Link formats consistent?
- [ ] Date/time formats consistent?

### Structure
- [ ] Logical flow from intro to details?
- [ ] No duplicate requirements?
- [ ] Related requirements grouped?
- [ ] Dependencies between features clear?
- [ ] Hierarchy makes sense?

### Style
- [ ] Consistent voice (active vs passive)?
- [ ] Tense consistent (present vs future)?
- [ ] Professional tone throughout?
- [ ] No informal language?

## Completeness Review

### Coverage
- [ ] All features documented?
- [ ] All user roles addressed?
- [ ] All integrations specified?
- [ ] All data types defined?
- [ ] All APIs listed?
- [ ] All error cases covered?

### Test Coverage
- [ ] Acceptance criteria for each feature?
- [ ] Test cases identified?
- [ ] Edge cases documented?
- [ ] Performance requirements stated?
- [ ] Browser compatibility needs?

### Documentation
- [ ] Architecture explained?
- [ ] Tech stack justified?
- [ ] Project structure defined?
- [ ] Build process documented?
- [ ] Deployment strategy clear?

### Missing Sections
- [ ] Success criteria for project?
- [ ] Definition of done?
- [ ] Rollback procedures?
- [ ] Monitoring requirements?
- [ ] Support procedures?

## Technical Feasibility Review

### Architecture
- [ ] Architecture realistic given constraints?
- [ ] Scalability addressed?
- [ ] Technology choices compatible?
- [ ] No architectural contradictions?

### Tech Stack
- [ ] All technologies well-supported?
- [ ] Tools work together?
- [ ] Learning curve reasonable?
- [ ] Community support available?
- [ ] Alternative options considered?

```
 React 18 + TypeScript: Mature, well-documented
 Recharts: Purpose-built for dashboards
 Tailwind CSS: Well-integrated with React
 Vite: Fast, modern build tool
```

### Timeline
- [ ] Requirements achievable in scope?
- [ ] No scope creep evident?
- [ ] Realistic effort estimation possible?
- [ ] Priorities clear?
- [ ] Phasing makes sense?

### Resources
- [ ] Skills described available?
- [ ] Tools specified are accessible?
- [ ] Licenses clear (if commercial)?
- [ ] Infrastructure requirements realistic?

### Dependencies
- [ ] External service requirements clear?
- [ ] API contracts defined?
- [ ] Data sources identified?
- [ ] No circular dependencies?

## Quality Issues Classification

### Critical 
- Contradicting requirements
- Impossible to implement technically
- Missing acceptance criteria
- Ambiguous core functionality
- Security requirements missing

### Warning 
- Incomplete feature description
- Unclear terminology
- Missing edge cases
- Performance targets unrealistic
- Insufficient test requirements

### Info 
- Style improvements
- Formatting suggestions
- Documentation enhancements
- Best practice recommendations
- Consistency adjustments

## Issues Format

```
**Severity:**  Critical |  Warning |  Info
**Type:** Clarity | Completeness | Consistency | Feasibility
**Location:** Section [X.X] - Feature Name
**Line:** [line number]

**Issue:**
Describe the problem

**Example:**
Show problematic text or code

**Recommendation:**
How to improve it

**Impact:**
Why this matters
```

## Output Report

### Specification Lint Report
```
# Dashboard Specification Lint Report

## Summary
- Total Issues: [count]
- Critical: [count]
- Warnings: [count]
- Info: [count]

## Specification Status: [APPROVED/APPROVED WITH NOTES/NEEDS REVISION/REJECTED]

## Critical Issues (Must Fix)
1. [Issue]
   - Section: [X.X]
   - Problem: [Description]
   - Fix: [Recommendation]

## Warnings (Should Fix)
[Similar format to critical]

## Info (Nice to Have)
[Similar format to critical]

## Consistency Check
- /✗ Terminology consistent
- /✗ Formatting consistent
- /✗ Structure logical
- /✗ Voice consistent

## Completeness Check
- /✗ All features covered
- /✗ All roles addressed
- /✗ Test requirements defined
- /✗ Architecture explained
- /✗ Tech stack justified

## Feasibility Check
- /✗ Architecturally sound
- /✗ Tech stack compatible
- /✗ Timeline realistic
- /✗ Resources available
- /✗ Dependencies clear

## Next Steps
1. Address critical issues
2. Resolve warnings
3. Re-submit for approval
4. Ready for development
```

## Lint Rules

### Rule: REQUIREMENT-CLARITY
Every requirement must be testable and measurable.
```
 "Support all devices"
 "Support desktop (1024px+), tablet (768-1023px), mobile (< 768px)"
```

### Rule: TERM-CONSISTENCY
Define each term once, use consistently.
```
DON'T use: export, download, save (for same feature)
DO use: "export" (defined in section X.X)
```

### Rule: ACCEPTANCE-CRITERIA
Each feature needs acceptance criteria.
```
Feature: Real-Time Metric Widget
Acceptance Criteria:
1. [ ] Displays metric name
2. [ ] Shows current value
3. [ ] Updates without page refresh
```

### Rule: TECH-JUSTIFICATION
Justify technology choices.
```
 "Use React"
 "Use React 18 for component composition, hooks support, and ecosystem maturity"
```

### Rule: PERFORMANCE-TARGETS
All performance requirements are measurable.
```
 "Fast page load"
 "Initial load < 2 seconds on 4G network, < 1MB bundle"
```

## Success Criteria
-  No critical issues remain
-  Specification is clear and testable
-  Terminology consistent throughout
-  Complete and ready for development
-  Technical approach validated
-  Ready for team review/approval
