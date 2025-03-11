# Playwright Codegen

## Prerequisites

- Ubuntu machine
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

> **Note:** The version available from the Ubuntu repositories might be older. If you need a more recent version (Playwright requires Node.js 14 or higher), consider installing Node via [Node Version Manager (nvm)](https://github.com/nvm-sh/nvm).

Verify your installations:

```bash
node -v
npm -v
```

### Troubleshooting: Node.js Version Error

If you see an error like:

```bash
You are running Node.js 12.22.9.
Playwright requires Node.js 14 or higher. 
Please update your version of Node.js.
```

It means your current Node.js version is outdated. To update:

1. **Install nvm** (if not already installed):

   ```bash
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
   ```

   Then, close and reopen your terminal or run `source ~/.bashrc` (or `source ~/.zshrc` if using Zsh) to load nvm.

2. **Install the latest LTS version of Node.js:**

   ```bash
   nvm install --lts
   ```

3. **Verify the update:**

   ```bash
   node -v
   ```

   Ensure the version is 14 or higher.

### 2. Set Up a New Playwright Project

Create a dedicated project directory and initialize a new npm project:

```bash
mkdir playwright-demo
cd playwright-demo
npm init -y
```

### 3. Install Playwright

Before installing Playwright, if you encounter errors related to image format dependencies (such as libavif), install the required package:

```bash
sudo apt-get install libavif-dev
```

Then, install Playwright as a dependency:

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

- **Node.js Version:** Ensure your Node.js version is up-to-date. If you encounter the Node.js version error, follow the instructions above to install and use nvm.
- **libavif Dependency:** If you receive errors related to image format dependencies, install `libavif-dev` using:
  ```bash
  sudo apt-get install libavif-dev
  ```
- **Dependency Issues:** Verify that all dependencies are installed correctly by reviewing the output during installation.
- **Further Help:** Check the official Playwright documentation for additional configuration options and troubleshooting tips.
