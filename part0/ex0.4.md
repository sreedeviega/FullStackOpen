<!-- Exercise 0.4: New Note Diagram -->
<!--  Mermaid diagram for depicting the situation where the user creates a new note on the page https://studies.cs.helsinki.fi/exampleapp/notes by writing something into the text field and clicking the Save button. -->

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: User types note and clicks "Save"

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: HTTP 302 Redirect to /notes
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML page with note list
    deactivate server

    browser->>server: GET main.css, main.js (again, as part of page reload)
    server-->>browser: CSS and JS files

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: JSON with notes
 