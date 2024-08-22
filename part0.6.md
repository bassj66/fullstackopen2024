 sequence Diagram
    participant user
    participant browser
    participant server


user->>browser: clic https://studies.cs.helsinki.fi/exampleapp/spa.

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.
activate server
server-->>browser: HTML document
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server
 
browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
server->>browser:[{content: "test2", date: "2024-08-21T20:12:01.178Z"}]

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/new_note_spa
server->>browser:[{message:"note created"}]
