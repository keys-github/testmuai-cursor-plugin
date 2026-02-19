---
name: visual-regression-testing
description: Perform visual regression testing with TestMu AI SmartUI using getSmartUIScreenshotInfo, summarizeSmartUIPixelDiff, summarizeSmartUILayoutDiff, summarizeSmartUIDomDiff, analyzeSmartUIHumanDiff, and analyzeSmartUIRun MCP tools. Use for detecting visual changes and UI regressions.
---

# Visual Regression Testing with SmartUI

## When to Use

- Reviewing visual changes between builds
- Investigating pixel, layout, or DOM differences in UI screenshots
- Analyzing a full SmartUI test run for visual regressions
- Understanding what changed visually in your application

## MCP Tools Used

- `getSmartUIScreenshotInfo` - Get screenshot metadata and comparison details
- `getSmartUIResources` - Fetch comparison resources (baseline vs current)
- `downloadSmartUIDomFiles` - Download DOM structure for comparison
- `summarizeSmartUIPixelDiff` - Analyze pixel-level visual changes
- `summarizeSmartUILayoutDiff` - Analyze layout and structural changes
- `summarizeSmartUIDomDiff` - Analyze DOM/code-level changes
- `analyzeSmartUIHumanDiff` - Get human-readable visual change descriptions
- `analyzeSmartUIRun` - Comprehensive analysis of an entire test run

## Steps

### 1. Analyze a Full Test Run

Use `analyzeSmartUIRun` for a comprehensive overview:

```
"Analyze SmartUI run for build abc123"
"Show me all visual changes in my latest SmartUI run"
```

**What the tool does:**
- Summarizes all screenshots with changes
- Categorizes changes by severity
- Highlights critical visual regressions

### 2. Inspect Individual Screenshots

Use `getSmartUIScreenshotInfo` to get details on a specific screenshot:

```
"Get SmartUI screenshot info for screenshot ID xyz789"
"Show me comparison details for this screenshot"
```

### 3. Analyze Specific Diff Types

Choose the right diff type based on what you need:

**Pixel Diff** — exact visual pixel changes:
```
"Summarize pixel differences for SmartUI screenshot xyz789"
"Show me pixel-level changes between baseline and current"
```

**Layout Diff** — structural/positioning changes:
```
"Summarize layout differences for SmartUI screenshot xyz789"
"What layout changes happened in this screenshot?"
```

**DOM Diff** — code-level changes in the DOM:
```
"Summarize DOM differences for SmartUI screenshot xyz789"
"What HTML/CSS changes caused the visual diff?"
```

**Human Diff** — natural language explanation:
```
"Give me a human-readable analysis of SmartUI screenshot xyz789"
"Explain what changed visually in this screenshot"
```

### 4. Download DOM Files

Use `downloadSmartUIDomFiles` for deep code-level comparison:

```
"Download DOM files for SmartUI screenshot xyz789"
"Get baseline and current DOM structures for comparison"
```

## Common Scenarios

**Review Full Test Run:**
```
"Analyze my SmartUI run abc123"
→ Returns summary of all visual changes across screenshots
→ Highlights critical regressions vs expected changes
```

**Investigate a Specific Change:**
```
"Get info for SmartUI screenshot xyz789"
"Summarize pixel diff for screenshot xyz789"
"Explain what changed in human terms"
```

**Debug Layout Issues:**
```
"Summarize layout diff for screenshot xyz789"
"Download DOM files for screenshot xyz789"
"What CSS changes caused this layout shift?"
```

## Example Workflow

**User**: "Review visual changes in my latest SmartUI build"

**Steps**:
1. Run overview: `"Analyze SmartUI run for build abc123"`
2. Identify flagged screenshots with significant changes
3. Deep dive: `"Summarize pixel diff for screenshot xyz789"`
4. Understand root cause: `"Summarize DOM diff for screenshot xyz789"`
5. Human summary: `"Give me a human-readable analysis of the changes"`
6. Approve or flag the changes

## Quick Tips

- Start with `analyzeSmartUIRun` for a high-level overview of all changes
- Use pixel diff for exact visual comparisons
- Use layout diff for structural/positioning changes
- Use DOM diff to understand what code changes caused the visual diff
- Human diff provides natural language explanations of visual changes
- SmartUI caches results for 60 minutes for faster repeated access
