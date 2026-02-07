# Playwright CLI Setup Guide

This guide walks through installing and configuring the Playwright CLI with all necessary components.

## Prerequisites

- Node.js 14+ installed
- npm (comes with Node.js)

## Installation Steps

### 1. Install Playwright CLI Globally

Install the latest version of `@playwright/cli` globally on your system:

```bash
npm i -g @playwright/cli@latest
```

This makes the `playwright-cli` command available from anywhere in your terminal.

### 2. Install Playwright Browsers

Initialize and install Playwright browsers and dependencies:

```bash
playwright-cli install
```

This downloads the necessary browser binaries (Chromium, Firefox, WebKit) and sets up the Playwright environment.

### 3. Install Playwright CLI Skills

Install additional skills and tools for the Playwright CLI:

```bash
playwright-cli install --skills
```

This adds extended functionality and capabilities to your Playwright CLI installation.

## Verify Installation

To verify everything is installed correctly, check the Playwright CLI version:

```bash
playwright-cli --version
```

## Common Commands

### Running Tests

Run all tests in your project:
```bash
npx playwright test
```

Run a specific test file:
```bash
npx playwright test tests/todo-page.spec.ts
```

Run tests matching a title pattern:
```bash
npx playwright test -g "add a todo item"
```

Run tests with headed browsers (see the browser):
```bash
npx playwright test --headed
```

Run only failed tests from the last run:
```bash
npx playwright test --last-failed
```

Run tests for a specific browser project:
```bash
npx playwright test --project=chromium
```

Debug tests with the Playwright Inspector:
```bash
npx playwright test --debug
```

### Code Generation

Generate test code by recording your actions in the browser:
```bash
npx playwright codegen https://example.com
```

Generate code and save authentication state for reuse:
```bash
npx playwright codegen --save-storage=auth.json https://example.com
```

### Browser Management

Install specific browsers only:
```bash
npx playwright install chromium webkit
```

Install browsers with system dependencies:
```bash
npx playwright install --with-deps
```

### Reporting and Debugging

Show the HTML test report:
```bash
npx playwright show-report
```

Show a specific report directory:
```bash
npx playwright show-report playwright-report/
```

View all available commands and options:
```bash
npx playwright --help
```

## Next Steps

Once installed, you can use Playwright CLI to:
- Run automated browser tests
- Test web applications
- Perform web scraping
- Generate test code by recording interactions
- Debug web pages with the Playwright Inspector
- View detailed HTML reports

For more information, visit the [Playwright documentation](https://playwright.dev/docs/intro).

## Troubleshooting

### Command not found
If `playwright-cli` is not recognized, ensure the global npm directory is in your PATH:
```bash
npm config get prefix
```

### Browser installation issues
If browsers fail to install, try clearing the cache and reinstalling:
```bash
rm -r ~/.cache/ms-playwright
playwright-cli install
```

### Permissions error
On macOS/Linux, you may need to use `sudo` for global installation:
```bash
sudo npm i -g @playwright/cli@latest
```
