# Rocketseed UI Automation Assessment

## Candidate

Giovanni Nagfaal

## Framework & Tools Used

* Playwright
* TypeScript
* Node.js
* Visual Studio Code

## Project Structure

```text
RocketseedPlaywright/
│
├── tests/
│   ├── Giovanni_Nagfaal_Rocketseed_UI_Assessment.spec.ts
│   └── example.spec.ts
│
├── playwright.config.ts
├── package.json
├── package-lock.json
└── README.md
```

## Prerequisites

Please ensure the following software is installed:

* Node.js (v18 or later recommended)
* npm (included with Node.js)

## Installation

Clone the repository:

```bash
git clone <repository-url>
cd RocketseedPlaywright
```

Install project dependencies:

```bash
npm install
```

Install Playwright browsers:

```bash
npx playwright install
```

## Execute the Test Suite

Run all tests:

```bash
npx playwright test
```

Run tests in headed mode:

```bash
npx playwright test --headed
```

Run the Rocketseed assessment test only:

```bash
npx playwright test tests/Giovanni_Nagfaal_Rocketseed_UI_Assessment.spec.ts --headed
```

## Test Report

After execution, view the Playwright HTML report:

```bash
npx playwright show-report
```

## Features Covered

1. Navigate to https://www.rocketseed.com
2. Validate successful website access
3. Interact with the Contact Us form
4. Populate:

   * Name
   * Email
   * Message
5. Capture screenshots during execution
6. Navigate through Features menu items
7. Validate page navigation and content visibility

## Screenshots

Screenshots are automatically generated during execution and stored in the screenshots folder.

## Notes

This solution was developed using Playwright with TypeScript and follows a maintainable automated testing approach with assertions, screenshots, and reporting support.
