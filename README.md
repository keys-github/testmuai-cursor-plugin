# TestMu AI for Cursor

Access TestMu AI's complete testing platform directly from Cursor using natural language. Run tests on HyperExecute, debug automation failures, perform visual regression testing with SmartUI, scan for accessibility issues, and test mobile apps—all without leaving your IDE.

## Getting Started

### Prerequisites

- Node.js 18 or higher ([download](https://nodejs.org/en/download))
- TestMu AI account ([sign up for free](https://accounts.lambdatest.com/register))

### Installation

1. **Configure MCP settings in Cursor**:
   - Open Cursor Settings
   - Navigate to MCP configuration
   - Add TestMu AI credentials:

   ```json
   {
     "mcpServers": {
       "testmu-ai": {
         "command": "npx",
         "args": ["mcp-remote@latest", "https://mcp.lambdatest.com/mcp"]
       }
     }
   }
   ```

3. **Restart Cursor** and verify:
   ```
   "Generate a HyperExecute YAML for my Playwright tests"
   ```

## What's Included

### Skills

- **run-tests-on-hyperexecute** — Generate HyperExecute YAML configs and run parallel tests
- **debug-automation-tests** — Debug Selenium/Appium test failures with command, network, console, and WebDriver logs
- **visual-regression-testing** — Analyze visual changes with SmartUI pixel, layout, and DOM diffs
- **scan-and-fix-accessibility** — Scan webpages for WCAG 2.1 violations and get code fixes
- **upload-and-test-mobile-app** — Upload APK/IPA files to TestMu AI for mobile testing

### Agents

- **hyperexecute-expert** — AI-powered HyperExecute documentation Q&A
- **test-debugger** — Systematic test failure diagnosis across multiple log sources

### MCP Tools (29 Available)

**HyperExecute**
- `generateHyperExecuteYAML` — Generate HyperExecute YAML config for 35+ frameworks
- `answerHyperExecuteQuery` — AI-powered documentation Q&A (RAG-based, no API key needed)
- `getHyperExecuteJobInfo` — Fetch job details, status, and results
- `getHyperExecuteJobSessions` — Fetch session-level details for a job

**Automation (Web & Mobile)**
- `getAutomationTestDetails` — Fetch test metadata (browser, OS, status, timing)
- `getAutomationTestCommandLogs` — Fetch Selenium/Appium command execution logs
- `getAutomationTestNetworkLogs` — Fetch HAR network traffic logs
- `getAutomationTestBrowserConsoleLogs` — Fetch browser console output
- `getAutomationTestSeleniumLogs` — Fetch raw WebDriver/Appium logs

**SmartUI (Visual Testing)**
- `getSmartUIScreenshotInfo` — Get screenshot metadata and comparison details
- `downloadSmartUIDomFiles` — Download DOM structures for comparison
- `getSmartUIResources` — Fetch comparison resources (baseline vs current)
- `summarizeSmartUIPixelDiff` — Analyze pixel-level visual changes
- `summarizeSmartUILayoutDiff` — Analyze layout and structural changes
- `summarizeSmartUIDomDiff` — Analyze DOM/code-level changes
- `analyzeSmartUIHumanDiff` — Human-readable visual change descriptions
- `analyzeSmartUIRun` — Comprehensive test run analysis

**Accessibility**
- `getAccessibilityReport` — WCAG 2.1 compliance scanning with axe-core
- `analyzeAppViaTunnel` — Scan localhost apps via TestMu AI tunnel
- `buildLocalAppForAnalysis` — Setup instructions for local accessibility testing

**Mobile App**
- `upload_app` — Upload APK/IPA files for mobile testing

**Phone Caller**
- `triggerSuiteRun` — Initiate phone test runs
- `listSuites` — List available test suites
- `getSuiteOverview` — Get suite statistics and schedules

## Use Cases

### 1. Run Tests on HyperExecute

**What**: Generate HyperExecute YAML configs and execute parallel tests across browsers and platforms.

**Skill**: `run-tests-on-hyperexecute`

**Tools**: `generateHyperExecuteYAML`, `getHyperExecuteJobInfo`, `getHyperExecuteJobSessions`

**Examples**:
```
"Generate a HyperExecute YAML for my Playwright tests in JavaScript"
"Create HyperExecute config for Pytest with 10 parallel sessions"
"Get status of HyperExecute job abc123"
"Show session details for my HyperExecute job"
```

**Supported Frameworks** (35+):
| Language | Frameworks |
|----------|-----------|
| JavaScript | Playwright, Cypress, Jest, Mocha, WebDriverIO, Selenium, Puppeteer, Taiko, TestCafe |
| Python | Pytest, Behave, Robot Framework, Selenium, Appium |
| Java | TestNG, JUnit, Cucumber, Selenium, Appium, REST-Assured |
| Ruby | RSpec, Capybara, Cucumber, Minitest |
| C# | NUnit, xUnit, MSTest, SpecFlow |
| PHP | PHPUnit, Codeception, Behat |
| Go | Testing, Testify, Ginkgo |

---

### 2. Debug Automation Test Failures

**What**: Diagnose test failures by fetching command, network, console, and WebDriver logs.

**Skill**: `debug-automation-tests`

**Tools**: `getAutomationTestDetails`, `getAutomationTestCommandLogs`, `getAutomationTestNetworkLogs`, `getAutomationTestBrowserConsoleLogs`, `getAutomationTestSeleniumLogs`

**Examples**:
```
"Get details of automation test session abc123"
"Get command logs for session xyz789"
"Show me network logs for my failed test"
"Get browser console logs for session abc123"
```

---

### 3. Visual Regression Testing with SmartUI

**What**: Detect visual changes between builds using pixel, layout, and DOM diff analysis.

**Skill**: `visual-regression-testing`

**Tools**: `analyzeSmartUIRun`, `getSmartUIScreenshotInfo`, `summarizeSmartUIPixelDiff`, `summarizeSmartUILayoutDiff`, `summarizeSmartUIDomDiff`, `analyzeSmartUIHumanDiff`

**Examples**:
```
"Analyze SmartUI run for build abc123"
"Summarize pixel differences for screenshot xyz789"
"Explain what changed visually in this screenshot"
"Download DOM files for comparison"
```

---

### 4. Accessibility Scanning

**What**: Identify WCAG 2.1 violations on your website and get specific code fixes.

**Skill**: `scan-and-fix-accessibility`

**Tools**: `getAccessibilityReport`, `analyzeAppViaTunnel`, `buildLocalAppForAnalysis`

**Examples**:
```
"Run accessibility scan for 'https://mysite.com'"
"Scan my localhost app on port 3000 for accessibility issues"
"Help me set up accessibility testing locally"
"Re-scan to verify accessibility fixes"
```

---

### 5. Upload and Test Mobile Apps

**What**: Upload APK/IPA files to TestMu AI for mobile automation testing.

**Skill**: `upload-and-test-mobile-app`

**Tools**: `upload_app`

**Examples**:
```
"Upload /builds/app-debug.apk to TestMu AI"
"Upload my iOS app from https://ci.example.com/artifacts/latest.ipa"
```

---

### 6. HyperExecute Documentation Q&A

**What**: Get answers about HyperExecute features, configuration, and troubleshooting.

**Agent**: `hyperexecute-expert` (invoke with `@hyperexecute-expert`)

**Tools**: `answerHyperExecuteQuery`

**Examples**:
```
@hyperexecute-expert "How do I configure caching in HyperExecute?"
@hyperexecute-expert "How to integrate HyperExecute with GitHub Actions?"
@hyperexecute-expert "My job is timing out, how do I fix it?"
```

---

### 7. Systematic Test Debugging

**What**: Deep-dive test failure diagnosis across multiple log sources.

**Agent**: `test-debugger` (invoke with `@test-debugger`)

**Tools**: `getAutomationTestDetails`, `getAutomationTestCommandLogs`, `getAutomationTestNetworkLogs`, `getAutomationTestBrowserConsoleLogs`, `getAutomationTestSeleniumLogs`, `getHyperExecuteJobInfo`

**Examples**:
```
@test-debugger "Session abc123 failed with element not found"
@test-debugger "Help me debug HyperExecute job xyz789"
@test-debugger "My test is flaky, sometimes passes sometimes fails"
```

**Plugin Not Responding**
- Restart Cursor after configuration changes
- Check Node.js version: `node --version` (need 18+)
- View MCP server logs in Cursor

**Need Help?**
- [GitHub Issues](https://github.com/AyushSomani001/testmuai-cursor-plugin/issues) — Report bugs or issues
- [TestMu AI Support](https://www.testmuai.com/support) — Platform questions
- [Documentation](https://www.testmuai.com/support/docs/) — Detailed guides

---
