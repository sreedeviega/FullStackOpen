<!--  Example 0.5 -->
<!--   the user goes to the single-page app version of the notes app at https://studies.cs.helsinki.fi/exampleapp/spa. -->

```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET /spa
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET main.css
    server-->>browser: CSS file

    browser->>server: GET spa.js
    server-->>browser: JavaScript file

    Note right of browser: JS runs and requests JSON data

    browser->>server: GET data.json
    server-->>browser: Notes in JSON format

    Note right of browser: JS renders notes on the page
