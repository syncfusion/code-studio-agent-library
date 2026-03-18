---
name: full-workflow
agent: agent
description: Complete automated development workflow
---
# Full Development Workflow

Execute complete development pipeline from specification to deployment-ready code.

## Overview
This workflow chains multiple prompts to create a complete, tested, reviewed, and secured dashboard application from the specification.

## Workflow Phases

### Phase 1: Specification Quality Assurance
**Prompt:** `/lint-spec.prompt.md`

**Objectives:**
- Validate specification clarity and completeness
- Check for consistency and logical flow
- Verify technical feasibility
- Ensure testability of all requirements

**Success Criteria:**
- ✓ No critical specification issues
- ✓ All requirements are clear and testable
- ✓ Technical approach validated
- ✓ Ready for code generation

**If issues found:**
- Fix critical issues in specification
- Update specification file
- Re-run lint-spec.prompt.md
- Wait for completion before Phase 2

---

### Phase 2: Code Generation
**Prompt:** `/compile.prompt.md`

**Objectives:**
- Generate all source code files from specification
- Create project structure
- Generate mock data
- Build all components and services
- Ensure TypeScript strict mode compliance

**Files Created:**
```
src/
├── components/
│   ├── Dashboard.tsx
│   ├── MetricWidget.tsx
│   ├── ChartWidget.tsx
│   ├── LayoutGrid.tsx
│   ├── FilterPanel.tsx
│   ├── Header.tsx
│   └── Sidebar.tsx
├── services/
│   ├── dashboardService.ts
│   ├── dataService.ts
│   └── exportService.ts
├── types/
│   ├── dashboard.types.ts
│   ├── metrics.types.ts
│   └── widget.types.ts
├── hooks/
│   ├── usePolling.ts
│   ├── useDashboard.ts
│   └── useLocalStorage.ts
├── utils/
│   ├── formatters.ts
│   ├── generators.ts
│   └── calculations.ts
├── data/
│   └── mockData.ts
├── styles/
│   └── globals.css
├── App.tsx
└── main.tsx
```

**Success Criteria:**
- ✓ No TypeScript compilation errors
- ✓ All components render without errors
- ✓ Mock data loads correctly
- ✓ Responsive design verified
- ✓ Ready for testing

**If errors occur:**
- Check error messages
- Fix compilation issues
- Re-run compile.prompt.md
- Wait for completion before Phase 3

---

### Phase 3: Test Generation & Execution
**Prompt:** `/test.prompt.md`

**Objectives:**
- Generate comprehensive unit tests
- Generate integration tests
- Generate E2E test scenarios
- Ensure 80%+ code coverage
- Run test suite

**Test Coverage:**
```
tests/
├── unit/
│   ├── formatters.test.ts
│   ├── hooks.test.ts
│   ├── components.test.tsx
│   └── calculations.test.ts
├── integration/
│   ├── dashboard.test.tsx
│   ├── dataService.test.ts
│   └── exportService.test.ts
└── e2e/
    └── userFlows.test.tsx
```

**Success Criteria:**
- ✓ Test coverage > 80%
- ✓ All tests passing
- ✓ Tests execute in < 10 seconds
- ✓ No test warnings
- ✓ Ready for code review

**If test failures occur:**
- Review failing tests
- Fix implementation issues
- Re-run test.prompt.md
- Wait for all tests to pass before Phase 4

---

### Phase 4: Code Quality Review
**Prompt:** `/review.prompt.md`

**Objectives:**
- Review code against specification
- Verify coding standards
- Check performance requirements
- Validate accessibility
- Ensure best practices

**Review Focus:**
- Spec compliance: Features implemented as specified
- Code quality: TypeScript, no `any`, clean code
- Performance: Load times, responsiveness
- React best practices: Hooks, component design
- Accessibility: WCAG compliance
- Testing: Coverage and quality

**Success Criteria:**
- ✓ No critical issues
- ✓ No high-priority issues (spec compliance)
- ✓ Code matches specification
- ✓ Ready for merge

**If issues found:**
- Address all critical issues
- High-priority issues must be fixed
- Medium/low can be optional
- Fix issues in src/ files
- Re-run review.prompt.md
- Wait for approval before Phase 5

---

### Phase 5: Security Audit
**Prompt:** `/security.prompt.md`

**Objectives:**
- Analyze code for vulnerabilities
- Check OWASP Top 10
- Verify dependency security
- Review authentication/authorization
- Validate data protection

**Security Focus:**
- Injection vulnerabilities (XSS, SQL)
- Authentication & authorization
- Data protection & encryption
- API security
- Dependency vulnerabilities
- Error handling security

**Success Criteria:**
- ✓ No critical vulnerabilities
- ✓ No hardcoded secrets
- ✓ Secure error handling
- ✓ Dependencies audit passing
- ✓ Ready for deployment

**If security issues found:**
- Fix all critical vulnerabilities immediately
- Address high-priority security issues
- Update dependencies if needed
- Re-run security.prompt.md
- Wait for security clearance before Phase 6

---

### Phase 6: Final Verification & Deployment Ready
**Objectives:**
- Run final checks
- Build production bundle
- Verify all requirements met
- Generate deployment summary

**Verification Steps:**
```bash
# 1. Run lint
npm run lint

# 2. Run tests with coverage
npm run test:coverage

# 3. Build for production
npm run build

# 4. Verify build size
# Expected: < 1MB gzipped

# 5. Check no console errors/warnings
# Run in development mode and verify console
```

**Deployment Checklist:**
- ✓ All tests passing (80%+ coverage)
- ✓ No TypeScript errors
- ✓ No ESLint warnings
- ✓ Security audit passed
- ✓ Code review approved
- ✓ Production build successful
- ✓ Bundle size optimized
- ✓ No console errors
- ✓ Responsive design verified
- ✓ Accessibility checked

---

## Workflow Execution

### Option 1: Run Complete Workflow
**Single Command:**
```
/full-workflow.prompt.md
```

This executes all phases sequentially, waiting for each to complete before starting the next.

### Option 2: Run Individual Phases
Run phases independently as needed:

```
Phase 1: /lint-spec.prompt.md
Phase 2: /compile.prompt.md
Phase 3: /test.prompt.md
Phase 4: /review.prompt.md
Phase 5: /security.prompt.md
```

### Option 3: Resume from Phase
If a phase fails and is fixed:
```
/lint-spec.prompt.md       # Phase 1
/compile.prompt.md         # Phase 2
# Fix issues if any
/compile.prompt.md         # Re-run Phase 2
/test.prompt.md            # Phase 3
# Continue workflow...
```

---

## Success Criteria - Complete Workflow

After all phases complete successfully:

### Specification ✓
- Specification is clear, complete, and consistent
- All requirements are testable
- Technical feasibility validated

### Code ✓
- All features implemented per specification
- TypeScript strict mode compliance
- No `any` types or compiler errors
- Clean, well-organized code structure
- Responsive design implemented
- Accessibility standards met

### Testing ✓
- 80%+ code coverage
- All unit, integration, and E2E tests passing
- No test warnings
- Tests run in < 10 seconds

### Quality ✓
- Code review passed
- All critical/high issues resolved
- Coding best practices followed
- Performance targets met

### Security ✓
- No critical vulnerabilities
- No hardcoded secrets
- Secure error handling
- Dependencies up to date
- OWASP Top 10 addressed

### Deployment Ready ✓
- Production build successful
- Bundle size optimized (< 1MB gzipped)
- No console errors/warnings
- Ready for deployment

---

## Troubleshooting

### If Phase Fails
1. **Review error message** - Understand what went wrong
2. **Fix the issue** - Edit the relevant source files
3. **Re-run the phase** - Execute the same prompt again
4. **Wait for completion** - Don't skip to next phase until fixed

### Common Issues & Solutions

#### TypeScript Errors
```
Issue: "No such file or directory"
Fix: Check file paths in error, ensure all imports use correct paths
Re-run: /compile.prompt.md
```

#### Test Failures
```
Issue: "Test suite failed"
Fix: Check test output for specific failures, fix implementation
Re-run: /test.prompt.md
```

#### Code Review Issues
```
Issue: "Critical issues in code"
Fix: Update implementation per review, rerun compile if needed
Re-run: /review.prompt.md
```

#### Security Vulnerabilities
```
Issue: "Hardcoded secrets found"
Fix: Move to environment variables
Re-run: /security.prompt.md
```

---

## Workflow Timeline

| Phase | Time | Status |
|-------|------|--------|
| Lint Spec | ~5 min | Not started |
| Compile | ~10 min | Not started |
| Testing | ~5 min | Not started |
| Review | ~10 min | Not started |
| Security | ~5 min | Not started |
| **Total** | **~35 min** | **Ready to begin** |

---

## Next Steps After Workflow

Once workflow completes successfully:

1. **Deploy to staging environment**
2. **Manual QA testing** (if needed)
3. **Performance testing** in production-like environment
4. **Deploy to production**
5. **Monitor dashboards** for errors

---

## Dashboard is Ready! 🎉

When all phases pass:
- ✅ Specification validated
- ✅ Code generated and tested
- ✅ Quality reviewed
- ✅ Security audited
- ✅ **Ready for production use**

Your analytics dashboard is complete and ready to deploy!
