---
name: release-manager
description: Coordinate software releases from planning through deployment to post-release verification. Use for major releases, coordinated multi-team deploys, or establishing a release process.
triggers:
  - plan a release
  - release checklist
  - ship this version
  - release coordination
  - deployment plan
allowed-tools: []
---

# Release Manager

Coordinate releases so nothing falls through the cracks.

## Writes
- `outputs/release-[version]-plan.md`

## Pre-Release Checklist

### Code Readiness
- [ ] All planned features merged to release branch
- [ ] No open blockers or critical bugs
- [ ] Code freeze communicated to team
- [ ] Feature flags configured for gradual rollout (if applicable)

### Quality
- [ ] All tests pass (unit, integration, e2e)
- [ ] QA sign-off on staging environment
- [ ] Performance benchmarks within acceptable range
- [ ] Security review complete for new features handling user data

### Documentation
- [ ] Changelog written (user-facing changes, not commit messages)
- [ ] API documentation updated for breaking changes
- [ ] Internal runbook updated if operational procedures changed
- [ ] Migration guide written if breaking changes exist

### Stakeholder Communication
- [ ] Release notes drafted for users
- [ ] Support team briefed on new features and known issues
- [ ] Marketing notified if the release includes public-facing changes
- [ ] Internal announcement prepared

## Deployment Plan

1. **Pre-deploy:** Run final test suite on staging, verify database migrations, confirm rollback procedure
2. **Deploy:** Execute deployment (canary, blue-green, or direct based on your strategy)
3. **Verify:** Check health endpoints, run smoke tests, monitor error rates for 15-30 minutes
4. **Announce:** Send release notes, update status page if applicable
5. **Monitor:** Watch error rates, performance metrics, and support channels for 24 hours

## Rollback Plan

Define before deploying:
- **Trigger:** What error rate or metric threshold triggers a rollback?
- **Procedure:** Exact steps to revert (redeploy previous version, revert migration, etc.)
- **Owner:** Who makes the rollback call?
- **Communication:** Who to notify if rolling back

## Changelog Format

```markdown
## [Version] — [Date]

### Added
- [Feature description] — [context for why it matters]

### Changed
- [What changed] — [impact on users]

### Fixed
- [Bug description] — [what users experienced before]

### Removed
- [What was removed] — [migration path if needed]
```
