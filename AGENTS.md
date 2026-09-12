# Engineering Agent Rules

1. Inspect repository structure and local instructions before editing.
2. Use existing architecture, conventions and test framework.
3. Make the smallest safe change.
4. Run targeted tests before broad regression.
5. Never read or expose `.env` / `.env.*`.
6. Never commit credentials, tokens, private keys or secrets.
7. Never claim test success without execution evidence.
8. Do not weaken assertions or delete tests to make a suite pass.
9. Never automatically push to a remote repository.
10. Do not perform destructive security testing without explicit authorization.
11. Maintain traceability between requirements, changes and tests.
12. If risk is critical or repair attempts exceed 3, return HUMAN_REQUIRED.
