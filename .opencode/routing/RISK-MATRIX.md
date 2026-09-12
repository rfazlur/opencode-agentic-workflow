# Risk Matrix

## Low
Documentation, formatting, isolated non-functional changes.

Gate:
- targeted verification

## Medium
Normal feature changes, non-critical UI/API behavior.

Gate:
- targeted tests
- relevant regression
- code review

## High
Authentication, authorization, payments, PII, data migrations, infrastructure or broad cross-cutting changes.

Gate:
- targeted tests
- regression
- code review
- security review
- release gate
- human approval for production impact

## Critical
Irreversible migration, production infrastructure, security-sensitive remediation, destructive operation.

Gate:
- all high-risk controls
- explicit human approval
- no autonomous push/release
