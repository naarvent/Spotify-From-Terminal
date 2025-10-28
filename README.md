# 🎧 Spotify From Terminal — Spotify TUI (Python)

A modern **terminal interface for Spotify**, built entirely in **Python** using [Textual](https://github.com/Textualize/textual) and [Spotipy](https://github.com/plamere/spotipy).  
It’s inspired by [Rigellute’s spotify-tui](https://github.com/Rigellute/spotify-tui), but reimagined in Python — combining the power of the Spotify Web API with a reactive TUI experience.

---

## 🚀 Overview

`spt` is a keyboard-first, compact, and fully interactive Spotify client for your terminal.

**Core goals:**
- Smooth navigation with minimal mouse use.  
- Full Spotify browsing and playback control.  
- Simple, portable configuration (no environment setup required).  
- Clean, responsive interface powered by Textual.

---

## 📸 Media

![Git-Terminal](https://github.com/user-attachments/assets/e6ea4d04-60c5-4b40-951b-e5620b043631)

---

## ✨ Main Features

### 🔑 Authentication
- OAuth2 login via Spotipy (`SpotifyOAuth`).
- Credentials stored securely in a local JSON config or environment variables.
- Token cache stored under your Documents directory for portability.

### 🧭 Navigation & UI
- Three-column Textual layout: Search, Library, and Playlists.
- Fully keyboard-driven with rich hotkey support.
- Responsive tables with resizable columns.
- Smooth transitions and non-blocking background updates.

### 🔍 Search
- Global Spotify search for tracks, albums, artists, and playlists.  
- Type-prefixed searches supported:
  - `/TRK` (tracks)
  - `/ART` (artists)
  - `/ALB` (albums)
  - `/PLY` (playlists)
- Results are interactive: you can drill into items and start playback directly.

### ▶️ Playback & Queue
- Play, pause, skip, previous, seek, and volume controls.
- Shuffle and repeat modes (off/context/track).
- Add to queue and control playback context (albums, playlists, etc.).
- Auto-restart if track progress > 3s on “previous” press.

### 💿 Library & Playlists
- Access user playlists, liked songs, and recently played tracks.
- View saved albums.
- Import playlists by URL or ID (`Ctrl+T`).
- All views update dynamically as your library changes.

### 💻 Devices
- List all available Spotify Connect devices.
- Transfer playback to any listed device with a single key.

### ❤️ Liked Tracks
- Toggle liked/saved state (`f`) and sync across all tables.
- Efficient background update of heart icons.

### 🎵 Lyrics
- Toggle lyrics view (`l`).
- Fetches synced lyrics from [LRCLIB](https://lrclib.net), or displays a timed pseudo-sync when not available.
- Optional ASCII-art headers rendered via `pyfiglet`.

### ⚙️ Misc
- “Now Playing” bar with progress and timing display.
- Log file stored in your cache directory.
- Threaded Spotify API calls for smooth interaction.

---

## ⌨️ Hotkeys

| Key | Action |
|-----|--------|
| Esc | Return / Clear |
| Ctrl+Q | Quit |
| ↑ / ↓ / j / k | Move between items |
| / | Focus search |
| Enter | Open / Play |
| Space | Play / Pause |
| n | Next track |
| p | Previous / Restart |
| r | Toggle repeat |
| Ctrl+S | Toggle shuffle |
| - / + | Volume down / up |
| m | Mute / Unmute |
| Ctrl+← / Ctrl+→ | Seek ±5s |
| d | Show devices |
| l | Toggle lyrics |
| c | Add to queue |
| f | Toggle favorite |
| Ctrl+T | Import playlist |
| Ctrl+R | Refresh |
| ? | Show help |

---

## 📂 Configuration & Paths

**Default locations (Windows example):**
- Token cache: `Documents/.cache_spotify_token`
- Config: `Documents/spt_config.json`
- Log: `Documents/spt_py_textual_spotify.log`

You can also use environment variables:
```
SPOTIPY_CLIENT_ID
SPOTIPY_CLIENT_SECRET
SPOTIPY_REDIRECT_URI
```

---

## 📦 Dependencies

**Runtime requirements:**
- Python 3.8+
- spotipy
- textual
- rich
- requests
- pyfiglet *(optional)*

**Install example:**
```
pip install spotipy textual rich requests pyfiglet
```

---

## ▶️ Run the App

**From source:**
```
python spt_tui.py
```

**Or from Windows executable:**
```
.\spt_tui.exe
```

On first run, you’ll be prompted for your Spotify credentials (Client ID, Secret, Redirect URI) unless already cached or set in environment variables.  
After authorization, the app stores tokens locally for quick reuse.

---

## 🎤 Lyrics Mode

- Synced lyrics (if available) scroll in time with playback.  
- Plain lyrics fall back to evenly distributed “pseudo-sync.”  
- Disabled automatically if `requests` is missing.

---

## 🛠️ Troubleshooting

- **Auth issues:** Verify your redirect URI matches in Spotify Developer settings.  
- **Playback fails:** Ensure a Spotify Connect device is active.  
- **Missing pyfiglet:** You’ll still get lyrics — just without ASCII headers.  
- **Logs:** Check `spt_py_textual_spotify.log` for details.
- **Log size file:** Be careful with the size of the log file. Right now the code has nothing to stop the log from growing, so be careful, I will implement a solution for this soon.
---

## 🔒 Security Notes

- Never commit your client secret or token files.  
- The cache stores sensitive OAuth data; delete it if needed.  

---

## 🙌 Credits

- Based on [Rigellute’s spotify-tui](https://github.com/Rigellute/spotify-tui)  
- Built with [Spotipy](https://github.com/plamere/spotipy)  
- UI powered by [Textual](https://github.com/Textualize/textual) and Rich  
