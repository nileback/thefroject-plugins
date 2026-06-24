---
name: code-migrator
description: Plan and execute safe code migrations between frameworks, languages, or major versions. Use when upgrading dependencies, switching frameworks, porting code, or doing large-scale codemod operations.
triggers:
  - migrate code
  - upgrade framework
  - port to
  - major version upgrade
  - codemod
---

# Code Migrator

You migrate code safely between technologies or versions. The cardinal rule: never big-bang. Always incremental.

## Gather Context First

1. **Migration type** — Framework swap, language port, major version upgrade, or dependency replacement?
2. **Source and target** — What are you migrating from and to? (include versions)
3. **Codebase size** — Files, lines of code, number of modules affected
4. **Test coverage** — What percentage of the code has tests? Which parts?
5. **Dependencies** — What third-party packages need migration too?
6. **Timeline** — Hard deadline or ongoing effort?
7. **Risk tolerance** — Can the app be down during migration? Feature freeze acceptable?

## Migration Strategy Selection

| Strategy | When to use | Risk |
|----------|-------------|------|
| **Strangler Fig** | Large apps. New code in new system, old code stays until replaced. | Low |
| **Parallel Run** | Critical systems. Both old and new run simultaneously. | Low (high effort) |
| **Branch by Abstraction** | Internal code. Add abstraction layer, swap implementation behind it. | Medium |
| **Big Bang** | Small codebases with high test coverage. Migrate everything at once. | High |

**Default recommendation:** Strangler Fig for framework changes, Branch by Abstraction for internal refactors.

## Migration Process

### Phase 1: Audit (do not write code yet)

1. **Map the surface area** — List every file, module, and dependency that will change
2. **Identify breaking changes** — Read the migration guide. List every breaking change that affects your code.
3. **Dependency compatibility** — Check that all third-party packages work with the target version
4. **Risk ranking** — Rate each module: low risk (simple, well-tested), medium (some complexity), high (critical path, poorly tested)
5. **Write missing tests** — Before migrating anything, add tests for the riskiest modules

### Phase 2: Scaffold

1. Set up the new tooling alongside the old (both should build and run)
2. Configure the new framework/version in a way that allows incremental adoption
3. Create a compatibility layer if needed (adapters, shims, type bridges)
4. Verify the development workflow works (build, test, lint, dev server)

### Phase 3: Migrate (leaf dependencies first)

Migration order:
1. **Utilities and helpers** — No dependencies on other modules
2. **Data models and types** — Shared across the codebase
3. **Services and API clients** — Depend on models, depended on by UI
4. **Components and pages** — Highest-level, most visible to users

For each module:
1. Migrate the code
2. Run tests (all must pass)
3. Manual smoke test if it affects UI
4. Commit with a descriptive message referencing the migration
5. Move to the next module

### Phase 4: Verify

1. Run the full test suite
2. Run integration/E2E tests
3. Check for runtime warnings or deprecation notices
4. Performance comparison (before vs. after)
5. Review bundle size changes
6. Test edge cases that automated tests might miss

### Phase 5: Clean Up

1. Remove old dependencies from package.json
2. Remove compatibility shims and adapters
3. Remove old configuration files
4. Update documentation (README, CLAUDE.md, etc.)
5. Update CI/CD pipeline if build commands changed

## Tracking Format

Save migration progress to plans/migration-tracker.md:

| Module | Status | Risk | Notes |
|--------|--------|------|-------|
| [module] | Not started / In progress / Done / Blocked | Low/Med/High | [notes] |

## Common Migration Patterns

**React class → functional:**
- Convert lifecycle methods to useEffect hooks
- Convert this.state to useState
- Extract logic into custom hooks
- Convert HOCs to hooks where possible

**JavaScript → TypeScript:**
- Start with `allowJs: true` and migrate file by file
- Rename .js to .ts/.tsx one module at a time
- Add types gradually (`any` is acceptable as a stepping stone, not a destination)
- Enable strict mode after all files are converted

**Major version upgrades:**
- Read the full changelog, not just the migration guide
- Search codebase for deprecated APIs
- Run codemods if the framework provides them (`npx @next/codemod`, etc.)
- Update one major version at a time (don't jump v2 → v5)

## Do NOT
- Migrate without tests. Write them first if they are missing.
- Mix migration commits with feature work. Keep them separate.
- Migrate everything at once on a large codebase. Incremental is safer.
- Ignore deprecation warnings. They become errors in the next version.
- Skip the audit phase. Understanding the surface area prevents surprises.
- Assume the migration guide covers everything. Search your codebase for affected patterns.
