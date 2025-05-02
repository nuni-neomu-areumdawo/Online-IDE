## Web-Based Integrated Development Environment

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

A web-based Integrated Development Environment built with HTML, CSS, and JavaScript that allows you to write and execute code directly in your browser.

<img width="1278" alt="image" src="https://github.com/user-attachments/assets/782c8799-b300-46ec-9a42-832a6f6df35a" />

*Example execution with simple program.*

https://nuni-neomu-areumdawo.github.io/Online-IDE/ - **You can run it locally too!!**

## Features
*   **Multi-Language Support:**
    *   Syntax highlighting for Python, Java, C, and C++.
    *   Client-side execution for **Python** using Pyodide.
    *   (Working on execution logic for Java, C, C++).
*   **Code Analysis (Python):**
    *   Real-time hints and warnings for potential issues (e.g., division by zero, unused imports, potential typos).
    *   Issues are underlined directly in the editor.
    *   Dedicated panel listing all detected issues.
    *   Clicking an issue in the panel highlights the corresponding line.
    *   Toggle visibility for hints and warnings separately or together.
    *   Navigate through issues using the "Next Issue" button.
*   **Code Management (LocalStorage):**
    *   Save snapshots of your code.
    *   View, load, rename, and delete saved code versions.
    *   Automatic saving of the 'Latest' version.
    *   Collapsible "Code History" panel.
*   **User Experience:**
    *   Smooth language switching with animations.
    *   Dynamic bokeh background effect that changes with the selected language.
    *   Visual feedback animation when running code.
    *   Toast notifications for actions like saving, loading, or errors.

## Getting Started

Since this is a **purely client-side application contained within a single HTML file**, running it is simple:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/nuni-neomu-areumdawo/Online-IDE.git
    ```

2.  **Navigate to the directory:**
    ```bash
    cd Online-IDE
    ```

3.  **Open the HTML file:**
    Simply open the `index.html` (or the main HTML file's name) in your preferred web browser (e.g., Chrome, Firefox, Edge).

**Note:** The first time you run Python code, Pyodide needs to be downloaded and initialized, which might take a few moments depending on your internet connection. Subsequent runs will be faster.

## How It Works

*   **Editor:** The [CodeMirror](https://codemirror.net/) library provides the text editor component, handling syntax highlighting, line numbers, and other editor features based on the selected language mode.
*   **Python Execution:** [Pyodide](https://pyodide.org/) loads the CPython interpreter compiled to WebAssembly into the browser. When you click "Run Code" for Python, the script from the editor is passed to Pyodide for execution directly in the browser, capturing `stdout` and `stderr` for display.
*   **Other Languages:** For Java, C, and C++, the IDE currently provides syntax highlighting via CodeMirror modes. The execution logic is a placeholder and does not compile or run code for these languages.
*   **Code Analysis:** Custom JavaScript functions parse the Python code in the editor, looking for specific patterns (e.g., regex checks, simple AST-like checks) to identify potential hints or warnings. These are then displayed in the side panel and used to mark the code in the editor./
*   **Persistence:** Code snippets and their metadata (timestamp, language, name) are saved and retrieved using the browser's `localStorage` API.
*   **Visuals:** The background bokeh effect and various animations are achieved using CSS (including `@keyframes` rules) and JavaScript to manipulate element styles and classes dynamically.

## Contributing

Contributions are welcome! If you have suggestions for improvements or find bugs, please feel free to:

1.  Open an issue to discuss the change or report the bug.
2.  Fork the repository, make your changes, and submit a pull request.

## 📄 License

This project is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details.

---
