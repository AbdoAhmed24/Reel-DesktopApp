# 🎬 Reel — Local Movie & TV Show Library Manager

**Reel** is a modern, cinematic local media player and library manager for Windows. It indexes your local movie and TV show folders, auto-enriches metadata from TMDB, auto-detects subtitles, and streams your media smoothly via built-in player or external players like VLC.

---

## 📌 Quick Setup Guide (Local App)

### 1. Keep this folder together
Do **not** move `Reel.exe` out of this folder by itself. It requires the accompanying files (`resources/`, `locales/`, `.dll` files) in this directory to run properly.

### 2. Move to a permanent location (Recommended)
Before pinning or launching, move this entire `Reel-win32-x64` folder to a permanent location, such as:
- `C:\Program Files\Reel\`  or  
- `C:\Users\<YourUsername>\AppData\Local\Reel\`

### 3. Launch Reel
Double-click **`Reel.exe`**.

> 💡 **Windows SmartScreen Note**: On first launch, Windows may show a *"Windows protected your PC"* message for unsigned local apps. Click **More info** → **Run anyway**.

---

## 🔍 Add Reel to Windows Search & Start Menu

To open Reel instantly like a native Windows application:

### Option A — Pin to Start or Taskbar (Easiest)
1. Right-click **`Reel.exe`**.
2. Select **Pin to Start** or **Pin to Taskbar**.

### Option B — Windows Search Integration
1. Press `Win + R`, type `shell:programs`, and press **Enter**.
2. Right-click inside the folder → **New** → **Shortcut**.
3. Browse to `Reel.exe` in your permanent folder and click **Finish**.
4. Name the shortcut **Reel**.
5. You can now press `Win` key, type **Reel**, and press **Enter** to open the app anytime!

---

## ⚙️ Initial Setup Checklist

When you launch Reel for the first time:

1. **Set Library Folders**:
   - Open **Settings** (gear icon in top-right).
   - Click **Choose folder** for **Movies** and select your local movies folder.
   - Click **Choose folder** for **TV Shows** and select your local TV shows folder.
2. **TMDB Metadata & Posters (Optional)**:
   - Enable TMDB metadata in Settings.
   - Enter a free API key from [themoviedb.org](https://www.themoviedb.org/settings/api).
   - *Note: TMDB enrichment is smart & incremental — adding a new episode or movie only fetches metadata for that new item, leaving existing metadata untouched.*
3. **External Player Integration (Optional)**:
   - To launch videos in external players like VLC or mpv, enter your player executable path (e.g. `C:\Program Files\VideoLAN\VLC\vlc.exe`).
   - Enable *Use external player by default* if desired.

---

## 💬 Subtitle Detection & Management

Reel includes powerful automatic and manual subtitle detection capabilities:

### 1. Automatic Local Subtitle Detection
- Reel automatically scans for subtitle files sitting next to your video files or in the same directory.
- **Supported extensions**: `.srt`, `.vtt`, `.ass`, `.ssa`, `.sub`, `.idx`, `.smi`.
- Matching subtitles are automatically detected, parsed, and made available in the player subtitle menu.

### 2. Custom Subtitle Search Folder
- You can set a global **Subtitle search folder** in **Settings**.
- Reel will scan this folder to auto-match external subtitle files to your videos.

### 3. Automatic Subtitle Format Conversion
- Non-standard subtitle formats (like `.srt` and `.ass`/`.ssa`) are automatically converted on-the-fly to WebVTT (`.vtt`) for seamless HTML5 video rendering with formatting tags cleaned.

### 4. Manual In-Player Subtitle Upload
- While watching any video, click the **Upload subtitles** button at the top right of the player (or drag-and-drop a file).
- Select any `.srt`, `.vtt`, `.ass`, or `.ssa` file to load it instantly.

### 5. External Player Subtitle Support
- When opening a video in an external player like VLC, mpv, or IINA, Reel automatically passes the matching subtitle file to the external player.

---

## 🔥 Key Features

- **Cinematic UI**: Vibrant dark design, backdrop art, hero banners, and smooth animations.
- **Smart TV Series Grouping**: Automatically groups episodes into series and seasons regardless of naming format.
- **On-the-Fly Transcoding**: Uses bundled `ffmpeg` to transparently remux/transcode unsupported containers or codecs (MKV, HEVC/H.265, AC3, DTS, etc.) into web-compatible H.264/AAC.
- **Bi-Directional External Player Sync**: Synchronizes watch progress automatically between Reel and VLC/mpv. If you watch half an episode in VLC, Reel updates your progress bar and resume point on window focus.
- **Next Episode & Credits Detection**: Auto-detects ending credits with a Netflix-style "Up Next" card for smooth binge-watching.
- **Keyboard Shortcuts**:
  - `Space` / `K`: Play / Pause
  - `Left Arrow` / `Right Arrow`: Seek ±10 seconds (Clamped safely so arrow seeking never forces accidental episode skips)
  - `Shift + Left/Right Arrow`: Seek ±30 seconds
  - `J` / `L`: Seek ±10 seconds
  - `M`: Mute / Unmute
  - `F`: Toggle Fullscreen
  - `Up Arrow` / `Down Arrow`: Volume control ±5%

---

## ❓ Troubleshooting

| Issue | Solution |
|-------|----------|
| **App won't start after moving `Reel.exe`** | You moved `Reel.exe` alone. Move the **entire** `Reel-win32-x64` folder. |
| **SmartScreen warning on Windows** | Click **More info → Run anyway**. |
| **Subtitles not showing up** | Ensure subtitle file matches video name or directory, or click **Upload subtitles** inside the player. |
| **Video doesn't play natively in browser** | Ensure Electron packaged app is running — bundled `ffmpeg` will automatically transcode MKV/HEVC/AC3 files. |

---

*Enjoy your local cinema with Reel!*
