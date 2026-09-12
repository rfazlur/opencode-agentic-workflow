# Task Routing

| Signal | Required agents |
|---|---|
| Feature | planner + developer + QA |
| Complex feature | planner + architect + debater + developer + QA |
| Bug | QA/reproduction + failure-analyzer + debugger |
| API | API tester |
| UI | UI tester |
| Automation | test-designer + automation-engineer |
| Auth/permission | security-reviewer |
| Payment/PII | security-reviewer + release-gate |
| Performance-sensitive | performance-reviewer |
| Critical production change | code-reviewer + security-reviewer + release-gate |

Parallelize independent read-only analysis when the runtime supports it. Do not parallelize conflicting edits to the same application files.
