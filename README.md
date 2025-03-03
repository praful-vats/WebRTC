# WebRTC Direct Connection

A browser-based peer-to-peer connection system using WebRTC with manual SDP exchange. This application enables direct browser-to-browser communication without requiring a signaling server.


## Features

- **Direct WebRTC connections** without a signaling server
- **Manual SDP exchange** between peers
- **Text messaging** with message history
- **Real-time collaborative text editor** with character-by-character synchronization
- **Operational transformation** for consistent editing experience
- **Cursor position preservation** during collaborative editing
- **Automatic sync recovery** for handling connection issues

## How It Works

This application demonstrates WebRTC's peer connection capabilities by manually exchanging Session Description Protocol (SDP) data between browsers:

1. One user (User 1) creates an offer
2. The offer is manually copied and pasted to the second user (User 2)
3. User 2 creates an answer based on the offer
4. The answer is manually copied and pasted back to User 1
5. A direct peer-to-peer connection is established
6. Users can now exchange messages and collaborate in real-time

## Setup Instructions

### Option 1: Run locally (simplest)

1. Download the HTML file to your computer
2. Open the file in a browser (Chrome or Firefox recommended)
3. Open a second tab or window with the same file

### Option 2: Host on a web server

1. Upload the HTML file to any web server
2. Access the page from two different browsers or devices

## Usage Guide

### Establishing Connection

1. **User 1**:
   - Click "Create Offer"
   - Copy the generated SDP offer text

2. **User 2**:
   - Paste the SDP offer into the "Paste SDP offer here" box
   - Click "Create Answer"
   - Copy the generated SDP answer

3. **User 1**:
   - Paste the SDP answer into the "Paste SDP answer here" box
   - Click "Add Answer"

4. **Connection Status**:
   - When successfully connected, status indicators will turn pink
   - Connection status will update to "Connection: connected"

### Sending Messages

1. Type a message in the "Type your message here..." box
2. Click "TRANSMIT" to send
3. Messages appear in the "Incoming Transmissions" section

### Real-time Collaborative Editing

1. Type in the collaborative editor box
2. Changes are automatically synchronized between peers
3. Cursor positions are preserved during editing
4. Sync status is displayed in the top-right of the editor panel
5. Click "Force Sync" if synchronization issues occur

## Technical Details

- **WebRTC API**: Used for peer-to-peer communication
- **DataChannel**: Two channels established:
  - `messageChannel`: For discrete message exchange
  - `realtimeChannel`: For collaborative editing
- **Operational Transformation**: Simplified implementation for handling concurrent edits
- **Debouncing**: Prevents overwhelming the connection with rapid changes
- **Periodic Sync**: Ensures document consistency over time
- **Error Recovery**: Automatic and manual sync mechanisms

## Limitations

- Requires manual exchange of SDP information (no signaling server)
- Intended for educational purposes to demonstrate WebRTC concepts
- Limited to text-based communication (no audio/video)
- Best suited for two-party connections
- May require HTTPS when hosted on a server (WebRTC security requirement)

## Troubleshooting

- **Connection Fails**: Ensure you've copied the complete SDP information
- **Text Out of Sync**: Click the "Force Sync" button
- **Disconnection**: Refresh both tabs and restart the connection process
- **Browser Compatibility**: Use recent versions of Chrome or Firefox
- **Network Issues**: Ensure both peers can establish UDP connections (may not work through some firewalls)

## Browser Support

Tested and working on:
- Google Chrome (v85+)
- Mozilla Firefox (v80+)
- Microsoft Edge (Chromium-based, v85+)

---

Created as a demonstration of WebRTC's peer-to-peer capabilities without relying on a signaling server.