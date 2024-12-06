```mermaid
sequenceDiagram
    participant User
    participant Server

    User->>SPA: Enter new note and click Save
    Note right of SPA: JavaScript handles input locally

    SPA->>Server: POST /new_note with note data
    activate Server
    Note right of Server: Store the note and send a response
    Server-->>SPA: 201 Created (Success)
    deactivate Server

    Note right of SPA: Update the UI with the new note

    SPA->>User: Render new note dynamically on the page
