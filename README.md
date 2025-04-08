# Corny Jokes Generator

A simple web application that fetches and displays random jokes from the [JokeAPI](https://jokeapi.dev/).

## Description

This repository contains a single HTML file (`joke-generator.html`) that acts as a standalone web page. It allows users to get random jokes, optionally filtering them by category.

## Features

*   Fetches jokes from the public JokeAPI.
*   Supports various joke categories (Programming, Misc, Pun, Spooky, Christmas, Any).
*   Displays both single-part and two-part jokes (setup and delivery).
*   Simple, clean user interface.
*   Loading indicator while fetching jokes.
*   Basic error handling for API fetch failures.

## How to Use

1.  **Clone the repository (optional):**
    ```bash
    git clone https://github.com/Ashraf2706/sample-repo.git
    cd sample-repo
    ```
2.  **Open the file:**
    *   Simply download the `joke-generator.html` file directly from the repository page.
    *   Double-click the downloaded file, or open it using your web browser (e.g., navigate File > Open File...).
3.  **Get Jokes:**
    *   The page will load an initial joke automatically.
    *   Select a category from the dropdown menu if desired (default is "Any").
    *   Click the "Get New Joke" button to fetch and display a new joke.

## Technology Used

*   **HTML:** Structure of the web page.
*   **CSS:** Styling for the user interface.
*   **JavaScript (Vanilla):** Functionality for fetching jokes and updating the page.
*   **JokeAPI:** External API used as the source for jokes ([https://v2.jokeapi.dev/](https://v2.jokeapi.dev/)).

## Security Assessment (`joke-generator.html`)

A brief security assessment of the `joke-generator.html` file was conducted:

*   **API Interaction:** Communication with the JokeAPI (`https://v2.jokeapi.dev/`) uses HTTPS, ensuring encrypted data transfer. The API used is public and does not require authentication keys, minimizing risks associated with key exposure.
*   **Cross-Site Scripting (XSS):** The application uses `.textContent` to insert joke data received from the API into the HTML DOM. This method automatically escapes HTML entities, effectively preventing XSS attacks that could arise from malicious content injected into the jokes via the API.
*   **Input Handling:** User input is limited to selecting a category from a predefined dropdown list. This value is used directly in the API URL construction. While JokeAPI handles various inputs, the risk associated with this specific input method is low as the options are controlled.
*   **Error Handling:** Errors during the API fetch process are caught, and a user-friendly message is displayed without revealing potentially sensitive system or error details in the UI. Detailed errors are logged to the browser's console for debugging purposes.
*   **Dependencies:** The application uses only standard browser APIs (HTML, CSS, JS) and does not rely on external libraries, reducing the attack surface related to third-party dependency vulnerabilities.

**Conclusion:**

The `joke-generator.html` file presents a **low security risk**. It employs safe practices for handling external data (`textContent`) and communicates securely (HTTPS) with the external API. The primary dependency is on the availability and security of the public JokeAPI itself. No significant vulnerabilities were identified within the application's own code.
