---
name: code-review
agent: agent
description: Review code for quality and spec compliance
---
# Code Review: Spec Compliance & Quality

## Task
Review the implementation in `src/` against `dashboard.prompt.md`

## Review Checklist

### Spec Compliance
- [ ] All required components implemented?
- [ ] All data types match specification?
- [ ] All features from spec are coded?
- [ ] Mock data matches spec examples?
- [ ] File structure matches planned layout?
- [ ] All acceptance criteria met?

### Code Quality
- [ ] TypeScript strict mode enforced?
- [ ] No `any` types used?
- [ ] Components are reusable and composable?
- [ ] Clear, descriptive naming conventions?
- [ ] Functions under 50 lines?
- [ ] Proper error handling implemented?
- [ ] No hardcoded values (use constants)?
- [ ] Consistent code formatting?

### Performance
- [ ] Initial load < 2 seconds?
- [ ] Polling updates < 500ms?
- [ ] Filter changes < 1 second?
- [ ] Export < 2 seconds?
- [ ] No unnecessary re-renders?
- [ ] Proper cleanup in useEffect?

### React & TypeScript Best Practices
- [ ] Proper PropTypes or TypeScript types?
- [ ] Hooks used correctly?
- [ ] No console warnings?
- [ ] Proper dependency arrays in useEffect?
- [ ] Event handlers properly bound?
- [ ] Memory leaks prevented?

### Accessibility
- [ ] Proper semantic HTML?
- [ ] ARIA labels where needed?
- [ ] Keyboard navigation supported?
- [ ] Color contrast sufficient?
- [ ] Images have alt text?

### Responsive Design
- [ ] Mobile layout works (< 768px)?
- [ ] Tablet layout works (768-1024px)?
- [ ] Desktop layout works (> 1024px)?
- [ ] No horizontal scroll on mobile?
- [ ] Touch-friendly button sizes?

### Testing
- [ ] Test coverage > 80%?
- [ ] Tests follow naming convention?
- [ ] All edge cases tested?
- [ ] Error scenarios tested?
- [ ] Performance tests included?

## Code Issues Format

For each issue found:

### Issue Template
```
**Type:** Bug | Warning | Suggestion
**Location:** src/components/MetricWidget.tsx (line 45)
**Severity:** Critical | High | Medium | Low
**Description:** 
What is the issue and why is it a problem?

**Example:**
const value = calculateTrend(data) // Potential undefined access

**Fix:**
const value = calculateTrend(data ?? [])

**Reference:** Dashboard spec section 1.2, React best practices
```

## Output Format

### Summary Report
```
# Code Review Report

## Overview
- Total Issues: [count]
- Critical: [count]
- High: [count]
- Medium: [count]
- Low: [count]

## Ready to Merge: [YES/NO]

If NO, list blocking issues that must be fixed before merge.

## Issues by File

### src/components/MetricWidget.tsx
- [Issue 1]
- [Issue 2]

### src/services/dataService.ts
- [Issue 3]
- [Issue 4]

## Recommendations
- [Improvement suggestion 1]
- [Improvement suggestion 2]
- [Performance optimization]

## Positives
- [What's working well]
- [Good patterns observed]
- [Clean implementation in X area]

## Next Steps
1. Address blocking issues
2. Optional: Consider recommendations
3. Re-run review after fixes
4. Merge when all critical/high fixed
```

## Red Flags (Always Critical)

- Unused imports
- Console.log in production code
- TODO/FIXME comments
- Inline CSS/magic numbers
- Missing error boundaries
- Unhandled promise rejections
- Memory leaks in useEffect
- Props drilling (more than 2 levels)
- Type errors (any types)
- Missing specifications

## Green Flags (Positive Patterns)

- Strong TypeScript types
- Custom hooks for reusability
- Consistent error handling
- Comprehensive test coverage
- Responsive design
- Accessible components
- Clean component composition
- Well-organized services
- Performance optimized

## Success Criteria
- ✓ No critical issues
- ✓ All high priority issues addressed
- ✓ Code matches spec requirements
- ✓ Ready for merge/deployment
