# Workflows — Standard Workflows

## How to Use

Master Agent selects the closest workflow and adapts it to the task.
Workflows are recommendations, not rigid algorithms. Roles and order may change.

---

## WF-1: New Project from Scratch

**Triggers:** "create project", "build app", "new service"

```
1. Analyst      -> requirements, user stories, business rules
   |-- [GATE] -> Client confirms requirements
   |-- Expert (if domain expertise needed)
2. Architect    -> architecture, stack, API contracts
   |-- [GATE] -> Client chooses option
3. Database     -> data schema, migrations
4. Backend      -> server logic, API
5. Frontend     -> UI, components, state
6. DevOps       -> Dockerfile, CI/CD, env
7. QA           -> tests, checklist
8. TechWriter   -> README, documentation
9. Auditor      -> final audit
   |-- [GATE] -> Client accepts result
```

---

## WF-2: New Feature / Enhancement

**Triggers:** "add feature", "build feature", "need enhancement"

```
1. Analyst      -> what's needed, how it affects existing
2. Architect    -> fit into architecture (if needed)
3. Backend/Frontend -> implementation (parallel or sequential)
4. QA           -> tests on new + regression
5. Auditor      -> audit changes
```

---

## WF-3: Bug / Fix

**Triggers:** "bug", "error", "not working", "broken"

```
1. QA           -> reproduce, localize
2. Backend/Frontend -> fix (whoever owns the code)
3. QA           -> verify fix + regression
4. Auditor      -> express audit (abbreviated)
```

---

## WF-4: Refactoring

**Triggers:** "refactor", "rewrite", "optimize", "tech debt"

```
1. Architect    -> analyze current state, refactoring plan
   |-- [GATE] -> Client confirms scope
2. QA           -> tests on current behavior (BEFORE refactoring)
3. Backend/Frontend -> refactoring
4. QA           -> run tests (behavior unchanged)
5. Auditor      -> audit
```

---

## WF-5: Code Review

**Triggers:** "review code", "check this", "look at this"

```
1. Architect    -> architecture compliance
2. QA           -> test coverage
3. Auditor      -> full audit
   |-- Result -> to Client
```

---

## WF-6: Documentation / Proposal / Report

**Triggers:** "documentation", "proposal", "report", "specs"

```
1. Analyst      -> structure, content
   |-- Expert (copywriter / marketer / CFO — by document type)
2. TechWriter   -> writing
   |-- [GATE] -> Client reviews
3. Auditor      -> fact and calculation check (if applicable)
```

---

## WF-7: Analytics / Research

**Triggers:** "analyze", "research", "compare options", "financial model"

```
1. Analyst      -> frame the question, methodology
   |-- Expert (by domain — financier, marketer, engineer, etc.)
2. Analysis execution (analyst + expert)
   |-- [GATE] -> interim results to Client
3. TechWriter   -> format results
4. Auditor      -> methodology and conclusions check
```

---

## WF-8: External API / Service Integration

**Triggers:** "integrate", "connect API", "work with [external service]"

```
1. Architect    -> API analysis, contracts, integration architecture
2. Backend      -> client implementation, error handling
3. QA           -> tests (mock + live if possible)
4. DevOps       -> env, secrets, monitoring
5. Auditor      -> integration security
```

---

## WF-9: Migration / Upgrade

**Triggers:** "upgrade version", "migration", "move to"

```
1. Architect    -> migration plan, risk assessment
   |-- [GATE] -> Client confirms
2. Database     -> data migrations (if any)
3. Backend/Frontend -> code adaptation
4. QA           -> full regression
5. DevOps       -> rollback plan
6. Auditor      -> migration audit
```

---

## WF-10: Emergency Fix (Hotfix)

**Triggers:** "urgent", "prod is down", "hotfix", "critical"

```
1. Backend/Frontend -> quick fix
2. QA              -> minimal verification
3. DevOps          -> deploy
4. Auditor         -> post-audit (after deploy, non-blocking)
```

WARNING: The ONLY workflow where audit runs AFTER deploy.

---

## Combining Workflows

Complex tasks may combine multiple workflows. For example:
- "Build an app with payment integration" -> WF-1 + WF-8
- "Rewrite frontend and update deps" -> WF-4 + WF-9

Master Agent merges steps, removes duplication, and builds a unified plan.
