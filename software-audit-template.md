# Software Audit Template for Technical Due Diligence

A structured template for auditing an existing codebase, whether you are assessing a potential acquisition, reviewing a vendor's work, or evaluating your own software health. For hands-on audit support, visit [ajairu.dev](https://ajairu.dev).

## How to use this template

Copy this document and fill in each section. The goal is an honest assessment, not a rubber stamp. If you do not know an answer, say "unknown" and flag it for investigation. Rate each area on a scale of 1 (critical issues) to 5 (excellent).

---

## 1. Project overview

| Field | Value |
|-------|-------|
| Project name | |
| Purpose | |
| Tech stack (languages, frameworks, databases) | |
| Age of codebase | |
| Team size (current and historical) | |
| Repository location | |
| Production URL (if applicable) | |
| Last significant release date | |

**Overall health rating:** 1 2 3 4 5

## 2. Code quality

### Structure and organisation
- [ ] Repository has a clear directory structure
- [ ] Separation of concerns (logic, data, presentation)
- [ ] No monolithic files exceeding 500 lines
- [ ] Consistent naming conventions
- [ ] Dead code and commented-out blocks are minimal

### Code style and standards
- [ ] Linter/formatter is configured and enforced
- [ ] Consistent code style across the codebase
- [ ] No obvious anti-patterns (god objects, deep nesting, duplicated logic)
- [ ] Dependencies are current and not abandoned

### Documentation
- [ ] README exists and is accurate
- [ ] Code comments explain "why", not "what"
- [ ] API documentation exists (OpenAPI/Swagger or equivalent)
- [ ] Architecture decision records or design docs exist for major decisions
- [ ] Setup instructions are complete and work on a fresh machine

**Code quality rating:** 1 2 3 4 5

## 3. Testing

| Aspect | Status | Notes |
|--------|--------|-------|
| Unit tests exist | Yes/No | |
| Unit test coverage % | | |
| Integration tests exist | Yes/No | |
| End-to-end tests exist | Yes/No | |
| Tests run in CI | Yes/No | |
| Tests are maintained (not failing or skipped) | Yes/No | |
| Test data is realistic | Yes/No | |

**Testing rating:** 1 2 3 4 5

## 4. Version control and CI/CD

### Version control
- [ ] Git is used
- [ ] Commit history is meaningful (not all "fix" or "wip")
- [ ] Branching strategy is defined and followed
- [ ] Pull requests or code reviews are used
- [ ] No secrets or credentials committed to history

### CI/CD
- [ ] Automated build pipeline exists
- [ ] Pipeline runs tests on every commit
- [ ] Automated deployment is configured
- [ ] Deployment is reproducible (not manual server changes)
- [ ] Rollback strategy exists

**Version control and CI/CD rating:** 1 2 3 4 5

## 5. Security

### Authentication and authorisation
- [ ] Authentication is implemented and enforced
- [ ] Authorisation checks are applied at the right level
- [ ] Passwords are hashed (bcrypt, argon2, or equivalent)
- [ ] Session management is secure
- [ ] API keys and secrets are stored securely (not in code or plaintext config)

### Data protection
- [ ] Personal data is identified and handled per UK GDPR requirements
- [ ] Data at rest is encrypted (if applicable)
- [ ] Data in transit uses HTTPS/TLS
- [ ] PII is not logged in application logs
- [ ] Data retention policy exists and is followed

### Dependencies and vulnerabilities
- [ ] Dependency scanning is in place
- [ ] Known vulnerabilities are tracked and patched
- [ ] Dependencies are pinned to specific versions
- [ ] No unnecessary or unused dependencies

**Security rating:** 1 2 3 4 5

## 6. Architecture and scalability

- [ ] Architecture is documented
- [ ] System can handle current load comfortably
- [ ] Horizontal scaling is possible (or vertical scaling is sufficient and documented)
- [ ] Database queries are efficient (no N+1 problems, indexes in place)
- [ ] Caching is used where appropriate
- [ ] Error handling is robust (graceful degradation, not crashes)
- [ ] Logging is structured and useful for debugging
- [ ] Monitoring and alerting are in place

**Architecture rating:** 1 2 3 4 5

## 7. Infrastructure and deployment

| Aspect | Status | Notes |
|--------|--------|-------|
| Infrastructure as code (Terraform, CloudFormation, etc.) | Yes/No | |
| Environment parity (dev/staging/prod are similar) | Yes/No | |
| Zero-downtime deployments | Yes/No | |
| Backup strategy | | |
| Disaster recovery plan | | |
| Monitoring tools | | |
| Uptime track record | | |

**Infrastructure rating:** 1 2 3 4 5

## 8. Technical debt

| Type | Severity | Notes |
|------|----------|-------|
| Outdated frameworks/libraries | Low/Med/High | |
| Deprecated APIs in use | Low/Med/High | |
| Known bugs not tracked | Low/Med/High | |
| Missing tests for critical paths | Low/Med/High | |
| Manual deployment steps | Low/Med/High | |
| Hardcoded configuration | Low/Med/High | |
| No upgrade path for key dependencies | Low/Med/High | |

**Technical debt rating:** 1 2 3 4 5

## 9. Knowledge and bus factor

- [ ] More than one person understands the codebase
- [ ] Key processes are documented, not tribal knowledge
- [ ] Onboarding a new developer would take days, not months
- [ ] Critical systems have runbooks for common incidents
- [ ] No single person is the sole dependency for a critical system

**Bus factor:** How many people would need to leave before the system becomes unmaintainable? ____

**Knowledge rating:** 1 2 3 4 5

## 10. Summary and recommendations

### Overall score
Average of all section ratings: ____ / 5

### Critical issues (must fix before proceeding)
1.
2.
3.

### Significant concerns (should address soon)
1.
2.
3.

### Strengths
1.
2.
3.

### Recommended next steps
1.
2.
3.

### Estimated effort to address critical issues
- [ ] Days
- [ ] Weeks
- [ ] Months

---

## Scoring guide

| Score | Meaning | Action |
|-------|---------|--------|
| 4.5-5.0 | Excellent | Proceed with confidence. Maintain standards. |
| 3.5-4.4 | Good | Minor improvements needed. Low risk. |
| 2.5-3.4 | Fair | Significant work needed. Medium risk. Budget for remediation. |
| 1.5-2.4 | Poor | Major concerns. High risk. Requires substantial investment. |
| 1.0-1.4 | Critical | Do not proceed without a remediation plan. |

## Next steps

- For a professional code audit conducted by an experienced engineer, contact [ajairu.dev](https://ajairu.dev)
- See the [System Integration Patterns](system-integration-patterns.md) guide for common integration scenarios
- See the [Build vs Buy Calculator](build-vs-buy-calculator.md) if you are deciding whether to rebuild

## Disclaimer

This template is provided as general guidance for technical due diligence, not professional advice. For a tailored audit of your specific codebase, contact [ajairu.dev](https://ajairu.dev).