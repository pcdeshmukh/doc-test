# doc-test

A repository dedicated to testing documentation generation and best practices for Google Apps Script projects.

## Overview

This repository serves as a sandbox for experimenting with and validating different methods of documenting Google Apps Script (GAS) code. The goal is to identify and implement efficient workflows for generating clear, maintainable, and accurate documentation directly from your Apps Script projects.

Whether you're looking to integrate with external documentation tools, leverage JSDoc within the GAS environment, or explore other documentation strategies, `doc-test` provides a practical space to test and refine your approach.

## Why this repository exists

* **Google Apps Script Specifics:** Documenting GAS projects can have unique challenges due to its browser-based IDE, specific execution environment, and deployment methods. This repo focuses on solutions that work well within these constraints.
* **Best Practices:** Explore and establish best practices for commenting, structuring code for documentation, and leveraging built-in features (like JSDoc support in the Apps Script editor).
* **Tooling Exploration:** Test the compatibility and effectiveness of various documentation tools (e.g., JSDoc parsers, static site generators) when applied to Apps Script projects.
* **Experimentation:** A safe place to try out new ideas for documentation without impacting production code.

## Getting Started

This repository primarily contains example Apps Script code and configuration files for various documentation tools. To make the most of it:

1.  **Clone this repository:**
    ```bash
    git clone [https://github.com/your-username/doc-test.git](https://github.com/your-username/doc-test.git)
    cd doc-test
    ```

2.  **Explore the examples:**
    * Navigate through the directories to see different approaches to structuring GAS projects for documentation.
    * Examine the `.gs` files for JSDoc examples and other commenting conventions.

3.  **Experiment with documentation tools:**
    * Refer to the specific subdirectories (if present) for instructions on running documentation generators against the provided code.
    * You might need to install Node.js and relevant `npm` packages for some documentation tools.

## Example Documentation Workflow (JSDoc with Apps Script)

One common approach for documenting Google Apps Script is to leverage JSDoc comments within your `.gs` files. The Apps Script editor itself provides some basic JSDoc parsing for autocomplete, but for comprehensive documentation, you'll typically extract these comments externally.

Here's a general workflow you might test:

1.  **Write JSDoc in your `.gs` files:**

    ```javascript
    /**
     * @file This file contains functions for managing Google Sheets.
     */

    /**
     * Retrieves all data from a specified sheet.
     * @param {GoogleAppsScript.Spreadsheet.Sheet} sheet The sheet to read data from.
     * @returns {Array<Array<any>>} A 2D array containing all sheet data.
     */
    function getAllSheetData(sheet) {
      if (!sheet) {
        throw new Error("Sheet cannot be null.");
      }
      return sheet.getDataRange().getValues();
    }

    /**
     * Logs a message to the Google Apps Script execution log.
     * @param {string} message The message to log.
     * @param {number} [level=1] The log level (optional, default is 1).
     */
    function logMessage(message, level) {
      level = level || 1;
      console.log(`[Level ${level}] ${message}`);
    }
    ```

2.  **Extract `.gs` files:** If you're using `clasp` or another tool to manage your Apps Script project locally, you can easily access these files. If working directly in the Apps Script editor, you'd typically copy them out.

3.  **Run a JSDoc generator:** Use a tool like JSDoc (the Node.js package) to parse your `.gs` files and generate HTML documentation.

    ```bash
    npm install -g jsdoc
    jsdoc -c jsdoc.json your-apps-script-project-folder/*.gs
    ```
    (You'd configure `jsdoc.json` to suit your needs.)

4.  **Review generated documentation:** Open the generated HTML files in your browser.

## Contributing

Feel free to contribute to this `doc-test` repository by:

* Adding new examples of Apps Script code with different documentation styles.
* Proposing new documentation tools or workflows.
* Improving existing documentation or examples.
* Reporting issues or suggesting enhancements.

Please ensure any contributions align with the goal of testing and refining documentation strategies for Google Apps Script.

## License

This project is licensed under the Apache License, Version 2.0 - see the [LICENSE](LICENSE) file for details.