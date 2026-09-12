# V3 Setup

## 1. Install

Copy `AGENTS.md`, `opencode.jsonc`, and `.opencode/` into your application repository.

## 2. Configure models

Inside OpenCode, inspect your available models:

```text
/models
```

Replace these placeholders in `opencode.jsonc`:

```text
MODEL_FREE
MODEL_GEMINI
MODEL_CLAUDE
```

Use exact `provider/model` IDs from your installation.

## 3. Validate read-only flows

Start with:

```text
/qa Analyze the checkout flow and create a risk-based QA strategy
```

Then:

```text
/review Review the current changes
```

## 4. Execute engineering flows

```text
/feature Add password reset with email OTP
/bug Checkout returns HTTP 500 after payment timeout
/automation Add regression automation for checkout
/release Evaluate whether the current changes are ready for release
```

## 5. Operating rule

Do not enable unrestricted approvals in production repositories.

V3 intentionally keeps:
- secrets denied
- destructive Git reset denied
- recursive deletion denied for coding agents
- push/commit approval-gated
- reviewer agents read-only
- repair loop bounded to 3 iterations
