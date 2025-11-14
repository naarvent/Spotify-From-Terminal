# 🎧 Spotify From Terminal — Spotify TUI (Python)

A modern **terminal interface for Spotify**, built entirely in **Python** using [Textual](https://github.com/Textualize/textual) and [Spotipy](https://github.com/plamere/spotipy).  
Inspired by [Rigellute’s spotify-tui](https://github.com/Rigellute/spotify-tui), but **expanded and reimagined** with new features, playlist tools, multi-selection, improved navigation, and more.

---

## 🚀 Overview
`spt` is a keyboard-first, compact, and fully interactive Spotify client for your terminal.

**Core goals:**
- Smooth navigation with minimal mouse use.  
- Full Spotify browsing and playback control.  
- Simple, portable configuration (no environment setup required).  
- Clean, responsive interface powered by Textual.  
- **Modern features like playlist creation, multi-add, better lyrics sync, and improved token handling.**

---

## 📸 Media


---

## ✨ Main Features

### 🔑 Authentication
- OAuth2 login via Spotipy (`SpotifyOAuth`).
- Credentials stored securely in a local JSON config or environment variables.
- Token cache stored in your Documents directory.
- **Improved token validation and refresh handling.**
- **More robust error recovery when OAuth fails.**

### 🧭 Navigation & UI
- Three-column Textual layout: Search, Library, and Playlists.
- Fully keyboard-driven with rich hotkey support.
- Responsive tables with resizable columns.
- Smooth transitions and non-blocking background updates.
- **Improved left/right focus behavior and expanded navigation logic.**

### 🔍 Search
- Global Spotify search for tracks, albums, artists, and playlists.  
- Type-prefixed searches:
  - `/TRK` (tracks)
  - `/ART` (artists)
  - `/ALB` (albums)
  - `/PLY` (playlists)
- Results are interactive and openable.

### ▶️ Playback & Queue
- Play, pause, skip, previous, seek, and volume control.
- Shuffle and repeat (off/context/track).
- Add to queue.
- Context playback for albums and playlists.
- Auto-restart if track progress > 3s on “previous.”
- **More accurate Now-Playing sync and internal timers.**

### 💿 Library & Playlists
- Access user playlists, liked songs, albums, and recently played.
- Import playlists by URL or ID (`Ctrl+T`).
- **NEW:** Create playlists directly from the TUI.
- All views update dynamically.

### ➕ NEW: Multi-Add / Multi-Review Mode
- Select multiple tracks with a new multi-add mode.
- Add all selected items to a playlist at once.
- UI indicators for selected rows.
- Toggle with `Ctrl+L`.

### 💻 Devices
- List all available Spotify Connect devices.
- Transfer playback instantly.

### ❤️ Liked Tracks
- Toggle liked/saved state (`f`).
- Efficient background syncing.
- Works across all track tables.

### 🎵 Lyrics
- Toggle lyrics (`l`).
- Fetches synced lyrics from LRCLIB.
- Fallback pseudo-sync if no timestamps.
- Optional ASCII headers via `pyfiglet`.
- **Improved timing alignment for lyrics sync.**

### ⚙️ Misc
- "Now Playing" bar with precise progress.
- Log file stored in your cache directory.
- Background-threaded Spotify API calls.
- **Improved logging and safer error handling.**

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
| Ctrl+L | **Toggle multi-add mode** |
| Ctrl+R | Refresh |
| ? | Help |

---

## 📂 Configuration & Paths

**Default locations (Windows example):**
- Token cache: `Documents/.cache_spotify_token`
- Config: `Documents/spt_config.json`
- Log: `Documents/spt_py_textual_spotify.log`

Environment variables supported:
```
SPOTIPY_CLIENT_ID
SPOTIPY_CLIENT_SECRET
SPOTIPY_REDIRECT_URI
```

Also supports custom config files created on first run.

---

## 📦 Dependencies

**Requirements:**
- Python 3.8+
- spotipy
- textual
- rich
- requests
- pyfiglet *(optional)*

Install example:
```
pip install spotipy textual rich requests pyfiglet
```

---

## ▶️ Run the App

From source:
```
python spt_tui.py
```

Windows executable:
```
./spt_tui.exe
```

First launch will prompt for Spotify OAuth credentials unless already cached.

---

## 🎤 Lyrics Mode
- Synced lyrics scroll in real time when available.
- Plain lyrics fall back to pseudo-sync.
- Disabled if `requests` is missing.
- **Improved sync timing and smoothness.**

---

## 🛠️ Troubleshooting
- **Auth issues:** Ensure redirect URI matches Spotify Developer settings.  
- **Playback fails:** Ensure a Spotify Connect device is active.  
- **Missing pyfiglet:** Lyrics still work; ASCII art won't.  
- **Huge log file:** Rotation added in v1.2 (no more infinite growth).  
- **Logs:** Check `spt_py_textual_spotify.log`.

---

## 🔒 Security Notes
- Never commit client secrets or token caches.  
- Clear local token cache if needed.

---

## 🙌 Credits
- Based on [Rigellute’s spotify-tui](https://github.com/Rigellute/spotify-tui)  
- Built with [Spotipy](https://github.com/plamere/spotipy)  
- UI powered by [Textual](https://github.com/Textualize/textual) and Rich
