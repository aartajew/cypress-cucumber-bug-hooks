# cypress-cucumber-bug-hooks

Reproduce bug with JSON report generation failure when using hooks. The problematic `After` hook is defined in [duckduckgo.js](cypress/e2e/duckduckgo.js) step definitions.

**Environment:**

Bug is reproducible on below setup:

- macOS Ventura 13.3.1
- Node.js v18.16.0
- npm v9.5.1
- Cypress v12.12.0
- Preprocessor v17.1.0

**Steps to reproduce:**

1. run `npm install`
2. run `npm test`

**Actual behavior:**

Below exception is thrown when parsing Cucumber messages:

```
TypeError: Cannot destructure property 'message' of 'testStepResult' as it is undefined.
```

**Expected behavior:**

Proper JSON report should be generated.
