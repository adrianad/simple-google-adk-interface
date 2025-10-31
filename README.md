# Simple Google ADK Interface

A lightweight, browser-based interface for interacting with Google's Agent Development Kit (ADK) API. This interface provides a clean chat UI to communicate with ADK agents, manage sessions, and view streaming responses.

## Features

- 🚀 Simple single-file HTML application - no build process required
- 💬 Real-time chat interface with ADK agents
- 📊 Session management (create, view, switch, delete)
- ⚡ Streaming and non-streaming response modes
- 🔧 Tool call visualization (see when agents use tools)
- 📱 Responsive design for desktop and mobile

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
   
   Open `index.html` and modify the `CONFIG` object (around line 183) with your ADK server settings:
   ```javascript
   const CONFIG = {
     serverUrl: 'http://127.0.0.1:8000',    // Your ADK server URL
     defaultAgent: 'stats',                  // Default agent name
     defaultUser: 'demo-user'                // Default user ID
   };
   ```

   Alternatively, you can reference the `.env.example` file for the expected configuration values.

3. **Start your ADK server**
   
   Make sure your ADK server is running and accessible at the configured URL.

4. **Open the interface**
   
   Simply open `index.html` in your web browser:
   ```bash
   # On macOS
   open index.html
   
   # On Linux
   xdg-open index.html
   
   # On Windows
   start index.html
   ```
   
   Or drag and drop the file into your browser window.

## Usage

### Connecting to the Server

1. Click the "Connect to Server" button in the header
2. The interface will automatically load existing sessions or create a new one

### Managing Sessions

- **View sessions**: All your sessions appear in the left sidebar
- **Create new session**: Click the "New Session" button
- **Switch sessions**: Click on any session in the sidebar
- **Delete session**: Click the 🗑️ icon next to a session

### Chatting with Agents

1. Select a session from the sidebar
2. Type your message in the input field at the bottom
3. Press Enter or click "Send"
4. View the agent's response in the chat area

### Streaming Mode

Toggle the "Streaming" checkbox in the header to switch between:
- **ON**: See responses as they're generated (recommended)
- **OFF**: Wait for complete responses before display

### Viewing Tool Calls

When agents use tools, you'll see collapsible sections showing:
- 🔧 Tool calls with arguments
- 📋 Tool responses with results

Click on any turn or tool section to expand/collapse details.

## Configuration Reference

The application uses the following configuration values:

- `ADK_SERVER_URL`: The base URL of your ADK server
- `ADK_DEFAULT_AGENT`: The default agent to use for new sessions
- `ADK_DEFAULT_USER`: The default user ID for session management

See `.env.example` for a template of these values.

## Troubleshooting

### Cannot connect to server
- Ensure your ADK server is running
- Check that the server URL in `CONFIG` matches your server's address
- Verify CORS is properly configured on your ADK server

### Sessions not loading
- Check browser console for error messages
- Verify the agent name and user ID are correct
- Ensure the ADK server has the necessary endpoints enabled

### Streaming not working
- Toggle streaming off and try non-streaming mode
- Check that your ADK server supports SSE (Server-Sent Events)
- Verify the `/run_sse` endpoint is available on your server

## Browser Compatibility

This interface works with modern browsers supporting:
- ES6+ JavaScript
- Fetch API
- Server-Sent Events (for streaming mode)

Tested on:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## License

This project is provided as-is for use with Google's Agent Development Kit.

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.
