```mermaid
sequenceDiagram
    participant User
    participant Server

    User->>Server: GET /spa
    activate Server
    Server-->>User: HTML document for SPA
    deactivate Server

    User->>Server: GET /main.css
    activate Server
    Server-->>User: CSS file
    deactivate Server

    User->>Server: GET /spa.js
    activate Server
    Server-->>User: JavaScript file
    deactivate Server

    Note right of User: Executing JavaScript to render the SPA

    User->>Server: GET /data.json
    activate Server
    Server-->>User: JSON data [{ "content": "Note 1", "date": "2023-1-1" }, ...]
    deactivate Server

    Note right of User: Rendering the notes dynamically using JavaScript
