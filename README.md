# Reel — Local Movie & TV Show Library Manager

**Reel** is a cinematic desktop app for Windows that turns your local movie and TV show folders into a beautiful, browsable library. It auto-enriches metadata and posters from TMDB, detects subtitles automatically, tracks your watch progress, and plays your media in a built-in player — complete with dual-audio switching and a per-show subtitle sync nudge — or hands off to an external player like VLC.

---

## Download

Grab the latest **`Reel-win32-x64.zip`** from the [Releases](../../releases) page.

> **Keep the complete `Reel-win32-x64` folder together at all times.** `Reel.exe` depends on the `resources/` folder, `locales/` folder, and the included `.dll` runtime files sitting next to it. Moving only `Reel.exe` will break the app.

---

## Step 1 — Install

1. Right-click the downloaded ZIP → **Extract All**.
2. Move the extracted **entire `Reel-win32-x64` folder** to a permanent location before launching, for example:

   ```
   C:\Program Files\Reel\
   ```
   or
   ```
   C:\Users\<YourName>\AppData\Local\Reel\
   ```

3. Open the folder and double-click **`Reel.exe`**.

> **Windows SmartScreen warning**: Because this release is not code-signed, Windows may show a *"Windows protected your PC"* prompt. If you downloaded the ZIP from the official GitHub release page, click **More info → Run anyway**.

---

## Step 2 — Add to Start Menu / Windows Search

Do this after moving the folder to its permanent location.

**Option A — Pin to Start (easiest)**
Right-click `Reel.exe` → **Pin to Start**.

**Option B — Pin to taskbar**
Right-click `Reel.exe` → **Pin to taskbar**.

**Option C — Windows Search (recommended)**
Makes Reel appear like a normally installed app when you press **Win** and type.

1. Press **Win + R**, type `shell:programs`, press **Enter**.
2. Right-click inside the folder → **New → Shortcut**.
3. Browse to your `Reel.exe`, complete the wizard, and name it **Reel**.
4. Press **Win**, type **Reel** — it now shows up under Apps.

**Option D — Desktop shortcut**
Right-click `Reel.exe` → **Show more options** → **Send to** → **Desktop (create shortcut)**.

---

## Step 3 — Set Your Library Folders

1. Open **Settings** (gear icon, top-right).
2. Under **Library folders**, click **Choose folder** for **Movies folder** and select your local movies directory.
3. Click **Choose folder** for **Shows folder** and select your local TV shows directory.

Reel scans the folders immediately and indexes everything it finds. It never moves, copies, or uploads your files.

Use **Rescan folders** in Settings any time you add new media or change a library path.

### Recommended folder structure

For the most reliable TV show grouping, organize your files like this:

```
Movies/
  Inception (2010).mkv
  The Dark Knight (2008).mkv

Shows/
  Breaking Bad/
    Season 1/
      Breaking.Bad.S01E01.mkv
      Breaking.Bad.S01E02.mkv
  The Wire/
    Season 1/
      The.Wire.1x01.mkv
```

Episode markers like `S01E01`, `1x01`, and most common scene naming patterns are all recognized automatically.

---

## Step 4 — Get a TMDB API Key (Free)

This unlocks posters, backdrops, plot summaries, cast lists, ratings, genres, and runtime for every title in your library.

1. Create a free account at [themoviedb.org](https://www.themoviedb.org/signup).
2. Go to [themoviedb.org/settings/api](https://www.themoviedb.org/settings/api).
3. Under **API Read Access Token**, click **Create** → fill in the form (select **Personal** for type) → submit.
4. Copy the **API Read Access Token (v3 auth)** — it starts with `eyJ...`.
5. In Reel, open **Settings → TMDB metadata**.
6. Toggle **Enable TMDB** on.
7. Paste your key into the **API key (v3)** field.
8. Choose which fields to fetch (poster art, backdrop, overview, rating, genres, runtime, cast) and save.

Metadata enrichment is smart and incremental — only newly added titles fetch data. Existing metadata is left untouched unless you explicitly click **Re-fetch metadata for all titles**.

---

## Step 5 — Get an OpenSubtitles API Key (Free, Optional)

This lets you search and download subtitles from directly inside the Reel player.

1. Create a free account at [opensubtitles.com](https://www.opensubtitles.com/en/users/sign_up).
2. Go to [opensubtitles.com/consumers](https://www.opensubtitles.com/consumers).
3. Click **New Consumer** → name your app (e.g. `Reel`) → submit.
4. Copy the API key shown on the consumers page.
5. In Reel, open **Settings → OpenSubtitles**.
6. Paste your key into the **API key** field.
7. Enter your opensubtitles.com **username** and **password** — these are required to download subtitles (searching works with the key alone).

Once saved, a subtitle search button appears inside the player.

---

## Step 6 — Set Up an External Player (Optional)

To open videos in VLC, mpv, or any other native player instead of (or alongside) the built-in player:

1. **Install VLC** from [videolan.org](https://www.videolan.org/) if you haven't already.
2. In Reel, open **Settings → External player**.
3. Set **Player name** to `VLC` (or whatever you prefer).
4. Set **Executable path** to the full path of your player, for example:
   ```
   C:\Program Files\VideoLAN\VLC\vlc.exe
   ```
5. Toggle **Use external player by default** if you want every Play button to open VLC automatically.

Reel passes the matching subtitle file to the external player automatically, and syncs your watch progress back when you return to Reel.

---

## You're All Set

At this point Reel is fully configured. Here's a quick summary of what you've unlocked:

| Feature | Requires |
|---|---|
| Browse and play your local library | Library folders (Step 3) |
| Posters, backdrops, plot, cast, ratings | TMDB API key (Step 4) |
| In-player subtitle search & download | OpenSubtitles API key + login (Step 5) |
| Launch in VLC / mpv | External player path (Step 6) |

---

## Features

### Library & Metadata

- **Movies and TV shows** indexed separately with their own browse pages.
- **Smart TV series grouping** — episodes are automatically grouped by show and season regardless of naming format.
- **TMDB enrichment** — posters, backdrops, hero banners, plot summaries, cast lists, ratings, genres, and runtime, fetched on demand with a free API key.
- **Immersive background mode** — optional full-bleed wallpaper that lets a title's backdrop fill the screen behind a minimal, floating UI. Toggle it in **Settings → Appearance**.
- **Collections** — group movies into franchises and box sets (e.g. Harry Potter, Marvel, Transformers).
- **Watch stats** — hours watched, movies and episodes finished, a 7-day activity bar chart, most-watched titles, and top genres.
- **Watched badges** — optional checkmark on poster cards for titles and episodes you've finished.

### Playback

- **Built-in video player** with a cinematic, full-screen UI.
- **Resume playback** — progress is saved per title and episode so you pick up exactly where you left off.
- **Dual-audio switching** — when a file carries multiple audio streams (e.g. original + dub, or commentary), an audio-track selector appears in the player so you can switch on the fly. The track menu only shows when there's more than one track.
- **Subtitle sync nudge** — shift subtitles earlier or later in 0.5-second steps from the player when a track runs ahead or behind. The nudge is remembered **per movie, and per show + season**, so every episode in a season shares one offset while a different season or title starts fresh.
- **Episode selector panel** — browse and jump to any episode without leaving the player.
- **Picture-in-picture** support.
- **Next Episode card** — an "Up Next" overlay appears near the end of an episode so you can jump to the next one. See the note below on credits detection.

### Subtitle Support

- **Automatic local detection** — scans for subtitle files next to your video files and throughout the same directory tree. Supported formats: `.srt`, `.vtt`, `.ass`, `.ssa`, `.sub`, `.idx`, `.smi`.
- **Smart matching** — subtitles are scored by filename similarity, season/episode number, and folder proximity. The best match loads automatically.
- **Custom subtitle folder** — point Reel at a global subtitles folder in Settings and it will scan there too.
- **Manual upload** — while watching, click **Upload subtitles** (or drag-and-drop a file) to load any subtitle instantly.
- **OpenSubtitles search** — search and download from the player with a free API key and login (Step 5).
- **On-the-fly format conversion** — `.srt`, `.ass`, and `.ssa` files are automatically converted to WebVTT for seamless in-browser rendering.

### Credits Detection & Auto-Play Next Episode

Reel can detect when the credits start and surface an "Up Next" card near the end of an episode. **This detection is experimental and can misfire on some content, so auto-play is best left off.** Keep **"Automatically play the next episode when credits start"** turned off in **Settings → Playback** and the Up Next card still appears as a manual prompt — you decide when to continue rather than having the app skip automatically.

### External Player Integration

- Launch any video in VLC, mpv, or a custom player with one click.
- The matching subtitle file is passed to the external player automatically.
- **Bi-directional progress sync** — watch progress made in VLC or mpv is reflected in Reel the moment you switch back to the app.

### Media Management

- **Delete from disk** — permanently removes a video file from your library folder. A confirmation dialog always appears first.
- For TV shows, choose to delete a single episode, a whole season, or the entire show.

### Keyboard Shortcuts

| Key | Action |
|---|---|
| `Space` / `K` | Play / Pause |
| `←` / `→` | Seek ±10 seconds |
| `Shift + ←` / `Shift + →` | Seek ±30 seconds |
| `J` / `L` | Seek ±10 seconds |
| `↑` / `↓` | Volume ±5% |
| `M` | Mute / Unmute |
| `F` | Toggle fullscreen |
| `Esc` | Close the open menu / episode panel |

Arrow key seeking is clamped so it never accidentally skips to a different episode.

---

## Troubleshooting

| Problem | Fix |
|---|---|
| App won't start after moving it | You moved only `Reel.exe`. Move the **entire** `Reel-win32-x64` folder. |
| Blank window or error on launch | Re-download and extract the release — a required file may be missing or corrupted. |
| Windows SmartScreen warning | Confirm the download is from the official Releases page, then click **More info → Run anyway**. |
| Media not appearing | Check that the correct folders are set in Settings, then click **Rescan folders**. |
| No posters or metadata | Make sure TMDB is enabled and your API key is entered correctly in Settings. |
| Subtitles not loading automatically | Ensure the subtitle file is in the same folder as the video and named similarly. Or use **Upload subtitles** inside the player. |
| Subtitles run ahead or behind | Use the subtitle sync nudge in the player to shift timing; it's remembered for that movie, or for that show's season. |
| OpenSubtitles download fails | Searching needs the API key; **downloading** also needs your opensubtitles.com username and password in **Settings → OpenSubtitles**. |
| Audio-track switcher missing | The track menu only appears when the file actually has more than one audio stream. |
| External player doesn't open | Verify the executable path in Settings points to the actual `.exe` file. |
| Reel doesn't appear in Windows search | Pin it to Start again, or create a Start Menu shortcut using `shell:programs` (Option C above). |

---

## Privacy

Reel does not upload your media files. Your library index, settings, and watch progress stay on your computer. TMDB and OpenSubtitles are only contacted when you have explicitly enabled and configured those features.
