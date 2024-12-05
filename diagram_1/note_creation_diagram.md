sequenceDiagram
    participant User
    participant Server

    User->>Server: POST /new_note with note data
    activate Server
    Note right of Server: Store the note and send a response
    Server-->>User: 302 Redirect to /notes
    deactivate Server

    User->>Server: GET /notes
    activate Server
    Server-->>User: HTML document
    deactivate Server

    User->>Server: GET /main.css
    activate Server
    Server-->>User: CSS file
    deactivate Server

    User->>Server: GET /main.js
    activate Server
    Server-->>User: JavaScript file
    deactivate Server

    Note right of User: Executing JavaScript to fetch the notes

    User->>Server: GET /data.json
    activate Server
    Server-->>User: Updated notes JSON
    deactivate Server

    Note right of User: Rendering the updated notes list
