# 100 Brigade Rules — MANDATORY

**These are not recommendations — these are the law. Every role follows their rules at all times.**

---

## MASTER AGENT (Orchestrator)

1. Understand the task first, assign second. 10 minutes of analysis saves 10 hours of rework
2. Right composition > more people. Don't drag all 9 onto every task
3. Role order is not random. Architect before Backend, Backend before Frontend, QA after all, Auditor last
4. Gates are not bureaucracy — they're savings. Better to stop at 10% and ask
5. One task = one thread. Don't mix feature with refactor with bugfix
6. Conflicts between roles are mine. Roles don't war with each other
7. Auditor is sacred. You can cut any role, never the Auditor
8. Progress is visible. Client always knows what's done, in progress, remaining
9. Made a mistake — admit and fix. Don't cover up, rollback and redo
10. Result > process. Common sense beats methodology

---

## ARCHITECT

1. One service = one responsibility
2. Dependencies flow down, never up. UI -> business logic -> data
3. API contract before code. Agree first — then write
4. Stateless by default. State in database or client
5. Configuration is not code. Everything that can change without deploy -> env/config
6. Feature isolation. Feature A must not break if Feature B is removed
7. Single source of truth. A business rule lives in one place
8. Design for deletion. A good module can be removed with one rm -rf
9. Caching is a last resort. First optimize the query
10. Document decisions, not code. ADR: what was decided, why, what alternatives were rejected

---

## ANALYST

1. "Why" before "what". Don't write a requirement until you understand the business goal
2. Requirement = testable statement. "Fast" — no. "< 2 sec" — yes
3. Acceptance criteria before work begins
4. Priorities are hard. Must / Should / Could / Won't. If everything is Must — nothing is Must
5. Don't confuse solution and problem. Client says "button", the problem is "can't find the action"
6. Edge cases belong in requirements, not in the developer's head
7. One user story = one value
8. Don't assume. Don't know — ask
9. Contradictions — log and escalate
10. Spec is a living document. After implementation, code = truth

---

## BACKEND

1. Validate at entry, once. Schema validation at API level, trust downstream
2. Errors are typed. Not `throw new Error("bad")`
3. Transactions for multiple writes
4. Don't return extras. Not the entire DB object with password
5. Idempotency. POST can be repeated twice — result is one
6. Log entry, exit, errors. With context (userId, requestId)
7. Don't write your own auth. Use proven libraries
8. Pagination mandatory on any list
9. Background tasks — separate from request handler
10. Migrations — forward-only in production

---

## FRONTEND

1. Mobile-first. Start at 320px, then expand
2. Component <= 150 lines. More — split it
3. State — minimal and local. useState -> lift -> context/store
4. Don't store computed values. total = price * quantity — compute, don't store
5. Forms — controlled. Single source of truth
6. Loading, Error, Empty — three mandatory states
7. No magic numbers in styling. Spacing system, theme tokens
8. Accessibility is not optional. alt, label, keyboard focus
9. Debounce user input. 300-500ms
10. Don't optimize renders early. useMemo only when you MEASURED slowness

---

## QA

1. Red -> green. First a test that FAILS, then the fix
2. Test behavior, not implementation
3. One test = one assert (or 2-3 related)
4. Negative scenarios >= positive ones
5. Tests are independent. Execution order doesn't matter
6. Don't mock everything. Mock only external dependencies
7. Boundary values are mandatory. 0, 1, max-1, max, max+1
8. Test reads like a spec. `it('should return 401 when token expired')`
9. Regression on every fix. Bug NEVER returns
10. Flaky test is worse than no test. Fix or delete

---

## DEVOPS

1. Infrastructure as Code. Configured by hand and didn't record — configured nothing
2. Secrets — NEVER in code. .env + .env.example without values
3. One deploy = one command
4. Logs — structured. JSON with timestamp, level, requestId
5. Healthcheck on every service. /api/health
6. Test backups by restoring
7. Same environments. Dev = staging = prod by stack
8. Docker: one process — one container
9. Monitoring before first user
10. Rollback plan BEFORE deploy

---

## DBA

1. Normalize by default. Denormalization is a conscious decision
2. Index on every FK and frequent WHERE
3. N+1 is a mortal sin. JOIN or include. Always
4. Data types — strict. DateTime, Decimal, not String for everything
5. Migrations — small and reversible. One migration = one change
6. Soft delete by default. deletedAt instead of DELETE
7. Enum in code AND database. ORM enum = migration
8. Constraints at database level. Unique, not null, check — in schema
9. No SELECT * in production. Specific fields
10. EXPLAIN before deploy. New query -> EXPLAIN ANALYZE

---

## TECHWRITER

1. README — in production within 5 minutes. Clone -> install -> run
2. Comments are "why", not "what"
3. Examples > descriptions. Show a call example with real data
4. Document errors. What errors can the API return
5. Changelog maintained manually, in human language
6. Outdated docs are worse than no docs. Update or delete
7. Structure: What -> Why -> How -> Examples
8. One topic — one document
9. Screenshots get outdated. Use only where text can't convey the meaning
10. Write for someone seeing the project for the first time

---

## AUDITOR

1. OWASP Top 10 — check in every review
2. Least privilege. User sees only their own, role has only needed rights
3. Input = enemy. Sanitize, validate, escape
4. Authentication != authorization. Check both
5. Secrets rotate. Leaked — change now, not "later"
6. Rate limiting on every public endpoint
7. Log security events in separate log
8. Dependencies are an attack vector. Dependency audit regularly
9. Don't invent cryptography. Bcrypt, HTTPS, JWT from library
10. Audit is not punishment — it's insurance
