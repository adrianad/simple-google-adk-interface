# Simple Google ADK Interface
Looks a bit nicer than adk web, in case you need to show it to someone not technical.

<img width="1673" height="603" alt="image" src="https://github.com/user-attachments/assets/e7331e6c-b377-4245-915d-0ff98fce2788" />


## Features

- Simple single-file HTML
- Session management (create, view, switch, delete)
- Streaming and non-streaming response modes
- Tool call visualization (see when agents use tools)

## Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/adrianad/simple-google-adk-interface.git
   cd simple-google-adk-interface
   ```

2.**Start your ADK server**
   
   ```bash
   adk api_server --session_service_uri=sqlite:///./session_storage.db --host 0.0.0.0 --allow_origins="*" --port 8000
   ```

3. **Configure the ADK server connection**
   
   Open `index.html` and locate the `CONFIG` object near the top of the `<script>` section:
   ```javascript
   const CONFIG = {
     serverUrl: 'http://127.0.0.1:8000',    // Your ADK server URL
     defaultAgent: 'stats',                  // Default agent name
     defaultUser: 'demo-user'                // Default user ID
   };
   ```
   
   Update these values to match your ADK server settings.

4. **Open in browser**
