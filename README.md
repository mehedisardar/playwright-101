# Playwright Codegen

## Prerequisites

- I'm using a ubuntu machine
- [Node.js and npm](https://nodejs.org/) (if not installed, see steps below)

## Step-by-Step Guide

### 1. Update Your System & Install Node.js

First, update your package lists:

```bash
sudo apt update
```

Install Node.js and npm:

```bash
sudo apt install nodejs npm
```

> **Note:** The version available from Ubuntu repositories might be older. If you need a more recent version, consider installing Node via [Node Version Manager (nvm)](https://github.com/nvm-sh/nvm).

Verify your installations:

```bash
node -v
npm -v
```

### 2. Set Up a New Playwright Project

Create a dedicated project directory and initialize a new npm project:

```bash
mkdir playwright-demo
cd playwright-demo
npm init -y
```

### 3. Install Playwright

Install Playwright as a dependency:

```bash
npm install playwright
```

Install the necessary browsers (Chromium, Firefox, and WebKit):

```bash
npx playwright install
```

### 4. Run Playwright Codegen

Generate test code by running the codegen tool with a target URL:

```bash
npx playwright codegen https://example.com
```

This command will:
- Launch a browser window with a side panel for code generation.
- Record your interactions (clicks, typing, etc.) on the webpage.
- Automatically generate test code based on your actions.

#### Optional: Specify a Target Language

If you prefer to generate code in another language (e.g., Python), run:

```bash
npx playwright codegen --target=python https://example.com
```

### 5. Interact with the Codegen Interface

- Use the launched browser to perform actions on the webpage.
- Watch as Playwright dynamically records your actions in the code generation panel.
- Once done, copy the generated code into a file or integrate it into your test suite.

## Additional Resources

- [Official Playwright Codegen Documentation](https://playwright.dev/docs/codegen)
- [Node Version Manager (nvm) on GitHub](https://github.com/nvm-sh/nvm)

## Troubleshooting

- **Node.js Version:** Ensure your Node.js version is up-to-date. Consider using nvm for managing Node versions.
- **Dependency Issues:** Verify that all dependencies are installed correctly by reviewing the output during installation.
- **Further Help:** Check the official Playwright documentation for additional configuration options and troubleshooting tips.

