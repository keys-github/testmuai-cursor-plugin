---
name: debug-automation-tests
description: Debug automation test failures on TestMu AI using getAutomationTestDetails, getAutomationTestCommandLogs, getAutomationTestNetworkLogs, getAutomationTestBrowserConsoleLogs, and getAutomationTestSeleniumLogs MCP tools. Use for diagnosing Selenium/Appium test failures.
---

# Debug Automation Tests

## When to Use

- Investigating why an automated test failed on TestMu AI
- Retrieving command, network, console, or Selenium logs from a test session
- Understanding test execution details (browser, OS, timing, status)
- Debugging Selenium or Appium test issues

## MCP Tools Used

- `getAutomationTestDetails` - Fetch test metadata (browser, OS, status, timing)
- `getAutomationTestCommandLogs` - Fetch Selenium/Appium command execution logs
- `getAutomationTestNetworkLogs` - Fetch HAR network traffic logs
- `getAutomationTestBrowserConsoleLogs` - Fetch browser console output (errors, warnings)
- `getAutomationTestSeleniumLogs` - Fetch raw WebDriver/Appium logs

## Steps

### 1. Get Test Details

Use `getAutomationTestDetails` to understand the test environment and outcome:

```
"Get details of automation test session abc123"
"Show me test info for session ID xyz789"
```

**What the tool returns:**
- Browser name, version, and OS
- Test status (passed/failed/error)
- Start time, duration, and resolution
- Available log types for further debugging

### 2. Fetch Command Logs

Use `getAutomationTestCommandLogs` to see what Selenium/Appium commands were executed:

```
"Get command logs for session abc123"
"Show me Selenium commands from test session xyz789"
```

**What the tool returns:**
- Chronological list of WebDriver commands
- Request/response for each command
- Timing information per command
- Errors at the command level

### 3. Fetch Network Logs

Use `getAutomationTestNetworkLogs` to inspect HTTP traffic:

```
"Get network logs for session abc123"
"Show me network requests from my failed test"
```

**What the tool returns:**
- HAR-format network trace
- Request URLs, methods, status codes
- Response times and payload sizes
- Failed requests that may have caused test failures

### 4. Fetch Browser Console Logs

Use `getAutomationTestBrowserConsoleLogs` to see JavaScript errors:

```
"Get browser console logs for session abc123"
"Show me JavaScript errors from my test"
```

**What the tool returns:**
- Console errors, warnings, and messages
- JavaScript exceptions
- Uncaught promise rejections
- Resource loading failures

### 5. Fetch Selenium/Appium Logs

Use `getAutomationTestSeleniumLogs` for raw WebDriver logs:

```
"Get Selenium logs for session abc123"
"Show me raw Appium logs from my mobile test"
```

## Common Scenarios

**Quick Test Investigation:**
```
"Get details and command logs for session abc123"
"Why did my test session xyz789 fail?"
```

**Network Issue Debugging:**
```
"Get network logs for session abc123 - I suspect an API is timing out"
"Show me failed network requests from my test"
```

**JavaScript Error Detection:**
```
"Get browser console logs for session abc123"
"Are there any JavaScript errors in my test session?"
```

**Full Debug Workflow:**
```
"Get all logs for automation session abc123"
```

## Example Workflow

**User**: "My Selenium test failed on TestMu AI, session ID is abc123"

**Steps**:
1. Get overview: `"Get details of automation test session abc123"`
2. Check commands: `"Get command logs for session abc123"` — find which command failed
3. Check network: `"Get network logs for session abc123"` — check for API failures
4. Check console: `"Get browser console logs for session abc123"` — find JS errors
5. Root cause identified, provide fix suggestion

## Quick Tips

- Start with `getAutomationTestDetails` to understand the test environment
- Command logs show the exact Selenium/Appium action that failed
- Network logs help identify backend/API failures
- Browser console logs reveal JavaScript and rendering issues
- Supports both web (Selenium) and mobile (Appium) test sessions
- Use pagination for large log sets (specify page number)
