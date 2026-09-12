# OpenCode Agentic Engineering Workflow V3

A production-oriented Developer + QA multi-agent workflow for OpenCode.

## V3 capabilities

- deterministic model routing through specialist agents
- intent / scope / risk / complexity classification
- parallelizable planning and QA analysis
- shared task state and artifact contracts
- failure classification
- bounded autonomous repair loop
- independent code/security review
- release gate with explicit PASS / PASS_WITH_RISK / BLOCKED
- safe Git and secret-handling defaults
- commands for feature, bug, QA, automation, review and release

## Architecture

```text
USER
  |
  v
ORCHESTRATOR
  |
  +--> CLASSIFY intent/scope/risk/complexity
  |
  +--> PLAN / ARCHITECT / QA / DEBATE
  |
  v
EXECUTION PLAN
  |
  +--> DEVELOPER
  +--> API TESTER
  +--> UI TESTER
  +--> AUTOMATION
  |
  v
TEST EXECUTION
  |
  +---- PASS ----------------------------+
  |                                      |
  +---- FAIL --> FAILURE ANALYZER        |
                  |                      |
                  +--> PRODUCT BUG       |
                  +--> TEST BUG          |
                  +--> ENVIRONMENT       |
                  +--> FLAKY             |
                  +--> DEPENDENCY        |
                  +--> UNKNOWN           |
                           |
                           v
                       DEBUGGER
                           |
                           v
                         FIX
                           |
                           v
                        RETEST
                           |
                    max 3 iterations
                           |
                           v
                    REVIEW + SECURITY
                           |
                           v
                      RELEASE GATE
                           |
                 +---------+---------+
                 v                   v
               RELEASE         HUMAN_REQUIRED
```

## Model tiers

- Free model: low-risk/simple/default work
- Gemini: analysis, requirements, QA and test design
- Claude: architecture challenge, coding, debugging, automation and independent review

Replace the placeholders in `opencode.jsonc` with exact model IDs exposed by your OpenCode provider.

## Commands

```text
/feature <request>
/bug <problem>
/qa <scope>
/automation <scope>
/review <scope>
/release <scope>
```

## Shared state

Each task uses:

```text
.opencode/runtime/<TASK-ID>/
  state.json
  requirements.md
  plan.md
  architecture.md
  qa-strategy.md
  test-cases.md
  execution.json
  failures.json
  root-cause.md
  review.md
  security.md
  release-gate.json
```

Agents should treat the state/artifacts as the source of truth and never invent missing evidence.
