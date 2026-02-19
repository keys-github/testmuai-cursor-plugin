---
name: run-tests-on-hyperexecute
description: Generate HyperExecute YAML config and run tests on TestMu AI HyperExecute using generateHyperExecuteYAML and getHyperExecuteJobInfo MCP tools. Use for fast parallel test execution with Selenium/Playwright/Cypress/TestNG/Pytest.
---

# Run Tests on HyperExecute

## When to Use

- Setting up test execution on TestMu AI HyperExecute
- Generating HyperExecute YAML configuration files
- Running parallel tests across browsers and platforms
- Checking HyperExecute job status and session results

## MCP Tools Used

- `generateHyperExecuteYAML` - Generate HyperExecute YAML config for your test framework
- `getHyperExecuteJobInfo` - Fetch job details, status, and test results
- `getHyperExecuteJobSessions` - Fetch session-level details for a job

## Steps

### 1. Generate HyperExecute YAML Config

Use the `generateHyperExecuteYAML` MCP tool:

```
"Generate a HyperExecute YAML for my Playwright tests in JavaScript"
"Create HyperExecute config for my Pytest tests with 5 parallel sessions"
"Generate YAML config for my TestNG-Selenium tests in Java"
```

**What the tool does:**
- Detects your test framework and language
- Generates a complete `hyperexecute.yaml` configuration
- Sets up parallel execution, caching, pre-commands, and test discovery
- Validates the config and warns about potential issues

**Supported Frameworks:**
- **JavaScript**: Playwright, Cypress, Jest, Mocha, WebDriverIO, Selenium, Puppeteer, Taiko, Protractor, TestCafe
- **Python**: Pytest, Behave, Robot Framework, Selenium, Appium
- **Java**: TestNG, JUnit, Cucumber, Selenium, Appium, REST-Assured
- **Ruby**: RSpec, Capybara, Cucumber, Minitest
- **C#**: NUnit, xUnit, MSTest, SpecFlow
- **PHP**: PHPUnit, Codeception, Behat
- **Go**: Testing, Testify, Ginkgo

### 2. Check Job Status

Use `getHyperExecuteJobInfo` to monitor your running job:

```
"Get status of HyperExecute job abc123"
"Show me the results of my last HyperExecute run"
```

### 3. View Session Details

Use `getHyperExecuteJobSessions` to inspect individual sessions:

```
"Get session details for HyperExecute job abc123"
"Show me the first 10 sessions from job xyz789"
```

## Common Scenarios

**Generate Config for Different Frameworks:**
```
"Generate HyperExecute YAML for Playwright tests in TypeScript"
"Create HyperExecute config for Cypress with Chrome and Firefox"
"Generate YAML for my Selenium-TestNG tests with 10 parallel sessions"
```

**Monitor and Debug Jobs:**
```
"Get status of HyperExecute job 12345"
"Show session details for my HyperExecute job"
"What's the result of job abc123?"
```

## Example Workflow

**User**: "I want to run my Playwright tests on HyperExecute"

**Steps**:
1. Generate config: `"Generate HyperExecute YAML for my Playwright tests in JavaScript"`
2. Tool creates `hyperexecute.yaml` with optimal settings
3. User runs tests with HyperExecute CLI
4. Check status: `"Get status of HyperExecute job <jobId>"`
5. View sessions: `"Get session details for job <jobId>"`

## Quick Tips

- Specify your test framework and language for best results
- The YAML generator includes smart defaults for caching, pre-commands, and parallelism
- Use `getHyperExecuteJobInfo` to poll job status during execution
- Session details include browser, OS, status, and timing information
- Supports 35+ test frameworks across 7 programming languages
