# 🚀 AI-MCP Connect - MCP Server for Spotify 🎵

AI-MCP-Connect is an MCP server that connects Claude with Spotify, allowing seamless music playback and management.

## ✨ Features
- ▶️ Start, pause, and skip playback
- 🔍 Search for tracks, albums, artists, and playlists
- 📌 Get info about a track, album, artist, or playlist
- 🎶 Manage the Spotify queue

## ⚙️ Configuration

### 🔑 Getting Spotify API Keys
1. Create an account on [Spotify Developer](https://developer.spotify.com/).
2. Navigate to the [Developer Dashboard](https://developer.spotify.com/dashboard).
3. Create a new app with `redirect_uri` set to `http://localhost:8888`.
4. Set "APIs used" to "Web Playback SDK".

### Run this project locally

Clone this repo:
```bash
$ git clone https://github.com/geeta052/AI-MCP-Connect.git
```

#### Add this tool as an MCP server
📍 **Windows:** `%APPDATA%/Claude/claude_desktop_config.json`

```json
"spotify": {
    "command": "uv",
    "args": [
      "--directory",
      "/path/to/AI-MCP-Connect",
      "run",
      "spotify-mcp"
    ],
    "env": {
      "SPOTIFY_CLIENT_ID": "YOUR_CLIENT_ID",
      "SPOTIFY_CLIENT_SECRET": "YOUR_CLIENT_SECRET",
      "SPOTIFY_REDIRECT_URI": "http://localhost:8888"
    }
}
```

## Building and Publishing

### Sync dependencies
```bash
$ uv sync
```

### Build package distributions
```bash
$ uv build
```
This creates source and wheel distributions in the `dist/` directory.

### Publish to PyPI
```bash
$ uv publish
```
Set PyPI credentials via environment variables or flags:
- Token: `--token` or `UV_PUBLISH_TOKEN`
- Username/password: `--username`/`UV_PUBLISH_USERNAME` and `--password`/`UV_PUBLISH_PASSWORD`
