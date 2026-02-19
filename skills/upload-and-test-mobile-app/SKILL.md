---
name: upload-and-test-mobile-app
description: Upload and test mobile apps on TestMu AI using upload_app MCP tool. Use for uploading APK/IPA files to TestMu AI for mobile automation testing with Appium/Espresso/XCUITest.
---

# Upload and Test Mobile App

## When to Use

- Uploading a mobile app (APK or IPA) to TestMu AI for testing
- Preparing apps for automated mobile testing with Appium/Espresso/XCUITest
- Testing mobile apps on real devices via TestMu AI
- Setting up mobile app testing in CI/CD pipelines

## MCP Tools Used

- `upload_app` - Upload APK/IPA files or URL to TestMu AI for testing

## Steps

### 1. Upload Your App

Use `upload_app` to upload your mobile app to TestMu AI:

**Upload from local file path:**
```
"Upload my app from /Users/me/builds/app-debug.apk to TestMu AI"
"Upload /path/to/my-app.ipa for testing on TestMu AI"
```

**Upload from URL:**
```
"Upload app from https://example.com/builds/latest.apk to TestMu AI"
"Upload my app from this URL: https://storage.example.com/app.ipa"
```

**What the tool does:**
- Uploads APK (Android) or IPA (iOS) file to TestMu AI
- Returns an app URL (lt:// format) for use in test capabilities
- Supports custom app name and visibility settings

**Parameters:**
- `appFilePath` - Local path to APK/IPA file (use this OR appUrl)
- `appUrl` - Public URL to download the app (use this OR appFilePath)
- `name` - Custom name for the uploaded app
- `visibility` - App visibility setting

### 2. Use App URL in Tests

After upload, you'll receive an `lt://` URL. Use this in your Appium capabilities:

```json
{
  "lt:options": {
    "app": "lt://APP_URL_RETURNED"
  }
}
```

### 3. Run Tests with HyperExecute

Combine with `generateHyperExecuteYAML` for mobile test execution:

```
"Generate HyperExecute YAML for my Appium tests with app lt://APP123"
"Create HyperExecute config for Espresso tests"
```

## Common Scenarios

**Upload Android App:**
```
"Upload /builds/app-debug.apk to TestMu AI"
→ Returns: lt://APP1234567890
→ Use this URL in your Appium test capabilities
```

**Upload iOS App:**
```
"Upload /builds/MyApp.ipa to TestMu AI as 'MyApp Beta'"
→ Returns: lt://APP0987654321
→ Use this URL in your XCUITest/Appium capabilities
```

**Upload from CI/CD Artifact URL:**
```
"Upload app from https://ci.example.com/artifacts/latest.apk to TestMu AI"
```

## Example Workflow

**User**: "I want to test my Android app on TestMu AI"

**Steps**:
1. Upload: `"Upload my app from /builds/app-debug.apk to TestMu AI"`
2. Get app URL: Tool returns `lt://APP1234567890`
3. Configure tests: Use the app URL in Appium capabilities
4. Generate config: `"Generate HyperExecute YAML for my Appium tests"`
5. Run tests on HyperExecute with the uploaded app

## Quick Tips

- Supports both APK (Android) and IPA (iOS) formats
- Use `appFilePath` for local files, `appUrl` for remote URLs
- The returned `lt://` URL is used in your test framework's capabilities
- Combine with HyperExecute for parallel mobile test execution
- Set a custom `name` to easily identify app versions
