<!--  Exercise 0.6 -->

<!--  The user creates a new note using the single-page version of the app. -->

```mermaid

sequenceDiagram
    participant browser
    participant server

    Note right of browser: User writes note and clicks Save

    browser->>server: POST /new_note_spa with note data (JSON)
    activate server
    server-->>browser: 201 Created or success response
    deactivate server

    Note right of browser: JavaScript adds the new note to the view dynamically
