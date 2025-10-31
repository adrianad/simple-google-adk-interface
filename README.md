# Simple Google ADK Interface

A lightweight, browser-based interface for interacting with Google's Agent Development Kit (ADK) API. This interface provides a clean chat UI to communicate with ADK agents, manage sessions, and view streaming responses.

## Features

- 🚀 Simple single-file HTML application - no build process required
- 💬 Real-time chat interface with ADK agents
- 📊 Session management (create, view, switch, delete)
- ⚡ Streaming and non-streaming response modes
- 🔧 Tool call visualization (see when agents use tools)

## Prerequisites

- A running ADK server (typically on `http://127.0.0.1:8000`)
- A modern web browser with JavaScript enabled

## Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/adrianad/simple-google-adk-interface.git
   cd simple-google-adk-interface
   ```

2. **Configure the ADK server connection**
   
   Open `index.html` and locate the `CONFIG` object near the top of the `<script>` section:
   ```javascript
   const CONFIG = {
     serverUrl: 'http://127.0.0.1:8000',    // Your ADK server URL
     defaultAgent: 'stats',                  // Default agent name
     defaultUser: 'demo-user'                // Default user ID
   };
   ```
   
   Update these values to match your ADK server settings.

3. **Start your ADK server**
   
   ```bash
   adk api_server --session_service_uri=sqlite:///./session_storage.db --host 0.0.0.0 --allow_origins="*" --port 8000
   ```

4. **Open in browser**
