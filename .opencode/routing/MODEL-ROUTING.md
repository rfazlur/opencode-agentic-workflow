# V3 Model Routing

## Tier policy

### FREE
Use for:
- simple exploration
- low-risk documentation
- trivial transformations
- default direct interaction

### GEMINI
Use for:
- requirements analysis
- QA strategy
- test design
- broad repository analysis
- API/UI test execution
- failure classification
- flaky-test analysis

### CLAUDE
Use for:
- architecture
- adversarial debate
- application implementation
- automation implementation
- debugging/RCA
- performance review
- code review
- security review
- release gate

## Routing principle

The orchestrator routes by delegating to specialist agents with explicit model assignments.

Do not attempt undocumented runtime model mutation.

## Critical work

For critical/high-risk work:
1. use Claude for implementation/reasoning
2. require independent review
3. require security review when applicable
4. require release gate
5. require human approval for production-impacting actions
