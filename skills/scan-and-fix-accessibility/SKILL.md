---
name: scan-and-fix-accessibility
description: Scan webpages for accessibility issues using getAccessibilityReport, analyzeAppViaTunnel, and buildLocalAppForAnalysis MCP tools. Use for WCAG compliance testing, identifying violations, and fixing accessibility bugs.
---

# Scan and Fix Accessibility

## When to Use

- Scanning a website or web app for WCAG 2.1 accessibility violations
- Testing a localhost app for accessibility issues
- Fixing specific accessibility bugs in your code
- Ensuring WCAG compliance before deployment

## MCP Tools Used

- `getAccessibilityReport` - Scan a public URL for WCAG 2.1 accessibility issues
- `analyzeAppViaTunnel` - Scan a localhost app via TestMu AI tunnel
- `buildLocalAppForAnalysis` - Get setup instructions for local accessibility testing

## Steps

### 1. Scan a Public URL

Use `getAccessibilityReport` to scan any publicly accessible webpage:

```
"Run accessibility scan for 'https://www.example.com'"
"Scan accessibility issues on https://mysite.com/checkout"
"Check WCAG compliance for https://staging.myapp.com"
```

**What the tool does:**
- Runs comprehensive WCAG 2.1 scan using axe-core engine
- Supports scanning multiple URLs at once
- Returns violations categorized by impact (Critical/Serious/Moderate/Minor)
- Provides remediation guidance for each violation

### 2. Scan a Localhost App

Use `analyzeAppViaTunnel` to scan apps running locally:

```
"Scan accessibility issues on my app running at port 3000"
"Run accessibility test on localhost:8080 via TestMu AI tunnel"
```

**Prerequisites:** TestMu AI tunnel must be running. Use `buildLocalAppForAnalysis` to get setup instructions.

### 3. Setup Local Testing

Use `buildLocalAppForAnalysis` for step-by-step setup:

```
"How do I set up accessibility testing for my local app?"
"Help me configure TestMu AI tunnel for accessibility scanning"
```

**What the tool provides:**
- Step-by-step tunnel setup instructions
- Cross-platform support (Mac Intel/Apple Silicon, Linux, Windows)
- Build and serve commands for your project

### 4. Analyze Results

Review the scan results and categorize issues:
- **Critical**: Blocks users entirely (missing form labels, keyboard traps)
- **Serious**: Major barriers (poor color contrast, missing alt text)
- **Moderate**: Best practice violations (heading hierarchy, landmark regions)
- **Minor**: Cosmetic or enhancement issues

### 5. Fix Issues in Code

For each violation, provide specific code fixes:

**Missing Alt Text:**
```html
<!-- Before -->
<img src="logo.png">

<!-- After -->
<img src="logo.png" alt="Company Logo">
```

**Poor Color Contrast:**
```css
/* Before - Contrast 2.8:1 (fails) */
color: #999;
background: #fff;

/* After - Contrast 4.6:1 (passes) */
color: #666;
background: #fff;
```

**Missing Form Label:**
```html
<!-- Before -->
<input type="email" placeholder="Email">

<!-- After -->
<label for="email">Email Address</label>
<input type="email" id="email" aria-required="true">
```

### 6. Verify Fixes

Re-scan after implementing fixes:

```
"Re-scan https://www.example.com to verify accessibility fixes"
"Run accessibility scan again on port 3000"
```

## Common Scenarios

**Scan and Fix Workflow:**
```
"Scan accessibility issues on https://mysite.com"
→ Returns violations with severity and remediation guidance
→ Fix issues in code
"Re-scan https://mysite.com to verify fixes"
```

**Local Development Workflow:**
```
"Help me set up accessibility testing locally"
→ Returns tunnel setup instructions
"Scan my app running at port 3000"
→ Returns WCAG violations
→ Fix and re-scan
```

## Example Workflow

**User**: "Fix accessibility issues on my checkout page at https://staging.myapp.com/checkout"

**Steps**:
1. Scan: `"Run accessibility scan for 'https://staging.myapp.com/checkout'"`
2. Results: Scan returns violations — 5 critical, 3 serious issues
3. Fix critical issues first (form labels, keyboard navigation)
4. Fix serious issues (color contrast, alt text)
5. Verify: `"Re-scan https://staging.myapp.com/checkout"`
6. Confirm: All critical and serious issues resolved

## Quick Reference

**Common WCAG Requirements:**
- Images need alt text (WCAG 1.1.1)
- Color contrast ≥ 4.5:1 for text (WCAG 1.4.3)
- All interactive elements keyboard accessible (WCAG 2.1.1)
- Forms have labels (WCAG 3.3.2)
- Proper heading hierarchy (WCAG 1.3.1)
- Focus visible on all interactive elements (WCAG 2.4.7)
