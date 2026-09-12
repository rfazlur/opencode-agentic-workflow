# Repair Loop

```text
TEST
 |
 +-- PASS --> REGRESSION --> REVIEW --> GATE
 |
 +-- FAIL --> FAILURE ANALYZER
                |
                +-- TEST_BUG ------> TESTER/FIX TEST
                |
                +-- PRODUCT_BUG ---> DEBUGGER ---> DEVELOPER
                |
                +-- ENVIRONMENT ---> HUMAN/ENV OWNER
                |
                +-- FLAKY ---------> FLAKY ANALYZER
                |
                +-- DEPENDENCY ----> DEPENDENCY OWNER
                |
                +-- UNKNOWN -------> DEBUGGER
                                      |
                                      v
                                    RETEST
                                      |
                               iteration < 3?
                                  /       \
                                yes        no
                                |           |
                                +--------> HUMAN_REQUIRED
```

Never weaken assertions, delete tests, or classify a failure as pass without evidence.
