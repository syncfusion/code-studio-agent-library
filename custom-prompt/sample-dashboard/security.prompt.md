---
name: security-audit
agent: agent
description: Security analysis and threat modeling
---
# Security Audit

## Task
Perform security analysis on specification and source code for the dashboard application.

## Specification Security Review

### Authentication & Authorization
- [ ] Authentication mechanism defined?
- [ ] Role-based access control (RBAC) implemented?
  - [ ] Admin role restrictions clear?
  - [ ] Manager role permissions defined?
  - [ ] Viewer role limits enforced?
- [ ] Session management requirements specified?
- [ ] Token expiration policies defined?
- [ ] Permission inheritance clear?

### Data Protection
- [ ] Sensitive data identification documented?
- [ ] Encryption requirements specified?
- [ ] Data retention policies defined?
- [ ] PII handling procedures clear?
- [ ] Export data security addressed?

### API Security
- [ ] Rate limiting requirements specified?
- [ ] Input validation requirements defined?
- [ ] Output encoding requirements?
- [ ] API versioning strategy?
- [ ] Backward compatibility considerations?

### Logging & Monitoring
- [ ] Audit logging requirements?
- [ ] Security event logging specified?
- [ ] Log retention policies?
- [ ] Monitoring alert thresholds?
- [ ] Incident response procedures?

## Code Security Review

### Injection Vulnerabilities
- [ ] SQL injection: No direct DB queries in frontend (OK for mock data)
- [ ] XSS prevention: React escapes by default ✓
- [ ] Template injection: Not applicable
- [ ] Command injection: Check eval(), exec() usage
- [ ] Check for dangerouslySetInnerHTML usage

```typescript
// ✓ SAFE
<div>{userData.name}</div>

// ✗ DANGEROUS
<div dangerouslySetInnerHTML={{__html: userData.name}} />
```

### Authentication & Authorization
- [ ] JWT tokens: Check token storage (localStorage vs sessionStorage)
- [ ] Token validation on each request?
- [ ] Protected routes properly guarded?
- [ ] Role checks enforced on client-side?
- [ ] Sensitive operations require role verification?

```typescript
// Check: Is auth token stored securely?
// localStorage: Vulnerable to XSS
// sessionStorage: Better, but still at risk
// HttpOnly cookies: Preferred (not in SPA)
```

### Cross-Site Request Forgery (CSRF)
- [ ] State-changing operations use POST/PUT/DELETE?
- [ ] CSRF tokens included in forms?
- [ ] SameSite cookie attribute set?
- [ ] Origin verification on backend?

### Data Security
- [ ] Sensitive data logged? ✗ Should not log passwords/tokens
- [ ] PII exposed in URL parameters? 
- [ ] Data encrypted in transit (HTTPS)?
- [ ] Sensitive data not stored in localStorage?

```typescript
// ✗ DANGEROUS
console.log('User:', user); // May include sensitive data
localStorage.setItem('apiKey', apiKey); // Exposed to XSS

// ✓ SAFER
console.log('User action completed'); // Generic log
// Use HttpOnly cookies for tokens
```

### Dependency Vulnerabilities
- [ ] npm audit passes?
- [ ] No known vulnerabilities in dependencies?
- [ ] Dependencies regularly updated?
- [ ] Lock file committed to version control?
- [ ] Outdated packages identified?

### Client-Side Validation
- [ ] All inputs validated on server too?
- [ ] Client validation doesn't expose sensitive logic?
- [ ] File upload validation in place?
- [ ] File type verification implemented?

### Error Handling
- [ ] Errors don't expose stack traces to users?
- [ ] Error messages are generic for security?
- [ ] Sensitive data not in error messages?

```typescript
// ✗ DANGEROUS
catch (error) {
  alert(error.message); // May expose database schema
}

// ✓ SAFER
catch (error) {
  console.error('Database error:', error);
  alert('An error occurred. Please try again.');
}
```

### Third-Party Libraries
- [ ] Charting library (Recharts) security vetted?
- [ ] No XSS vulnerabilities in dependencies?
- [ ] Icons library (Lucide React) safe?
- [ ] CSS framework (Tailwind) secure?

### Environment Variables
- [ ] No API keys hardcoded?
- [ ] .env files not committed?
- [ ] Environment variables properly typed?
- [ ] Development/production configs separated?

```typescript
// ✗ DANGEROUS
const API_KEY = "sk-abc123"; // Hardcoded

// ✓ SAFER
const API_KEY = process.env.REACT_APP_API_KEY;
```

### Export Functionality Security
- [ ] PDF export doesn't include sensitive user data?
- [ ] CSV export filtered by user permissions?
- [ ] Export includes appropriate disclaimers?
- [ ] Export audit logged?
- [ ] File download properly secured?

### Responsive Design Security
- [ ] Mobile view doesn't expose data unintentionally?
- [ ] Touch events properly validated?
- [ ] No sensitive data in data attributes?

## Vulnerability Classification

### Critical ⛔
- SQL/XSS injection
- Authentication bypass
- Privilege escalation
- Hardcoded secrets
- Unencrypted sensitive data

### High ⚠️
- Weak input validation
- Inadequate access control
- Missing rate limiting
- Exposed sensitive errors
- CSRF vulnerabilities

### Medium ⚡
- Dependency vulnerabilities
- Missing security headers
- Weak error handling
- Insufficient logging

### Low ℹ️
- Security best practice deviations
- Code quality improvements
- Documentation gaps

## Output Format

### Security Audit Report
```
# Security Audit Report

## Summary
- Total Issues: [count]
- Critical: [count]
- High: [count]
- Medium: [count]
- Low: [count]

## Risk Assessment: [CRITICAL/HIGH/MEDIUM/LOW]

## Critical Issues (Must Fix)
1. [Issue]
   - Location: File, line number
   - Risk: Explanation
   - Fix: Recommendation

## High Priority Issues
[List similar to critical]

## Recommendations
- [Security best practice 1]
- [Security best practice 2]
- [Compliance requirement]

## Compliance Checklist
- [ ] OWASP Top 10 covered
- [ ] GDPR considerations addressed
- [ ] Data classification complete
- [ ] Access control enforced
- [ ] Audit logging implemented
- [ ] Error handling secure

## Next Steps
1. Fix critical issues immediately
2. Address high priority before deployment
3. Schedule regular security reviews
4. Implement continuous dependency scanning
5. Add security testing to CI/CD
```

## Success Criteria
- ✓ No critical vulnerabilities
- ✓ No hardcoded secrets
- ✓ Proper access controls
- ✓ Secure error handling
- ✓ Dependencies up to date
- ✓ Security best practices followed
