# Vapi-Live-Call-Control

This Node.js project allows you to initiate calls through a voice assistant API, capture audio from live calls via WebSocket, save the audio as a WAV file, and inject custom messages into the ongoing call. This project is ideal for applications like call monitoring or voice assistants that handle customer support.

## Features

- **Initiate a Call**: Start a call using an assistant and retrieve a listen URL and control URL.
- **Capture Audio**: Stream audio in real-time and save it as a WAV file.
- **Inject Custom Messages**: Dynamically inject a custom message during a live call.

## Setup

### Prerequisites

- [Node.js](https://nodejs.org/) installed on your machine.
- A valid API key from the voice assistant service (VAPI).
- An Assistant ID, Phone Number ID, and Customer Phone Number from the API.

### Installation

1. Clone the repository or download the project files.
   ```bash
   git clone https://github.com/HamChowderr/Vapi-Live-Call-Control
   cd vapi-live-call-control
   ```

2. Install the required Node.js packages:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root of the project and add your API key:
   ```env
   VAPI_API_KEY=your_api_key_here
   ```

### Configuration

Replace the following values in the `index.js` file:

- **Assistant ID**: `'AssistantUUID'`
- **Customer Phone Number**: `'+13231234567'`
- **Phone Number ID**: `'PhoneUUID'`

These values represent your unique API identifiers and customer phone number. Be sure to replace them with your actual values if you are running this in your own environment.

### Usage

1. **Initiate the Call**:
   Run the script:
   ```bash
   node index.js
   ```

2. **Answer the Call**:
   After initiating the call, you will be prompted to press ENTER once the call is answered to start capturing the audio.

3. **Inject a Custom Message**:
   After answering the call, you can enter a custom message for the assistant to say during the call.

4. **Capture and Save Audio**:
   The audio stream will be saved as a WAV file in the root directory with a unique timestamp-based filename.

### Project Structure

```
voice-assistant-call-listener/
│
├── index.js       # Main application logic
├── .env           # Environment file with the API key (not included in the repository)
├── package.json   # Node.js dependencies and scripts
└── README.md      # Project documentation (this file)
```

### Dependencies

- [ws](https://www.npmjs.com/package/ws) - WebSocket library for handling the audio stream.
- [axios](https://www.npmjs.com/package/axios) - HTTP client for making API requests.
- [dotenv](https://www.npmjs.com/package/dotenv) - Loads environment variables from a `.env` file.
- [readline](https://nodejs.org/api/readline.html) - Interface for reading user input.

### Troubleshooting

- **WebSocket Connection Errors**: Ensure that the assistant is correctly initiated and the phone call is active before starting the WebSocket connection.
- **API Key Issues**: Make sure your `.env` file is correctly configured and your `VAPI_API_KEY` is valid.
